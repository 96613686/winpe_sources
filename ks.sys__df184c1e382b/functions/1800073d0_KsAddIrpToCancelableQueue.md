# KsAddIrpToCancelableQueue

- ea: `0x1800073d0`
- end: `0x1800074cb`
- name: `KsAddIrpToCancelableQueue`
- size: `251`
- prototype: `void __stdcall(PLIST_ENTRY QueueHead, PKSPIN_LOCK SpinLock, PIRP Irp, KSLIST_ENTRY_LOCATION ListLocation, PDRIVER_CANCEL DriverCancel)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180006210`
- `0x18000f090`
- `0x1800134a4`
- `0x180017ef0`
- `0x180033fb0`
- `0x180047fe0`
- `0x1800481d0`
- `0x18005e4e0`

## callees

- `0x1800073d0`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007408`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007408`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007458`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007497`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007458`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007497`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1800074a7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1800074a7`

## pseudocode

```c

```
