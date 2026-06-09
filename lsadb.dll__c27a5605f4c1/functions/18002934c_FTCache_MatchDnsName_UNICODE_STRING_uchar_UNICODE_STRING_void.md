# FTCache::MatchDnsName(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)

- ea: `0x18002934c`
- end: `0x1800294a4`
- name: `?MatchDnsName@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z`
- size: `344`
- prototype: `int(FTCache *__hidden this, struct _UNICODE_STRING *, unsigned __int8 *, struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002901c`

## callees

- `0x18000fd18`
- `0x180021aa8`
- `0x180021ad4`
- `0x180022210`
- `0x180022278`
- `0x18002934c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293ea`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180029365`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180029365`

## pseudocode

```c

```
