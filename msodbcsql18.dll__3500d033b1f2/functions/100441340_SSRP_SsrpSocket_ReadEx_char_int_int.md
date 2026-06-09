# SSRP::SsrpSocket::ReadEx(char *,int,int)

- ea: `0x100441340`
- end: `0x10044160c`
- name: `?ReadEx@SsrpSocket@SSRP@@QEAAHPEADHH@Z`
- size: `716`
- prototype: `__int64 __fastcall(SSRP::SsrpSocket *__hidden this, char *, int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x10043f9dc`
- `0x100441a7c`
- `0x100442008`

## callees

- `0x100441340`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546f73`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x100441428`
- `KERNEL32!GetTickCount` at `0x100441428`
- `WS2_32!__imp_closesocket` at `0x10044154b`
- `WS2_32!__imp_closesocket` at `0x10044154b`
- `WS2_32!__imp_recv` at `0x10044152d`
- `WS2_32!__imp_recv` at `0x10044152d`
- `WS2_32!__imp_select` at `0x1004414a6`
- `WS2_32!__imp_select` at `0x1004414a6`
- `WS2_32!__imp_WSAGetLastError` at `0x10044153b`
- `WS2_32!__imp_WSAGetLastError` at `0x10044153b`

## pseudocode

```c

```
