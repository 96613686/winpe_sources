# DXG_HOST_VIRTUALGPU_VMBUS::VmBusCreateDevice(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x140283450`
- end: `0x140283945`
- name: `?VmBusCreateDevice@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1269`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x14000d7d0`
- `0x140015780`
- `0x14001ab20`
- `0x14001b890`
- `0x14001e338`
- `0x14001f460`
- `0x14002e110`
- `0x14002ec90`
- `0x14003f3d8`
- `0x1400491a8`
- `0x140060300`
- `0x1400a0100`
- `0x1400a0540`
- `0x140283450`
- `0x1403535f0`
- `0x1403c8540`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402835db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140283609`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402835db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140283609`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402835ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402835f8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402835ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402835f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283663`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283684`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283746`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283767`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283663`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283684`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283746`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140283767`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140283657`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140283678`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028373a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028375b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140283657`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140283678`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028373a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028375b`
- `watchdog!WdLogSingleEntry0` at `0x1402834a9`
- `watchdog!WdLogSingleEntry0` at `0x140283578`
- `watchdog!WdLogSingleEntry0` at `0x1402837d7`
- `watchdog!WdLogSingleEntry0` at `0x1402838c5`
- `watchdog!WdLogSingleEntry0` at `0x1402834a9`
- `watchdog!WdLogSingleEntry0` at `0x140283578`
- `watchdog!WdLogSingleEntry0` at `0x1402837d7`
- `watchdog!WdLogSingleEntry0` at `0x1402838c5`
- `watchdog!WdLogSingleEntry1` at `0x140283783`
- `watchdog!WdLogSingleEntry1` at `0x14028386e`
- `watchdog!WdLogSingleEntry1` at `0x140283783`
- `watchdog!WdLogSingleEntry1` at `0x14028386e`

## string_xrefs

- `0x1402834ba`: `The adapter is already closed by the guest`
- `0x140283794`: `Failed to create CDD device: 0x%I64x`
- `0x140283589`: `CDD device must be created in CSRSS process context`
- `0x14028387f`: `Failed to create device: 0x%I64x`
- `0x1402837e8`: `CSRSS process context can only create CDD devices`

## pseudocode

```c

```
