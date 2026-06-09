# ndisMapOpenByName

- ea: `0x1400a0314`
- end: `0x1400a04ea`
- name: `ndisMapOpenByName`
- size: `470`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140173a68`

## callees

- `0x14001cf50`
- `0x14001e4b0`
- `0x140029620`
- `0x140036a70`
- `0x140044370`
- `0x14005edf0`
- `0x1400a0314`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400a03de`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400a03de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a049c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a049c`
- `ntoskrnl!ExAllocatePool2` at `0x1400a038e`
- `ntoskrnl!ExAllocatePool2` at `0x1400a038e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a0489`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a0489`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a03f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a03f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a0477`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a0477`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a0433`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a0433`

## pseudocode

```c

```
