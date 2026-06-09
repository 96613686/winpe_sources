# IsAppliedGPOListEmpty(HKEY__ *)

- ea: `0x1800217d4`
- end: `0x18002198d`
- name: `?IsAppliedGPOListEmpty@@YAHPEAUHKEY__@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800213ac`

## callees

- `0x1800217d4`
- `0x180022bd4`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002194e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021967`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002194e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800218e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800218e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002181d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002181d`

## string_xrefs

- `0x18002184a`: `IsGPOListEmpty: Failed to open %s key with error: %d. Assuming GPO list is NOT empty.`
- `0x180021873`: `IsGPOListEmpty: Failed to open %s key with error: %d. Assuming GPO list is NOT empty.`
- `0x18002190f`: `IsGPOListEmpty: Failed to query subkeys info for %s key with error: %d. Assuming GPO list is NOT empty.`
- `0x18002193a`: `IsGPOListEmpty: Failed to query subkeys info for %s key with error: %d. Assuming GPO list is NOT empty.`

## pseudocode

```c

```
