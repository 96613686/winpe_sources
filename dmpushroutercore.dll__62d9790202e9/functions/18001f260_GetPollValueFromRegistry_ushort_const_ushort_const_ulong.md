# GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x18001f260`
- end: `0x18001f3fa`
- name: `?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f5fc`

## callees

- `0x1800039f0`
- `0x18000c504`
- `0x18001f260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f3bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f3bf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001f2bd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001f2bd`

## pseudocode

```c

```
