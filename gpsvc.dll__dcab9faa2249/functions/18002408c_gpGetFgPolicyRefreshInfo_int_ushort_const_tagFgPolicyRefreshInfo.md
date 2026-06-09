# gpGetFgPolicyRefreshInfo(int,ushort const *,_tagFgPolicyRefreshInfo *)

- ea: `0x18002408c`
- end: `0x18002469f`
- name: `?gpGetFgPolicyRefreshInfo@@YAKHPEBGPEAU_tagFgPolicyRefreshInfo@@@Z`
- size: `1555`
- prototype: `unsigned int(int, const unsigned __int16 *, struct _tagFgPolicyRefreshInfo *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180023b6c`
- `0x180034870`
- `0x180058f20`
- `0x18005ce5c`
- `0x1800689e0`

## callees

- `0x18002408c`
- `0x1800686a4`
- `0x1800698a0`
- `0x180074884`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002466b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002466b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002443b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002443b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024524`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800242d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800242d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800243fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800244d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024512`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800243fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800244d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024512`

## string_xrefs

- `0x180024382`: `gpGetFgPolicyRefreshInfo: Failed to read user policy state key from HKCU`
- `0x1800243b5`: `gpGetFgPolicyRefreshInfo: Failed to read user policy state key from HKCU`

## pseudocode

```c

```
