# MinCryptVerifySignedHash

- ea: `0x18013c460`
- end: `0x18013c663`
- name: `MinCryptVerifySignedHash`
- size: `515`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, PUCHAR pbHash@<rdx>, ULONG cbHash@<r8d>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18013c740`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x18013c09c`
- `0x18013c460`
- `0x18013d688`
- `0x18013d6d0`
- `0x18013d87c`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18013c61d`
- `bcrypt!BCryptDestroyKey` at `0x18013c61d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18013c54f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18013c54f`
- `bcrypt!BCryptImportKeyPair` at `0x18013c5aa`
- `bcrypt!BCryptImportKeyPair` at `0x18013c5aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18013c635`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18013c635`
- `bcrypt!BCryptVerifySignature` at `0x18013c5f9`
- `bcrypt!BCryptVerifySignature` at `0x18013c5f9`
- `ntdll!RtlNtStatusToDosError` at `0x18013c561`
- `ntdll!RtlNtStatusToDosError` at `0x18013c561`

## pseudocode

```c

```
