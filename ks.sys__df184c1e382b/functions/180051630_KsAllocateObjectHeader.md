# KsAllocateObjectHeader

- ea: `0x180051630`
- end: `0x1800517eb`
- name: `KsAllocateObjectHeader`
- size: `443`
- prototype: `NTSTATUS __stdcall(KSOBJECT_HEADER *Header, ULONG ItemsCount, PKSOBJECT_CREATE_ITEM ItemsList, PIRP Irp, const KSDISPATCH_TABLE *Table)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180033ba0`
- `0x180037310`
- `0x180039c00`

## callees

- `0x180048ae8`
- `0x180051630`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800517d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800517d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005165e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800516f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005165e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800516f0`

## pseudocode

```c

```
