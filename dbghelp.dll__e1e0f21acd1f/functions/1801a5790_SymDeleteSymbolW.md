# SymDeleteSymbolW

- ea: `0x1801a5790`
- end: `0x1801a58a8`
- name: `SymDeleteSymbolW`
- size: `280`
- prototype: `BOOL __stdcall(HANDLE hProcess, ULONG64 BaseOfDll, PCWSTR Name, DWORD64 Address, DWORD Flags)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801a5730`

## callees

- `0x18000982c`
- `0x18000a820`
- `0x18000aeec`
- `0x1801a5790`
- `0x1801af6b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a57ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a57dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5802`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a57ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a57dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5802`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a5892`

## pseudocode

```c

```
