# DfsRootFolder::SetupLinkReparsePoint(ushort const *,void *,long *)

- ea: `0x14002ffe0`
- end: `0x140030218`
- name: `?SetupLinkReparsePoint@DfsRootFolder@@IEAAKPEBGPEAXPEAJ@Z`
- size: `568`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, const unsigned __int16 *, void *, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x1400293c4`
- `0x140030e44`
- `0x140031108`

## callees

- `0x140005a94`
- `0x140005b28`
- `0x1400096ac`
- `0x140025d40`
- `0x1400296d8`
- `0x14002ffe0`
- `0x1400586a8`

## import_xrefs

- `ntdll!NtClose` at `0x140030123`
- `ntdll!NtClose` at `0x140030123`
- `ntdll!RtlNtStatusToDosError` at `0x140030176`
- `ntdll!RtlNtStatusToDosError` at `0x140030176`

## pseudocode

```c

```
