# V2UpdateHostedNetworkInterface(_GUID const *,ulong,IP_ADAPTER_BINDING_INFO const *,_V2_DHCP_INTERFACE_INFO *)

- ea: `0x18002dedc`
- end: `0x18002e36b`
- name: `?V2UpdateHostedNetworkInterface@@YAKPEBU_GUID@@KPEBUIP_ADAPTER_BINDING_INFO@@PEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `1167`
- prototype: `unsigned int(const struct _GUID *, unsigned int, const struct IP_ADAPTER_BINDING_INFO *, struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180025c54`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000fe48`
- `0x18002db50`
- `0x18002dedc`
- `0x18002e374`
- `0x1800313f0`
- `0x1800321b8`
- `0x180034098`
- `0x180039390`
- `0x18004634c`
- `0x18008ae20`
- `0x18008af3c`
- `0x18008afec`
- `0x18008c070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e10f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e10f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e2e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e2e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e2f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e2f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dfb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dfb0`

## pseudocode

```c

```
