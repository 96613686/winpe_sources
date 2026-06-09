# CTcpSock::Connect(CNetAddr const &)

- ea: `0x180066120`
- end: `0x1800663c4`
- name: `?Connect@CTcpSock@@QEAAXAEBVCNetAddr@@@Z`
- size: `676`
- prototype: `void __fastcall(CTcpSock *__hidden this, const struct CNetAddr *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005c588`

## callees

- `0x180066120`
- `0x180066684`
- `0x18006700c`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800f82f0`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x1800661fb`
- `WS2_32!WSAIoctl` at `0x1800661fb`
- `WS2_32!__imp_bind` at `0x180066174`
- `WS2_32!__imp_bind` at `0x180066174`
- `WS2_32!__imp_ntohs` at `0x1800662d2`
- `WS2_32!__imp_ntohs` at `0x1800662d2`
- `WS2_32!__imp_WSAGetLastError` at `0x180066184`
- `WS2_32!__imp_WSAGetLastError` at `0x180066205`
- `WS2_32!__imp_WSAGetLastError` at `0x180066184`
- `WS2_32!__imp_WSAGetLastError` at `0x180066205`

## string_xrefs

- `0x1800662dd`: `_peerAddr.IsComplete()`

## pseudocode

```c

```
