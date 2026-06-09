# WSASetSocketSecurity

- ea: `0x18001fe90`
- end: `0x18001ff4e`
- name: `WSASetSocketSecurity`
- size: `190`
- prototype: `__int64 __fastcall(SOCKET s, LPVOID lpvInBuffer, DWORD cbInBuffer, LPWSAOVERLAPPED lpOverlapped, LPWSAOVERLAPPED_COMPLETION_ROUTINE)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012bd0`
- `0x18001fe90`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x18001ff29`
- `WS2_32!WSAIoctl` at `0x18001ff29`
- `WS2_32!__imp_setsockopt` at `0x18001fee6`
- `WS2_32!__imp_setsockopt` at `0x18001fee6`

## pseudocode

```c

```
