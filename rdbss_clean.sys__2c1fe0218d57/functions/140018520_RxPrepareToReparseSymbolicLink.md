# RxPrepareToReparseSymbolicLink

- ea: `0x140018520`
- end: `0x1400186b2`
- name: `RxPrepareToReparseSymbolicLink`
- size: `402`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, BOOLEAN SymbolicLinkEmbeddedInOldPath, PUNICODE_STRING NewPath, BOOLEAN NewPathIsAbsolute, PBOOLEAN ReparseRequired)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x140016e20`
- `0x140017310`
- `0x140018520`
- `0x140025d80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400185eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400185eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001863e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001863e`

## pseudocode

```c

```
