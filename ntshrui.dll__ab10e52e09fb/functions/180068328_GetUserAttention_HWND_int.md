# GetUserAttention(HWND__ *,int)

- ea: `0x180068328`
- end: `0x1800683e2`
- name: `?GetUserAttention@@YAXPEAUHWND__@@H@Z`
- size: `186`
- prototype: `void __fastcall(HWND, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800652cc`
- `0x180065460`
- `0x1800658b0`
- `0x180068b38`
- `0x18006939c`

## callees

- `0x180068328`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006839f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006839f`
- `USER32!FlashWindowEx` at `0x180068370`
- `USER32!FlashWindowEx` at `0x180068370`
- `USER32!GetAncestor` at `0x180068341`
- `USER32!GetAncestor` at `0x180068341`

## pseudocode

```c

```
