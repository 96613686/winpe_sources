# DfsDeleteLinkReparsePoint(_UNICODE_STRING *,void *,uchar)

- ea: `0x140025060`
- end: `0x140025208`
- name: `?DfsDeleteLinkReparsePoint@@YAJPEAU_UNICODE_STRING@@PEAXE@Z`
- size: `424`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x140025210`
- `0x140030784`

## callees

- `0x14000fd24`
- `0x140024f4c`
- `0x140025060`
- `0x140025acc`
- `0x140025d40`

## import_xrefs

- `ntdll!NtClose` at `0x14002518c`
- `ntdll!NtClose` at `0x14002518c`
- `ntdll!NtFsControlFile` at `0x14002513e`
- `ntdll!NtFsControlFile` at `0x14002513e`

## pseudocode

```c

```
