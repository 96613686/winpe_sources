# SID_CACHE::Remove(ushort const *)

- ea: `0x1800bb9cc`
- end: `0x1800bba59`
- name: `?Remove@SID_CACHE@@QEAAJPEBG@Z`
- size: `141`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180095b24`

## callees

- `0x180022870`
- `0x1800bb9cc`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800bba07`
- `ntdll!_wcsicmp` at `0x1800bba07`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bba46`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bba46`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb9ea`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb9ea`

## pseudocode

```c

```
