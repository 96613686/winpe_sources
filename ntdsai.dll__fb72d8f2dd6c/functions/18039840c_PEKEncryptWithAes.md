# PEKEncryptWithAes

- ea: `0x18039840c`
- end: `0x180398a48`
- name: `PEKEncryptWithAes`
- size: `1596`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, void *Src, ULONG cbIV, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG, ULONG *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180397cc4`

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
- `0x18039840c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180398556`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180398a1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180475c46`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180398556`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180398a1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180475c46`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1803985b9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1803985b9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180398a0b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180475c30`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180398a0b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180475c30`
- `bcrypt!BCryptEncrypt` at `0x1803988e0`
- `bcrypt!BCryptEncrypt` at `0x1803988e0`
- `bcrypt!BCryptDestroyKey` at `0x1803989f9`
- `bcrypt!BCryptDestroyKey` at `0x180475c1e`
- `bcrypt!BCryptDestroyKey` at `0x1803989f9`
- `bcrypt!BCryptDestroyKey` at `0x180475c1e`
- `bcrypt!BCryptSetProperty` at `0x1803986b8`
- `bcrypt!BCryptSetProperty` at `0x1803986b8`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1803987b8`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1803987b8`

## pseudocode

```c

```
