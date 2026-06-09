# ShimHelper::_Compat_DetachInputQueue_ThreadProc

- ea: `0x1801ce590`
- end: `0x1801ce753`
- name: `ShimHelper::_Compat_DetachInputQueue_ThreadProc`
- size: `451`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1801ce348`
- `0x1801ce590`
- `0x1801ce828`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1801ce6cc`
- `KERNEL32!CreateThread` at `0x1801ce6cc`
- `KERNEL32!LocalFree` at `0x1801ce73b`
- `KERNEL32!LocalFree` at `0x1801ce73b`
- `KERNEL32!CloseHandle` at `0x1801ce6da`
- `KERNEL32!CloseHandle` at `0x1801ce6da`
- `USER32!GetPropW` at `0x1801ce5fc`
- `USER32!GetPropW` at `0x1801ce5fc`
- `USER32!SetPropW` at `0x1801ce62f`
- `USER32!SetPropW` at `0x1801ce66c`
- `USER32!SetPropW` at `0x1801ce62f`
- `USER32!SetPropW` at `0x1801ce66c`
- `USER32!RemovePropW` at `0x1801ce704`
- `USER32!RemovePropW` at `0x1801ce71b`
- `USER32!RemovePropW` at `0x1801ce704`
- `USER32!RemovePropW` at `0x1801ce71b`
- `USER32!GetWindowThreadProcessId` at `0x1801ce5cd`
- `USER32!GetWindowThreadProcessId` at `0x1801ce5cd`
- `USER32!AllowSetForegroundWindow` at `0x1801ce64f`
- `USER32!AllowSetForegroundWindow` at `0x1801ce64f`
- `USER32!SetWindowLongPtrW` at `0x1801ce618`
- `USER32!SetWindowLongPtrW` at `0x1801ce643`
- `USER32!SetWindowLongPtrW` at `0x1801ce6f3`
- `USER32!SetWindowLongPtrW` at `0x1801ce618`
- `USER32!SetWindowLongPtrW` at `0x1801ce643`
- `USER32!SetWindowLongPtrW` at `0x1801ce6f3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801ce5a6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801ce5a6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801ce732`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801ce732`

## string_xrefs

- `0x1801ce65f`: `_IE_Compat_No_SFW`
- `0x1801ce714`: `_IE_Compat_No_SFW`

## pseudocode

```c

```
