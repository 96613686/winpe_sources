# CVScrollHelper::OnWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140061904`
- end: `0x140061b8b`
- name: `?OnWndProc@CVScrollHelper@@QEAAXPEAUHWND__@@I_K_J@Z`
- size: `647`
- prototype: `void __usercall(CVScrollHelper *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140049fa0`
- `0x140054c90`
- `0x140054fb0`

## callees

- `0x140061838`
- `0x140061904`
- `0x140061b94`
- `0x140061d60`
- `0x140061dc8`
- `0x140113390`

## import_xrefs

- `USER32!ScrollWindow` at `0x140061b50`
- `USER32!ScrollWindow` at `0x140061b50`
- `USER32!GetScrollInfo` at `0x1400619cc`
- `USER32!GetScrollInfo` at `0x140061b31`
- `USER32!GetScrollInfo` at `0x1400619cc`
- `USER32!GetScrollInfo` at `0x140061b31`
- `USER32!GetDpiForWindow` at `0x1400619f7`
- `USER32!GetDpiForWindow` at `0x1400619f7`
- `USER32!SetScrollInfo` at `0x140061b21`
- `USER32!SetScrollInfo` at `0x140061b21`
- `USER32!MapWindowPoints` at `0x140061ada`
- `USER32!MapWindowPoints` at `0x140061ada`
- `USER32!UpdateWindow` at `0x140061b5a`
- `USER32!UpdateWindow` at `0x140061b5a`
- `USER32!GetWindowRect` at `0x140061aac`
- `USER32!GetWindowRect` at `0x140061aac`
- `USER32!IsChild` at `0x140061abe`
- `USER32!IsChild` at `0x140061abe`
- `KERNEL32!MulDiv` at `0x140061a16`
- `KERNEL32!MulDiv` at `0x140061a16`
- `COMCTL32!__imp_SetWindowSubclass` at `0x140061981`
- `COMCTL32!__imp_SetWindowSubclass` at `0x140061981`

## pseudocode

```c

```
