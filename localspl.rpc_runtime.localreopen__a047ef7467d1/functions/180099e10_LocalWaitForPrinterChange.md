# LocalWaitForPrinterChange

- ea: `0x180099e10`
- end: `0x180099ffd`
- name: `LocalWaitForPrinterChange`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004a38`
- `0x180008520`
- `0x180008560`
- `0x18003e984`
- `0x18003ea2c`
- `0x180054638`
- `0x180099e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099e82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099e82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099ef1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099f83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099f70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099f79`
- `SPOOLSS!WaitForPrinterChange` at `0x180099ff2`
- `SPOOLSS!WaitForPrinterChange` at `0x180099ff2`
- `SPOOLSS!DllFreeSplMem` at `0x180099fab`
- `SPOOLSS!DllFreeSplMem` at `0x180099fab`

## string_xrefs

- `0x180099e99`: `CreateEvent for ChangeEvent failed: Error %d`

## pseudocode

```c

```
