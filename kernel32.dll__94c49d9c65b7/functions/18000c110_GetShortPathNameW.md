# GetShortPathNameW

- ea: `0x18000c110`
- end: `0x18000c5cf`
- name: `GetShortPathNameW`
- size: `1215`
- prototype: `DWORD __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a6d8`
- `0x18000ceb0`
- `0x18003fb7c`

## callees

- `0x18000a438`
- `0x18000a55c`
- `0x18000c110`
- `0x18000cdfc`
- `0x18001a69c`
- `0x18005c390`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!wcslen` at `0x18000c2be`
- `ntdll!wcslen` at `0x18000c457`
- `ntdll!wcslen` at `0x18000c4f9`
- `ntdll!wcslen` at `0x18000c554`
- `ntdll!wcslen` at `0x18000c2be`
- `ntdll!wcslen` at `0x18000c457`
- `ntdll!wcslen` at `0x18000c4f9`
- `ntdll!wcslen` at `0x18000c554`
- `ntdll!RtlSetLastWin32Error` at `0x18000c176`
- `ntdll!RtlSetLastWin32Error` at `0x18000c306`
- `ntdll!RtlSetLastWin32Error` at `0x18000c176`
- `ntdll!RtlSetLastWin32Error` at `0x18000c306`
- `ntdll!RtlFreeHeap` at `0x18000c59b`
- `ntdll!RtlFreeHeap` at `0x18000c5b8`
- `ntdll!RtlFreeHeap` at `0x18007ab0f`
- `ntdll!RtlFreeHeap` at `0x18007ab2e`
- `ntdll!RtlFreeHeap` at `0x18000c59b`
- `ntdll!RtlFreeHeap` at `0x18000c5b8`
- `ntdll!RtlFreeHeap` at `0x18007ab0f`
- `ntdll!RtlFreeHeap` at `0x18007ab2e`
- `ntdll!RtlAllocateHeap` at `0x18000c2ee`
- `ntdll!RtlAllocateHeap` at `0x18000c3ac`
- `ntdll!RtlAllocateHeap` at `0x18000c2ee`
- `ntdll!RtlAllocateHeap` at `0x18000c3ac`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c2c7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c389`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c2c7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c389`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c431`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c431`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c449`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c449`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c1c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c1c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c1b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c5c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007ab38`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c1b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000c5c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007ab38`

## pseudocode

```c

```
