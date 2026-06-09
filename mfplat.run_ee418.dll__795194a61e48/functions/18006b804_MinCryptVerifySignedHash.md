# MinCryptVerifySignedHash

- ea: `0x18006b804`
- end: `0x18006ba47`
- name: `MinCryptVerifySignedHash`
- size: `579`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, PUCHAR pbHash@<rdx>, ULONG cbHash@<r8d>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006af48`
- `0x18006cbe8`

## callees

- `0x18006b804`
- `0x18006bc0c`
- `0x18006c054`
- `0x18006c7bc`
- `0x1801200d0`
- `0x180120ecc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006ba27`
- `ntdll!RtlNtStatusToDosError` at `0x18006ba27`
- `bcrypt!BCryptVerifySignature` at `0x18006b9de`
- `bcrypt!BCryptVerifySignature` at `0x18006b9de`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b954`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b954`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006b9fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006b9fe`
- `bcrypt!BCryptDestroyKey` at `0x18006ba38`
- `bcrypt!BCryptDestroyKey` at `0x18006ba38`
- `bcrypt!BCryptImportKeyPair` at `0x18006b994`
- `bcrypt!BCryptImportKeyPair` at `0x18006b994`

## pseudocode

```c

```
