# KerbBuildQueryKdcProxyCacheResponse(_LUID *,_KERB_QUERY_KDC_PROXY_CACHE_RESPONSE *)

- ea: `0x180096e28`
- end: `0x1800971ba`
- name: `?KerbBuildQueryKdcProxyCacheResponse@@YAJPEAU_LUID@@PEAU_KERB_QUERY_KDC_PROXY_CACHE_RESPONSE@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(struct _LUID *, struct _KERB_QUERY_KDC_PROXY_CACHE_RESPONSE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800a3a50`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x180009afc`
- `0x18000a630`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800968b0`
- `0x180096e28`
- `0x180098084`
- `0x1800980d8`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180096e85`
- `ntdll!RtlEnterCriticalSection` at `0x180096ed9`
- `ntdll!RtlEnterCriticalSection` at `0x180097000`
- `ntdll!RtlEnterCriticalSection` at `0x180097047`
- `ntdll!RtlEnterCriticalSection` at `0x180096e85`
- `ntdll!RtlEnterCriticalSection` at `0x180096ed9`
- `ntdll!RtlEnterCriticalSection` at `0x180097000`
- `ntdll!RtlEnterCriticalSection` at `0x180097047`
- `ntdll!RtlLeaveCriticalSection` at `0x180096eb6`
- `ntdll!RtlLeaveCriticalSection` at `0x180096f0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180097088`
- `ntdll!RtlLeaveCriticalSection` at `0x180097186`
- `ntdll!RtlLeaveCriticalSection` at `0x180096eb6`
- `ntdll!RtlLeaveCriticalSection` at `0x180096f0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180097088`
- `ntdll!RtlLeaveCriticalSection` at `0x180097186`

## string_xrefs

- `0x180096f16`: `KerbBuildKdcProxyCacheEntryDataArray failed: %#x\n`
- `0x18009715d`: `KerbBuildKdcProxyCacheEntryDataArray failed: %#x\n`
- `0x180096f27`: `KerbBuildQueryKdcProxyCacheResponse`
- `0x18009716e`: `KerbBuildQueryKdcProxyCacheResponse`

## pseudocode

```c

```
