# NdisMSendNetBufferListsComplete

- ea: `0x140013010`
- end: `0x14001382a`
- name: `NdisMSendNetBufferListsComplete`
- size: `2074`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, PNET_BUFFER_LIST NetBufferList, ULONG SendCompleteFlags)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14005f400`

## callees

- `0x14000a5a0`
- `0x14000de20`
- `0x140013010`
- `0x140013830`
- `0x140013ea0`
- `0x140014280`
- `0x1400143b0`
- `0x140030450`
- `0x1400837ac`
- `0x14009f8e4`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400136a8`
- `ntoskrnl!KfRaiseIrql` at `0x1400136a8`
- `ntoskrnl!KeLowerIrql` at `0x1400135ad`
- `ntoskrnl!KeLowerIrql` at `0x1400135ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013163`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013163`
- `ntoskrnl!MmBadPointer` at `0x1400e797e`
- `ntoskrnl!IoGetStackLimits` at `0x1400134e8`
- `ntoskrnl!IoGetStackLimits` at `0x1400134e8`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140013616`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140013616`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013691`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013691`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001308a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001363e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001308a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001363e`

## pseudocode

```c

```
