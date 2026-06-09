# SetFileShortNameW

- ea: `0x180063b60`
- end: `0x180063c86`
- name: `SetFileShortNameW`
- size: `294`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCWSTR lpShortName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180063b10`

## callees

- `0x18000ccf0`
- `0x180063b60`

## import_xrefs

- `ntdll!wcslen` at `0x180063b95`
- `ntdll!wcslen` at `0x180063bae`
- `ntdll!wcslen` at `0x180063bfb`
- `ntdll!wcslen` at `0x180063b95`
- `ntdll!wcslen` at `0x180063bae`
- `ntdll!wcslen` at `0x180063bfb`
- `ntdll!wcscpy_s` at `0x180063c19`
- `ntdll!wcscpy_s` at `0x180063c19`
- `ntdll!NtSetInformationFile` at `0x180063c3b`
- `ntdll!NtSetInformationFile` at `0x180063c3b`
- `ntdll!RtlSetLastWin32Error` at `0x180063b7f`
- `ntdll!RtlSetLastWin32Error` at `0x180063b7f`
- `ntdll!RtlFreeHeap` at `0x180063c5b`
- `ntdll!RtlFreeHeap` at `0x180063c5b`
- `ntdll!RtlAllocateHeap` at `0x180063bdf`
- `ntdll!RtlAllocateHeap` at `0x180063bdf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180063bc1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180063bc1`

## pseudocode

```c

```
