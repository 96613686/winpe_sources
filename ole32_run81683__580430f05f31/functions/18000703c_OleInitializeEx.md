# OleInitializeEx

- ea: `0x18000703c`
- end: `0x180007175`
- name: `OleInitializeEx`
- size: `313`
- prototype: `HRESULT __stdcall(LPVOID pvReserved)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800054a0`
- `0x180007030`
- `0x180085a00`

## callees

- `0x180005744`
- `0x180005e40`
- `0x18000703c`
- `0x180007244`
- `0x18000895c`
- `0x18000a4a8`
- `0x180059194`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180007106`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180007106`
- `USER32!RegisterWindowMessageW` at `0x180007122`
- `USER32!RegisterWindowMessageW` at `0x180007135`
- `USER32!RegisterWindowMessageW` at `0x180007122`
- `USER32!RegisterWindowMessageW` at `0x180007135`
- `combase!__imp_?CoVrfNotifyOleInit@@YAXXZ` at `0x1800070c3`
- `combase!__imp_?CoVrfNotifyOleInit@@YAXXZ` at `0x1800070c3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007056`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007056`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000716a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000716a`

## string_xrefs

- `0x18000711b`: `OM_POST_WM_COMMAND`

## pseudocode

```c

```
