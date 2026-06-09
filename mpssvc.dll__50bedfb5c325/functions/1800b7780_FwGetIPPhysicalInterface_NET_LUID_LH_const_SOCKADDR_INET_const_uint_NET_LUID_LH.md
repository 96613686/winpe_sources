# FwGetIPPhysicalInterface(_NET_LUID_LH const *,_SOCKADDR_INET const *,uint,_NET_LUID_LH *)

- ea: `0x1800b7780`
- end: `0x1800b7954`
- name: `?FwGetIPPhysicalInterface@@YAKPEBT_NET_LUID_LH@@PEBT_SOCKADDR_INET@@IPEAT1@@Z`
- size: `468`
- prototype: `unsigned int(const union _NET_LUID_LH *, const union _SOCKADDR_INET *, unsigned int, union _NET_LUID_LH *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800347c0`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x1800b7780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b77d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b786a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b77d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b786a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b77c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b77c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b7859`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b7859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7929`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800b78c6`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800b78c6`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800b7914`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800b7914`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x1800b783b`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x1800b783b`

## pseudocode

```c

```
