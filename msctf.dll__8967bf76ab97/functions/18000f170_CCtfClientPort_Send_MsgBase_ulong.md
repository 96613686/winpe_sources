# CCtfClientPort::Send(MsgBase *,ulong)

- ea: `0x18000f170`
- end: `0x18000f441`
- name: `?Send@CCtfClientPort@@QEAAJPEAUMsgBase@@K@Z`
- size: `721`
- prototype: `__int64 __fastcall(CCtfClientPort *__hidden this, struct MsgBase *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180019180`
- `0x18002ccf0`
- `0x18008969c`

## callees

- `0x18000e160`
- `0x18000f170`
- `0x18000f450`
- `0x180043548`
- `0x18005ba10`
- `0x18008ced0`
- `0x1800b4434`
- `0x180106a60`

## import_xrefs

- `ntdll!NtAlpcDeletePortSection` at `0x18000f252`
- `ntdll!NtAlpcDeletePortSection` at `0x18000f252`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000f22d`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000f2e3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000f22d`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000f2e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f2fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f2fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f265`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f265`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3b6`

## pseudocode

```c

```
