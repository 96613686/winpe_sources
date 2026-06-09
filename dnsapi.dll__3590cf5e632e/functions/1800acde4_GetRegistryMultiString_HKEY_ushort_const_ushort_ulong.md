# GetRegistryMultiString(HKEY__ *,ushort const *,ushort * *,ulong *)

- ea: `0x1800acde4`
- end: `0x1800acfd5`
- name: `?GetRegistryMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAGPEAK@Z`
- size: `497`
- prototype: `__int64 __fastcall(HKEY hkey, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800abc38`

## callees

- `0x1800407cc`
- `0x18005a640`
- `0x18008b5f0`
- `0x1800acde4`
- `0x1800dc9e0`
- `0x1800e0620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aceb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acf3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aceb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acf3b`

## pseudocode

```c

```
