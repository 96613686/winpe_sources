# DfsRootFolder::ExpandLinkDirectories(_UNICODE_STRING *,_UNICODE_STRING *,void *,uchar,ulong *)

- ea: `0x14002a25c`
- end: `0x14002a3ee`
- name: `?ExpandLinkDirectories@DfsRootFolder@@QEAAJPEAU_UNICODE_STRING@@0PEAXEPEAK@Z`
- size: `402`
- prototype: `int(DfsRootFolder *__hidden this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, unsigned __int8, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14002a3f4`
- `0x140031604`

## callees

- `0x14000fd24`
- `0x140025d40`
- `0x14002a25c`
- `0x14002a848`
- `0x1400582e4`

## import_xrefs

- `ntdll!NtClose` at `0x14002a332`
- `ntdll!NtClose` at `0x14002a36b`
- `ntdll!NtClose` at `0x14002a332`
- `ntdll!NtClose` at `0x14002a36b`

## pseudocode

```c

```
