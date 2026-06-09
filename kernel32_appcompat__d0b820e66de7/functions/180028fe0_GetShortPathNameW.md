# GetShortPathNameW

- ea: `0x180028fe0`
- end: `0x18002950a`
- name: `GetShortPathNameW`
- size: `1322`
- prototype: `DWORD __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180028610`
- `0x1800296bc`
- `0x180043664`

## callees

- `0x18001813c`
- `0x18002854c`
- `0x180028fe0`
- `0x18002aca8`
- `0x18002adcc`
- `0x180061d70`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!wcslen` at `0x1800291a5`
- `ntdll!wcslen` at `0x18002936e`
- `ntdll!wcslen` at `0x180029416`
- `ntdll!wcslen` at `0x180029477`
- `ntdll!wcslen` at `0x1800291a5`
- `ntdll!wcslen` at `0x18002936e`
- `ntdll!wcslen` at `0x180029416`
- `ntdll!wcslen` at `0x180029477`
- `ntdll!RtlSetLastWin32Error` at `0x180029046`
- `ntdll!RtlSetLastWin32Error` at `0x1800291ff`
- `ntdll!RtlSetLastWin32Error` at `0x180029046`
- `ntdll!RtlSetLastWin32Error` at `0x1800291ff`
- `ntdll!RtlFreeHeap` at `0x1800294c4`
- `ntdll!RtlFreeHeap` at `0x1800294e7`
- `ntdll!RtlFreeHeap` at `0x180082d37`
- `ntdll!RtlFreeHeap` at `0x180082d5c`
- `ntdll!RtlFreeHeap` at `0x1800294c4`
- `ntdll!RtlFreeHeap` at `0x1800294e7`
- `ntdll!RtlFreeHeap` at `0x180082d37`
- `ntdll!RtlFreeHeap` at `0x180082d5c`
- `ntdll!RtlAllocateHeap` at `0x1800291e1`
- `ntdll!RtlAllocateHeap` at `0x1800292b1`
- `ntdll!RtlAllocateHeap` at `0x1800291e1`
- `ntdll!RtlAllocateHeap` at `0x1800292b1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800291b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180029288`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800291b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180029288`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002933c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002933c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002935a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002935a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800290a0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800290a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002908d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800294f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180082d6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002908d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800294f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180082d6c`

## pseudocode

```c

```
