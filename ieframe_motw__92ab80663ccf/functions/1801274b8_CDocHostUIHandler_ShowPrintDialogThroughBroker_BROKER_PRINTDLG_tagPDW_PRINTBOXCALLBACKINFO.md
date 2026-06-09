# CDocHostUIHandler::ShowPrintDialogThroughBroker(_BROKER_PRINTDLG *,tagPDW *,PRINTBOXCALLBACKINFO *)

- ea: `0x1801274b8`
- end: `0x180127950`
- name: `?ShowPrintDialogThroughBroker@CDocHostUIHandler@@IEAAJPEAU_BROKER_PRINTDLG@@PEAUtagPDW@@PEAUPRINTBOXCALLBACKINFO@@@Z`
- size: `1176`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, struct _BROKER_PRINTDLG *, struct tagPDW *, struct PRINTBOXCALLBACKINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180126f88`

## callees

- `0x1800cd150`
- `0x1800cd2a4`
- `0x1800cd638`
- `0x1801274b8`
- `0x180594010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1801275a6`
- `msvcrt!memcpy_s` at `0x18012766e`
- `msvcrt!memcpy_s` at `0x18012783a`
- `msvcrt!memcpy_s` at `0x1801278fc`
- `msvcrt!memcpy_s` at `0x1801275a6`
- `msvcrt!memcpy_s` at `0x18012766e`
- `msvcrt!memcpy_s` at `0x18012783a`
- `msvcrt!memcpy_s` at `0x1801278fc`
- `KERNEL32!GlobalAlloc` at `0x1801277ea`
- `KERNEL32!GlobalAlloc` at `0x1801278af`
- `KERNEL32!GlobalAlloc` at `0x1801277ea`
- `KERNEL32!GlobalAlloc` at `0x1801278af`
- `KERNEL32!GlobalLock` at `0x180127562`
- `KERNEL32!GlobalLock` at `0x1801275f8`
- `KERNEL32!GlobalLock` at `0x18012781b`
- `KERNEL32!GlobalLock` at `0x1801278dd`
- `KERNEL32!GlobalLock` at `0x180127562`
- `KERNEL32!GlobalLock` at `0x1801275f8`
- `KERNEL32!GlobalLock` at `0x18012781b`
- `KERNEL32!GlobalLock` at `0x1801278dd`
- `KERNEL32!GlobalUnlock` at `0x1801275bd`
- `KERNEL32!GlobalUnlock` at `0x180127685`
- `KERNEL32!GlobalUnlock` at `0x18012784a`
- `KERNEL32!GlobalUnlock` at `0x18012790c`
- `KERNEL32!GlobalUnlock` at `0x1801275bd`
- `KERNEL32!GlobalUnlock` at `0x180127685`
- `KERNEL32!GlobalUnlock` at `0x18012784a`
- `KERNEL32!GlobalUnlock` at `0x18012790c`
- `KERNEL32!GlobalSize` at `0x180127808`
- `KERNEL32!GlobalSize` at `0x1801278ca`
- `KERNEL32!GlobalSize` at `0x180127808`
- `KERNEL32!GlobalSize` at `0x1801278ca`
- `KERNEL32!GlobalReAlloc` at `0x1801277cd`
- `KERNEL32!GlobalReAlloc` at `0x180127895`
- `KERNEL32!GlobalReAlloc` at `0x1801277cd`
- `KERNEL32!GlobalReAlloc` at `0x180127895`
- `KERNEL32!GetLastError` at `0x1801275cb`
- `KERNEL32!GetLastError` at `0x180127693`
- `KERNEL32!GetLastError` at `0x180127864`
- `KERNEL32!GetLastError` at `0x180127926`
- `KERNEL32!GetLastError` at `0x1801275cb`
- `KERNEL32!GetLastError` at `0x180127693`
- `KERNEL32!GetLastError` at `0x180127864`
- `KERNEL32!GetLastError` at `0x180127926`
- `USER32!AllowSetForegroundWindow` at `0x1801276e7`
- `USER32!AllowSetForegroundWindow` at `0x1801276e7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180127585`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18012764d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180127585`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18012764d`

## pseudocode

```c

```
