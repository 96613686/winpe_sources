# CreateToolhelp32Snapshot

- ea: `0x180073800`
- end: `0x180073b17`
- name: `CreateToolhelp32Snapshot`
- size: `791`
- prototype: `HANDLE __stdcall(DWORD dwFlags, DWORD th32ProcessID)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000ccf0`
- `0x180027370`
- `0x18002f7d8`
- `0x18004ebb0`
- `0x180073800`

## import_xrefs

- `ntdll!NtUnmapViewOfSection` at `0x180073a84`
- `ntdll!NtUnmapViewOfSection` at `0x180083b46`
- `ntdll!NtUnmapViewOfSection` at `0x180073a84`
- `ntdll!NtUnmapViewOfSection` at `0x180083b46`
- `ntdll!NtClose` at `0x180073a6a`
- `ntdll!NtClose` at `0x180083b2c`
- `ntdll!NtClose` at `0x180073a6a`
- `ntdll!NtClose` at `0x180083b2c`
- `ntdll!NtFreeVirtualMemory` at `0x180073abb`
- `ntdll!NtFreeVirtualMemory` at `0x180083b7a`
- `ntdll!NtFreeVirtualMemory` at `0x180073abb`
- `ntdll!NtFreeVirtualMemory` at `0x180083b7a`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180073ad1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180073aea`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180083b90`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180083ba9`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180073ad1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180073aea`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180083b90`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x180083ba9`

## pseudocode

```c

```
