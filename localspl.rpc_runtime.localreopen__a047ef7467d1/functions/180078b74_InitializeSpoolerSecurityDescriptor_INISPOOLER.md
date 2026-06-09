# InitializeSpoolerSecurityDescriptor(_INISPOOLER *)

- ea: `0x180078b74`
- end: `0x180078ccc`
- name: `?InitializeSpoolerSecurityDescriptor@@YAHPEAU_INISPOOLER@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075f58`

## callees

- `0x1800170a0`
- `0x180035ae4`
- `0x18003ea2c`
- `0x180078b74`
- `0x180098628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078c90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078cb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078cb4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180078c5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180078c5a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180078c20`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180078c20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078c67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078bd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078bd3`

## string_xrefs

- `0x180078ca6`: `InitializeSpoolerSecurityDescriptor`
- `0x180078ba8`: `ServerSecurityDescriptor`
- `0x180078c04`: `ServerSecurityDescriptor`
- `0x180078c53`: `ServerSecurityDescriptor`

## pseudocode

```c

```
