# OleInitializeEx

- ea: `0x18001b63c`
- end: `0x18001b79e`
- name: `OleInitializeEx`
- size: `354`
- prototype: `HRESULT __stdcall(LPVOID pvReserved)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002e7a0`
- `0x1800393c0`
- `0x1800800d0`

## callees

- `0x18001b63c`
- `0x18001bb48`
- `0x18001bc24`
- `0x18001c18c`
- `0x18001d030`
- `0x18001d12c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001b721`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001b721`
- `USER32!RegisterWindowMessageW` at `0x18001b743`
- `USER32!RegisterWindowMessageW` at `0x18001b75c`
- `USER32!RegisterWindowMessageW` at `0x18001b743`
- `USER32!RegisterWindowMessageW` at `0x18001b75c`
- `combase!__imp_?CoVrfNotifyOleInit@@YAXXZ` at `0x18001b6cf`
- `combase!__imp_?CoVrfNotifyOleInit@@YAXXZ` at `0x18001b6cf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b65d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b65d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b78d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b78d`

## string_xrefs

- `0x18001b73c`: `OM_POST_WM_COMMAND`

## pseudocode

```c

```
