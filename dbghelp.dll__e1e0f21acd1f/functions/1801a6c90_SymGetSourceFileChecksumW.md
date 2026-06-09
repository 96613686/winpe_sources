# SymGetSourceFileChecksumW

- ea: `0x1801a6c90`
- end: `0x1801a6d7b`
- name: `SymGetSourceFileChecksumW`
- size: `235`
- prototype: `BOOL __stdcall(HANDLE hProcess, ULONG64 Base, PCWSTR FileSpec, DWORD *pCheckSumType, BYTE *pChecksum, DWORD checksumSize, DWORD *pActualBytesWritten)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1801a6c20`

## callees

- `0x18000982c`
- `0x18000a820`
- `0x18000aeec`
- `0x180194fa4`
- `0x1801a6c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6cf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6cf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a6d65`

## pseudocode

```c

```
