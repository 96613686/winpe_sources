# DfsRemoveReparseIfOrphaned(void *,_UNICODE_STRING *,__int64,_LIST_ENTRY *)

- ea: `0x14002634c`
- end: `0x140026544`
- name: `?DfsRemoveReparseIfOrphaned@@YAKPEAXPEAU_UNICODE_STRING@@_JPEAU_LIST_ENTRY@@@Z`
- size: `504`
- prototype: `unsigned int(void *, struct _UNICODE_STRING *, __int64, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x140026018`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140025210`
- `0x140025b9c`
- `0x140025e5c`
- `0x14002634c`
- `0x14002654c`
- `0x140026610`
- `0x14005ce3a`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1400263d3`
- `ntdll!NtQueryInformationFile` at `0x1400263d3`
- `ntdll!RtlNtStatusToDosError` at `0x14002640a`
- `ntdll!RtlNtStatusToDosError` at `0x14002640a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002642e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002650e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002642e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002650e`

## pseudocode

```c

```
