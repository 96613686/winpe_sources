# WcpPrivilegedRemoveFile

- ea: `0x180036030`
- end: `0x1800361a9`
- name: `WcpPrivilegedRemoveFile`
- size: `377`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800361b0`

## callees

- `0x180034b38`
- `0x180036030`
- `0x180036ee8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800360ef`
- `ntdll!NtOpenFile` at `0x1800360ef`
- `ntdll!NtSetInformationFile` at `0x180036138`
- `ntdll!NtSetInformationFile` at `0x180036138`
- `ntdll!NtClose` at `0x180036172`
- `ntdll!NtClose` at `0x180036172`
- `ntdll!RtlNtStatusToDosError` at `0x18003614e`
- `ntdll!RtlNtStatusToDosError` at `0x18003614e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036071`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036071`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036089`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003618d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003618d`

## pseudocode

```c

```
