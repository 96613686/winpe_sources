# cdp::ListenSocket::OnAcceptCompleted(cdp::ListenSocket::EventTunnel &,cdp::Socket::Operation &,cdp::ListenSocket::Context &,ulong)

- ea: `0x1802daba4`
- end: `0x1802daed5`
- name: `?OnAcceptCompleted@ListenSocket@cdp@@AEAAXAEAVEventTunnel@12@AEAUOperation@Socket@2@AEAUContext@12@K@Z`
- size: `817`
- prototype: `void __usercall(cdp::ListenSocket *__hidden this@<rcx>, struct cdp::ListenSocket::EventTunnel *@<rdx>, struct cdp::Socket::Operation *@<r8>, struct cdp::ListenSocket::Context *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016b070`

## callees

- `0x180013da0`
- `0x1800206e0`
- `0x180089704`
- `0x18008ac28`
- `0x18008acc0`
- `0x1800f06e4`
- `0x180133350`
- `0x1801cf6f4`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fcb36`
- `0x1802a3cec`
- `0x1802c1950`
- `0x1802cc3a0`
- `0x1802da6bc`
- `0x1802daba4`
- `0x1802daf68`
- `0x1802dbff8`

## import_xrefs

- `WS2_32!__imp_getpeername` at `0x1802dadc8`
- `WS2_32!__imp_getpeername` at `0x1802dadc8`
- `WS2_32!__imp_setsockopt` at `0x1802dad4f`
- `WS2_32!__imp_setsockopt` at `0x1802dad4f`
- `WS2_32!__imp_WSAGetLastError` at `0x1802dad5a`
- `WS2_32!__imp_WSAGetLastError` at `0x1802dadd3`
- `WS2_32!__imp_WSAGetLastError` at `0x1802dad5a`
- `WS2_32!__imp_WSAGetLastError` at `0x1802dadd3`

## string_xrefs

- `0x1802dad7d`: `Failed to update the accept socket's context, WSA error %u`
- `0x1802dabf3`: `Completing an accept operation when none are pending`

## pseudocode

```c

```
