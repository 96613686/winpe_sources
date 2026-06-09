# NdisFSendNetBufferListsComplete

- ea: `0x14003b2c0`
- end: `0x14003bc3f`
- name: `NdisFSendNetBufferListsComplete`
- size: `2431`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNET_BUFFER_LIST NetBufferList, ULONG SendCompleteFlags)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140035540`
- `0x14009ba90`
- `0x1400a4de0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x140032cb0`
- `0x14003a3b0`
- `0x14003b2c0`
- `0x14003bc50`
- `0x1400a4d24`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003b5d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b623`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b659`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b68f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b5d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b623`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b659`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b68f`
- `ntoskrnl!MmBadPointer` at `0x1400ef2a8`
- `ntoskrnl!IoGetStackLimits` at `0x14003b9df`
- `ntoskrnl!IoGetStackLimits` at `0x14003b9df`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003ba94`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003ba94`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bb0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bb0f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003babc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003babc`

## pseudocode

```c

```
