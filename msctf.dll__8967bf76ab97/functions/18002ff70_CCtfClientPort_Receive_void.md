# CCtfClientPort::Receive(void)

- ea: `0x18002ff70`
- end: `0x180030750`
- name: `?Receive@CCtfClientPort@@QEAAJXZ`
- size: `2016`
- prototype: `__int64 __fastcall(CCtfClientPort *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18002ef30`
- `0x18002f070`
- `0x18002f140`

## callees

- `0x18002ff70`
- `0x180030758`
- `0x180032438`
- `0x180043548`
- `0x180053638`
- `0x18008ced0`
- `0x18009eac6`
- `0x1800a69f8`
- `0x1800b4434`
- `0x1800b44b8`
- `0x180106a60`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18003004f`
- `ntdll!AlpcGetMessageAttribute` at `0x180030062`
- `ntdll!AlpcGetMessageAttribute` at `0x18003004f`
- `ntdll!AlpcGetMessageAttribute` at `0x180030062`
- `ntdll!NtAlpcDeletePortSection` at `0x1800303b9`
- `ntdll!NtAlpcDeletePortSection` at `0x1800303b9`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800300f1`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180030397`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180030485`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800300f1`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180030397`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180030485`
- `ntdll!NtAlpcCancelMessage` at `0x1800305e8`
- `ntdll!NtAlpcCancelMessage` at `0x180030628`
- `ntdll!NtAlpcCancelMessage` at `0x180030661`
- `ntdll!NtAlpcCancelMessage` at `0x1800306aa`
- `ntdll!NtAlpcCancelMessage` at `0x18003071d`
- `ntdll!NtAlpcCancelMessage` at `0x1800305e8`
- `ntdll!NtAlpcCancelMessage` at `0x180030628`
- `ntdll!NtAlpcCancelMessage` at `0x180030661`
- `ntdll!NtAlpcCancelMessage` at `0x1800306aa`
- `ntdll!NtAlpcCancelMessage` at `0x18003071d`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002ffcd`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18003000b`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002ffcd`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18003000b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003057f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003057f`

## pseudocode

```c

```
