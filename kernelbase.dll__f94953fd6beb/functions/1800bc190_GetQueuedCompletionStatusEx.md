# GetQueuedCompletionStatusEx

- ea: `0x1800bc190`
- end: `0x1800bc2f9`
- name: `GetQueuedCompletionStatusEx`
- size: `361`
- prototype: `BOOL __stdcall(HANDLE CompletionPort, LPOVERLAPPED_ENTRY lpCompletionPortEntries, ULONG ulCount, PULONG ulNumEntriesRemoved, DWORD dwMilliseconds, BOOL fAlertable)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800bc190`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800bc26c`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2a0`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2ad`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2ef`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc26c`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2a0`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2ad`
- `ntdll!RtlSetLastWin32Error` at `0x1800bc2ef`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x1800bc233`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x1800bc233`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800bc2bd`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x18018b2e6`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800bc2bd`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x18018b2e6`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800bc255`
- `ntdll!NtRemoveIoCompletionEx` at `0x1800bc255`

## pseudocode

```c

```
