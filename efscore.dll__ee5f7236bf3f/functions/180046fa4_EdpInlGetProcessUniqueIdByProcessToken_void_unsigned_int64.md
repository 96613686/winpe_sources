# EdpInlGetProcessUniqueIdByProcessToken(void *,unsigned __int64 *)

- ea: `0x180046fa4`
- end: `0x1800470e7`
- name: `?EdpInlGetProcessUniqueIdByProcessToken@@YAJPEAXPEA_K@Z`
- size: `323`
- prototype: `__int64 __fastcall(void *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800471cc`
- `0x18008deb4`
- `0x1800977b0`

## callees

- `0x180046fa4`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800470b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800470b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047045`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047045`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180047025`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180047025`
- `ntdll!RtlNtStatusToDosError` at `0x180047076`
- `ntdll!RtlNtStatusToDosError` at `0x180047076`

## pseudocode

```c

```
