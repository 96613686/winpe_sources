# DfsADBlobCache::GetObjectDN(_UNICODE_STRING *)

- ea: `0x140008580`
- end: `0x140008608`
- name: `?GetObjectDN@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@@Z`
- size: `136`
- prototype: `unsigned int __fastcall(DfsADBlobCache *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000789c`
- `0x140008610`
- `0x140009220`
- `0x1400093c4`
- `0x14000af60`

## callees

- `0x1400011c4`
- `0x140008580`
- `0x14003e95c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1400085c3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400085c3`
- `ntdll!RtlNtStatusToDosError` at `0x1400085d5`
- `ntdll!RtlNtStatusToDosError` at `0x1400085d5`

## pseudocode

```c

```
