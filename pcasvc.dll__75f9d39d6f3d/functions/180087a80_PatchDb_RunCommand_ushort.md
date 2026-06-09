# PatchDb_RunCommand(ushort *)

- ea: `0x180087a80`
- end: `0x180087c19`
- name: `?PatchDb_RunCommand@@YAKPEAG@Z`
- size: `409`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180087254`
- `0x180087480`
- `0x1800877d0`
- `0x180088060`

## callees

- `0x18000c018`
- `0x180012920`
- `0x18007a9cf`
- `0x180087a80`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180087b90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180087b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087baa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180087b4b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180087b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180087ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180087ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087beb`

## string_xrefs

- `0x180087b5f`: `Failed to create process [%ws] %d`
- `0x180087b71`: `PatchDb_RunCommand`
- `0x180087bc6`: `PatchDb_RunCommand`

## pseudocode

```c

```
