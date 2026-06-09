# GetLongPathNameW

- ea: `0x180027ed0`
- end: `0x1800284df`
- name: `GetLongPathNameW`
- size: `1551`
- prototype: `DWORD __stdcall(LPCWSTR lpszShortPath, LPWSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f174`
- `0x180027c90`
- `0x180072450`

## callees

- `0x180027ed0`
- `0x1800284e8`
- `0x18002854c`
- `0x180061d70`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!wcslen` at `0x180028020`
- `ntdll!wcslen` at `0x180028155`
- `ntdll!wcslen` at `0x180028239`
- `ntdll!wcslen` at `0x18002832b`
- `ntdll!wcslen` at `0x180028020`
- `ntdll!wcslen` at `0x180028155`
- `ntdll!wcslen` at `0x180028239`
- `ntdll!wcslen` at `0x18002832b`
- `ntdll!RtlSetLastWin32Error` at `0x18002812d`
- `ntdll!RtlSetLastWin32Error` at `0x18002818b`
- `ntdll!RtlSetLastWin32Error` at `0x1800284cf`
- `ntdll!RtlSetLastWin32Error` at `0x18002812d`
- `ntdll!RtlSetLastWin32Error` at `0x18002818b`
- `ntdll!RtlSetLastWin32Error` at `0x1800284cf`
- `ntdll!RtlFreeHeap` at `0x180028465`
- `ntdll!RtlFreeHeap` at `0x180028488`
- `ntdll!RtlFreeHeap` at `0x180082c15`
- `ntdll!RtlFreeHeap` at `0x180082c3a`
- `ntdll!RtlFreeHeap` at `0x180028465`
- `ntdll!RtlFreeHeap` at `0x180028488`
- `ntdll!RtlFreeHeap` at `0x180082c15`
- `ntdll!RtlFreeHeap` at `0x180082c3a`
- `ntdll!RtlAllocateHeap` at `0x180028056`
- `ntdll!RtlAllocateHeap` at `0x18002810b`
- `ntdll!RtlAllocateHeap` at `0x180028056`
- `ntdll!RtlAllocateHeap` at `0x18002810b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18002802f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800280e2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18002802f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800280e2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180028207`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180028207`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180028225`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180028225`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027f57`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027f57`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180027f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180028498`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180027f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180028498`

## pseudocode

```c

```
