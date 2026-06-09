# DhcpRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)

- ea: `0x1800231d0`
- end: `0x1800234ca`
- name: `?DhcpRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z`
- size: `762`
- prototype: `__int64 __fastcall(void *, struct _SUPPORT_FUNCTIONS_50 *, struct _IP_AUTO_DHCP_GLOBAL_INFO *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021de8`
- `0x180075f14`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x1800231d0`
- `0x1800234d0`
- `0x18002362c`
- `0x180052bf4`
- `0x18005cc68`
- `0x180095b28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800232dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800232dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800232f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800232f9`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180023446`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180023446`
- `ntdll!RtlNtStatusToDosError` at `0x18002347b`
- `ntdll!RtlNtStatusToDosError` at `0x18002347b`

## pseudocode

```c

```
