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

- `0x18003ede0`
- `0x180042d90`
- `0x180050254`
- `0x180051660`
- `0x18005639c`
- `0x180056ec0`
- `0x18005fc70`

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
