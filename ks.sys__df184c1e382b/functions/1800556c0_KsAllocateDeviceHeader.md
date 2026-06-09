# KsAllocateDeviceHeader

- ea: `0x1800556c0`
- end: `0x1800558d6`
- name: `KsAllocateDeviceHeader`
- size: `534`
- prototype: `NTSTATUS __stdcall(KSDEVICE_HEADER *Header, ULONG ItemsCount, PKSOBJECT_CREATE_ITEM ItemsList)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180039e30`
- `0x1800542d4`

## callees

- `0x18001a000`
- `0x180048ae8`
- `0x1800556c0`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1800557b8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800557b8`
- `ntoskrnl!KeInitializeSpinLock` at `0x180055876`
- `ntoskrnl!KeInitializeSpinLock` at `0x180055876`
- `ntoskrnl!KeInitializeEvent` at `0x1800557fd`
- `ntoskrnl!KeInitializeEvent` at `0x180055829`
- `ntoskrnl!KeInitializeEvent` at `0x180055863`
- `ntoskrnl!KeInitializeEvent` at `0x1800557fd`
- `ntoskrnl!KeInitializeEvent` at `0x180055829`
- `ntoskrnl!KeInitializeEvent` at `0x180055863`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800558c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800558c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800556e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180055749`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800556e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180055749`

## pseudocode

```c

```
