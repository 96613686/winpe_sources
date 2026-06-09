# DXG_HOST_VIRTUALGPU_VMBUS::VmBusCreateDevice(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x14028a060`
- end: `0x14028a555`
- name: `?VmBusCreateDevice@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1269`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x14000d990`
- `0x140015940`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001e508`
- `0x14001f630`
- `0x14002e2e0`
- `0x14002ee60`
- `0x14003f638`
- `0x1400493a8`
- `0x1400606b0`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14028a060`
- `0x140353aa0`
- `0x1403c78f0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14028a1eb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14028a219`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14028a1eb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14028a219`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14028a1da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14028a208`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14028a1da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14028a208`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a273`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a294`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a356`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a377`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a273`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a294`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a356`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028a377`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a267`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a288`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a34a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a36b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a267`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a288`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a34a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028a36b`
- `watchdog!WdLogSingleEntry0` at `0x14028a0b9`
- `watchdog!WdLogSingleEntry0` at `0x14028a188`
- `watchdog!WdLogSingleEntry0` at `0x14028a3e7`
- `watchdog!WdLogSingleEntry0` at `0x14028a4d5`
- `watchdog!WdLogSingleEntry0` at `0x14028a0b9`
- `watchdog!WdLogSingleEntry0` at `0x14028a188`
- `watchdog!WdLogSingleEntry0` at `0x14028a3e7`
- `watchdog!WdLogSingleEntry0` at `0x14028a4d5`
- `watchdog!WdLogSingleEntry1` at `0x14028a393`
- `watchdog!WdLogSingleEntry1` at `0x14028a47e`
- `watchdog!WdLogSingleEntry1` at `0x14028a393`
- `watchdog!WdLogSingleEntry1` at `0x14028a47e`

## string_xrefs

- `0x14028a0ca`: `The adapter is already closed by the guest`
- `0x14028a3a4`: `Failed to create CDD device: 0x%I64x`
- `0x14028a199`: `CDD device must be created in CSRSS process context`
- `0x14028a48f`: `Failed to create device: 0x%I64x`
- `0x14028a3f8`: `CSRSS process context can only create CDD devices`

## pseudocode

```c

```
