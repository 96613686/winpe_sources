# RxCancelTimerRequest

- ea: `0x1400204a0`
- end: `0x14002062d`
- name: `RxCancelTimerRequest`
- size: `397`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pDeviceObject, PRX_WORKERTHREAD_ROUTINE Routine, PVOID pContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140048600`

## callees

- `0x1400204a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020549`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020549`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020561`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020608`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020561`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020608`
- `ntoskrnl!KeCancelTimer` at `0x14002052d`
- `ntoskrnl!KeCancelTimer` at `0x1400205c1`
- `ntoskrnl!KeCancelTimer` at `0x14002052d`
- `ntoskrnl!KeCancelTimer` at `0x1400205c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400204c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400204c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020580`

## pseudocode

```c

```
