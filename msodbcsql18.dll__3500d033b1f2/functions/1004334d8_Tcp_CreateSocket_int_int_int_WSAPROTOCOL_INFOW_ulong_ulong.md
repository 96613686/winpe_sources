# Tcp::CreateSocket(int,int,int,_WSAPROTOCOL_INFOW *,ulong,ulong *)

- ea: `0x1004334d8`
- end: `0x1004336f0`
- name: `?CreateSocket@Tcp@@SA_KHHHPEAU_WSAPROTOCOL_INFOW@@KPEAK@Z`
- size: `536`
- prototype: `unsigned __int64 __fastcall(int af, int type, int protocol, LPWSAPROTOCOL_INFOW lpProtocolInfo, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100433a94`

## callees

- `0x1004334d8`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!SetHandleInformation` at `0x10043360b`
- `KERNEL32!SetHandleInformation` at `0x10043360b`
- `KERNEL32!GetLastError` at `0x100433615`
- `KERNEL32!GetLastError` at `0x100433615`
- `WS2_32!WSASocketW` at `0x100433565`
- `WS2_32!WSASocketW` at `0x100433565`
- `WS2_32!__imp_closesocket` at `0x10043364b`
- `WS2_32!__imp_closesocket` at `0x10043364b`
- `WS2_32!__imp_socket` at `0x1004335ae`
- `WS2_32!__imp_socket` at `0x1004335ae`
- `WS2_32!__imp_WSAGetLastError` at `0x100433578`
- `WS2_32!__imp_WSAGetLastError` at `0x1004335bd`
- `WS2_32!__imp_WSAGetLastError` at `0x100433656`
- `WS2_32!__imp_WSAGetLastError` at `0x100433578`
- `WS2_32!__imp_WSAGetLastError` at `0x1004335bd`
- `WS2_32!__imp_WSAGetLastError` at `0x100433656`

## pseudocode

```c

```
