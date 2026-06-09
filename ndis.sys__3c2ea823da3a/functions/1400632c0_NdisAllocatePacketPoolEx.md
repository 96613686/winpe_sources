# NdisAllocatePacketPoolEx

- ea: `0x1400632c0`
- end: `0x1400635d9`
- name: `NdisAllocatePacketPoolEx`
- size: `793`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_HANDLE PoolHandle, UINT NumberOfDescriptors, UINT NumberOfOverflowDescriptors, UINT ProtocolReservedLength)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140063250`
- `0x1400c55f0`
- `0x14018b240`

## callees

- `0x140007d80`
- `0x1400082b0`
- `0x140029620`
- `0x140056c50`
- `0x1400632c0`
- `0x1400635e0`

## import_xrefs

- `ntoskrnl!RtlGetCallersAddress` at `0x1400632fe`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400632fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063579`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063579`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006341c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006341c`
- `ntoskrnl!ExAllocatePool2` at `0x1400633df`
- `ntoskrnl!ExAllocatePool2` at `0x1400633df`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400634b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063568`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400634b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063568`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063469`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063531`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063469`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063531`

## pseudocode

```c

```
