# SymGetTypeFromNameW

- ea: `0x1801a7540`
- end: `0x1801a764c`
- name: `SymGetTypeFromNameW`
- size: `268`
- prototype: `BOOL __stdcall(HANDLE hProcess, ULONG64 BaseOfDll, PCWSTR Name, PSYMBOL_INFOW Symbol)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1801a7470`

## callees

- `0x1800089f0`
- `0x180008ad0`
- `0x18000982c`
- `0x18000a820`
- `0x18000aeec`
- `0x180018e6c`
- `0x180169420`
- `0x1801925e4`
- `0x1801a7540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a7591`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a7591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a756b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a756b`

## pseudocode

```c

```
