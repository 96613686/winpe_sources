# KdNetConnection::InitializeSocket(ulong)

- ea: `0x180431260`
- end: `0x1804316f2`
- name: `?InitializeSocket@KdNetConnection@@UEAAJK@Z`
- size: `1170`
- prototype: `int(KdNetConnection *__hidden this, unsigned int)`
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
- `0x180431260`
- `0x180431c58`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431550`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1804315af`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180431550`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1804315af`
- `WS2_32!WSAIoctl` at `0x18043147d`
- `WS2_32!WSAIoctl` at `0x18043147d`
- `WS2_32!__imp_bind` at `0x1804315ea`
- `WS2_32!__imp_bind` at `0x1804315ea`
- `WS2_32!__imp_closesocket` at `0x1804312e6`
- `WS2_32!__imp_closesocket` at `0x18043169d`
- `WS2_32!__imp_closesocket` at `0x1804312e6`
- `WS2_32!__imp_closesocket` at `0x18043169d`
- `WS2_32!__imp_htons` at `0x18043155f`
- `WS2_32!__imp_htons` at `0x1804315be`
- `WS2_32!__imp_htons` at `0x18043155f`
- `WS2_32!__imp_htons` at `0x1804315be`
- `WS2_32!__imp_ioctlsocket` at `0x18043135b`
- `WS2_32!__imp_ioctlsocket` at `0x18043135b`
- `WS2_32!__imp_setsockopt` at `0x1804313a9`
- `WS2_32!__imp_setsockopt` at `0x1804313d9`
- `WS2_32!__imp_setsockopt` at `0x18043140b`
- `WS2_32!__imp_setsockopt` at `0x18043143d`
- `WS2_32!__imp_setsockopt` at `0x1804314aa`
- `WS2_32!__imp_setsockopt` at `0x1804313a9`
- `WS2_32!__imp_setsockopt` at `0x1804313d9`
- `WS2_32!__imp_setsockopt` at `0x18043140b`
- `WS2_32!__imp_setsockopt` at `0x18043143d`
- `WS2_32!__imp_setsockopt` at `0x1804314aa`
- `WS2_32!__imp_socket` at `0x180431305`
- `WS2_32!__imp_socket` at `0x180431305`
- `WS2_32!__imp_gethostbyname` at `0x1804314f6`
- `WS2_32!__imp_gethostbyname` at `0x1804314f6`
- `WS2_32!__imp_WSAGetLastError` at `0x18043131a`
- `WS2_32!__imp_WSAGetLastError` at `0x1804315fb`
- `WS2_32!__imp_WSAGetLastError` at `0x180431617`
- `WS2_32!__imp_WSAGetLastError` at `0x18043131a`
- `WS2_32!__imp_WSAGetLastError` at `0x1804315fb`
- `WS2_32!__imp_WSAGetLastError` at `0x180431617`

## string_xrefs

- `0x180431634`: `BindAccessErr`
- `0x18043160e`: `Port %s already in use by another process. Check for other running debugger instances and try again.\n`
- `0x18043137d`: `Could not set socket to non-blocking mode. KDNET transport may become\nout-of-sync with high packet losses.\n`
- `0x180431647`: `Port %s in use by OS. Restart this computer or reconfigure KDNET to use a different port and try again.\n`

## pseudocode

```c

```
