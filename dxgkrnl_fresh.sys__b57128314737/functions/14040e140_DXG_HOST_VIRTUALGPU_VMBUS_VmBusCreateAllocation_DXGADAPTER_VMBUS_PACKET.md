# DXG_HOST_VIRTUALGPU_VMBUS::VmBusCreateAllocation(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x14040e140`
- end: `0x14040ec3e`
- name: `?VmBusCreateAllocation@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `2814`
- prototype: `char __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140015b30`
- `0x140018054`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001c790`
- `0x14001d1a0`
- `0x14001f2f0`
- `0x14002ef40`
- `0x14003bfbc`
- `0x14003c448`
- `0x140046b74`
- `0x1400493a8`
- `0x14004d064`
- `0x1400532c8`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140284b68`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14037612c`
- `0x140393f58`
- `0x14040e140`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040e7c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040eb1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040e7c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040eb1a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14040eb0e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14040eb0e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14040e7b4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14040e7b4`
- `watchdog!WdLogSingleEntry0` at `0x14040e19b`
- `watchdog!WdLogSingleEntry0` at `0x14040e1c5`
- `watchdog!WdLogSingleEntry0` at `0x14040e21a`
- `watchdog!WdLogSingleEntry0` at `0x14040e24a`
- `watchdog!WdLogSingleEntry0` at `0x14040e276`
- `watchdog!WdLogSingleEntry0` at `0x14040e303`
- `watchdog!WdLogSingleEntry0` at `0x14040e328`
- `watchdog!WdLogSingleEntry0` at `0x14040e379`
- `watchdog!WdLogSingleEntry0` at `0x14040e3f6`
- `watchdog!WdLogSingleEntry0` at `0x14040e4a7`
- `watchdog!WdLogSingleEntry0` at `0x14040e588`
- `watchdog!WdLogSingleEntry0` at `0x14040e5eb`
- `watchdog!WdLogSingleEntry0` at `0x14040e661`
- `watchdog!WdLogSingleEntry0` at `0x14040e74b`
- `watchdog!WdLogSingleEntry0` at `0x14040ebd2`
- `watchdog!WdLogSingleEntry0` at `0x14040e19b`
- `watchdog!WdLogSingleEntry0` at `0x14040e1c5`
- `watchdog!WdLogSingleEntry0` at `0x14040e21a`
- `watchdog!WdLogSingleEntry0` at `0x14040e24a`
- `watchdog!WdLogSingleEntry0` at `0x14040e276`
- `watchdog!WdLogSingleEntry0` at `0x14040e303`
- `watchdog!WdLogSingleEntry0` at `0x14040e328`
- `watchdog!WdLogSingleEntry0` at `0x14040e379`
- `watchdog!WdLogSingleEntry0` at `0x14040e3f6`
- `watchdog!WdLogSingleEntry0` at `0x14040e4a7`
- `watchdog!WdLogSingleEntry0` at `0x14040e588`
- `watchdog!WdLogSingleEntry0` at `0x14040e5eb`
- `watchdog!WdLogSingleEntry0` at `0x14040e661`
- `watchdog!WdLogSingleEntry0` at `0x14040e74b`
- `watchdog!WdLogSingleEntry0` at `0x14040ebd2`
- `watchdog!WdLogSingleEntry1` at `0x14040ea48`
- `watchdog!WdLogSingleEntry1` at `0x14040eb67`
- `watchdog!WdLogSingleEntry1` at `0x14040ea48`
- `watchdog!WdLogSingleEntry1` at `0x14040eb67`

## string_xrefs

- `0x14040e1d6`: `OpenCrossAdapter is not supported`
- `0x14040eb78`: `Failed to create allocation: 0x%I64x`
- `0x14040ea65`: `Failed to make staging allocation resident. Returning 0x%I64x`

## pseudocode

```c

```
