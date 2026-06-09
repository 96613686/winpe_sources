# SHComputeDPI(HWND__ *,int *,int *)

- ea: `0x180061504`
- end: `0x1800615dd`
- name: `?SHComputeDPI@@YAXPEAUHWND__@@PEAH1@Z`
- size: `217`
- prototype: `void __fastcall(HWND, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800636f0`

## callees

- `0x180061504`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180061532`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180061532`
- `GDI32!GetDeviceCaps` at `0x180061595`
- `GDI32!GetDeviceCaps` at `0x1800615a5`
- `GDI32!GetDeviceCaps` at `0x180061595`
- `GDI32!GetDeviceCaps` at `0x1800615a5`
- `USER32!GetDC` at `0x18006157f`
- `USER32!GetDC` at `0x18006157f`
- `USER32!ReleaseDC` at `0x1800615b2`
- `USER32!ReleaseDC` at `0x1800615b2`

## pseudocode

```c

```
