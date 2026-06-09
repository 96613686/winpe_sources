# BasepOpenRestartableFile

- ea: `0x180117308`
- end: `0x180117917`
- name: `BasepOpenRestartableFile`
- size: `1551`
- prototype: `__int64 __usercall@<rax>(HANDLE hTemplateFile@<rcx>, LPCWSTR lpFileName@<rdx>, int, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800d770c`

## callees

- `0x18004b770`
- `0x18004b9d0`
- `0x18004be40`
- `0x180053c30`
- `0x1800b92b0`
- `0x1800d6840`
- `0x1800d6a90`
- `0x1800ff2f8`
- `0x180117308`
- `0x180117920`
- `0x18012d93c`
- `0x18012e700`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18011744f`
- `ntdll!NtQueryVolumeInformationFile` at `0x180117569`
- `ntdll!NtQueryVolumeInformationFile` at `0x18011744f`
- `ntdll!NtQueryVolumeInformationFile` at `0x180117569`
- `ntdll!RtlSetLastWin32Error` at `0x18011765d`
- `ntdll!RtlSetLastWin32Error` at `0x180117856`
- `ntdll!RtlSetLastWin32Error` at `0x1801178dd`
- `ntdll!RtlSetLastWin32Error` at `0x18011765d`
- `ntdll!RtlSetLastWin32Error` at `0x180117856`
- `ntdll!RtlSetLastWin32Error` at `0x1801178dd`
- `ntdll!RtlNtStatusToDosError` at `0x1801177d8`
- `ntdll!RtlNtStatusToDosError` at `0x1801177d8`
- `ntdll!RtlFreeHeap` at `0x18011788a`
- `ntdll!RtlFreeHeap` at `0x18011788a`
- `ntdll!RtlAllocateHeap` at `0x180117599`
- `ntdll!RtlAllocateHeap` at `0x180117599`

## pseudocode

```c

```
