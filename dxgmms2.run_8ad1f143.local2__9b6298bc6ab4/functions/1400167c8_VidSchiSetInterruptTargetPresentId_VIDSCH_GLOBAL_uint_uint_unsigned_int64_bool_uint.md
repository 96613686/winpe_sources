# VidSchiSetInterruptTargetPresentId(_VIDSCH_GLOBAL *,uint,uint,unsigned __int64,bool,uint)

- ea: `0x1400167c8`
- end: `0x140016b6d`
- name: `?VidSchiSetInterruptTargetPresentId@@YAJPEAU_VIDSCH_GLOBAL@@II_K_NI@Z`
- size: `933`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, unsigned int, unsigned int, unsigned __int64, bool, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400164ec`
- `0x140017df0`
- `0x14001d344`
- `0x140034b28`
- `0x140037aac`
- `0x140043088`
- `0x140043248`
- `0x140056a04`
- `0x1400ab908`
- `0x1400dee68`
- `0x1400f8aa0`
- `0x1401016d8`

## callees

- `0x1400167c8`
- `0x140017190`
- `0x140017630`
- `0x140058680`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016839`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016839`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001688c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400169a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001688c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400169a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400169bb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016add`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400169bb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016add`
- `ntoskrnl!ExQueueWorkItem` at `0x140016ac5`
- `ntoskrnl!ExQueueWorkItem` at `0x140016b07`
- `ntoskrnl!ExQueueWorkItem` at `0x140016ac5`
- `ntoskrnl!ExQueueWorkItem` at `0x140016b07`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140016b22`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140016b22`
- `ntoskrnl!DbgPrintEx` at `0x140016b58`
- `ntoskrnl!DbgPrintEx` at `0x140016b58`
- `dxgkrnl!DpSynchronizeExecution` at `0x140016959`
- `dxgkrnl!DpSynchronizeExecution` at `0x140016959`

## string_xrefs

- `0x140016b42`: `\nThe GPU Scheduler detected driver failing to set interrupt target PresentId.\nWe broke into the debugger to allow a chance for debugging this issue.\nVidPnSourceId = %d.\nPlane = %d.\nInterruptTargetPresentId = 0x%I64x.\nWe broke into the debugger to allow a chance for debugging this issue.\nTo disable debug breaks on these failures, run "?? dxgmms2!g_BreakOnSetInterruptTargetPresentIdErrors=0" command,\nor "ed 0x%p 0"\n\n`

## pseudocode

```c

```
