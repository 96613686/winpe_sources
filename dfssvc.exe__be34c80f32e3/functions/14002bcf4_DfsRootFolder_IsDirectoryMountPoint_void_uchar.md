# DfsRootFolder::IsDirectoryMountPoint(void *,uchar *)

- ea: `0x14002bcf4`
- end: `0x14002bdbf`
- name: `?IsDirectoryMountPoint@DfsRootFolder@@QEAAJPEAXPEAE@Z`
- size: `203`
- prototype: `int(DfsRootFolder *__hidden this, void *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400291d0`

## callees

- `0x14002bcf4`
- `0x14005ce70`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x14002bd4a`
- `ntdll!NtQueryInformationFile` at `0x14002bd83`
- `ntdll!NtQueryInformationFile` at `0x14002bd4a`
- `ntdll!NtQueryInformationFile` at `0x14002bd83`

## pseudocode

```c

```
