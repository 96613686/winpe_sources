# KerbSetPassword(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800b2c30`
- end: `0x1800b3a0e`
- name: `?KerbSetPassword@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `3550`
- prototype: `__int64 __fastcall(void **, char *, unsigned __int64, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, service_task`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x1800093f0`
- `0x180009afc`
- `0x18000a630`
- `0x180016600`
- `0x18001905c`
- `0x180019360`
- `0x18002bd40`
- `0x18002f8b0`
- `0x1800326a0`
- `0x1800670f8`
- `0x180067c48`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800b0688`
- `0x1800b1618`
- `0x1800b2c30`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEraseUnicodeString` at `0x1800b314c`
- `ntdll!RtlEraseUnicodeString` at `0x1800b314c`
- `ntdll!EtwLogTraceEvent` at `0x1800b2d9d`
- `ntdll!EtwLogTraceEvent` at `0x1800b30db`
- `ntdll!EtwLogTraceEvent` at `0x1800b2d9d`
- `ntdll!EtwLogTraceEvent` at `0x1800b30db`
- `ntdll!RtlRunDecodeUnicodeString` at `0x1800b329f`
- `ntdll!RtlRunDecodeUnicodeString` at `0x1800b329f`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3855`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3855`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b389d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b389d`
- `LSASRV!LsaIReferenceCredHandle` at `0x1800b36a0`
- `LSASRV!LsaIReferenceCredHandle` at `0x1800b36a0`
- `LSASRV!LsaIDereferenceCredHandle` at `0x1800b31b7`
- `LSASRV!LsaIDereferenceCredHandle` at `0x1800b31b7`

## string_xrefs

- `0x1800b39b1`: `Failed to call kpasswd service: 0x%x`

## pseudocode

```c

```
