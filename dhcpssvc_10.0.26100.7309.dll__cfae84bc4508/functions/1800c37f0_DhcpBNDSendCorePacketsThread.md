# DhcpBNDSendCorePacketsThread

- ea: `0x1800c37f0`
- end: `0x1800c3bf0`
- name: `DhcpBNDSendCorePacketsThread`
- size: `1024`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002854`
- `0x18000323c`
- `0x18001ceb4`
- `0x1800be714`
- `0x1800bf90c`
- `0x1800c1540`
- `0x1800c19a0`
- `0x1800c37f0`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800c38e6`
- `WS2_32!WSAResetEvent` at `0x1800c38e6`
- `WS2_32!WSASetEvent` at `0x1800c3947`
- `WS2_32!WSASetEvent` at `0x1800c3977`
- `WS2_32!WSASetEvent` at `0x1800c3b99`
- `WS2_32!WSASetEvent` at `0x1800c3947`
- `WS2_32!WSASetEvent` at `0x1800c3977`
- `WS2_32!WSASetEvent` at `0x1800c3b99`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c385e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c3a0c`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c3aa8`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c385e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c3a0c`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c3aa8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3871`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c38f6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3957`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3987`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3ba9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3871`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c38f6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3957`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3987`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3ba9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3ae7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3b1b`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3ae7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3b1b`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c3acf`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c3acf`
- `KERNEL32!EnterCriticalSection` at `0x1800c38bb`
- `KERNEL32!EnterCriticalSection` at `0x1800c38bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800c39cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800c39cb`

## string_xrefs

- `0x1800c3911`: `DhcpBNDSendThread`
- `0x1800c39a2`: `DhcpBNDSendCorePacketsThread`
- `0x1800c3bc4`: `DhcpBNDSendCorePacketsThread`

## pseudocode

```c

```
