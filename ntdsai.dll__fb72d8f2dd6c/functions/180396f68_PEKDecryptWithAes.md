# PEKDecryptWithAes

- ea: `0x180396f68`
- end: `0x1803975a4`
- name: `PEKDecryptWithAes`
- size: `1596`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, void *Src, ULONG cbIV, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG, ULONG *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180396770`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180021aa3`
- `0x180030af8`
- `0x180396f68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803970b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180397578`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180475ba1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803970b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180397578`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180475ba1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180397115`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180397115`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180397567`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180475b8b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180397567`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180475b8b`
- `bcrypt!BCryptDestroyKey` at `0x180397555`
- `bcrypt!BCryptDestroyKey` at `0x180475b79`
- `bcrypt!BCryptDestroyKey` at `0x180397555`
- `bcrypt!BCryptDestroyKey` at `0x180475b79`
- `bcrypt!BCryptDecrypt` at `0x18039743c`
- `bcrypt!BCryptDecrypt` at `0x18039743c`
- `bcrypt!BCryptSetProperty` at `0x180397214`
- `bcrypt!BCryptSetProperty` at `0x180397214`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180397314`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180397314`

## pseudocode

```c

```
