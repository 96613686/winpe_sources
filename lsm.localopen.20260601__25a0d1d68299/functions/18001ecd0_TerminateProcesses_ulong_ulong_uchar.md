# TerminateProcesses(ulong,ulong,uchar)

- ea: `0x18001ecd0`
- end: `0x18001f0f0`
- name: `?TerminateProcesses@@YAJKKE@Z`
- size: `1056`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ec40`

## callees

- `0x1800077a0`
- `0x18001ecd0`
- `0x18001f0f8`
- `0x18001f250`
- `0x18001f5f0`
- `0x18004e850`
- `0x18004f354`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001f002`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001f002`
- `ntdll!NtClose` at `0x18001edaf`
- `ntdll!NtClose` at `0x18001edaf`
- `ntdll!NtQueryInformationProcess` at `0x18001ede1`
- `ntdll!NtQueryInformationProcess` at `0x18001ee15`
- `ntdll!NtQueryInformationProcess` at `0x18001ee75`
- `ntdll!NtQueryInformationProcess` at `0x18001ede1`
- `ntdll!NtQueryInformationProcess` at `0x18001ee15`
- `ntdll!NtQueryInformationProcess` at `0x18001ee75`
- `ntdll!NtTerminateProcess` at `0x18001f097`
- `ntdll!NtTerminateProcess` at `0x18001f097`
- `ntdll!NtWaitForSingleObject` at `0x18001eeb8`
- `ntdll!NtWaitForSingleObject` at `0x18001ef71`
- `ntdll!NtWaitForSingleObject` at `0x18001eeb8`
- `ntdll!NtWaitForSingleObject` at `0x18001ef71`
- `ntdll!NtGetNextProcess` at `0x18001ed98`
- `ntdll!NtGetNextProcess` at `0x18001ed98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ef47`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ef8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f084`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ef47`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ef8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f084`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ed39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001eedc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ed39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001eedc`

## string_xrefs

- `0x18001f07d`: `Attempting to terminate the process.\n`
- `0x18001ef88`: `Process appears to be stuck during session termination.`

## pseudocode

```c

```
