# DXG_HOST_GLOBAL_VMBUS::VmBusOpenSyncObject(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x140192fa0`
- end: `0x140193a6d`
- name: `?VmBusOpenSyncObject@DXG_HOST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `2765`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update`

## callees

- `0x140012380`
- `0x140015970`
- `0x140015d70`
- `0x14001667c`
- `0x140017fb8`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001cbe0`
- `0x14001cec0`
- `0x14001d070`
- `0x14001f120`
- `0x140030820`
- `0x140030860`
- `0x140033bd4`
- `0x14003f3d8`
- `0x14004885c`
- `0x1400491a8`
- `0x1400a0100`
- `0x140192fa0`
- `0x140193a74`
- `0x1401975c0`
- `0x140323854`
- `0x14032df70`
- `0x14036d1b4`
- `0x1403bb24c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019307c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401933df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019356f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140193649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019387f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140193a1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019307c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401933df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019356f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140193649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019387f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140193a1c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401933d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140193873`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140193a10`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401933d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140193873`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140193a10`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140193070`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140193563`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019363d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140193070`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140193563`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019363d`
- `watchdog!WdLogSingleEntry2` at `0x1401932b2`
- `watchdog!WdLogSingleEntry2` at `0x14019343b`
- `watchdog!WdLogSingleEntry2` at `0x14019366c`
- `watchdog!WdLogSingleEntry2` at `0x140193752`
- `watchdog!WdLogSingleEntry2` at `0x1401938ef`
- `watchdog!WdLogSingleEntry2` at `0x1401932b2`
- `watchdog!WdLogSingleEntry2` at `0x14019343b`
- `watchdog!WdLogSingleEntry2` at `0x14019366c`
- `watchdog!WdLogSingleEntry2` at `0x140193752`
- `watchdog!WdLogSingleEntry2` at `0x1401938ef`
- `watchdog!WdLogSingleEntry0` at `0x1401930f6`
- `watchdog!WdLogSingleEntry0` at `0x140193376`
- `watchdog!WdLogSingleEntry0` at `0x1401935ea`
- `watchdog!WdLogSingleEntry0` at `0x140193816`
- `watchdog!WdLogSingleEntry0` at `0x1401939b3`
- `watchdog!WdLogSingleEntry0` at `0x1401930f6`
- `watchdog!WdLogSingleEntry0` at `0x140193376`
- `watchdog!WdLogSingleEntry0` at `0x1401935ea`
- `watchdog!WdLogSingleEntry0` at `0x140193816`
- `watchdog!WdLogSingleEntry0` at `0x1401939b3`
- `watchdog!WdLogSingleEntry1` at `0x140193145`
- `watchdog!WdLogSingleEntry1` at `0x1401931bf`
- `watchdog!WdLogSingleEntry1` at `0x1401931f4`
- `watchdog!WdLogSingleEntry1` at `0x140193145`
- `watchdog!WdLogSingleEntry1` at `0x1401931bf`
- `watchdog!WdLogSingleEntry1` at `0x1401931f4`

## string_xrefs

- `0x140193200`: `Cannot open keyed mutex from a shared resource which doesn't include a keyed mutex: 0x%I64x`
- `0x1401932c3`: `Failed to open sync object (0x%I64x), returning 0x%I64x`
- `0x140193763`: `Failed to open sync object (0x%I64x), returning 0x%I64x`
- `0x140193900`: `Failed to open sync object (0x%I64x), returning 0x%I64x`

## pseudocode

```c

```
