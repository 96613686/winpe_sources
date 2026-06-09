# CUtils::CreateSystemSid(void * *)

- ea: `0x18004af10`
- end: `0x18004af5b`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18002f7c0`
- `0x18008db9c`

## callees

- `0x180031378`
- `0x18004af10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004af1f`
- `ntdll!RtlNtStatusToDosError` at `0x18004af1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af2d`

## pseudocode

```c

```
