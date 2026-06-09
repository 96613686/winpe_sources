# SID_CACHE::Query(ushort const *,void * *)

- ea: `0x180030754`
- end: `0x18003084a`
- name: `?Query@SID_CACHE@@QEAAJPEBGPEAPEAX@Z`
- size: `246`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002e0f0`
- `0x1800306c8`

## callees

- `0x180022870`
- `0x18002f460`
- `0x180030754`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180030787`
- `ntdll!NtQuerySystemTime` at `0x180030787`
- `ntdll!_wcsicmp` at `0x1800307bd`
- `ntdll!_wcsicmp` at `0x1800307bd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800307f9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800307f9`
- `ntdll!RtlEnterCriticalSection` at `0x18003079c`
- `ntdll!RtlEnterCriticalSection` at `0x18003079c`

## pseudocode

```c

```
