# LoadFile

- ea: `0x180020d14`
- end: `0x180020f8c`
- name: `LoadFile`
- size: `632`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180020b18`
- `0x1800d0b08`

## callees

- `0x18000e4a0`
- `0x180020d14`
- `0x18004e1f4`
- `0x18004e580`
- `0x18007e650`
- `0x18007f140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020f2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020e91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f42`
- `rtutils!TracePrintfExA` at `0x180020e18`
- `rtutils!TracePrintfExA` at `0x180020ec8`
- `rtutils!TracePrintfExA` at `0x180020e18`
- `rtutils!TracePrintfExA` at `0x180020ec8`

## string_xrefs

- `0x180020e0c`: `ReadPhonebookFile: g_hmutexPb not initialized`
- `0x180020ebe`: `ReadPhonebookFile: WaitForSingleObject Failed: Ret:%d, Error:%d`

## pseudocode

```c

```
