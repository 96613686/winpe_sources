# ACAttachProcess(_EPROCESS *)

- ea: `0x140012d34`
- end: `0x140012d83`
- name: `?ACAttachProcess@@YAPEAU_EPROCESS@@PEAU1@@Z`
- size: `79`
- prototype: `struct _EPROCESS *__fastcall(PRKPROCESS Process)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140014980`
- `0x140017b90`
- `0x140017ca4`
- `0x140018644`
- `0x140018810`
- `0x140021080`

## callees

- `0x140012d34`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140012d41`
- `ntoskrnl!IoGetCurrentProcess` at `0x140012d41`
- `ntoskrnl!KeDetachProcess` at `0x140012d59`
- `ntoskrnl!KeDetachProcess` at `0x140012d59`
- `ntoskrnl!KeAttachProcess` at `0x140012d68`
- `ntoskrnl!KeAttachProcess` at `0x140012d68`

## pseudocode

```c

```
