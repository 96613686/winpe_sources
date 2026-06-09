# GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x18001f0c0`
- end: `0x18001f25a`
- name: `?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ffb4`

## callees

- `0x1800039f0`
- `0x18000c504`
- `0x18001f0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f21f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f21f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001f11d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001f11d`

## pseudocode

```c

```
