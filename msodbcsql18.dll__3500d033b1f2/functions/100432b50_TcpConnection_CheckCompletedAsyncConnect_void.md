# TcpConnection::CheckCompletedAsyncConnect(void)

- ea: `0x100432b50`
- end: `0x100432c67`
- name: `?CheckCompletedAsyncConnect@TcpConnection@@QEAAKXZ`
- size: `279`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10043731c`
- `0x100437444`

## callees

- `0x100432b50`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `WS2_32!WSAGetOverlappedResult` at `0x100432bb3`
- `WS2_32!WSAGetOverlappedResult` at `0x100432bb3`
- `WS2_32!__imp_setsockopt` at `0x100432bd5`
- `WS2_32!__imp_setsockopt` at `0x100432bd5`
- `WS2_32!__imp_WSAGetLastError` at `0x100432be0`
- `WS2_32!__imp_WSAGetLastError` at `0x100432bf4`
- `WS2_32!__imp_WSAGetLastError` at `0x100432be0`
- `WS2_32!__imp_WSAGetLastError` at `0x100432bf4`

## pseudocode

```c

```
