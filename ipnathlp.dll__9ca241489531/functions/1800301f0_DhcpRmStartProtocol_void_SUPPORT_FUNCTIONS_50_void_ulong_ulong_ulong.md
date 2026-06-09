# DhcpRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)

- ea: `0x1800301f0`
- end: `0x1800304ce`
- name: `?DhcpRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z`
- size: `734`
- prototype: `__int64 __fastcall(void *, struct _SUPPORT_FUNCTIONS_50 *, struct _IP_AUTO_DHCP_GLOBAL_INFO *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ef3c`
- `0x180070598`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x1800301f0`
- `0x1800304d4`
- `0x18003062c`
- `0x18004ed64`
- `0x1800586e8`
- `0x18008e908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030313`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030313`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180030457`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180030457`
- `ntdll!RtlNtStatusToDosError` at `0x180030486`
- `ntdll!RtlNtStatusToDosError` at `0x180030486`

## pseudocode

```c

```
