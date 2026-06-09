# SetFileBandwidthReservation

- ea: `0x1800570e0`
- end: `0x180057209`
- name: `SetFileBandwidthReservation`
- size: `297`
- prototype: `BOOL __stdcall(HANDLE hFile, DWORD nPeriodMilliseconds, DWORD nBytesPerPeriod, BOOL bDiscardable, LPDWORD lpTransferSize, LPDWORD lpNumOutstandingRequests)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x18000f920`
- `0x1800570e0`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18005713b`
- `ntdll!NtQueryInformationFile` at `0x1800571d1`
- `ntdll!NtQueryInformationFile` at `0x18005713b`
- `ntdll!NtQueryInformationFile` at `0x1800571d1`
- `ntdll!NtSetInformationFile` at `0x1800571aa`
- `ntdll!NtSetInformationFile` at `0x1800571aa`
- `ntdll!RtlSetLastWin32Error` at `0x180057163`
- `ntdll!RtlSetLastWin32Error` at `0x180057163`

## pseudocode

```c

```
