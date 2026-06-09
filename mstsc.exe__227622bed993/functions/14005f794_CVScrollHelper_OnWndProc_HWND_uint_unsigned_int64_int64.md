# CVScrollHelper::OnWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14005f794`
- end: `0x14005fa1b`
- name: `?OnWndProc@CVScrollHelper@@QEAAXPEAUHWND__@@I_K_J@Z`
- size: `647`
- prototype: `void __usercall(CVScrollHelper *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047e30`
- `0x140052b20`
- `0x140052e40`

## callees

- `0x14005f6c8`
- `0x14005f794`
- `0x14005fa24`
- `0x14005fbf0`
- `0x14005fc58`
- `0x140111220`

## import_xrefs

- `USER32!ScrollWindow` at `0x14005f9e0`
- `USER32!ScrollWindow` at `0x14005f9e0`
- `USER32!GetScrollInfo` at `0x14005f85c`
- `USER32!GetScrollInfo` at `0x14005f9c1`
- `USER32!GetScrollInfo` at `0x14005f85c`
- `USER32!GetScrollInfo` at `0x14005f9c1`
- `USER32!GetDpiForWindow` at `0x14005f887`
- `USER32!GetDpiForWindow` at `0x14005f887`
- `USER32!SetScrollInfo` at `0x14005f9b1`
- `USER32!SetScrollInfo` at `0x14005f9b1`
- `USER32!MapWindowPoints` at `0x14005f96a`
- `USER32!MapWindowPoints` at `0x14005f96a`
- `USER32!UpdateWindow` at `0x14005f9ea`
- `USER32!UpdateWindow` at `0x14005f9ea`
- `USER32!GetWindowRect` at `0x14005f93c`
- `USER32!GetWindowRect` at `0x14005f93c`
- `USER32!IsChild` at `0x14005f94e`
- `USER32!IsChild` at `0x14005f94e`
- `KERNEL32!MulDiv` at `0x14005f8a6`
- `KERNEL32!MulDiv` at `0x14005f8a6`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14005f811`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14005f811`

## pseudocode

```c

```
