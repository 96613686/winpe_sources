# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18007f490`
- end: `0x18007f53f`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `175`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007f470`

## callees

- `0x1800127c0`
- `0x1800154cc`
- `0x18007f490`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f4f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f4f8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18007f4c3`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18007f4c3`

## pseudocode

```c

```
