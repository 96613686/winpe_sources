# GetLongPathNameW

- ea: `0x18000c7f0`
- end: `0x18000cd92`
- name: `GetLongPathNameW`
- size: `1442`
- prototype: `DWORD __stdcall(LPCWSTR lpszShortPath, LPWSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c5e0`
- `0x180021320`
- `0x18006b100`

## callees

- `0x18000c7f0`
- `0x18000cd98`
- `0x18000cdfc`
- `0x18005c390`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!wcslen` at `0x18000c934`
- `ntdll!wcslen` at `0x18000ca45`
- `ntdll!wcslen` at `0x18000cb11`
- `ntdll!wcslen` at `0x18000cbfd`
- `ntdll!wcslen` at `0x18000c934`
- `ntdll!wcslen` at `0x18000ca45`
- `ntdll!wcslen` at `0x18000cb11`
- `ntdll!wcslen` at `0x18000cbfd`
- `ntdll!RtlSetLastWin32Error` at `0x18000ca23`
- `ntdll!RtlSetLastWin32Error` at `0x18000ca75`
- `ntdll!RtlSetLastWin32Error` at `0x18000cd88`
- `ntdll!RtlSetLastWin32Error` at `0x18000ca23`
- `ntdll!RtlSetLastWin32Error` at `0x18000ca75`
- `ntdll!RtlSetLastWin32Error` at `0x18000cd88`
- `ntdll!RtlFreeHeap` at `0x18000cd31`
- `ntdll!RtlFreeHeap` at `0x18000cd4e`
- `ntdll!RtlFreeHeap` at `0x18007abcf`
- `ntdll!RtlFreeHeap` at `0x18007abee`
- `ntdll!RtlFreeHeap` at `0x18000cd31`
- `ntdll!RtlFreeHeap` at `0x18000cd4e`
- `ntdll!RtlFreeHeap` at `0x18007abcf`
- `ntdll!RtlFreeHeap` at `0x18007abee`
- `ntdll!RtlAllocateHeap` at `0x18000c95e`
- `ntdll!RtlAllocateHeap` at `0x18000ca07`
- `ntdll!RtlAllocateHeap` at `0x18000c95e`
- `ntdll!RtlAllocateHeap` at `0x18000ca07`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c93d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c9e4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c93d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c9e4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000caeb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000caeb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000cb03`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000cb03`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c871`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c871`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c864`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000cd58`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c864`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000cd58`

## pseudocode

```c

```
