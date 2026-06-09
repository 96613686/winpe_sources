# Csl::CreateRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &,bool &)

- ea: `0x180056330`
- end: `0x180056484`
- name: `?CreateRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@AEA_N@Z`
- size: `340`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum Csl::RegistryKeyAccess, struct Csl::RegistryKey *, bool *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005b2a8`
- `0x1800c821c`
- `0x1800ed98c`
- `0x1800fb5b0`
- `0x1800fea78`

## callees

- `0x180032344`
- `0x180056330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056402`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800563d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005643f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005646a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800563d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005643f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005646a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056386`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056386`

## string_xrefs

- `0x18005639e`: `Failed to create registry key with name '%ws'`
- `0x1800563aa`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c

```
