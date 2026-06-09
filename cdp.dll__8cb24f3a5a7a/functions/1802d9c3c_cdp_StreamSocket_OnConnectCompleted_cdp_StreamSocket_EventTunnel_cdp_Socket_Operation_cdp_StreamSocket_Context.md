# cdp::StreamSocket::OnConnectCompleted(cdp::StreamSocket::EventTunnel &,cdp::Socket::Operation &,cdp::StreamSocket::Context &,ulong,int &)

- ea: `0x1802d9c3c`
- end: `0x1802d9f70`
- name: `?OnConnectCompleted@StreamSocket@cdp@@AEAAXAEAVEventTunnel@12@AEAUOperation@Socket@2@AEAUContext@12@KAEAH@Z`
- size: `820`
- prototype: `void __usercall(cdp::StreamSocket *__hidden this@<rcx>, struct cdp::StreamSocket::EventTunnel *@<rdx>, struct cdp::Socket::Operation *@<r8>, struct cdp::StreamSocket::Context *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802d9f80`

## callees

- `0x180089704`
- `0x18008acc0`
- `0x180133350`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fcb36`
- `0x1802a3cec`
- `0x1802cc3a0`
- `0x1802d90f4`
- `0x1802d91c4`
- `0x1802d9c3c`
- `0x1802da680`
- `0x1802dbff8`

## import_xrefs

- `WS2_32!__imp_getpeername` at `0x1802d9e9f`
- `WS2_32!__imp_getpeername` at `0x1802d9e9f`
- `WS2_32!__imp_setsockopt` at `0x1802d9dac`
- `WS2_32!__imp_setsockopt` at `0x1802d9e24`
- `WS2_32!__imp_setsockopt` at `0x1802d9dac`
- `WS2_32!__imp_setsockopt` at `0x1802d9e24`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9db9`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9e31`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9eac`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9db9`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9e31`
- `WS2_32!__imp_WSAGetLastError` at `0x1802d9eac`

## string_xrefs

- `0x1802d9ddc`: `Failed to update the stream socket context, WSA error %u`
- `0x1802d9c8f`: `Completing a connect operation when none are pending`

## pseudocode

```c

```
