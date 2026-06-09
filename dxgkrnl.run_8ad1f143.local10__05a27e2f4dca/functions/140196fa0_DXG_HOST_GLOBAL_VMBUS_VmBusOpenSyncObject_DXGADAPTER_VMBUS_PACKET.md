# DXG_HOST_GLOBAL_VMBUS::VmBusOpenSyncObject(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x140196fa0`
- end: `0x140197a6d`
- name: `?VmBusOpenSyncObject@DXG_HOST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `2765`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update`

## callees

- `0x140012540`
- `0x140015b30`
- `0x140015f30`
- `0x14001683c`
- `0x140018054`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001cd10`
- `0x14001cff0`
- `0x14001d1a0`
- `0x14001f2f0`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x14003f638`
- `0x140048a5c`
- `0x1400493a8`
- `0x1400a0bd0`
- `0x140196fa0`
- `0x140197a74`
- `0x14019b5c0`
- `0x14032a5c4`
- `0x140334ce0`
- `0x14036d1f4`
- `0x1403ba56c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019707c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401973df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019756f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140197649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019787f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140197a1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019707c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401973df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019756f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140197649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019787f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140197a1c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401973d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140197873`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140197a10`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401973d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140197873`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140197a10`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140197070`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140197563`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019763d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140197070`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140197563`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019763d`
- `watchdog!WdLogSingleEntry2` at `0x1401972b2`
- `watchdog!WdLogSingleEntry2` at `0x14019743b`
- `watchdog!WdLogSingleEntry2` at `0x14019766c`
- `watchdog!WdLogSingleEntry2` at `0x140197752`
- `watchdog!WdLogSingleEntry2` at `0x1401978ef`
- `watchdog!WdLogSingleEntry2` at `0x1401972b2`
- `watchdog!WdLogSingleEntry2` at `0x14019743b`
- `watchdog!WdLogSingleEntry2` at `0x14019766c`
- `watchdog!WdLogSingleEntry2` at `0x140197752`
- `watchdog!WdLogSingleEntry2` at `0x1401978ef`
- `watchdog!WdLogSingleEntry0` at `0x1401970f6`
- `watchdog!WdLogSingleEntry0` at `0x140197376`
- `watchdog!WdLogSingleEntry0` at `0x1401975ea`
- `watchdog!WdLogSingleEntry0` at `0x140197816`
- `watchdog!WdLogSingleEntry0` at `0x1401979b3`
- `watchdog!WdLogSingleEntry0` at `0x1401970f6`
- `watchdog!WdLogSingleEntry0` at `0x140197376`
- `watchdog!WdLogSingleEntry0` at `0x1401975ea`
- `watchdog!WdLogSingleEntry0` at `0x140197816`
- `watchdog!WdLogSingleEntry0` at `0x1401979b3`
- `watchdog!WdLogSingleEntry1` at `0x140197145`
- `watchdog!WdLogSingleEntry1` at `0x1401971bf`
- `watchdog!WdLogSingleEntry1` at `0x1401971f4`
- `watchdog!WdLogSingleEntry1` at `0x140197145`
- `watchdog!WdLogSingleEntry1` at `0x1401971bf`
- `watchdog!WdLogSingleEntry1` at `0x1401971f4`

## string_xrefs

- `0x140197200`: `Cannot open keyed mutex from a shared resource which doesn't include a keyed mutex: 0x%I64x`
- `0x1401972c3`: `Failed to open sync object (0x%I64x), returning 0x%I64x`
- `0x140197763`: `Failed to open sync object (0x%I64x), returning 0x%I64x`
- `0x140197900`: `Failed to open sync object (0x%I64x), returning 0x%I64x`

## pseudocode

```c

```
