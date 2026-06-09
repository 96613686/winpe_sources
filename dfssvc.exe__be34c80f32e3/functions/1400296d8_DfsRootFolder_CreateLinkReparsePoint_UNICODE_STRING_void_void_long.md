# DfsRootFolder::CreateLinkReparsePoint(_UNICODE_STRING *,void *,void *,long *)

- ea: `0x1400296d8`
- end: `0x1400298d7`
- name: `?CreateLinkReparsePoint@DfsRootFolder@@AEAAKPEAU_UNICODE_STRING@@PEAX1PEAJ@Z`
- size: `511`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, struct _UNICODE_STRING *, void *, void *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x14002ffe0`

## callees

- `0x14000fd24`
- `0x1400291d0`
- `0x1400296d8`
- `0x140029a18`
- `0x14002bc30`
- `0x14002ec0c`
- `0x1400303c8`
- `0x140058008`
- `0x1400586a8`

## import_xrefs

- `ntdll!NtClose` at `0x1400297ec`
- `ntdll!NtClose` at `0x1400297ec`
- `ntdll!NtFsControlFile` at `0x1400297bc`
- `ntdll!NtFsControlFile` at `0x1400297bc`
- `ntdll!RtlNtStatusToDosError` at `0x140029843`
- `ntdll!RtlNtStatusToDosError` at `0x140029843`

## pseudocode

```c

```
