# CscTppSimpleWorkItemCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180022310`
- end: `0x1800223ad`
- name: `?CscTppSimpleWorkItemCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `157`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022310`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002235c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002235c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002236f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002236f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022339`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022339`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022387`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022387`
- `KERNEL32!CallbackMayRunLong` at `0x1800223a5`
- `KERNEL32!CallbackMayRunLong` at `0x1800223a5`
- `KERNEL32!LocalFree` at `0x180022378`
- `KERNEL32!LocalFree` at `0x180022378`

## pseudocode

```c

```
