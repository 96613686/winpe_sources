# SymGetSearchPathW

- ea: `0x1801a6b00`
- end: `0x1801a6b5b`
- name: `SymGetSearchPathW`
- size: `91`
- prototype: `BOOL __stdcall(HANDLE hProcess, PWSTR SearchPathA, DWORD SearchPathLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001a080`

## callees

- `0x18000aeec`
- `0x180012ed4`
- `0x1801a6b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6b20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6b48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6b20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6b48`

## pseudocode

```c

```
