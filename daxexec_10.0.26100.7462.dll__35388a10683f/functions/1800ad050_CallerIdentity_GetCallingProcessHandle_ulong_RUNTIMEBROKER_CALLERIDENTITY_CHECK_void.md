# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800ad050`
- end: `0x1800ad1a4`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `340`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a844`
- `0x1800ad688`

## callees

- `0x18000e234`
- `0x1800ad050`
- `0x1800ad58c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad0d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad0d6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ad0f2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ad0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad109`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800ad079`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800ad079`

## pseudocode

```c

```
