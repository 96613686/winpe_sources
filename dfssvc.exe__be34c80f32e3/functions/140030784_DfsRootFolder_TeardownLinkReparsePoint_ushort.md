# DfsRootFolder::TeardownLinkReparsePoint(ushort *)

- ea: `0x140030784`
- end: `0x140030814`
- name: `?TeardownLinkReparsePoint@DfsRootFolder@@IEAAKPEAG@Z`
- size: `144`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x14002e544`

## callees

- `0x140025060`
- `0x140025d40`
- `0x140030784`
- `0x1400586a8`

## import_xrefs

- `ntdll!NtClose` at `0x1400307f3`
- `ntdll!NtClose` at `0x1400307f3`
- `ntdll!RtlNtStatusToDosError` at `0x140030801`
- `ntdll!RtlNtStatusToDosError` at `0x140030801`

## pseudocode

```c

```
