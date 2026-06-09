# CUtils::CreateSystemSid(void * *)

- ea: `0x180047dcc`
- end: `0x180047e04`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18002d804`
- `0x180088ea4`

## callees

- `0x18002f1f0`
- `0x180047dcc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180047ddb`
- `ntdll!RtlNtStatusToDosError` at `0x180047ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047de9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047de3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047de3`

## pseudocode

```c

```
