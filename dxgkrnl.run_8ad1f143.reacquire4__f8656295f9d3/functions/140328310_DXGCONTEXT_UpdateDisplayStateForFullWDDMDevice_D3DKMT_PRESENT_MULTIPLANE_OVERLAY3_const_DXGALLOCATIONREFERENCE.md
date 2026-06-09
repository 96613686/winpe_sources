# DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,DXGALLOCATIONREFERENCE *,_D3DDDIFORMAT *,int,uint)

- ea: `0x140328310`
- end: `0x140328cb3`
- name: `?UpdateDisplayStateForFullWDDMDevice@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAVDXGALLOCATIONREFERENCE@@PEAW4_D3DDDIFORMAT@@HI@Z`
- size: `2467`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *, struct DXGALLOCATIONREFERENCE *, enum _D3DDDIFORMAT *, int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14033de10`

## callees

- `0x140015288`
- `0x140015458`
- `0x14001b890`
- `0x14001bd70`
- `0x1401f20d8`
- `0x140328310`
- `0x140328cbc`
- `0x140328d60`
- `0x140328e30`
- `0x140328f9c`
- `0x14039eca0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140328729`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140328729`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14032871d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14032871d`
- `watchdog!WdLogSingleEntry0` at `0x1403284a5`
- `watchdog!WdLogSingleEntry0` at `0x1403285f7`
- `watchdog!WdLogSingleEntry0` at `0x1403287ad`
- `watchdog!WdLogSingleEntry0` at `0x14032889e`
- `watchdog!WdLogSingleEntry0` at `0x1403288f4`
- `watchdog!WdLogSingleEntry0` at `0x14032894f`
- `watchdog!WdLogSingleEntry0` at `0x1403289dc`
- `watchdog!WdLogSingleEntry0` at `0x140328a42`
- `watchdog!WdLogSingleEntry0` at `0x140328b48`
- `watchdog!WdLogSingleEntry0` at `0x140328c62`
- `watchdog!WdLogSingleEntry0` at `0x1403284a5`
- `watchdog!WdLogSingleEntry0` at `0x1403285f7`
- `watchdog!WdLogSingleEntry0` at `0x1403287ad`
- `watchdog!WdLogSingleEntry0` at `0x14032889e`
- `watchdog!WdLogSingleEntry0` at `0x1403288f4`
- `watchdog!WdLogSingleEntry0` at `0x14032894f`
- `watchdog!WdLogSingleEntry0` at `0x1403289dc`
- `watchdog!WdLogSingleEntry0` at `0x140328a42`
- `watchdog!WdLogSingleEntry0` at `0x140328b48`
- `watchdog!WdLogSingleEntry0` at `0x140328c62`
- `watchdog!WdLogSingleEntry5` at `0x1403289bc`
- `watchdog!WdLogSingleEntry5` at `0x140328c42`
- `watchdog!WdLogSingleEntry5` at `0x1403289bc`
- `watchdog!WdLogSingleEntry5` at `0x140328c42`

## pseudocode

```c

```
