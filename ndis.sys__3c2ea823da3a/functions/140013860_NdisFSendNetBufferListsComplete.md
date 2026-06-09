# NdisFSendNetBufferListsComplete

- ea: `0x140013860`
- end: `0x140013e94`
- name: `NdisFSendNetBufferListsComplete`
- size: `1588`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNET_BUFFER_LIST NetBufferList, ULONG SendCompleteFlags)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14002df40`
- `0x140096810`
- `0x14009f9a0`

## callees

- `0x14000a5a0`
- `0x14000de20`
- `0x140013860`
- `0x140013ea0`
- `0x140014250`
- `0x140030450`
- `0x14009f8e4`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140013983`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400139c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013983`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400139c6`
- `ntoskrnl!MmBadPointer` at `0x1400e79fe`
- `ntoskrnl!IoGetStackLimits` at `0x140013c5f`
- `ntoskrnl!IoGetStackLimits` at `0x140013c5f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140013d15`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140013d15`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d90`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d3d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d3d`

## pseudocode

```c

```
