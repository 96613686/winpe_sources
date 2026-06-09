# SetFileBandwidthReservation

- ea: `0x18005c4f0`
- end: `0x18005c632`
- name: `SetFileBandwidthReservation`
- size: `322`
- prototype: `BOOL __stdcall(HANDLE hFile, DWORD nPeriodMilliseconds, DWORD nBytesPerPeriod, BOOL bDiscardable, LPDWORD lpTransferSize, LPDWORD lpNumOutstandingRequests)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x18000ccf0`
- `0x18005c4f0`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18005c54b`
- `ntdll!NtQueryInformationFile` at `0x18005c5f3`
- `ntdll!NtQueryInformationFile` at `0x18005c54b`
- `ntdll!NtQueryInformationFile` at `0x18005c5f3`
- `ntdll!NtSetInformationFile` at `0x18005c5c6`
- `ntdll!NtSetInformationFile` at `0x18005c5c6`
- `ntdll!RtlSetLastWin32Error` at `0x18005c579`
- `ntdll!RtlSetLastWin32Error` at `0x18005c579`

## pseudocode

```c

```
