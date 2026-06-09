# KerbDiscoverKdcProxyCacheEntry(_UNICODE_STRING *,_KERB_LOGON_SESSION * *,_KERB_PRIMARY_CREDENTIAL * *,_KDC_PROXY_CACHE_ENTRY * *)

- ea: `0x18000951c`
- end: `0x18000973d`
- name: `?KerbDiscoverKdcProxyCacheEntry@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_LOGON_SESSION@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@PEAPEAU_KDC_PROXY_CACHE_ENTRY@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, struct _KERB_LOGON_SESSION **, struct _KERB_PRIMARY_CREDENTIAL **, struct _KDC_PROXY_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180099d4c`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18000951c`
- `0x180009afc`
- `0x18000a630`
- `0x18000a650`
- `0x18000aa74`
- `0x18007108c`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180009679`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180009679`
- `ntdll!RtlReleaseResource` at `0x18000968b`
- `ntdll!RtlReleaseResource` at `0x18000968b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009654`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009654`
- `ntdll!RtlEnterCriticalSection` at `0x18000956d`
- `ntdll!RtlEnterCriticalSection` at `0x1800095a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800096b2`
- `ntdll!RtlEnterCriticalSection` at `0x18000956d`
- `ntdll!RtlEnterCriticalSection` at `0x1800095a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800096b2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800095c8`
- `ntdll!RtlLeaveCriticalSection` at `0x180009605`
- `ntdll!RtlLeaveCriticalSection` at `0x1800096d3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800095c8`
- `ntdll!RtlLeaveCriticalSection` at `0x180009605`
- `ntdll!RtlLeaveCriticalSection` at `0x1800096d3`

## pseudocode

```c

```
