# GetModuleHandleExA

- ea: `0x1800e2ea0`
- end: `0x1800e3070`
- name: `GetModuleHandleExA`
- size: `464`
- prototype: `BOOL __stdcall(DWORD dwFlags, LPCSTR lpModuleName, HMODULE *phModule)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18004b9d0`
- `0x1800e2ea0`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800e2ff0`
- `ntdll!RtlFreeUnicodeString` at `0x1800e2ff0`
- `ntdll!RtlInitUnicodeString` at `0x1800e300a`
- `ntdll!RtlInitUnicodeString` at `0x1800e300a`
- `ntdll!RtlSetLastWin32Error` at `0x1800e3056`
- `ntdll!RtlSetLastWin32Error` at `0x1800e3056`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e2f3e`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e2f3e`
- `ntdll!LdrGetDllHandle` at `0x1800e3022`
- `ntdll!LdrGetDllHandle` at `0x1800e3022`
- `ntdll!RtlPcToFileHeader` at `0x1800e2f8f`
- `ntdll!RtlPcToFileHeader` at `0x1800e2f8f`
- `ntdll!LdrAddRefDll` at `0x1800e2fc1`
- `ntdll!LdrAddRefDll` at `0x1800e2fc1`

## pseudocode

```c

```
