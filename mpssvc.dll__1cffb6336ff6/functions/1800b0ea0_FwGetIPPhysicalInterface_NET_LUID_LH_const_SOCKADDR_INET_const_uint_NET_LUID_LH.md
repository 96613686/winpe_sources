# FwGetIPPhysicalInterface(_NET_LUID_LH const *,_SOCKADDR_INET const *,uint,_NET_LUID_LH *)

- ea: `0x1800b0ea0`
- end: `0x1800b1043`
- name: `?FwGetIPPhysicalInterface@@YAKPEBT_NET_LUID_LH@@PEBT_SOCKADDR_INET@@IPEAT1@@Z`
- size: `419`
- prototype: `unsigned int(const union _NET_LUID_LH *, const union _SOCKADDR_INET *, unsigned int, union _NET_LUID_LH *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f5c0`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800b0ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0ee3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0ee3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0f67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0f67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b101f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b101f`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800b0fc8`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800b0fc8`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800b1010`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800b1010`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x1800b0f4f`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x1800b0f4f`

## pseudocode

```c

```
