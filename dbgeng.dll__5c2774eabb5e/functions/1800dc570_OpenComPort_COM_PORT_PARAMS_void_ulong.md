# OpenComPort(_COM_PORT_PARAMS *,void * *,ulong *)

- ea: `0x1800dc570`
- end: `0x1800dc812`
- name: `?OpenComPort@@YAJPEAU_COM_PORT_PARAMS@@PEAPEAXPEAK@Z`
- size: `674`
- prototype: `int(struct _COM_PORT_PARAMS *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18042efec`
- `0x180430a80`

## callees

- `0x1800dc570`
- `0x1800f0f40`
- `0x1803f6b10`
- `0x1803f6f7c`
- `0x1803f7024`
- `0x1804198a4`
- `0x180419a18`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc70d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc70d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc721`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc77d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc77d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dc6f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dc6f8`
- `WS2_32!WSASocketW` at `0x1800dc659`
- `WS2_32!WSASocketW` at `0x1800dc659`
- `WS2_32!__imp_closesocket` at `0x1800dc68f`
- `WS2_32!__imp_closesocket` at `0x1800dc68f`
- `WS2_32!__imp_connect` at `0x1800dc67b`
- `WS2_32!__imp_connect` at `0x1800dc67b`
- `WS2_32!__imp_setsockopt` at `0x1800dc6be`
- `WS2_32!__imp_setsockopt` at `0x1800dc6be`
- `WS2_32!__imp_WSAStartup` at `0x1800dc5de`
- `WS2_32!__imp_WSAStartup` at `0x1800dc5de`

## pseudocode

```c

```
