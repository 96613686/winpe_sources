# CUtils::CreateRdsMsSid(void * *)

- ea: `0x18008300c`
- end: `0x180083057`
- name: `?CreateRdsMsSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f7c0`

## callees

- `0x18008300c`
- `0x1800991c4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18008301b`
- `ntdll!RtlNtStatusToDosError` at `0x18008301b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180083029`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180083029`

## pseudocode

```c

```
