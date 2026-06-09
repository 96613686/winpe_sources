# VidSchiProcessHwQueuePageFaultedDpc

- ea: `0x140054c50`
- end: `0x14005521e`
- name: `VidSchiProcessHwQueuePageFaultedDpc`
- size: `1486`
- prototype: `__int64 __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400201c0`

## callees

- `0x140017750`
- `0x14001ef8c`
- `0x14001f640`
- `0x140027b90`
- `0x140035ec4`
- `0x1400403fc`
- `0x140048b64`
- `0x14004e984`
- `0x14005443c`
- `0x140054c50`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140054eb2`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140054eb2`
- `ntoskrnl!DbgPrintEx` at `0x140054f0c`
- `ntoskrnl!DbgPrintEx` at `0x140054f0c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054cc6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140054cc6`
- `ntoskrnl!KeSetEvent` at `0x1400551eb`
- `ntoskrnl!KeSetEvent` at `0x1400551eb`
- `watchdog!WdLogSingleEntry5` at `0x140054d5b`
- `watchdog!WdLogSingleEntry5` at `0x140054d5b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140054d36`

## string_xrefs

- `0x140054ef7`: `\nThe GPU Scheduler detected a HW queue page fault at GPU VA 0x%I64X.\nWe broke into the debugger to allow a chance for debugging this issue.\nRun "!dxgkdx.gpuva -a %d -p 0x%p -o %d 0x%I64X[ -h]" command for more info.\nTo disable debug breaks on page fault, run "?? dxgmms2!g_PageFaultDebugMode=1" command,\nor "ed 0x%p 1"\n\n`

## pseudocode

```c

```
