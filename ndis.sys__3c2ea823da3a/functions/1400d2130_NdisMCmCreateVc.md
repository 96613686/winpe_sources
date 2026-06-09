# NdisMCmCreateVc

- ea: `0x1400d2130`
- end: `0x1400d2667`
- name: `NdisMCmCreateVc`
- size: `1335`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE MiniportAdapterHandle, NDIS_HANDLE NdisAfHandle, NDIS_HANDLE MiniportVcContext, PNDIS_HANDLE NdisVcHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140029620`
- `0x1400d2130`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d21d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d261c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d262d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d21d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d261c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d262d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d219d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d21e4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d219d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d21e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d217b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d21b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d217b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d21b4`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1400d23d2`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1400d23d2`

## pseudocode

```c

```
