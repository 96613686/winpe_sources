# DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,DXGALLOCATIONREFERENCE *,_D3DDDIFORMAT *,int,uint)

- ea: `0x14032f080`
- end: `0x14032fa23`
- name: `?UpdateDisplayStateForFullWDDMDevice@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAVDXGALLOCATIONREFERENCE@@PEAW4_D3DDDIFORMAT@@HI@Z`
- size: `2467`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *, struct DXGALLOCATIONREFERENCE *, enum _D3DDDIFORMAT *, int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1404098b8`

## callees

- `0x140015448`
- `0x140015618`
- `0x14001b9c0`
- `0x14001bea0`
- `0x1401f44b0`
- `0x14032f080`
- `0x14032fa2c`
- `0x14032fad0`
- `0x14032fba0`
- `0x14032fd0c`
- `0x14039fa80`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032f499`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032f499`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14032f48d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14032f48d`
- `watchdog!WdLogSingleEntry0` at `0x14032f215`
- `watchdog!WdLogSingleEntry0` at `0x14032f367`
- `watchdog!WdLogSingleEntry0` at `0x14032f51d`
- `watchdog!WdLogSingleEntry0` at `0x14032f60e`
- `watchdog!WdLogSingleEntry0` at `0x14032f664`
- `watchdog!WdLogSingleEntry0` at `0x14032f6bf`
- `watchdog!WdLogSingleEntry0` at `0x14032f74c`
- `watchdog!WdLogSingleEntry0` at `0x14032f7b2`
- `watchdog!WdLogSingleEntry0` at `0x14032f8b8`
- `watchdog!WdLogSingleEntry0` at `0x14032f9d2`
- `watchdog!WdLogSingleEntry0` at `0x14032f215`
- `watchdog!WdLogSingleEntry0` at `0x14032f367`
- `watchdog!WdLogSingleEntry0` at `0x14032f51d`
- `watchdog!WdLogSingleEntry0` at `0x14032f60e`
- `watchdog!WdLogSingleEntry0` at `0x14032f664`
- `watchdog!WdLogSingleEntry0` at `0x14032f6bf`
- `watchdog!WdLogSingleEntry0` at `0x14032f74c`
- `watchdog!WdLogSingleEntry0` at `0x14032f7b2`
- `watchdog!WdLogSingleEntry0` at `0x14032f8b8`
- `watchdog!WdLogSingleEntry0` at `0x14032f9d2`
- `watchdog!WdLogSingleEntry5` at `0x14032f72c`
- `watchdog!WdLogSingleEntry5` at `0x14032f9b2`
- `watchdog!WdLogSingleEntry5` at `0x14032f72c`
- `watchdog!WdLogSingleEntry5` at `0x14032f9b2`

## pseudocode

```c

```
