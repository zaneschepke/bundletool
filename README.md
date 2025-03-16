# Bundletool Build APKs Action

This action downloads `bundletool` and builds a .apks file from an Android App Bundle (AAB).

## Inputs
- `bundletool-version`: Version of bundletool to download (default: `1.18.1`).
- `java-version`: Version of Java to set up (11, 17) (default: `17`).
- `bundle-file`: Path to the AAB file (required).
- `output-file`: Path to the output .apks file (default: `app-release.apks`).
- `keystore-file`: Path to the keystore .jks file (required).
- `keystore-password`: Keystore password (required).
- `key-alias`: Keystore key alias (required).
- `key-password`: Key password (required).

## Outputs
- `apks-path`: Path to the generated .apks file.

## Example
```yaml
- name: Build APKs with Bundletool
  uses: your-username/bundletool-action@v1.0.0
  with:
    bundletool-version: '1.18.1'
    java-version: '17'
    bundle-file: 'app/build/outputs/bundle/release/app-release.aab'
    output-file: 'app-release.apks'
    keystore-file: 'keystore.jks'
    keystore-password: ${{ secrets.KEYSTORE_PASSWORD }}
    key-alias: ${{ secrets.KEY_ALIAS }}
    key-password: ${{ secrets.KEY_PASSWORD }}