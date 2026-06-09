# CITcpConnection::AsyncConnect(bool &)

- ea: `0x180021350`
- end: `0x180021682`
- name: `?AsyncConnect@CITcpConnection@@AEAAJAEA_N@Z`
- size: `818`
- prototype: `__int64 __fastcall(CITcpConnection *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b6460`

## callees

- `0x1800063b0`
- `0x180018d14`
- `0x180021350`
- `0x1800846c0`
- `0x1800b7eb4`
- `0x1800b8420`

## import_xrefs

- `WS2_32!getaddrinfo` at `0x1800213eb`
- `WS2_32!getaddrinfo` at `0x1800213eb`
- `WS2_32!freeaddrinfo` at `0x180021645`
- `WS2_32!freeaddrinfo` at `0x180021645`
- `WS2_32!__imp_closesocket` at `0x180021485`
- `WS2_32!__imp_closesocket` at `0x180021485`
- `WS2_32!__imp_connect` at `0x18002157b`
- `WS2_32!__imp_connect` at `0x18002157b`
- `WS2_32!__imp_ioctlsocket` at `0x180021542`
- `WS2_32!__imp_ioctlsocket` at `0x1800215f6`
- `WS2_32!__imp_ioctlsocket` at `0x180021542`
- `WS2_32!__imp_ioctlsocket` at `0x1800215f6`
- `WS2_32!__imp_setsockopt` at `0x1800214fe`
- `WS2_32!__imp_setsockopt` at `0x1800214fe`
- `WS2_32!__imp_socket` at `0x1800214a2`
- `WS2_32!__imp_socket` at `0x1800214a2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800213f5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800214b5`
- `WS2_32!__imp_WSAGetLastError` at `0x180021508`
- `WS2_32!__imp_WSAGetLastError` at `0x18002154c`
- `WS2_32!__imp_WSAGetLastError` at `0x180021585`
- `WS2_32!__imp_WSAGetLastError` at `0x180021600`
- `WS2_32!__imp_WSAGetLastError` at `0x1800213f5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800214b5`
- `WS2_32!__imp_WSAGetLastError` at `0x180021508`
- `WS2_32!__imp_WSAGetLastError` at `0x18002154c`
- `WS2_32!__imp_WSAGetLastError` at `0x180021585`
- `WS2_32!__imp_WSAGetLastError` at `0x180021600`

## string_xrefs

- `0x18002142c`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrconn.cpp`
- `0x180021451`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrconn.cpp`
- `0x1800214c6`: `Failed to create connection socket`
- `0x180021675`: `CITcpConnection::AsyncConnect (com\complus\dtc\dtc\tipgw\commgr\src\commgrconn.cpp@1420): The port number that DTC is using to connect to the partner TIP transaction manager is invalid.`

## pseudocode

```c

```
