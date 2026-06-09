# KerbPurgeKdcProxyCacheWorker(_LUID *,uchar,ulong *)

- ea: `0x18009a414`
- end: `0x18009a5bd`
- name: `?KerbPurgeKdcProxyCacheWorker@@YAJPEAU_LUID@@EPEAK@Z`
- size: `425`
- prototype: `__int64 __fastcall(struct _LUID *, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800a2a50`

## callees

- `0x180009afc`
- `0x18000a630`
- `0x18006bd54`
- `0x18006e748`
- `0x18009a414`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18009a461`
- `ntdll!RtlEnterCriticalSection` at `0x18009a4ab`
- `ntdll!RtlEnterCriticalSection` at `0x18009a4ff`
- `ntdll!RtlEnterCriticalSection` at `0x18009a528`
- `ntdll!RtlEnterCriticalSection` at `0x18009a461`
- `ntdll!RtlEnterCriticalSection` at `0x18009a4ab`
- `ntdll!RtlEnterCriticalSection` at `0x18009a4ff`
- `ntdll!RtlEnterCriticalSection` at `0x18009a528`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a4a2`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a4f2`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a583`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a598`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a4a2`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a4f2`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a583`
- `ntdll!RtlLeaveCriticalSection` at `0x18009a598`

## pseudocode

```c

```
