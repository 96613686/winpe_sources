# NdisAllocatePacketPoolEx

- ea: `0x140068690`
- end: `0x1400689a9`
- name: `NdisAllocatePacketPoolEx`
- size: `793`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_HANDLE PoolHandle, UINT NumberOfDescriptors, UINT NumberOfOverflowDescriptors, UINT ProtocolReservedLength)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140068620`
- `0x1400ca7a0`
- `0x140191240`

## callees

- `0x140029eb0`
- `0x14002a5b0`
- `0x14002ab60`
- `0x14005b490`
- `0x140068690`
- `0x1400689b0`

## import_xrefs

- `ntoskrnl!RtlGetCallersAddress` at `0x1400686ce`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400686ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068949`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400687ec`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400687ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400687af`
- `ntoskrnl!ExAllocatePool2` at `0x1400687af`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068880`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068938`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068880`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068938`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068839`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068901`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068839`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068901`

## pseudocode

```c

```
