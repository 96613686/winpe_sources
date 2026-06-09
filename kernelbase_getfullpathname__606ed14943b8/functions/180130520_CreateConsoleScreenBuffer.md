# CreateConsoleScreenBuffer

- ea: `0x180130520`
- end: `0x1801307f7`
- name: `CreateConsoleScreenBuffer`
- size: `727`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, DWORD dwShareMode, const SECURITY_ATTRIBUTES *lpSecurityAttributes, DWORD dwFlags, LPVOID lpScreenBufferData)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800665f4`
- `0x180130520`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18013068f`
- `ntdll!RtlInitUnicodeString` at `0x18013068f`
- `ntdll!NtCreateFile` at `0x180130700`
- `ntdll!NtCreateFile` at `0x180130700`
- `ntdll!RtlSetLastWin32Error` at `0x18013077d`
- `ntdll!RtlSetLastWin32Error` at `0x1801307c6`
- `ntdll!RtlSetLastWin32Error` at `0x18013077d`
- `ntdll!RtlSetLastWin32Error` at `0x1801307c6`
- `ntdll!RtlNtStatusToDosError` at `0x18013076f`
- `ntdll!RtlNtStatusToDosError` at `0x1801307b8`
- `ntdll!RtlNtStatusToDosError` at `0x18013076f`
- `ntdll!RtlNtStatusToDosError` at `0x1801307b8`
- `ntdll!NtClose` at `0x18013078e`
- `ntdll!NtClose` at `0x18013078e`
- `ntdll!RtlFreeHeap` at `0x180130729`
- `ntdll!RtlFreeHeap` at `0x180130729`
- `ntdll!RtlAllocateHeap` at `0x1801305fb`
- `ntdll!RtlAllocateHeap` at `0x1801305fb`

## pseudocode

```c

```
