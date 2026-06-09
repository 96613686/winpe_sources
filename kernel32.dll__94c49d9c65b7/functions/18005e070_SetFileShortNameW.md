# SetFileShortNameW

- ea: `0x18005e070`
- end: `0x18005e15f`
- name: `SetFileShortNameW`
- size: `239`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCWSTR lpShortName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18005e020`

## callees

- `0x18000f920`
- `0x18005e070`

## import_xrefs

- `ntdll!wcslen` at `0x18005e09f`
- `ntdll!wcslen` at `0x18005e0b2`
- `ntdll!wcslen` at `0x18005e0ed`
- `ntdll!wcslen` at `0x18005e09f`
- `ntdll!wcslen` at `0x18005e0b2`
- `ntdll!wcslen` at `0x18005e0ed`
- `ntdll!wcscpy_s` at `0x18005e105`
- `ntdll!wcscpy_s` at `0x18005e105`
- `ntdll!NtSetInformationFile` at `0x18005e121`
- `ntdll!NtSetInformationFile` at `0x18005e121`
- `ntdll!RtlSetLastWin32Error` at `0x18005e08f`
- `ntdll!RtlSetLastWin32Error` at `0x18005e08f`
- `ntdll!RtlFreeHeap` at `0x18005e13b`
- `ntdll!RtlFreeHeap` at `0x18005e13b`
- `ntdll!RtlAllocateHeap` at `0x18005e0d7`
- `ntdll!RtlAllocateHeap` at `0x18005e0d7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e0bf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e0bf`

## pseudocode

```c

```
