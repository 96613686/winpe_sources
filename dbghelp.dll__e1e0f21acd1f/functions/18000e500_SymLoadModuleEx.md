# SymLoadModuleEx

- ea: `0x18000e500`
- end: `0x18000e5d4`
- name: `SymLoadModuleEx`
- size: `212`
- prototype: `DWORD64 __stdcall(HANDLE hProcess, HANDLE hFile, PCSTR ImageName, PCSTR ModuleName, DWORD64 BaseOfDll, DWORD DllSize, PMODLOAD_DATA Data, DWORD Flags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e4c0`

## callees

- `0x1800089f0`
- `0x1800091a0`
- `0x18000d5c0`
- `0x18000e500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e57f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e57f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5bf`

## pseudocode

```c

```
