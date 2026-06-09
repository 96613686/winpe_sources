# KdNetConnection::InitializeSocketIpv6(in6_addr)

- ea: `0x180431700`
- end: `0x180431c50`
- name: `?InitializeSocketIpv6@KdNetConnection@@UEAAJUin6_addr@@@Z`
- size: `1360`
- prototype: `__int64 __fastcall(KdNetConnection *__hidden this, struct in6_addr *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18007cf9c`
- `0x18007d308`
- `0x1800db578`
- `0x1800f0f40`
- `0x180195214`
- `0x18038605c`
- `0x180431700`
- `0x180431cec`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431a61`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431ad6`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431a61`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431ad6`
- `WS2_32!getaddrinfo` at `0x1804319e8`
- `WS2_32!getaddrinfo` at `0x1804319e8`
- `WS2_32!WSAIoctl` at `0x180431941`
- `WS2_32!WSAIoctl` at `0x180431941`
- `WS2_32!__imp_bind` at `0x180431b11`
- `WS2_32!__imp_bind` at `0x180431b11`
- `WS2_32!__imp_closesocket` at `0x18043179f`
- `WS2_32!__imp_closesocket` at `0x180431bfb`
- `WS2_32!__imp_closesocket` at `0x18043179f`
- `WS2_32!__imp_closesocket` at `0x180431bfb`
- `WS2_32!__imp_htons` at `0x180431a70`
- `WS2_32!__imp_htons` at `0x180431ae5`
- `WS2_32!__imp_htons` at `0x180431a70`
- `WS2_32!__imp_htons` at `0x180431ae5`
- `WS2_32!__imp_ioctlsocket` at `0x180431815`
- `WS2_32!__imp_ioctlsocket` at `0x180431815`
- `WS2_32!__imp_setsockopt` at `0x180431866`
- `WS2_32!__imp_setsockopt` at `0x180431898`
- `WS2_32!__imp_setsockopt` at `0x1804318cc`
- `WS2_32!__imp_setsockopt` at `0x180431900`
- `WS2_32!__imp_setsockopt` at `0x180431971`
- `WS2_32!__imp_setsockopt` at `0x180431866`
- `WS2_32!__imp_setsockopt` at `0x180431898`
- `WS2_32!__imp_setsockopt` at `0x1804318cc`
- `WS2_32!__imp_setsockopt` at `0x180431900`
- `WS2_32!__imp_setsockopt` at `0x180431971`
- `WS2_32!__imp_socket` at `0x1804317bf`
- `WS2_32!__imp_socket` at `0x1804317bf`
- `WS2_32!__imp_WSAGetLastError` at `0x1804317d4`
- `WS2_32!__imp_WSAGetLastError` at `0x180431b22`
- `WS2_32!__imp_WSAGetLastError` at `0x180431b3e`
- `WS2_32!__imp_WSAGetLastError` at `0x1804317d4`
- `WS2_32!__imp_WSAGetLastError` at `0x180431b22`
- `WS2_32!__imp_WSAGetLastError` at `0x180431b3e`

## string_xrefs

- `0x180431b5b`: `BindAccessErr`
- `0x180431b35`: `Port %s already in use by another process. Check for other running debugger instances and try again.\n`
- `0x180431837`: `Could not set socket to non-blocking mode. KDNET transport may become\nout-of-sync with high packet losses.\n`
- `0x180431b6e`: `Port %s in use by OS. Restart this computer or reconfigure KDNET to use a different port and try again.\n`

## pseudocode

```c

```
