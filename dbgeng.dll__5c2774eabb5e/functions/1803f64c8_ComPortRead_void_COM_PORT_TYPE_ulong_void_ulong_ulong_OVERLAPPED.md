# ComPortRead(void *,COM_PORT_TYPE,ulong,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x1803f64c8`
- end: `0x1803f681d`
- name: `?ComPortRead@@YAJPEAXW4COM_PORT_TYPE@@K0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180432510`

## callees

- `0x1800f0f40`
- `0x1803f64c8`
- `0x180416524`
- `0x180416698`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1803f675c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1803f675c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f673b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f67b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f673b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f67b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1803f66ee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1803f66ee`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1803f67a0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1803f67a0`
- `WS2_32!WSAGetOverlappedResult` at `0x1803f6694`
- `WS2_32!WSAGetOverlappedResult` at `0x1803f6694`
- `WS2_32!WSARecv` at `0x1803f6619`
- `WS2_32!WSARecv` at `0x1803f6619`
- `WS2_32!__imp_select` at `0x1803f659b`
- `WS2_32!__imp_select` at `0x1803f659b`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f65ab`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f65c2`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6631`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6644`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6658`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f66a4`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f66bb`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f65ab`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f65c2`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6631`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6644`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f6658`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f66a4`
- `WS2_32!__imp_WSAGetLastError` at `0x1803f66bb`

## pseudocode

```c

```
