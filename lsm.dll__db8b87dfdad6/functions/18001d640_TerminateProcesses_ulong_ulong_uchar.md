# TerminateProcesses(ulong,ulong,uchar)

- ea: `0x18001d640`
- end: `0x18001da01`
- name: `?TerminateProcesses@@YAJKKE@Z`
- size: `961`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d5bc`

## callees

- `0x1800074c0`
- `0x18001d640`
- `0x18001da08`
- `0x18001db30`
- `0x18001deb8`
- `0x18004b460`
- `0x18004bf44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001d925`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001d925`
- `ntdll!NtClose` at `0x18001d709`
- `ntdll!NtClose` at `0x18001d709`
- `ntdll!NtQueryInformationProcess` at `0x18001d735`
- `ntdll!NtQueryInformationProcess` at `0x18001d763`
- `ntdll!NtQueryInformationProcess` at `0x18001d7bd`
- `ntdll!NtQueryInformationProcess` at `0x18001d735`
- `ntdll!NtQueryInformationProcess` at `0x18001d763`
- `ntdll!NtQueryInformationProcess` at `0x18001d7bd`
- `ntdll!NtTerminateProcess` at `0x18001d9ae`
- `ntdll!NtTerminateProcess` at `0x18001d9ae`
- `ntdll!NtWaitForSingleObject` at `0x18001d7fa`
- `ntdll!NtWaitForSingleObject` at `0x18001d8a1`
- `ntdll!NtWaitForSingleObject` at `0x18001d7fa`
- `ntdll!NtWaitForSingleObject` at `0x18001d8a1`
- `ntdll!NtGetNextProcess` at `0x18001d6f8`
- `ntdll!NtGetNextProcess` at `0x18001d6f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d87d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d8b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d9a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d87d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d8b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001d9a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d6a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d818`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d6a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d818`

## string_xrefs

- `0x18001d99a`: `Attempting to terminate the process.\n`
- `0x18001d8b2`: `Process appears to be stuck during session termination.`

## pseudocode

```c

```
