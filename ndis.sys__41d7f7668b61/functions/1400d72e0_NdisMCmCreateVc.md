# NdisMCmCreateVc

- ea: `0x1400d72e0`
- end: `0x1400d7817`
- name: `NdisMCmCreateVc`
- size: `1335`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE MiniportAdapterHandle, NDIS_HANDLE NdisAfHandle, NDIS_HANDLE MiniportVcContext, PNDIS_HANDLE NdisVcHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14002ab60`
- `0x1400d72e0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d7382`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d77cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d77dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d7382`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d77cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d77dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d734d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d7394`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d734d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d7394`
- `ntoskrnl!ExAllocatePool2` at `0x1400d732b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d7364`
- `ntoskrnl!ExAllocatePool2` at `0x1400d732b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d7364`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1400d7582`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1400d7582`

## pseudocode

```c

```
