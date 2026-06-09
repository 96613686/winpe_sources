# LsapCrEncryptDataWithAES

- ea: `0x1801427c4`
- end: `0x180142a42`
- name: `LsapCrEncryptDataWithAES`
- size: `638`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180143158`

## callees

- `0x1800b86d0`
- `0x1800b92d4`
- `0x1801427c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014295d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014295d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142a0c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142a0c`
- `bcrypt!BCryptDestroyKey` at `0x1801429f5`
- `bcrypt!BCryptDestroyKey` at `0x1801429f5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014284f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014284f`
- `bcrypt!BCryptSetProperty` at `0x1801428bf`
- `bcrypt!BCryptSetProperty` at `0x1801428bf`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1801428f7`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1801428f7`
- `bcrypt!BCryptGetProperty` at `0x180142885`
- `bcrypt!BCryptGetProperty` at `0x180142885`
- `bcrypt!BCryptEncrypt` at `0x180142941`
- `bcrypt!BCryptEncrypt` at `0x1801429b3`
- `bcrypt!BCryptEncrypt` at `0x180142941`
- `bcrypt!BCryptEncrypt` at `0x1801429b3`

## pseudocode

```c

```
