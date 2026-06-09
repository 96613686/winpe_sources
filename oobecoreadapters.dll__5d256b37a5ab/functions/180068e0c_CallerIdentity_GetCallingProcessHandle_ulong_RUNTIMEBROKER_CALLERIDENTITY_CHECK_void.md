# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180068e0c`
- end: `0x180068ebb`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `175`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180068dec`

## callees

- `0x1800076d4`
- `0x180068dc0`
- `0x180068e0c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068e74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068e74`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180068e3f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180068e3f`

## pseudocode

```c

```
