# RefreshDisplay(_GPOINFO *)

- ea: `0x18009ac70`
- end: `0x18009af8c`
- name: `?RefreshDisplay@@YAHPEAU_GPOINFO@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(struct _GPOINFO *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`

## callees

- `0x18001ae60`
- `0x18002c690`
- `0x18005334c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x18009ac70`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009aea7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009aea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af4b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009ade9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009ade9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009aef9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009aef9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af04`

## string_xrefs

- `0x18009ad5e`: `RefreshDisplay: Failed to impersonate user`
- `0x18009ad83`: `RefreshDisplay: Failed to impersonate user`
- `0x18009aec2`: `RefreshDisplay: Completed WaitForSingleObject.`
- `0x18009aee5`: `RefreshDisplay: Completed WaitForSingleObject.`

## pseudocode

```c

```
