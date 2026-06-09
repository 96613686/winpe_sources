# KsAllocateDeviceHeader

- ea: `0x180055520`
- end: `0x180055736`
- name: `KsAllocateDeviceHeader`
- size: `534`
- prototype: `NTSTATUS __stdcall(KSDEVICE_HEADER *Header, ULONG ItemsCount, PKSOBJECT_CREATE_ITEM ItemsList)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180039de0`
- `0x180054134`

## callees

- `0x180019fc0`
- `0x180048ae8`
- `0x180055520`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x180055618`
- `ntoskrnl!ExInitializeResourceLite` at `0x180055618`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800556d6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800556d6`
- `ntoskrnl!KeInitializeEvent` at `0x18005565d`
- `ntoskrnl!KeInitializeEvent` at `0x180055689`
- `ntoskrnl!KeInitializeEvent` at `0x1800556c3`
- `ntoskrnl!KeInitializeEvent` at `0x18005565d`
- `ntoskrnl!KeInitializeEvent` at `0x180055689`
- `ntoskrnl!KeInitializeEvent` at `0x1800556c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180055725`
- `ntoskrnl!ExFreePoolWithTag` at `0x180055725`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180055545`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800555a9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180055545`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800555a9`

## pseudocode

```c

```
