# WspiapiLegacyGetNameInfo

- ea: `0x180125d80`
- end: `0x180125fd6`
- name: `WspiapiLegacyGetNameInfo`
- size: `598`
- prototype: `int __stdcall(const struct sockaddr *ptSocketAddress, socklen_t tSocketLength, char *pszNodeName, size_t tNodeLength, char *pszServiceName, size_t tServiceLength, int iFlags)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1801200d0`
- `0x18012115c`
- `0x180125d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180125ee5`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180125faa`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180125ee5`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180125faa`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180125f44`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180125f44`
- `WS2_32!__imp_inet_ntoa` at `0x180125f8a`
- `WS2_32!__imp_inet_ntoa` at `0x180125f8a`
- `WS2_32!__imp_ntohs` at `0x180125ea4`
- `WS2_32!__imp_ntohs` at `0x180125ea4`
- `WS2_32!__imp_gethostbyaddr` at `0x180125f20`
- `WS2_32!__imp_gethostbyaddr` at `0x180125f20`
- `WS2_32!__imp_getservbyport` at `0x180125e8a`
- `WS2_32!__imp_getservbyport` at `0x180125e8a`
- `WS2_32!__imp_WSAGetLastError` at `0x180125f5e`
- `WS2_32!__imp_WSAGetLastError` at `0x180125f5e`

## pseudocode

```c

```
