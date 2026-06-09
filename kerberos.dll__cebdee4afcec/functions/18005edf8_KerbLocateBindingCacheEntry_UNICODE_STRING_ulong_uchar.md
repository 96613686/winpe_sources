# KerbLocateBindingCacheEntry(_UNICODE_STRING *,ulong,uchar)

- ea: `0x18005edf8`
- end: `0x18005f03c`
- name: `?KerbLocateBindingCacheEntry@@YAPEAU_KERB_BINDING_CACHE_ENTRY@@PEAU_UNICODE_STRING@@KE@Z`
- size: `580`
- prototype: `struct _KERB_BINDING_CACHE_ENTRY *__fastcall(struct _UNICODE_STRING *, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180037ea8`
- `0x1800389b8`
- `0x18005ebb0`
- `0x18007d3b8`

## callees

- `0x18002c31c`
- `0x18002d020`
- `0x18005edf8`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005efd5`
- `ntdll!RtlReleaseResource` at `0x18005f024`
- `ntdll!RtlReleaseResource` at `0x18005efd5`
- `ntdll!RtlReleaseResource` at `0x18005f024`
- `ntdll!RtlAcquireResourceShared` at `0x18005ee25`
- `ntdll!RtlAcquireResourceShared` at `0x18005ee25`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005efe4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005efe4`

## string_xrefs

- `0x18005eefc`: `Purging KDC cache entry Realm: %wZ, Addr: %wZ, DcFlags %x\n`
- `0x18005ef08`: `KerbLocateBindingCacheEntry`
- `0x18005ef3b`: `KerbLocateBindingCacheEntry`
- `0x18005ef47`: `**Using** KDC cache entry Realm: %wZ, Addr: %wZ, DcFlags %x\n`

## pseudocode

```c

```
