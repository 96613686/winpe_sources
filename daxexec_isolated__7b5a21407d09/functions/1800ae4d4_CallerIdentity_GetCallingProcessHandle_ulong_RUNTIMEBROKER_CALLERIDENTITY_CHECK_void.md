# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800ae4d4`
- end: `0x1800ae63d`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c430`
- `0x1800aeb4c`

## callees

- `0x18000ff24`
- `0x1800ae4d4`
- `0x1800aea50`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ae57f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ae57f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ae563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ae563`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae596`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800ae503`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800ae503`

## pseudocode

```c

```
