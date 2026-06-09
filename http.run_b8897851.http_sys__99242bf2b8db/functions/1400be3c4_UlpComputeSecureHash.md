# UlpComputeSecureHash

- ea: `0x1400be3c4`
- end: `0x1400be577`
- name: `UlpComputeSecureHash`
- size: `435`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400be2b8`

## callees

- `0x1400be3c4`
- `0x140167700`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400be472`
- `ntoskrnl!ExAllocatePool3` at `0x1400be472`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be54a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be54a`
- `ksecdd!BCryptCreateHash` at `0x1400be4b6`
- `ksecdd!BCryptCreateHash` at `0x1400be4b6`
- `ksecdd!BCryptHashData` at `0x1400be4d6`
- `ksecdd!BCryptHashData` at `0x1400be4d6`
- `ksecdd!BCryptDestroyHash` at `0x1400be512`
- `ksecdd!BCryptDestroyHash` at `0x1400be512`
- `ksecdd!BCryptFinishHash` at `0x1400be4fa`
- `ksecdd!BCryptFinishHash` at `0x1400be4fa`
- `ksecdd!BCryptGetProperty` at `0x1400be42a`
- `ksecdd!BCryptGetProperty` at `0x1400be42a`

## pseudocode

```c

```
