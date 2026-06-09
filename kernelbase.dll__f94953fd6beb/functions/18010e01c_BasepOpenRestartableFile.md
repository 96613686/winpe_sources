# BasepOpenRestartableFile

- ea: `0x18010e01c`
- end: `0x18010e5fa`
- name: `BasepOpenRestartableFile`
- size: `1502`
- prototype: `__int64 __usercall@<rax>(HANDLE hTemplateFile@<rcx>, LPCWSTR lpFileName@<rdx>, int, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800d061c`

## callees

- `0x180013250`
- `0x1800134a0`
- `0x1800138c0`
- `0x1800149d0`
- `0x180048f30`
- `0x1800cf810`
- `0x1800cfa60`
- `0x1800f60d8`
- `0x18010e01c`
- `0x18010e600`
- `0x1801242c8`
- `0x180125028`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18010e163`
- `ntdll!NtQueryVolumeInformationFile` at `0x18010e277`
- `ntdll!NtQueryVolumeInformationFile` at `0x18010e163`
- `ntdll!NtQueryVolumeInformationFile` at `0x18010e277`
- `ntdll!RtlSetLastWin32Error` at `0x18010e35f`
- `ntdll!RtlSetLastWin32Error` at `0x18010e54c`
- `ntdll!RtlSetLastWin32Error` at `0x18010e5c7`
- `ntdll!RtlSetLastWin32Error` at `0x18010e35f`
- `ntdll!RtlSetLastWin32Error` at `0x18010e54c`
- `ntdll!RtlSetLastWin32Error` at `0x18010e5c7`
- `ntdll!RtlNtStatusToDosError` at `0x18010e4d4`
- `ntdll!RtlNtStatusToDosError` at `0x18010e4d4`
- `ntdll!RtlFreeHeap` at `0x18010e57a`
- `ntdll!RtlFreeHeap` at `0x18010e57a`
- `ntdll!RtlAllocateHeap` at `0x18010e2a1`
- `ntdll!RtlAllocateHeap` at `0x18010e2a1`

## pseudocode

```c

```
