# ADAPTER_DISPLAY::CreateCddAllocations(DXGDEVICE *,uint,_D3DKMT_DISPLAYMODE const &,COREDEVICEACCESS *)

- ea: `0x1401f3454`
- end: `0x1401f41ce`
- name: `?CreateCddAllocations@ADAPTER_DISPLAY@@QEAAJPEAVDXGDEVICE@@IAEBU_D3DKMT_DISPLAYMODE@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3450`
- prototype: `__int64 __fastcall(ADAPTER_DISPLAY *__hidden this, struct DXGDEVICE *, unsigned int, const struct _D3DKMT_DISPLAYMODE *, struct COREDEVICEACCESS *)`
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1401f45e8`
- `0x1402cabc4`
- `0x1402d2824`

## callees

- `0x14001b9c0`
- `0x14001d1a0`
- `0x140021e50`
- `0x140033d80`
- `0x140069874`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401d1828`
- `0x1401df954`
- `0x1401f3454`
- `0x140324bfc`
- `0x14032a5c4`
- `0x140393f58`
- `0x1403c2a5c`
- `0x1403d38fc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3b4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3f65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3b4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f3f65`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f3b40`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f3f59`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f3b40`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f3f59`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f3986`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f3986`
- `watchdog!WdLogSingleEntry4` at `0x1401f36f9`
- `watchdog!WdLogSingleEntry4` at `0x1401f3c02`
- `watchdog!WdLogSingleEntry4` at `0x1401f36f9`
- `watchdog!WdLogSingleEntry4` at `0x1401f3c02`
- `watchdog!WdLogSingleEntry2` at `0x1401f357f`
- `watchdog!WdLogSingleEntry2` at `0x1401f357f`
- `watchdog!WdLogSingleEntry3` at `0x1401f3775`
- `watchdog!WdLogSingleEntry3` at `0x1401f3775`
- `watchdog!WdLogSingleEntry0` at `0x1401f34f3`
- `watchdog!WdLogSingleEntry0` at `0x1401f35f8`
- `watchdog!WdLogSingleEntry0` at `0x1401f3660`
- `watchdog!WdLogSingleEntry0` at `0x1401f37e0`
- `watchdog!WdLogSingleEntry0` at `0x1401f39aa`
- `watchdog!WdLogSingleEntry0` at `0x1401f39fc`
- `watchdog!WdLogSingleEntry0` at `0x1401f3adb`
- `watchdog!WdLogSingleEntry0` at `0x1401f3de1`
- `watchdog!WdLogSingleEntry0` at `0x1401f3e37`
- `watchdog!WdLogSingleEntry0` at `0x1401f3ef4`
- `watchdog!WdLogSingleEntry0` at `0x1401f3f96`
- `watchdog!WdLogSingleEntry0` at `0x1401f405a`
- `watchdog!WdLogSingleEntry0` at `0x1401f409b`
- `watchdog!WdLogSingleEntry0` at `0x1401f4127`
- `watchdog!WdLogSingleEntry0` at `0x1401f34f3`
- `watchdog!WdLogSingleEntry0` at `0x1401f35f8`
- `watchdog!WdLogSingleEntry0` at `0x1401f3660`
- `watchdog!WdLogSingleEntry0` at `0x1401f37e0`
- `watchdog!WdLogSingleEntry0` at `0x1401f39aa`
- `watchdog!WdLogSingleEntry0` at `0x1401f39fc`
- `watchdog!WdLogSingleEntry0` at `0x1401f3adb`
- `watchdog!WdLogSingleEntry0` at `0x1401f3de1`
- `watchdog!WdLogSingleEntry0` at `0x1401f3e37`
- `watchdog!WdLogSingleEntry0` at `0x1401f3ef4`
- `watchdog!WdLogSingleEntry0` at `0x1401f3f96`
- `watchdog!WdLogSingleEntry0` at `0x1401f405a`
- `watchdog!WdLogSingleEntry0` at `0x1401f409b`
- `watchdog!WdLogSingleEntry0` at `0x1401f4127`
- `watchdog!WdLogSingleEntry5` at `0x1401f3962`
- `watchdog!WdLogSingleEntry5` at `0x1401f3d42`
- `watchdog!WdLogSingleEntry5` at `0x1401f3962`
- `watchdog!WdLogSingleEntry5` at `0x1401f3d42`

## string_xrefs

- `0x1401f39b8`: `NULL != CreateStandardAlloc.hResource`
- `0x1401f3a0a`: `0 != CreateStandardAlloc.hGlobalShare`
- `0x1401f3df2`: `(NULL != CreateStandardAlloc.hAllocation[0]) && (NULL != CreateStandardAlloc.hResource)`

## pseudocode

```c

```
