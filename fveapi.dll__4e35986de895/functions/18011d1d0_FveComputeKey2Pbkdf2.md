# FveComputeKey2Pbkdf2

- ea: `0x18011d1d0`
- end: `0x18011d37f`
- name: `FveComputeKey2Pbkdf2`
- size: `431`
- prototype: `__int64 __fastcall(char, PUCHAR pbPassword, ULONG cbPassword, PUCHAR pbSalt, ULONG, BCRYPT_ALG_HANDLE hAlgorithm, int, ULONGLONG)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18010bf0c`
- `0x18011d550`

## callees

- `0x18001ea4c`
- `0x180118df8`
- `0x18011d1d0`
- `0x18011d418`

## import_xrefs

- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x18011d369`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x18011d369`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18011d2b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18011d320`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18011d2b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18011d320`

## string_xrefs

- `0x18011d226`: `FveComputeKey2Pbkdf2`

## pseudocode

```c

```
