# VidSchiSetInterruptTargetPresentId(_VIDSCH_GLOBAL *,uint,uint,unsigned __int64,bool,uint)

- ea: `0x140015c70`
- end: `0x140016015`
- name: `?VidSchiSetInterruptTargetPresentId@@YAJPEAU_VIDSCH_GLOBAL@@II_K_NI@Z`
- size: `933`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, unsigned int, unsigned int, unsigned __int64, bool, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140015994`
- `0x140018014`
- `0x1400238a0`
- `0x140033418`
- `0x140036b08`
- `0x1400431f8`
- `0x1400433b8`
- `0x1400572d4`
- `0x1400accb8`
- `0x1400e72c8`
- `0x1401033a0`
- `0x14010a7d8`

## callees

- `0x140015c70`
- `0x14002b878`
- `0x1400347ac`
- `0x140058f50`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015ce1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015ce1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015d34`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015e4f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015d34`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015e4f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015e63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015f85`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015e63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015f85`
- `ntoskrnl!ExQueueWorkItem` at `0x140015f6d`
- `ntoskrnl!ExQueueWorkItem` at `0x140015faf`
- `ntoskrnl!ExQueueWorkItem` at `0x140015f6d`
- `ntoskrnl!ExQueueWorkItem` at `0x140015faf`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140015fca`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140015fca`
- `ntoskrnl!DbgPrintEx` at `0x140016000`
- `ntoskrnl!DbgPrintEx` at `0x140016000`
- `dxgkrnl!DpSynchronizeExecution` at `0x140015e01`
- `dxgkrnl!DpSynchronizeExecution` at `0x140015e01`

## string_xrefs

- `0x140015fea`: `\nThe GPU Scheduler detected driver failing to set interrupt target PresentId.\nWe broke into the debugger to allow a chance for debugging this issue.\nVidPnSourceId = %d.\nPlane = %d.\nInterruptTargetPresentId = 0x%I64x.\nWe broke into the debugger to allow a chance for debugging this issue.\nTo disable debug breaks on these failures, run "?? dxgmms2!g_BreakOnSetInterruptTargetPresentIdErrors=0" command,\nor "ed 0x%p 0"\n\n`

## pseudocode

```c

```
