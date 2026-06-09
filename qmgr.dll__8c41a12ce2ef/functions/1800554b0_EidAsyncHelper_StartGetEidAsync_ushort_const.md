# EidAsyncHelper::StartGetEidAsync(ushort const *)

- ea: `0x1800554b0`
- end: `0x180055793`
- name: `?StartGetEidAsync@EidAsyncHelper@@QEAA_NPEBG@Z`
- size: `739`
- prototype: `bool __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWSTR wszServerName)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b40`
- `0x1800548e4`
- `0x180054dd0`

## callees

- `0x18000db20`
- `0x180033480`
- `0x1800554b0`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800b1160`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180055692`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180055692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055511`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055511`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055558`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005571a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005571a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800556c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800556c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005559c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005559c`
- `FirewallAPI!NetworkIsolationGetEnterpriseIdAsync` at `0x18005560e`
- `FirewallAPI!NetworkIsolationGetEnterpriseIdAsync` at `0x18005560e`

## pseudocode

```c

```
