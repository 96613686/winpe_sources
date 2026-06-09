# KerbQueryS4U2ProxyCache(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a3ba0`
- end: `0x1800a3ec3`
- name: `?KerbQueryS4U2ProxyCache@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `803`
- prototype: `__int64 __fastcall(void **, _DWORD *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180007e80`
- `0x180009afc`
- `0x18000a630`
- `0x180070680`
- `0x18009d38c`
- `0x18009df14`
- `0x1800a3ba0`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800a3d9d`
- `ntdll!RtlReleaseResource` at `0x1800a3e6a`
- `ntdll!RtlReleaseResource` at `0x1800a3d9d`
- `ntdll!RtlReleaseResource` at `0x1800a3e6a`
- `ntdll!RtlAcquireResourceShared` at `0x1800a3cd8`
- `ntdll!RtlAcquireResourceShared` at `0x1800a3cd8`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3cbc`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3cc9`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3cbc`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3cc9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3daa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3db3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e77`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e80`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3daa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3db3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e77`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e80`

## pseudocode

```c

```
