# RxPostRecurrentTimerRequest

- ea: `0x140020770`
- end: `0x140020906`
- name: `RxPostRecurrentTimerRequest`
- size: `406`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pDeviceObject, PRX_WORKERTHREAD_ROUTINE Routine, PVOID pContext, LARGE_INTEGER TimeInterval)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140020770`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020808`
- `ntoskrnl!ExAllocatePool2` at `0x140020808`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400208e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400208e6`
- `ntoskrnl!KeInitializeTimer` at `0x14002083d`
- `ntoskrnl!KeInitializeTimer` at `0x14002083d`
- `ntoskrnl!KeInitializeDpc` at `0x140020857`
- `ntoskrnl!KeInitializeDpc` at `0x140020857`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400208cc`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400208cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400207a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400207a8`

## pseudocode

```c

```
