# LsapCrGenerateHMACWithSHA512

- ea: `0x180142a48`
- end: `0x180142c73`
- name: `LsapCrGenerateHMACWithSHA512`
- size: `555`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180142d48`
- `0x180143158`

## callees

- `0x180142a48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142c21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142c21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142c4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142ae7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142b4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142ae7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142b4e`
- `bcrypt!BCryptHashData` at `0x180142ba7`
- `bcrypt!BCryptHashData` at `0x180142ba7`
- `bcrypt!BCryptDestroyHash` at `0x180142bf6`
- `bcrypt!BCryptDestroyHash` at `0x180142bf6`
- `bcrypt!BCryptFinishHash` at `0x180142bc7`
- `bcrypt!BCryptFinishHash` at `0x180142bc7`
- `bcrypt!BCryptCreateHash` at `0x180142b86`
- `bcrypt!BCryptCreateHash` at `0x180142b86`
- `bcrypt!BCryptGetProperty` at `0x180142ac1`
- `bcrypt!BCryptGetProperty` at `0x180142b26`
- `bcrypt!BCryptGetProperty` at `0x180142ac1`
- `bcrypt!BCryptGetProperty` at `0x180142b26`

## pseudocode

```c

```
