# TcpIoCompletionCb

- ea: `0x180051490`
- end: `0x18005165a`
- name: `TcpIoCompletionCb`
- size: `458`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18004f928`
- `0x180051490`
- `0x180051660`
- `0x180051718`
- `0x180083954`
- `0x18008b5f0`
- `0x1800d2880`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800514e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051582`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800514e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051582`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800514fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800515c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800514fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800515c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800514cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800514cc`
- `WS2_32!WSAGetOverlappedResult` at `0x1800515a7`
- `WS2_32!WSAGetOverlappedResult` at `0x1800515a7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800515b7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800515b7`

## pseudocode

```c

```
