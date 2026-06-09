# DxgkCreateDeviceImpl(_D3DKMT_CREATEDEVICE *,DXGK_VIRTUAL_GPU_PARAV *,DXG_SET_GUEST_DATA * *,uchar)

- ea: `0x1403c8540`
- end: `0x1403c9032`
- name: `?DxgkCreateDeviceImpl@@YAJPEAU_D3DKMT_CREATEDEVICE@@PEAUDXGK_VIRTUAL_GPU_PARAV@@PEAPEAUDXG_SET_GUEST_DATA@@E@Z`
- size: `2802`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEDEVICE *Src, struct DXGK_VIRTUAL_GPU_PARAV *, struct DXG_SET_GUEST_DATA **, unsigned __int8)`
- caller_count: `3`
- callee_count: `24`
- tags: ``

## callers

- `0x140283450`
- `0x1403c84fc`
- `0x1403c8520`

## callees

- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x1400155fc`
- `0x140015780`
- `0x140015910`
- `0x140015a00`
- `0x14001b890`
- `0x14001c910`
- `0x14001d0e4`
- `0x14001f460`
- `0x14002ec90`
- `0x140055044`
- `0x1400593c8`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1401e54cc`
- `0x140323854`
- `0x1403535f0`
- `0x140359cd0`
- `0x140362ec0`
- `0x1403c8540`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c894c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c899e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c894c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403c899e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c893b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c898d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c893b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403c898d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8a82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8aa3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8c62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8c87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8cd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8cfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8a82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8aa3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8c62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8c87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8cd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c8cfc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8a76`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8a97`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8c56`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8c7b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8ccb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8cf0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8a76`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8a97`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8c56`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8c7b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8ccb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403c8cf0`
- `watchdog!WdLogSingleEntry2` at `0x1403c8768`
- `watchdog!WdLogSingleEntry2` at `0x1403c8b00`
- `watchdog!WdLogSingleEntry2` at `0x1403c8c22`
- `watchdog!WdLogSingleEntry2` at `0x1403c8768`
- `watchdog!WdLogSingleEntry2` at `0x1403c8b00`
- `watchdog!WdLogSingleEntry2` at `0x1403c8c22`
- `watchdog!WdLogSingleEntry3` at `0x1403c8f20`
- `watchdog!WdLogSingleEntry3` at `0x1403c8f20`
- `watchdog!WdLogSingleEntry0` at `0x1403c8871`
- `watchdog!WdLogSingleEntry0` at `0x1403c88d7`
- `watchdog!WdLogSingleEntry0` at `0x1403c8871`
- `watchdog!WdLogSingleEntry0` at `0x1403c88d7`
- `watchdog!WdLogSingleEntry1` at `0x1403c8610`
- `watchdog!WdLogSingleEntry1` at `0x1403c86f9`
- `watchdog!WdLogSingleEntry1` at `0x1403c8a3d`
- `watchdog!WdLogSingleEntry1` at `0x1403c8eb5`
- `watchdog!WdLogSingleEntry1` at `0x1403c8fbf`
- `watchdog!WdLogSingleEntry1` at `0x1403c8610`
- `watchdog!WdLogSingleEntry1` at `0x1403c86f9`
- `watchdog!WdLogSingleEntry1` at `0x1403c8a3d`
- `watchdog!WdLogSingleEntry1` at `0x1403c8eb5`
- `watchdog!WdLogSingleEntry1` at `0x1403c8fbf`

## pseudocode

```c

```
