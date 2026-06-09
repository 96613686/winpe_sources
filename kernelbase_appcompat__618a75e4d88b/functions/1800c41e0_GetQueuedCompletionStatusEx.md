# GetQueuedCompletionStatusEx

- ea: `0x1800c41e0`
- end: `0x1800c4374`
- name: `GetQueuedCompletionStatusEx`
- size: `404`
- prototype: `BOOL __stdcall(HANDLE CompletionPort, LPOVERLAPPED_ENTRY lpCompletionPortEntries, ULONG ulCount, PULONG ulNumEntriesRemoved, DWORD dwMilliseconds, BOOL fAlertable)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x1800c41e0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800c42c8`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4302`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4315`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4364`
- `ntdll!RtlSetLastWin32Error` at `0x1800c42c8`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4302`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4315`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4364`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x1800c4283`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x1800c4283`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800c432b`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x180197416`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800c432b`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x180197416`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800c42ab`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800c42ab`

## pseudocode

```c

```
