# KsUnregisterWorker

- ea: `0x18000aa80`
- end: `0x18000ab07`
- name: `KsUnregisterWorker`
- size: `135`
- prototype: `void __stdcall(PKSWORKER Worker)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18003edd0`
- `0x180042d90`
- `0x1800503f4`
- `0x180051800`
- `0x18005653c`
- `0x180057060`
- `0x18005fe10`

## callees

- `0x18000aa80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000aa94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000aa94`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000aaaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000aad8`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000aaaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000aad8`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000aaf9`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000aaf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000aac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000aac0`

## pseudocode

```c

```
