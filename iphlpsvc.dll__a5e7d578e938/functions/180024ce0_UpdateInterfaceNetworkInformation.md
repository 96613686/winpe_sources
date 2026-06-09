# UpdateInterfaceNetworkInformation

- ea: `0x180024ce0`
- end: `0x180025094`
- name: `UpdateInterfaceNetworkInformation`
- size: `948`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180023e98`
- `0x1800242b0`
- `0x180024810`
- `0x180024c80`

## callees

- `0x18000d7c0`
- `0x180024ce0`
- `0x1800250a0`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ee0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ee0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f81`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180024f52`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180024f52`
- `IPHLPAPI!ConvertGuidToStringA` at `0x180024e86`
- `IPHLPAPI!ConvertGuidToStringA` at `0x180024e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025083`
- `NSI!NsiGetAllParameters` at `0x180024d8c`
- `NSI!NsiGetAllParameters` at `0x180024e3e`
- `NSI!NsiGetAllParameters` at `0x180024d8c`
- `NSI!NsiGetAllParameters` at `0x180024e3e`

## string_xrefs

- `0x180024f6d`: `UpdateInterfaceNetworkInformation: "%ls", GUID = %lsDNS suffix = "%ls"`
- `0x180024ffe`: `UpdateInterfaceNetworkInformation: Error %d querying Interface name and network GUID`
- `0x180025051`: `UpdateInterfaceNetworkInformation: Error %d querying GUID for interface "%ls"`
- `0x18002506f`: `UpdateInterfaceNetworkInformation: Error %d querying DNS suffix for interface "%ls"`

## pseudocode

```c

```
