# FTP_ASYNC_SOCKET::GlobalInitialize(void)

- ea: `0x180007244`
- end: `0x180007571`
- name: `?GlobalInitialize@FTP_ASYNC_SOCKET@@SAJXZ`
- size: `813`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800029fc`

## callees

- `0x180007244`
- `0x180047050`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180007501`
- `ADVAPI32!RegQueryValueExW` at `0x180007501`
- `ADVAPI32!RegCloseKey` at `0x18000754f`
- `ADVAPI32!RegCloseKey` at `0x18000754f`
- `ADVAPI32!RegOpenKeyW` at `0x1800074cd`
- `ADVAPI32!RegOpenKeyW` at `0x1800074cd`
- `WS2_32!WSAIoctl` at `0x180007356`
- `WS2_32!WSAIoctl` at `0x1800073b1`
- `WS2_32!WSAIoctl` at `0x180007466`
- `WS2_32!WSAIoctl` at `0x1800074aa`
- `WS2_32!WSAIoctl` at `0x180007356`
- `WS2_32!WSAIoctl` at `0x1800073b1`
- `WS2_32!WSAIoctl` at `0x180007466`
- `WS2_32!WSAIoctl` at `0x1800074aa`
- `WS2_32!__imp_closesocket` at `0x1800073bf`
- `WS2_32!__imp_closesocket` at `0x180007540`
- `WS2_32!__imp_closesocket` at `0x1800073bf`
- `WS2_32!__imp_closesocket` at `0x180007540`
- `WS2_32!__imp_socket` at `0x1800072b6`
- `WS2_32!__imp_socket` at `0x1800073d1`
- `WS2_32!__imp_socket` at `0x1800072b6`
- `WS2_32!__imp_socket` at `0x1800073d1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800072db`
- `WS2_32!__imp_WSAGetLastError` at `0x180007361`
- `WS2_32!__imp_WSAGetLastError` at `0x1800073e9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800072db`
- `WS2_32!__imp_WSAGetLastError` at `0x180007361`
- `WS2_32!__imp_WSAGetLastError` at `0x1800073e9`
- `iisutil!PuDbgPrintError` at `0x180007316`
- `iisutil!PuDbgPrintError` at `0x180007424`
- `iisutil!PuDbgPrintError` at `0x180007316`
- `iisutil!PuDbgPrintError` at `0x180007424`

## string_xrefs

- `0x1800074c4`: `System\CurrentControlSet\Services\FTPSVC\Parameters`

## pseudocode

```c

```
