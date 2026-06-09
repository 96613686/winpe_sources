# DxgkCreateDeviceImpl(_D3DKMT_CREATEDEVICE *,DXGK_VIRTUAL_GPU_PARAV *,DXG_SET_GUEST_DATA * *,uchar)

- ea: `0x1403c78f0`
- end: `0x1403c83e2`
- name: `?DxgkCreateDeviceImpl@@YAJPEAU_D3DKMT_CREATEDEVICE@@PEAUDXGK_VIRTUAL_GPU_PARAV@@PEAPEAUDXG_SET_GUEST_DATA@@E@Z`
- size: `2802`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEDEVICE *Src, struct DXGK_VIRTUAL_GPU_PARAV *, struct DXG_SET_GUEST_DATA **, unsigned __int8)`
- caller_count: `3`
- callee_count: `24`
- tags: ``

## callers

- `0x14028a060`
- `0x1403c78ac`
- `0x1403c78d0`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x1400157bc`
- `0x140015940`
- `0x140015ad0`
- `0x140015bc0`
- `0x14001b9c0`
- `0x14001ca40`
- `0x14001d214`
- `0x14001f630`
- `0x14002ee60`
- `0x1400552b4`
- `0x140059638`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401e784c`
- `0x14032a5c4`
- `0x140353aa0`
- `0x14035a180`
- `0x140363370`
- `0x1403c78f0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c7cfc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c7d4e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c7cfc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c7d4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c7ceb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c7d3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c7ceb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c7d3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c7e32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c7e53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8037`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8087`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c80ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c7e32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c7e53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8037`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8087`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c80ac`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c7e26`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c7e47`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8006`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c802b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c807b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c80a0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c7e26`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c7e47`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8006`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c802b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c807b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c80a0`
- `watchdog!WdLogSingleEntry2` at `0x1403c7b18`
- `watchdog!WdLogSingleEntry2` at `0x1403c7eb0`
- `watchdog!WdLogSingleEntry2` at `0x1403c7fd2`
- `watchdog!WdLogSingleEntry2` at `0x1403c7b18`
- `watchdog!WdLogSingleEntry2` at `0x1403c7eb0`
- `watchdog!WdLogSingleEntry2` at `0x1403c7fd2`
- `watchdog!WdLogSingleEntry3` at `0x1403c82d0`
- `watchdog!WdLogSingleEntry3` at `0x1403c82d0`
- `watchdog!WdLogSingleEntry0` at `0x1403c7c21`
- `watchdog!WdLogSingleEntry0` at `0x1403c7c87`
- `watchdog!WdLogSingleEntry0` at `0x1403c7c21`
- `watchdog!WdLogSingleEntry0` at `0x1403c7c87`
- `watchdog!WdLogSingleEntry1` at `0x1403c79c0`
- `watchdog!WdLogSingleEntry1` at `0x1403c7aa9`
- `watchdog!WdLogSingleEntry1` at `0x1403c7ded`
- `watchdog!WdLogSingleEntry1` at `0x1403c8265`
- `watchdog!WdLogSingleEntry1` at `0x1403c836f`
- `watchdog!WdLogSingleEntry1` at `0x1403c79c0`
- `watchdog!WdLogSingleEntry1` at `0x1403c7aa9`
- `watchdog!WdLogSingleEntry1` at `0x1403c7ded`
- `watchdog!WdLogSingleEntry1` at `0x1403c8265`
- `watchdog!WdLogSingleEntry1` at `0x1403c836f`

## pseudocode

```c

```
