# TdrCollectProcessDebugBlob(_TDR_RECOVERY_CONTEXT *)

- ea: `0x140238290`
- end: `0x14023864a`
- name: `?TdrCollectProcessDebugBlob@@YAJPEAU_TDR_RECOVERY_CONTEXT@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(struct _TDR_RECOVERY_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14019b250`

## callees

- `0x140033870`
- `0x1400468cc`
- `0x1400469f4`
- `0x1401fee70`
- `0x1401ff130`
- `0x140238290`
- `0x1402388c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402383d6`
- `ntoskrnl!ExAllocatePool2` at `0x1402383d6`
- `ntoskrnl!ObfDereferenceObject` at `0x140238366`
- `ntoskrnl!ObfDereferenceObject` at `0x14023861f`
- `ntoskrnl!ObfDereferenceObject` at `0x140238366`
- `ntoskrnl!ObfDereferenceObject` at `0x14023861f`
- `ntoskrnl!MmCreateSection` at `0x140238491`
- `ntoskrnl!MmCreateSection` at `0x140238491`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1402384f9`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1402384f9`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140238603`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140238603`
- `ntoskrnl!KeSetEvent` at `0x140238353`
- `ntoskrnl!KeSetEvent` at `0x140238353`
- `watchdog!WdLogSingleEntry0` at `0x14023831e`
- `watchdog!WdLogSingleEntry0` at `0x14023839e`
- `watchdog!WdLogSingleEntry0` at `0x1402384d2`
- `watchdog!WdLogSingleEntry0` at `0x1402385a0`
- `watchdog!WdLogSingleEntry0` at `0x14023831e`
- `watchdog!WdLogSingleEntry0` at `0x14023839e`
- `watchdog!WdLogSingleEntry0` at `0x1402384d2`
- `watchdog!WdLogSingleEntry0` at `0x1402385a0`
- `watchdog!WdLogSingleEntry1` at `0x140238436`
- `watchdog!WdLogSingleEntry1` at `0x1402384a9`
- `watchdog!WdLogSingleEntry1` at `0x140238511`
- `watchdog!WdLogSingleEntry1` at `0x140238568`
- `watchdog!WdLogSingleEntry1` at `0x1402385c5`
- `watchdog!WdLogSingleEntry1` at `0x140238436`
- `watchdog!WdLogSingleEntry1` at `0x1402384a9`
- `watchdog!WdLogSingleEntry1` at `0x140238511`
- `watchdog!WdLogSingleEntry1` at `0x140238568`
- `watchdog!WdLogSingleEntry1` at `0x1402385c5`

## pseudocode

```c

```
