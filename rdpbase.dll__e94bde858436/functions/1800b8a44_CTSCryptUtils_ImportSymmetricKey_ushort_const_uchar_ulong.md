# CTSCryptUtils::ImportSymmetricKey(ushort const *,uchar *,ulong)

- ea: `0x1800b8a44`
- end: `0x1800b8c8a`
- name: `?ImportSymmetricKey@CTSCryptUtils@@QEAAJPEBGPEAEK@Z`
- size: `582`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ecc38`

## callees

- `0x180071a60`
- `0x1800721d4`
- `0x1800787d4`
- `0x1800923f8`
- `0x1800b8504`
- `0x1800b8a44`

## import_xrefs

- `bcrypt!BCryptImportKey` at `0x1800b8c16`
- `bcrypt!BCryptImportKey` at `0x1800b8c16`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b8c6d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b8c6d`
- `bcrypt!BCryptGetProperty` at `0x1800b8b80`
- `bcrypt!BCryptGetProperty` at `0x1800b8b80`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b8ae6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b8ae6`

## pseudocode

```c

```
