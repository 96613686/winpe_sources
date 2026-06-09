# DXGADAPTER::PinFrameBufferForSave(uint,unsigned __int64,uint,_MDL * *,_DXGK_ADL * *)

- ea: `0x1403e7338`
- end: `0x1403e77bd`
- name: `?PinFrameBufferForSave@DXGADAPTER@@QEAAJI_KIPEAPEAU_MDL@@PEAPEAU_DXGK_ADL@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned __int64, unsigned int, struct _MDL **, struct _DXGK_ADL **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400352a0`
- `0x1400352e0`

## callees

- `0x14001b890`
- `0x14001d0e4`
- `0x14003d670`
- `0x14003e3b0`
- `0x14003e638`
- `0x14003e760`
- `0x140044010`
- `0x1403e7338`

## import_xrefs

- `ntoskrnl!MmMapViewInSystemSpace` at `0x1403e7486`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1403e7486`
- `ntoskrnl!IoAllocateMdl` at `0x1403e74db`
- `ntoskrnl!IoAllocateMdl` at `0x1403e74db`
- `ntoskrnl!MmProbeAndLockPages` at `0x1403e7552`
- `ntoskrnl!MmProbeAndLockPages` at `0x1403e7552`
- `ntoskrnl!MmUnlockPages` at `0x1403e7768`
- `ntoskrnl!MmUnlockPages` at `0x1403e7768`
- `ntoskrnl!IoFreeMdl` at `0x1403e777c`
- `ntoskrnl!IoFreeMdl` at `0x1403e777c`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1403e7792`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1403e7792`
- `watchdog!WdLogSingleEntry0` at `0x1403e74f7`
- `watchdog!WdLogSingleEntry0` at `0x1403e76ba`
- `watchdog!WdLogSingleEntry0` at `0x1403e74f7`
- `watchdog!WdLogSingleEntry0` at `0x1403e76ba`
- `watchdog!WdLogSingleEntry1` at `0x1403e736a`
- `watchdog!WdLogSingleEntry1` at `0x1403e73cd`
- `watchdog!WdLogSingleEntry1` at `0x1403e7434`
- `watchdog!WdLogSingleEntry1` at `0x1403e74a9`
- `watchdog!WdLogSingleEntry1` at `0x1403e75a9`
- `watchdog!WdLogSingleEntry1` at `0x1403e764c`
- `watchdog!WdLogSingleEntry1` at `0x1403e736a`
- `watchdog!WdLogSingleEntry1` at `0x1403e73cd`
- `watchdog!WdLogSingleEntry1` at `0x1403e7434`
- `watchdog!WdLogSingleEntry1` at `0x1403e74a9`
- `watchdog!WdLogSingleEntry1` at `0x1403e75a9`
- `watchdog!WdLogSingleEntry1` at `0x1403e764c`

## string_xrefs

- `0x1403e7406`: `PinFrameBufferForSave CommitSize (%I64u) is not a multiple of PAGE_SIZE`
- `0x1403e744a`: `Frame buffer save area already pinned for PhysicalAdapterIndex %u. PinFrameBufferForSave cannot be called again without first calling Unpin.`

## pseudocode

```c

```
