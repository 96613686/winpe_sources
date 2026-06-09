# CreateToolhelp32Snapshot

- ea: `0x18006c250`
- end: `0x18006c548`
- name: `CreateToolhelp32Snapshot`
- size: `760`
- prototype: `HANDLE __stdcall(DWORD dwFlags, DWORD th32ProcessID)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000f920`
- `0x180029380`
- `0x18002dc90`
- `0x18004a5d0`
- `0x18006c250`

## import_xrefs

- `ntdll!NtUnmapViewOfSection` at `0x18006c4ce`
- `ntdll!NtUnmapViewOfSection` at `0x18007b9d5`
- `ntdll!NtUnmapViewOfSection` at `0x18006c4ce`
- `ntdll!NtUnmapViewOfSection` at `0x18007b9d5`
- `ntdll!NtClose` at `0x18006c4ba`
- `ntdll!NtClose` at `0x18007b9c1`
- `ntdll!NtClose` at `0x18006c4ba`
- `ntdll!NtClose` at `0x18007b9c1`
- `ntdll!NtFreeVirtualMemory` at `0x18006c4ff`
- `ntdll!NtFreeVirtualMemory` at `0x18007ba03`
- `ntdll!NtFreeVirtualMemory` at `0x18006c4ff`
- `ntdll!NtFreeVirtualMemory` at `0x18007ba03`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006c50f`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006c522`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18007ba13`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18007ba26`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006c50f`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006c522`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18007ba13`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18007ba26`

## pseudocode

```c

```
