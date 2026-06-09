# LsaDbpCacheBinding(_UNICODE_STRING *,void * *,ushort * *,ushort * *,void * *,_LSAP_BINDING_CACHE_ENTRY * *)

- ea: `0x1800164a8`
- end: `0x1800165e9`
- name: `?LsaDbpCacheBinding@@YAJPEAU_UNICODE_STRING@@PEAPEAXPEAPEAG21PEAPEAU_LSAP_BINDING_CACHE_ENTRY@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, union _LARGE_INTEGER *, union _LARGE_INTEGER *, union _LARGE_INTEGER *, void **, union _LARGE_INTEGER **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001aa00`

## callees

- `0x180001fb8`
- `0x1800164a8`
- `0x1800165f0`
- `0x18001663c`
- `0x1800166a4`

## import_xrefs

- `LSASRV!LsapDuplicateString` at `0x180016516`
- `LSASRV!LsapDuplicateString` at `0x180016516`
- `LSASRV!LsapAllocateLsaHeap` at `0x1800164d9`
- `LSASRV!LsapAllocateLsaHeap` at `0x1800164d9`
- `ntdll!NtQuerySystemTime` at `0x180016509`
- `ntdll!NtQuerySystemTime` at `0x180016509`
- `ntdll!RtlLeaveCriticalSection` at `0x1800165c3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800165c3`
- `ntdll!RtlEnterCriticalSection` at `0x180016589`
- `ntdll!RtlEnterCriticalSection` at `0x180016589`

## pseudocode

```c

```
