# CSharePagePerm::_OnNotify(HWND__ *,int,tagNMHDR *)

- ea: `0x18006bd18`
- end: `0x18006be4b`
- name: `?_OnNotify@CSharePagePerm@@AEAA_JPEAUHWND__@@HPEAUtagNMHDR@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(CSharePagePerm *__hidden this, HWND, int, struct tagNMHDR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006ce90`

## callees

- `0x18006bd18`
- `0x18006be54`
- `0x18006c418`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x18006be1a`
- `ntdll!WinSqmAddToStream` at `0x18006be1a`
- `SHELL32!ShellExecuteW` at `0x18006be37`
- `SHELL32!ShellExecuteW` at `0x18006be37`
- `USER32!SetWindowLongPtrW` at `0x18006bd8c`
- `USER32!SetWindowLongPtrW` at `0x18006bd8c`
- `USER32!SendMessageW` at `0x18006bd55`
- `USER32!SendMessageW` at `0x18006bd55`

## string_xrefs

- `0x18006be27`: `https://go.microsoft.com/fwlink/p/?linkid=869763`

## pseudocode

```c

```
