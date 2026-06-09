# UpdateInterfaceNetworkInformation

- ea: `0x180024cd0`
- end: `0x180025084`
- name: `UpdateInterfaceNetworkInformation`
- size: `948`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180023e88`
- `0x1800242a0`
- `0x180024800`
- `0x180024c70`

## callees

- `0x18000d7b0`
- `0x180024cd0`
- `0x180025090`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ed0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ed0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f71`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180024f42`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180024f42`
- `IPHLPAPI!ConvertGuidToStringA` at `0x180024e76`
- `IPHLPAPI!ConvertGuidToStringA` at `0x180024e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025073`
- `NSI!NsiGetAllParameters` at `0x180024d7c`
- `NSI!NsiGetAllParameters` at `0x180024e2e`
- `NSI!NsiGetAllParameters` at `0x180024d7c`
- `NSI!NsiGetAllParameters` at `0x180024e2e`

## string_xrefs

- `0x180024f5d`: `UpdateInterfaceNetworkInformation: "%ls", GUID = %lsDNS suffix = "%ls"`
- `0x180024fee`: `UpdateInterfaceNetworkInformation: Error %d querying Interface name and network GUID`
- `0x180025041`: `UpdateInterfaceNetworkInformation: Error %d querying GUID for interface "%ls"`
- `0x18002505f`: `UpdateInterfaceNetworkInformation: Error %d querying DNS suffix for interface "%ls"`

## pseudocode

```c

```
