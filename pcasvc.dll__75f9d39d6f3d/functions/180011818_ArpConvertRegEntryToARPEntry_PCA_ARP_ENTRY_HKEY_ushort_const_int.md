# ArpConvertRegEntryToARPEntry(_PCA_ARP_ENTRY *,HKEY__ *,ushort const *,int)

- ea: `0x180011818`
- end: `0x180011b4e`
- name: `?ArpConvertRegEntryToARPEntry@@YAKPEAU_PCA_ARP_ENTRY@@PEAUHKEY__@@PEBGH@Z`
- size: `822`
- prototype: `unsigned int __fastcall(struct _PCA_ARP_ENTRY *, HKEY hKey, LPCWSTR lpSubKey, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010b1c`

## callees

- `0x180011818`
- `0x180012920`
- `0x180056256`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800119aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800119e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ad5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800119aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800119e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011934`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800118fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800118fe`

## string_xrefs

- `0x18001190e`: `Failed to open key [%d]`
- `0x180011ac1`: `SystemComponent`
- `0x180011a79`: `UninstallString`

## pseudocode

```c

```
