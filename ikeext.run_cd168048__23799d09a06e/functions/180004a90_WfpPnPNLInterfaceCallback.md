# WfpPnPNLInterfaceCallback

- ea: `0x180004a90`
- end: `0x1800054c7`
- name: `WfpPnPNLInterfaceCallback`
- size: `2615`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1800037c4`
- `0x180003b90`
- `0x180003cf0`
- `0x180003df0`
- `0x180004508`
- `0x180004a90`
- `0x180005f40`
- `0x1800061ec`
- `0x180010db0`
- `0x180016534`
- `0x18004882c`
- `0x18004890c`
- `0x18004ce90`
- `0x180050850`
- `0x180112480`
- `0x180117f9c`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004cb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004cb1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800051c0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000522c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800052be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180005324`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800053fd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180005445`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000548d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800051c0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000522c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800052be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180005324`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800053fd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180005445`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000548d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000533f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000533f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050a3`
- `WS2_32!WSAIoctl` at `0x180004b39`
- `WS2_32!WSAIoctl` at `0x180004b39`
- `WS2_32!__imp_WSAGetLastError` at `0x1800050da`
- `WS2_32!__imp_WSAGetLastError` at `0x1800050da`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180004bb2`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180004bb2`

## string_xrefs

- `0x1800053a9`: `WfpPnPComputeAddressListDelta`
- `0x1800054b3`: `WfpPnpThreadPoolCallback`

## pseudocode

```c

```
