# DiagnosticsManager::QueryInterfaceDiagnosticsInfo(_GUID,NP_INTERFACE_DIAGNOSTICS_DATA *)

- ea: `0x180007994`
- end: `0x180007d5e`
- name: `?QueryInterfaceDiagnosticsInfo@DiagnosticsManager@@SAJU_GUID@@PEAUNP_INTERFACE_DIAGNOSTICS_DATA@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct NP_INTERFACE_DIAGNOSTICS_DATA *)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1800d9260`
- `0x180112580`

## callees

- `0x180007784`
- `0x180007994`
- `0x180007d64`
- `0x1800097ec`
- `0x18000e190`
- `0x180015628`
- `0x180024770`
- `0x18002cb10`
- `0x18002ceb0`
- `0x18009284c`
- `0x180096a78`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba25`
- `0x180136d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d10`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007abf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007abf`

## string_xrefs

- `0x180007a0e`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c

```
