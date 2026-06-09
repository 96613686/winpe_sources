# LsapCrDecryptDataWithAES

- ea: `0x180142514`
- end: `0x1801427be`
- name: `LsapCrDecryptDataWithAES`
- size: `682`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180142d48`

## callees

- `0x1800b86d0`
- `0x1800b92d4`
- `0x180142514`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801426bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801426bd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014277f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014277f`
- `bcrypt!BCryptDecrypt` at `0x18014269f`
- `bcrypt!BCryptDecrypt` at `0x180142716`
- `bcrypt!BCryptDecrypt` at `0x18014269f`
- `bcrypt!BCryptDecrypt` at `0x180142716`
- `bcrypt!BCryptDestroyKey` at `0x180142768`
- `bcrypt!BCryptDestroyKey` at `0x180142768`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180142599`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180142599`
- `bcrypt!BCryptSetProperty` at `0x180142615`
- `bcrypt!BCryptSetProperty` at `0x180142615`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18014264d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18014264d`
- `bcrypt!BCryptGetProperty` at `0x1801425d5`
- `bcrypt!BCryptGetProperty` at `0x1801425d5`

## pseudocode

```c

```
