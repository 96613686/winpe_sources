# Tcp::CreateSocket(int,int,int,_WSAPROTOCOL_INFOW *,ulong,ulong *)

- ea: `0x180163040`
- end: `0x180163298`
- name: `?CreateSocket@Tcp@@SA_KHHHPEAU_WSAPROTOCOL_INFOW@@KPEAK@Z`
- size: `600`
- prototype: `unsigned __int64 __fastcall(int af, int type, int protocol, LPWSAPROTOCOL_INFOW lpProtocolInfo, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180163690`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180163040`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801631a9`
- `KERNEL32!GetLastError` at `0x1801631a9`
- `KERNEL32!SetHandleInformation` at `0x18016319b`
- `KERNEL32!SetHandleInformation` at `0x18016319b`
- `WS2_32!WSASocketW` at `0x1801630df`
- `WS2_32!WSASocketW` at `0x1801630df`
- `WS2_32!__imp_closesocket` at `0x1801631e4`
- `WS2_32!__imp_closesocket` at `0x1801631e4`
- `WS2_32!__imp_socket` at `0x180163137`
- `WS2_32!__imp_socket` at `0x180163137`
- `WS2_32!__imp_WSAGetLastError` at `0x1801630f2`
- `WS2_32!__imp_WSAGetLastError` at `0x180163146`
- `WS2_32!__imp_WSAGetLastError` at `0x1801631ef`
- `WS2_32!__imp_WSAGetLastError` at `0x1801630f2`
- `WS2_32!__imp_WSAGetLastError` at `0x180163146`
- `WS2_32!__imp_WSAGetLastError` at `0x1801631ef`

## pseudocode

```c

```
