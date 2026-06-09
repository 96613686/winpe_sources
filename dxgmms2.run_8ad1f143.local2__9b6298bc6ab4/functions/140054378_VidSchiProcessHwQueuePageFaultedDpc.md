# VidSchiProcessHwQueuePageFaultedDpc

- ea: `0x140054378`
- end: `0x140054946`
- name: `VidSchiProcessHwQueuePageFaultedDpc`
- size: `1486`
- prototype: `__int64 __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400230e0`

## callees

- `0x14001ca80`
- `0x140020aec`
- `0x140021c90`
- `0x14002a250`
- `0x1400370b4`
- `0x1400416d8`
- `0x1400485c4`
- `0x14004e274`
- `0x140053d2c`
- `0x140054378`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400545da`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400545da`
- `ntoskrnl!DbgPrintEx` at `0x140054634`
- `ntoskrnl!DbgPrintEx` at `0x140054634`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400543ee`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400543ee`
- `ntoskrnl!KeSetEvent` at `0x140054913`
- `ntoskrnl!KeSetEvent` at `0x140054913`
- `watchdog!WdLogSingleEntry5` at `0x140054483`
- `watchdog!WdLogSingleEntry5` at `0x140054483`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14005445e`

## string_xrefs

- `0x14005461f`: `\nThe GPU Scheduler detected a HW queue page fault at GPU VA 0x%I64X.\nWe broke into the debugger to allow a chance for debugging this issue.\nRun "!dxgkdx.gpuva -a %d -p 0x%p -o %d 0x%I64X[ -h]" command for more info.\nTo disable debug breaks on page fault, run "?? dxgmms2!g_PageFaultDebugMode=1" command,\nor "ed 0x%p 1"\n\n`

## pseudocode

```c

```
