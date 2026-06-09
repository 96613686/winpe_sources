# CUtils::CreateAdminSid(void * *)

- ea: `0x180082efc`
- end: `0x180082f47`
- name: `?CreateAdminSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f7c0`
- `0x180087ae0`
- `0x18008db9c`

## callees

- `0x180082efc`
- `0x180099090`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180082f0b`
- `ntdll!RtlNtStatusToDosError` at `0x180082f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180082f19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180082f19`

## pseudocode

```c

```
