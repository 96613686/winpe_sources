# VidSchiWorkerThreadTimerCallback(_EX_TIMER *,void *)

- ea: `0x14000a150`
- end: `0x14000a2a5`
- name: `?VidSchiWorkerThreadTimerCallback@@YAXPEAU_EX_TIMER@@PEAX@Z`
- size: `341`
- prototype: `void __fastcall(struct _EX_TIMER *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000a150`
- `0x14000a768`
- `0x1400120fc`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a199`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a199`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a1e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a1e3`
- `ntoskrnl!ExCancelTimer` at `0x14000a1ba`
- `ntoskrnl!ExCancelTimer` at `0x14000a1ba`
- `ntoskrnl!KeSetEvent` at `0x14000a257`
- `ntoskrnl!KeSetEvent` at `0x14000a257`
- `HAL!KeQueryPerformanceCounter` at `0x14000a16f`
- `HAL!KeQueryPerformanceCounter` at `0x14000a16f`

## pseudocode

```c

```
