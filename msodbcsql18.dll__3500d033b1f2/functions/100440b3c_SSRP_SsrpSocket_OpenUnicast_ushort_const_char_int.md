# SSRP::SsrpSocket::OpenUnicast(ushort const *,char *,int)

- ea: `0x100440b3c`
- end: `0x100440edf`
- name: `?OpenUnicast@SsrpSocket@SSRP@@QEAA_NPEBGPEADH@Z`
- size: `931`
- prototype: `bool(SSRP::SsrpSocket *__hidden this, const unsigned __int16 *, char *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x10043f9dc`
- `0x1004403c0`

## callees

- `0x100440b3c`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x100440c6a`
- `WS2_32!GetAddrInfoW` at `0x100440c9f`
- `WS2_32!GetAddrInfoW` at `0x100440c6a`
- `WS2_32!GetAddrInfoW` at `0x100440c9f`
- `WS2_32!FreeAddrInfoW` at `0x100440e17`
- `WS2_32!FreeAddrInfoW` at `0x100440e17`
- `WS2_32!__imp_closesocket` at `0x100440dfa`
- `WS2_32!__imp_closesocket` at `0x100440dfa`
- `WS2_32!__imp_sendto` at `0x100440de7`
- `WS2_32!__imp_sendto` at `0x100440de7`
- `WS2_32!__imp_socket` at `0x100440daf`
- `WS2_32!__imp_socket` at `0x100440daf`
- `WS2_32!__imp_WSAGetLastError` at `0x100440c78`
- `WS2_32!__imp_WSAGetLastError` at `0x100440c78`

## pseudocode

```c

```
