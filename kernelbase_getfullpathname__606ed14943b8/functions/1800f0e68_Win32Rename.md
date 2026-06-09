# Win32Rename

- ea: `0x1800f0e68`
- end: `0x1800f1019`
- name: `Win32Rename`
- size: `433`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800f0d80`

## callees

- `0x18004b9d0`
- `0x1800f0e68`
- `0x180194eb9`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1800f0f47`
- `ntdll!NtSetInformationFile` at `0x1800f0f47`
- `ntdll!RtlSetLastWin32Error` at `0x1800f1007`
- `ntdll!RtlSetLastWin32Error` at `0x1800f1007`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f0ec6`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f0ec6`
- `ntdll!RtlFreeHeap` at `0x1800f0f6e`
- `ntdll!RtlFreeHeap` at `0x1800f0f8c`
- `ntdll!RtlFreeHeap` at `0x1800f0ff9`
- `ntdll!RtlFreeHeap` at `0x1800f0f6e`
- `ntdll!RtlFreeHeap` at `0x1800f0f8c`
- `ntdll!RtlFreeHeap` at `0x1800f0ff9`
- `ntdll!RtlAllocateHeap` at `0x1800f0ef8`
- `ntdll!RtlAllocateHeap` at `0x1800f0ef8`

## pseudocode

```c

```
