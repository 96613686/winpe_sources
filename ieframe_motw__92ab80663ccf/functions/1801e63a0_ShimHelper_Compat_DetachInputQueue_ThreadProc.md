# ShimHelper::_Compat_DetachInputQueue_ThreadProc

- ea: `0x1801e63a0`
- end: `0x1801e65c2`
- name: `ShimHelper::_Compat_DetachInputQueue_ThreadProc`
- size: `546`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1801e6180`
- `0x1801e63a0`
- `0x1801e66b4`
- `0x180594010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1801e6510`
- `KERNEL32!CreateThread` at `0x1801e6510`
- `KERNEL32!LocalFree` at `0x1801e65a3`
- `KERNEL32!LocalFree` at `0x1801e65a3`
- `KERNEL32!CloseHandle` at `0x1801e6524`
- `KERNEL32!CloseHandle` at `0x1801e6524`
- `USER32!GetPropW` at `0x1801e6418`
- `USER32!GetPropW` at `0x1801e6418`
- `USER32!SetPropW` at `0x1801e6457`
- `USER32!SetPropW` at `0x1801e64a6`
- `USER32!SetPropW` at `0x1801e6457`
- `USER32!SetPropW` at `0x1801e64a6`
- `USER32!RemovePropW` at `0x1801e655a`
- `USER32!RemovePropW` at `0x1801e6577`
- `USER32!RemovePropW` at `0x1801e655a`
- `USER32!RemovePropW` at `0x1801e6577`
- `USER32!GetWindowThreadProcessId` at `0x1801e63e3`
- `USER32!GetWindowThreadProcessId` at `0x1801e63e3`
- `USER32!AllowSetForegroundWindow` at `0x1801e6483`
- `USER32!AllowSetForegroundWindow` at `0x1801e6483`
- `USER32!SetWindowLongPtrW` at `0x1801e643a`
- `USER32!SetWindowLongPtrW` at `0x1801e6471`
- `USER32!SetWindowLongPtrW` at `0x1801e6543`
- `USER32!SetWindowLongPtrW` at `0x1801e643a`
- `USER32!SetWindowLongPtrW` at `0x1801e6471`
- `USER32!SetWindowLongPtrW` at `0x1801e6543`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801e63b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801e63b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801e6594`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801e6594`

## string_xrefs

- `0x1801e6499`: `_IE_Compat_No_SFW`
- `0x1801e6570`: `_IE_Compat_No_SFW`

## pseudocode

```c

```
