# CiSetCatalogHintByFilePath

- ea: `0x1800448b8`
- end: `0x180044a35`
- name: `CiSetCatalogHintByFilePath`
- size: `381`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800444cc`
- `0x18021c2b4`

## callees

- `0x1800448b8`
- `0x1801f14d4`

## import_xrefs

- `ntdll!NtClose` at `0x1800449db`
- `ntdll!NtClose` at `0x1800449db`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180044908`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180044908`
- `ntdll!RtlReleaseRelativeName` at `0x180044a0e`
- `ntdll!RtlReleaseRelativeName` at `0x180044a0e`
- `ntdll!RtlFreeHeap` at `0x1800449fe`
- `ntdll!RtlFreeHeap` at `0x1800449fe`
- `ntdll!NtCreateFile` at `0x1800449b2`
- `ntdll!NtCreateFile` at `0x1800449b2`

## pseudocode

```c

```
