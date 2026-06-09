# DnsFwIoCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x18006f730`
- end: `0x18006f81f`
- name: `?DnsFwIoCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `239`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, __int64 Context, struct _OVERLAPPED *Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18004368c`
- `0x180046ec0`
- `0x18006f730`
- `0x1800855d4`
- `0x180086700`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18006f796`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18006f796`
- `WS2_32!WSAGetOverlappedResult` at `0x18006f7c6`
- `WS2_32!WSAGetOverlappedResult` at `0x18006f7c6`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f7d0`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f7d0`

## pseudocode

```c

```
