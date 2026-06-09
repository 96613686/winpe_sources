# VidSchiWorkerThreadTimerCallback(_EX_TIMER *,void *)

- ea: `0x14000a4c0`
- end: `0x14000a615`
- name: `?VidSchiWorkerThreadTimerCallback@@YAXPEAU_EX_TIMER@@PEAX@Z`
- size: `341`
- prototype: `void __fastcall(struct _EX_TIMER *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000a4c0`
- `0x14000aa18`
- `0x14001265c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a509`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a509`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a553`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a553`
- `ntoskrnl!ExCancelTimer` at `0x14000a52a`
- `ntoskrnl!ExCancelTimer` at `0x14000a52a`
- `ntoskrnl!KeSetEvent` at `0x14000a5c7`
- `ntoskrnl!KeSetEvent` at `0x14000a5c7`
- `HAL!KeQueryPerformanceCounter` at `0x14000a4df`
- `HAL!KeQueryPerformanceCounter` at `0x14000a4df`

## pseudocode

```c

```
