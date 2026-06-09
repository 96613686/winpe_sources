# CngAdtEnableAuditPrivilege(_LUID)

- ea: `0x1800b4210`
- end: `0x1800b4320`
- name: `?CngAdtEnableAuditPrivilege@@YAJU_LUID@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(LUID)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075dd8`

## callees

- `0x1800b4210`
- `0x1800b86d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b426e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b427e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b428e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b426e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b427e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b428e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4252`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4239`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b42fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b42fe`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b42de`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800b42de`

## pseudocode

```c

```
