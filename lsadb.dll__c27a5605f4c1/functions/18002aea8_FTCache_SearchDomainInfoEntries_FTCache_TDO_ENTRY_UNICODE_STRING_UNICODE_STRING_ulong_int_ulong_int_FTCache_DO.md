# FTCache::SearchDomainInfoEntries(FTCache::TDO_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,int *,ulong *,int *,FTCache::DOMAIN_INFO_ENTRY * *,FTCache::DOMAIN_INFO_ENTRY * *)

- ea: `0x18002aea8`
- end: `0x18002b139`
- name: `?SearchDomainInfoEntries@FTCache@@AEAAJPEAUTDO_ENTRY@1@PEAU_UNICODE_STRING@@1PEAKPEAH23PEAPEAUDOMAIN_INFO_ENTRY@1@4@Z`
- size: `657`
- prototype: `int(FTCache *__hidden this, struct FTCache::TDO_ENTRY *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int *, int *, unsigned int *, int *, struct FTCache::DOMAIN_INFO_ENTRY **, struct FTCache::DOMAIN_INFO_ENTRY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180021b94`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x180012fa4`
- `0x18002aea8`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002af23`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b015`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002af23`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b015`

## pseudocode

```c

```
