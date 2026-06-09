# BLTQUEUE::PrepareStagingBuffer(DXGDEVICE *,uint,COREDEVICEACCESS *)

- ea: `0x140301f60`
- end: `0x1403027b8`
- name: `?PrepareStagingBuffer@BLTQUEUE@@QEAAJPEAVDXGDEVICE@@IPEAVCOREDEVICEACCESS@@@Z`
- size: `2136`
- prototype: `__int64 __fastcall(BLTQUEUE *__hidden this, struct DXGDEVICE *, unsigned int, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x14037db44`

## callees

- `0x14001b890`
- `0x14001bd70`
- `0x14001d070`
- `0x14002d9f0`
- `0x1400a0100`
- `0x1400a0540`
- `0x140290750`
- `0x1403016fc`
- `0x140301f60`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x140340858`
- `0x14035df30`
- `0x1403aee14`
- `0x1403c36ac`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403020ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403023a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140302542`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403020ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403023a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140302542`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140302395`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140302395`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403020be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140302536`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403020be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140302536`
- `watchdog!WdLogSingleEntry3` at `0x140302123`
- `watchdog!WdLogSingleEntry3` at `0x1403021f4`
- `watchdog!WdLogSingleEntry3` at `0x140302123`
- `watchdog!WdLogSingleEntry3` at `0x1403021f4`
- `watchdog!WdLogSingleEntry0` at `0x140301fb4`
- `watchdog!WdLogSingleEntry0` at `0x140302060`
- `watchdog!WdLogSingleEntry0` at `0x14030232f`
- `watchdog!WdLogSingleEntry0` at `0x1403024c7`
- `watchdog!WdLogSingleEntry0` at `0x14030255b`
- `watchdog!WdLogSingleEntry0` at `0x14030269b`
- `watchdog!WdLogSingleEntry0` at `0x140302701`
- `watchdog!WdLogSingleEntry0` at `0x140301fb4`
- `watchdog!WdLogSingleEntry0` at `0x140302060`
- `watchdog!WdLogSingleEntry0` at `0x14030232f`
- `watchdog!WdLogSingleEntry0` at `0x1403024c7`
- `watchdog!WdLogSingleEntry0` at `0x14030255b`
- `watchdog!WdLogSingleEntry0` at `0x14030269b`
- `watchdog!WdLogSingleEntry0` at `0x140302701`
- `watchdog!WdLogSingleEntry1` at `0x14030219a`
- `watchdog!WdLogSingleEntry1` at `0x140302291`
- `watchdog!WdLogSingleEntry1` at `0x14030260d`
- `watchdog!WdLogSingleEntry1` at `0x14030219a`
- `watchdog!WdLogSingleEntry1` at `0x140302291`
- `watchdog!WdLogSingleEntry1` at `0x14030260d`

## string_xrefs

- `0x14030261e`: `VmBusSendMakeResident failed: 0x%I64x`
- `0x14030229d`: `DxgkCreateSynchronizationObjectInternal failed: 0x%I64x`

## pseudocode

```c

```
