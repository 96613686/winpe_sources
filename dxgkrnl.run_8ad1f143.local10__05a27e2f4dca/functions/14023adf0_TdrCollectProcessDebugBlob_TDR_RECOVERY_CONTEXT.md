# TdrCollectProcessDebugBlob(_TDR_RECOVERY_CONTEXT *)

- ea: `0x14023adf0`
- end: `0x14023b1aa`
- name: `?TdrCollectProcessDebugBlob@@YAJPEAU_TDR_RECOVERY_CONTEXT@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(struct _TDR_RECOVERY_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14019f260`

## callees

- `0x140033a40`
- `0x140046b2c`
- `0x140046c54`
- `0x140201250`
- `0x140201510`
- `0x14023adf0`
- `0x14023b428`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14023af36`
- `ntoskrnl!ExAllocatePool2` at `0x14023af36`
- `ntoskrnl!ObfDereferenceObject` at `0x14023aec6`
- `ntoskrnl!ObfDereferenceObject` at `0x14023b17f`
- `ntoskrnl!ObfDereferenceObject` at `0x14023aec6`
- `ntoskrnl!ObfDereferenceObject` at `0x14023b17f`
- `ntoskrnl!MmCreateSection` at `0x14023aff1`
- `ntoskrnl!MmCreateSection` at `0x14023aff1`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14023b059`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14023b059`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14023b163`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14023b163`
- `ntoskrnl!KeSetEvent` at `0x14023aeb3`
- `ntoskrnl!KeSetEvent` at `0x14023aeb3`
- `watchdog!WdLogSingleEntry0` at `0x14023ae7e`
- `watchdog!WdLogSingleEntry0` at `0x14023aefe`
- `watchdog!WdLogSingleEntry0` at `0x14023b032`
- `watchdog!WdLogSingleEntry0` at `0x14023b100`
- `watchdog!WdLogSingleEntry0` at `0x14023ae7e`
- `watchdog!WdLogSingleEntry0` at `0x14023aefe`
- `watchdog!WdLogSingleEntry0` at `0x14023b032`
- `watchdog!WdLogSingleEntry0` at `0x14023b100`
- `watchdog!WdLogSingleEntry1` at `0x14023af96`
- `watchdog!WdLogSingleEntry1` at `0x14023b009`
- `watchdog!WdLogSingleEntry1` at `0x14023b071`
- `watchdog!WdLogSingleEntry1` at `0x14023b0c8`
- `watchdog!WdLogSingleEntry1` at `0x14023b125`
- `watchdog!WdLogSingleEntry1` at `0x14023af96`
- `watchdog!WdLogSingleEntry1` at `0x14023b009`
- `watchdog!WdLogSingleEntry1` at `0x14023b071`
- `watchdog!WdLogSingleEntry1` at `0x14023b0c8`
- `watchdog!WdLogSingleEntry1` at `0x14023b125`

## pseudocode

```c

```
