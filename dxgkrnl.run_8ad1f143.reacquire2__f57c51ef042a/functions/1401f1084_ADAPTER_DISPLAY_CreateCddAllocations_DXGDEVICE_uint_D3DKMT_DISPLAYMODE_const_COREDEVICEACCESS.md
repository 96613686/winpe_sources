# ADAPTER_DISPLAY::CreateCddAllocations(DXGDEVICE *,uint,_D3DKMT_DISPLAYMODE const &,COREDEVICEACCESS *)

- ea: `0x1401f1084`
- end: `0x1401f1df5`
- name: `?CreateCddAllocations@ADAPTER_DISPLAY@@QEAAJPEAVDXGDEVICE@@IAEBU_D3DKMT_DISPLAYMODE@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3441`
- prototype: `__int64 __fastcall(ADAPTER_DISPLAY *__hidden this, struct DXGDEVICE *, unsigned int, const struct _D3DKMT_DISPLAYMODE *, struct COREDEVICEACCESS *)`
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1401f2210`
- `0x1402c4174`
- `0x1402cbd7c`

## callees

- `0x14001b890`
- `0x14001d070`
- `0x140021c80`
- `0x140033bb0`
- `0x140069314`
- `0x1400a0100`
- `0x1400a0540`
- `0x1401cec28`
- `0x1401dd5e4`
- `0x1401f1084`
- `0x14031de8c`
- `0x140323854`
- `0x140340858`
- `0x1403c36ac`
- `0x1403d34dc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1762`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1b8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1762`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1b8c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f1756`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f1b80`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f1756`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f1b80`
- `watchdog!WdLogSingleEntry4` at `0x1401f1329`
- `watchdog!WdLogSingleEntry4` at `0x1401f1818`
- `watchdog!WdLogSingleEntry4` at `0x1401f1329`
- `watchdog!WdLogSingleEntry4` at `0x1401f1818`
- `watchdog!WdLogSingleEntry2` at `0x1401f11af`
- `watchdog!WdLogSingleEntry2` at `0x1401f11af`
- `watchdog!WdLogSingleEntry3` at `0x1401f13a5`
- `watchdog!WdLogSingleEntry3` at `0x1401f13a5`
- `watchdog!WdLogSingleEntry0` at `0x1401f1123`
- `watchdog!WdLogSingleEntry0` at `0x1401f1228`
- `watchdog!WdLogSingleEntry0` at `0x1401f1290`
- `watchdog!WdLogSingleEntry0` at `0x1401f1410`
- `watchdog!WdLogSingleEntry0` at `0x1401f15c0`
- `watchdog!WdLogSingleEntry0` at `0x1401f1612`
- `watchdog!WdLogSingleEntry0` at `0x1401f16f1`
- `watchdog!WdLogSingleEntry0` at `0x1401f1a08`
- `watchdog!WdLogSingleEntry0` at `0x1401f1a5e`
- `watchdog!WdLogSingleEntry0` at `0x1401f1b1b`
- `watchdog!WdLogSingleEntry0` at `0x1401f1bbd`
- `watchdog!WdLogSingleEntry0` at `0x1401f1c81`
- `watchdog!WdLogSingleEntry0` at `0x1401f1cc2`
- `watchdog!WdLogSingleEntry0` at `0x1401f1d4e`
- `watchdog!WdLogSingleEntry0` at `0x1401f1123`
- `watchdog!WdLogSingleEntry0` at `0x1401f1228`
- `watchdog!WdLogSingleEntry0` at `0x1401f1290`
- `watchdog!WdLogSingleEntry0` at `0x1401f1410`
- `watchdog!WdLogSingleEntry0` at `0x1401f15c0`
- `watchdog!WdLogSingleEntry0` at `0x1401f1612`
- `watchdog!WdLogSingleEntry0` at `0x1401f16f1`
- `watchdog!WdLogSingleEntry0` at `0x1401f1a08`
- `watchdog!WdLogSingleEntry0` at `0x1401f1a5e`
- `watchdog!WdLogSingleEntry0` at `0x1401f1b1b`
- `watchdog!WdLogSingleEntry0` at `0x1401f1bbd`
- `watchdog!WdLogSingleEntry0` at `0x1401f1c81`
- `watchdog!WdLogSingleEntry0` at `0x1401f1cc2`
- `watchdog!WdLogSingleEntry0` at `0x1401f1d4e`
- `watchdog!WdLogSingleEntry5` at `0x1401f1592`
- `watchdog!WdLogSingleEntry5` at `0x1401f1969`
- `watchdog!WdLogSingleEntry5` at `0x1401f1592`
- `watchdog!WdLogSingleEntry5` at `0x1401f1969`

## string_xrefs

- `0x1401f15ce`: `NULL != CreateStandardAlloc.hResource`
- `0x1401f1620`: `0 != CreateStandardAlloc.hGlobalShare`
- `0x1401f1a19`: `(NULL != CreateStandardAlloc.hAllocation[0]) && (NULL != CreateStandardAlloc.hResource)`

## pseudocode

```c

```
