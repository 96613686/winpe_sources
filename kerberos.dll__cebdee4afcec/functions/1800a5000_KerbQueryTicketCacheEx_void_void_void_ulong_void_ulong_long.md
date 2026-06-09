# KerbQueryTicketCacheEx(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a5000`
- end: `0x1800a537e`
- name: `?KerbQueryTicketCacheEx@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `894`
- prototype: `__int64 __fastcall(void **, char *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180007e80`
- `0x180009afc`
- `0x18000a630`
- `0x180067f34`
- `0x18006c288`
- `0x18006cd70`
- `0x18006d240`
- `0x180070680`
- `0x1800a5000`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800a52f9`
- `ntdll!RtlReleaseResource` at `0x1800a52f9`
- `ntdll!RtlAcquireResourceShared` at `0x1800a5103`
- `ntdll!RtlAcquireResourceShared` at `0x1800a5103`
- `ntdll!RtlEnterCriticalSection` at `0x1800a50ea`
- `ntdll!RtlEnterCriticalSection` at `0x1800a50f4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a50ea`
- `ntdll!RtlEnterCriticalSection` at `0x1800a50f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a5303`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a530d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a5303`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a530d`

## pseudocode

```c

```
