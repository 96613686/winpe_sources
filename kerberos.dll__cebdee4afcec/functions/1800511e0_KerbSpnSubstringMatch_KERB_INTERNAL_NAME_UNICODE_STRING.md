# KerbSpnSubstringMatch(_KERB_INTERNAL_NAME *,_UNICODE_STRING *)

- ea: `0x1800511e0`
- end: `0x180051448`
- name: `?KerbSpnSubstringMatch@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z`
- size: `616`
- prototype: `int(struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005de50`

## callees

- `0x180007e80`
- `0x18000b300`
- `0x1800511e0`
- `0x180070680`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18005131b`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18005131b`
- `ntdll!RtlReleaseResource` at `0x1800513cd`
- `ntdll!RtlReleaseResource` at `0x18005143e`
- `ntdll!RtlReleaseResource` at `0x1800513cd`
- `ntdll!RtlReleaseResource` at `0x18005143e`
- `ntdll!RtlAcquireResourceShared` at `0x180051300`
- `ntdll!RtlAcquireResourceShared` at `0x180051300`

## string_xrefs

- `0x1800513b4`: `Missed cache for %wZ\n`
- `0x1800513f1`: `HIT cache for %wZ\n`

## pseudocode

```c

```
