# KsAllocateObjectHeader

- ea: `0x180051490`
- end: `0x18005164b`
- name: `KsAllocateObjectHeader`
- size: `443`
- prototype: `NTSTATUS __stdcall(KSOBJECT_HEADER *Header, ULONG ItemsCount, PKSOBJECT_CREATE_ITEM ItemsList, PIRP Irp, const KSDISPATCH_TABLE *Table)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180033ba0`
- `0x180037200`
- `0x180039bb0`

## callees

- `0x180048ae8`
- `0x180051490`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180051638`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051638`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800514be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051550`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800514be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051550`

## pseudocode

```c

```
