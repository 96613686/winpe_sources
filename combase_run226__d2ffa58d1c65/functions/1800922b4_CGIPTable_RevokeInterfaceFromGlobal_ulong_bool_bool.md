# CGIPTable::_RevokeInterfaceFromGlobal(ulong,bool,bool)

- ea: `0x1800922b4`
- end: `0x18009278c`
- name: `?_RevokeInterfaceFromGlobal@CGIPTable@@QEAAJK_N0@Z`
- size: `1240`
- prototype: `HRESULT __fastcall(CGIPTable *this, unsigned int dwCookie, bool bPostedRevoke, bool waitIfBusy)`
- caller_count: `10`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18002f0ec`
- `0x18002f83c`
- `0x18008b700`
- `0x18008ba3c`
- `0x180091f5c`
- `0x1800920e4`
- `0x1800922a0`
- `0x1800927a0`
- `0x180092b10`
- `0x180092d40`

## callees

- `0x180006250`
- `0x180006570`
- `0x180006ea0`
- `0x18000712c`
- `0x18000be10`
- `0x18000d030`
- `0x180012dd4`
- `0x180027cfc`
- `0x180037d10`
- `0x180037eb0`
- `0x1800678f0`
- `0x18007340c`
- `0x18007b38c`
- `0x180082c38`
- `0x180087660`
- `0x18008db2c`
- `0x1800922b4`
- `0x1800cf598`
- `0x1800e52cc`
- `0x1800eda64`
- `0x180118630`
- `0x180122e0c`
- `0x1801251d0`
- `0x18012848c`
- `0x18012d010`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800926f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800926f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092651`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009239c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009239c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180092569`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180092569`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180092472`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18009276e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180092472`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18009276e`

## string_xrefs

- `0x180092324`: `onecore\com\combase\coll\pgalloc.cxx`
- `0x180092556`: `onecore\com\combase\dcomrem\giptbl.cxx`

## pseudocode

```c

```
