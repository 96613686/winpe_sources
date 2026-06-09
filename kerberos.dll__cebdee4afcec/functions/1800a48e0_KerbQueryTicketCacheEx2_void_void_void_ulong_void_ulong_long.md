# KerbQueryTicketCacheEx2(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a48e0`
- end: `0x1800a4c5e`
- name: `?KerbQueryTicketCacheEx2@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `894`
- prototype: `__int64 __fastcall(void **, char *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180007e80`
- `0x180009afc`
- `0x18000a630`
- `0x18006cd70`
- `0x18006d240`
- `0x180070680`
- `0x1800a1350`
- `0x1800a20e0`
- `0x1800a48e0`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800a4bd9`
- `ntdll!RtlReleaseResource` at `0x1800a4bd9`
- `ntdll!RtlAcquireResourceShared` at `0x1800a49e3`
- `ntdll!RtlAcquireResourceShared` at `0x1800a49e3`
- `ntdll!RtlEnterCriticalSection` at `0x1800a49ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800a49d4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a49ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800a49d4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4be3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4bed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4be3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4bed`

## pseudocode

```c

```
