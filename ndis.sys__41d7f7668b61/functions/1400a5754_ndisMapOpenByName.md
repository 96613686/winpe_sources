# ndisMapOpenByName

- ea: `0x1400a5754`
- end: `0x1400a592a`
- name: `ndisMapOpenByName`
- size: `470`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140179a68`

## callees

- `0x140005840`
- `0x1400110b0`
- `0x140012610`
- `0x14002ab60`
- `0x140048e70`
- `0x140063390`
- `0x1400a5754`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400a581e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400a581e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a58dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a58dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400a57ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400a57ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a58c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a58c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a5833`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a5833`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a5873`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a5873`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a58b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a58b7`

## pseudocode

```c

```
