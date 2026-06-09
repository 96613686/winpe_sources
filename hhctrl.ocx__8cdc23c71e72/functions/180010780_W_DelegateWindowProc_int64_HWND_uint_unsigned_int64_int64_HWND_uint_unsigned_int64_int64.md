# W_DelegateWindowProc(__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180010780`
- end: `0x1800107d2`
- name: `?W_DelegateWindowProc@@YA_JP6A_JPEAUHWND__@@I_K_J@Z0I12@Z`
- size: `82`
- prototype: `__int64 __fastcall(WNDPROC lpPrevWndFunc, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a670`
- `0x18000a750`
- `0x18000a810`
- `0x18000a8e0`
- `0x18000a910`
- `0x18000f510`
- `0x18000f670`
- `0x18000f760`
- `0x18001d040`
- `0x18003afd0`
- `0x18003b6a0`
- `0x18004d270`
- `0x18004dc90`
- `0x18004de60`
- `0x18004df00`

## callees

- `0x180010780`

## import_xrefs

- `USER32!CallWindowProcA` at `0x1800107c3`
- `USER32!CallWindowProcA` at `0x1800107c3`
- `USER32!CallWindowProcW` at `0x1800107bb`
- `USER32!CallWindowProcW` at `0x1800107bb`
- `USER32!IsWindowUnicode` at `0x180010798`
- `USER32!IsWindowUnicode` at `0x180010798`

## pseudocode

```c

```
