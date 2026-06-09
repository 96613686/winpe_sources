# DfsGetTotalRegistryValueSizeForKey(HKEY__ *,ulong *)

- ea: `0x140020fc0`
- end: `0x1400210f5`
- name: `?DfsGetTotalRegistryValueSizeForKey@@YAJPEAUHKEY__@@PEAK@Z`
- size: `309`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140021460`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140020fc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140021012`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140021012`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400210a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400210a3`

## pseudocode

```c

```
