# BLTQUEUE::PrepareStagingBuffer(DXGDEVICE *,uint,COREDEVICEACCESS *)

- ea: `0x140308cd0`
- end: `0x140309528`
- name: `?PrepareStagingBuffer@BLTQUEUE@@QEAAJPEAVDXGDEVICE@@IPEAVCOREDEVICEACCESS@@@Z`
- size: `2136`
- prototype: `__int64 __fastcall(BLTQUEUE *__hidden this, struct DXGDEVICE *, unsigned int, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x14037f364`

## callees

- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d1a0`
- `0x14002dbc0`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1402970b0`
- `0x14030846c`
- `0x140308cd0`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14035e3e0`
- `0x140393f58`
- `0x1403b7b70`
- `0x1403c2a5c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140308e3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140309111`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403092b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140308e3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140309111`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403092b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140309105`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140309105`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140308e2e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403092a6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140308e2e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403092a6`
- `watchdog!WdLogSingleEntry3` at `0x140308e93`
- `watchdog!WdLogSingleEntry3` at `0x140308f64`
- `watchdog!WdLogSingleEntry3` at `0x140308e93`
- `watchdog!WdLogSingleEntry3` at `0x140308f64`
- `watchdog!WdLogSingleEntry0` at `0x140308d24`
- `watchdog!WdLogSingleEntry0` at `0x140308dd0`
- `watchdog!WdLogSingleEntry0` at `0x14030909f`
- `watchdog!WdLogSingleEntry0` at `0x140309237`
- `watchdog!WdLogSingleEntry0` at `0x1403092cb`
- `watchdog!WdLogSingleEntry0` at `0x14030940b`
- `watchdog!WdLogSingleEntry0` at `0x140309471`
- `watchdog!WdLogSingleEntry0` at `0x140308d24`
- `watchdog!WdLogSingleEntry0` at `0x140308dd0`
- `watchdog!WdLogSingleEntry0` at `0x14030909f`
- `watchdog!WdLogSingleEntry0` at `0x140309237`
- `watchdog!WdLogSingleEntry0` at `0x1403092cb`
- `watchdog!WdLogSingleEntry0` at `0x14030940b`
- `watchdog!WdLogSingleEntry0` at `0x140309471`
- `watchdog!WdLogSingleEntry1` at `0x140308f0a`
- `watchdog!WdLogSingleEntry1` at `0x140309001`
- `watchdog!WdLogSingleEntry1` at `0x14030937d`
- `watchdog!WdLogSingleEntry1` at `0x140308f0a`
- `watchdog!WdLogSingleEntry1` at `0x140309001`
- `watchdog!WdLogSingleEntry1` at `0x14030937d`

## string_xrefs

- `0x14030938e`: `VmBusSendMakeResident failed: 0x%I64x`
- `0x14030900d`: `DxgkCreateSynchronizationObjectInternal failed: 0x%I64x`

## pseudocode

```c

```
