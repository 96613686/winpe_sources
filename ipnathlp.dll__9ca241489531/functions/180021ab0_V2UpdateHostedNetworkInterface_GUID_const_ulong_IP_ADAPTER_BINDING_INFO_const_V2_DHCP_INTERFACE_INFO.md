# V2UpdateHostedNetworkInterface(_GUID const *,ulong,IP_ADAPTER_BINDING_INFO const *,_V2_DHCP_INTERFACE_INFO *)

- ea: `0x180021ab0`
- end: `0x180021f20`
- name: `?V2UpdateHostedNetworkInterface@@YAKPEBU_GUID@@KPEBUIP_ADAPTER_BINDING_INFO@@PEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `1136`
- prototype: `unsigned int(const struct _GUID *, unsigned int, const struct IP_ADAPTER_BINDING_INFO *, struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800237ec`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000f2b0`
- `0x18002173c`
- `0x180021ab0`
- `0x18002cb40`
- `0x18002d87c`
- `0x1800319e8`
- `0x180036738`
- `0x18003bf04`
- `0x180042a44`
- `0x180084538`
- `0x180084654`
- `0x180084700`
- `0x180085644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021cd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021cd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021eb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021eb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021b7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021b7e`

## pseudocode

```c

```
