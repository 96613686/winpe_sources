# TcpWSA::PostReadAsync(SNI_Packet *,ulong)

- ea: `0x100448d70`
- end: `0x100449106`
- name: `?PostReadAsync@TcpWSA@@AEAAKPEAVSNI_Packet@@K@Z`
- size: `918`
- prototype: `unsigned int __fastcall(TcpWSA *__hidden this, struct SNI_Packet *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x100448900`
- `0x100449140`

## callees

- `0x10043a7c4`
- `0x10043a930`
- `0x10043b1c4`
- `0x10043b1f8`
- `0x100448d70`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x100448ef3`
- `KERNEL32!GetOverlappedResult` at `0x100448ef3`
- `KERNEL32!GetLastError` at `0x100448efd`
- `KERNEL32!GetLastError` at `0x100448efd`
- `WS2_32!WSARecv` at `0x100448e80`
- `WS2_32!WSARecv` at `0x100448e80`
- `WS2_32!__imp_WSAGetLastError` at `0x100448e8b`
- `WS2_32!__imp_WSAGetLastError` at `0x100448e8b`

## pseudocode

```c

```
