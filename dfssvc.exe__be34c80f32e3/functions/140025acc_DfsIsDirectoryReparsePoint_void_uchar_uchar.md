# DfsIsDirectoryReparsePoint(void *,uchar *,uchar *)

- ea: `0x140025acc`
- end: `0x140025b95`
- name: `?DfsIsDirectoryReparsePoint@@YAJPEAXPEAE1@Z`
- size: `201`
- prototype: `__int64 __fastcall(HANDLE FileHandle, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x140025060`

## callees

- `0x140025acc`
- `0x14005ce70`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x140025b23`
- `ntdll!NtQueryInformationFile` at `0x140025b5f`
- `ntdll!NtQueryInformationFile` at `0x140025b23`
- `ntdll!NtQueryInformationFile` at `0x140025b5f`

## pseudocode

```c

```
