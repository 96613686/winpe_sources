# SSRP::SsrpSocket::OpenUnicast(wchar_t const *,char *,int)

- ea: `0x1801ab420`
- end: `0x1801ab808`
- name: `?OpenUnicast@SsrpSocket@SSRP@@QEAA_NPEB_WPEADH@Z`
- size: `1000`
- prototype: `bool(SSRP::SsrpSocket *__hidden this, const wchar_t *, char *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801aa0b0`
- `0x1801aabe0`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x1801ab420`
- `0x1801ad6a0`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x1801ab564`
- `WS2_32!GetAddrInfoW` at `0x1801ab59c`
- `WS2_32!GetAddrInfoW` at `0x1801ab564`
- `WS2_32!GetAddrInfoW` at `0x1801ab59c`
- `WS2_32!FreeAddrInfoW` at `0x1801ab72f`
- `WS2_32!FreeAddrInfoW` at `0x1801ab72f`
- `WS2_32!__imp_closesocket` at `0x1801ab711`
- `WS2_32!__imp_closesocket` at `0x1801ab711`
- `WS2_32!__imp_sendto` at `0x1801ab6fe`
- `WS2_32!__imp_sendto` at `0x1801ab6fe`
- `WS2_32!__imp_socket` at `0x1801ab6c9`
- `WS2_32!__imp_socket` at `0x1801ab6c9`
- `WS2_32!__imp_WSAGetLastError` at `0x1801ab572`
- `WS2_32!__imp_WSAGetLastError` at `0x1801ab572`

## pseudocode

```c

```
