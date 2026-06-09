# CUtils::CreateAdminSid(void * *)

- ea: `0x18007e504`
- end: `0x18007e53c`
- name: `?CreateAdminSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002d804`
- `0x180082e50`
- `0x180088ea4`

## callees

- `0x18007e504`
- `0x180093b84`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18007e513`
- `ntdll!RtlNtStatusToDosError` at `0x18007e513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e521`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e51b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e51b`

## pseudocode

```c

```
