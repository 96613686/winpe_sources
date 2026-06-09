# CngRsa32Compat_rc4_key

- ea: `0x180003570`
- end: `0x1800035dd`
- name: `CngRsa32Compat_rc4_key`
- size: `109`
- prototype: `NTSTATUS __fastcall(BCRYPT_KEY_HANDLE *phKey, __int64, UCHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003cb8`
- `0x180003d84`

## callees

- `0x180003570`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800035c1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800035c1`
- `bcrypt!BCryptDestroyKey` at `0x180003592`
- `bcrypt!BCryptDestroyKey` at `0x180003592`

## pseudocode

```c

```
