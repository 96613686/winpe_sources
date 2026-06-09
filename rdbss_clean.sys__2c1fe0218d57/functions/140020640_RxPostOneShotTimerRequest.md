# RxPostOneShotTimerRequest

- ea: `0x140020640`
- end: `0x140020765`
- name: `RxPostOneShotTimerRequest`
- size: `293`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pDeviceObject, PRX_WORK_ITEM pWorkItem, PRX_WORKERTHREAD_ROUTINE Routine, PVOID pContext, LARGE_INTEGER TimeInterval)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140020640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020683`
- `ntoskrnl!ExAllocatePool2` at `0x140020683`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020744`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020744`
- `ntoskrnl!KeInitializeTimer` at `0x14002069f`
- `ntoskrnl!KeInitializeTimer` at `0x14002069f`
- `ntoskrnl!KeInitializeDpc` at `0x1400206bc`
- `ntoskrnl!KeInitializeDpc` at `0x1400206bc`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002072e`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002072e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400206df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400206df`

## pseudocode

```c

```
