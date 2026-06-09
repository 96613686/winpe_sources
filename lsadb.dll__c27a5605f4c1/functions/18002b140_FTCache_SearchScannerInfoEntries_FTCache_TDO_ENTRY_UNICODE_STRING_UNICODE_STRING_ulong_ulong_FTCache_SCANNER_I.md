# FTCache::SearchScannerInfoEntries(FTCache::TDO_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,ulong *,FTCache::SCANNER_INFO_ENTRY * *,FTCache::SCANNER_INFO_ENTRY * *)

- ea: `0x18002b140`
- end: `0x18002b38d`
- name: `?SearchScannerInfoEntries@FTCache@@AEAAJPEAUTDO_ENTRY@1@PEAU_UNICODE_STRING@@1PEAK2PEAPEAUSCANNER_INFO_ENTRY@1@3@Z`
- size: `589`
- prototype: `int(FTCache *__hidden this, struct FTCache::TDO_ENTRY *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int *, unsigned int *, struct FTCache::SCANNER_INFO_ENTRY **, struct FTCache::SCANNER_INFO_ENTRY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180021b94`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x18002b140`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b19d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b280`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b19d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b280`

## pseudocode

```c

```
