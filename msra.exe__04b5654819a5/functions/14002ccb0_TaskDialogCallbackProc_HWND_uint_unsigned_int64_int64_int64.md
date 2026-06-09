# TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x14002ccb0`
- end: `0x14002cd6f`
- name: `?TaskDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `191`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x14002c3b8`
- `0x14002ccb0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14002cd03`
- `KERNEL32!WaitForSingleObject` at `0x14002cd03`
- `USER32!SendMessageW` at `0x14002cce5`
- `USER32!SendMessageW` at `0x14002cce5`
- `USER32!PostMessageW` at `0x14002cd1f`
- `USER32!PostMessageW` at `0x14002cd1f`
- `OLEAUT32!__imp_SysAllocString` at `0x14002cd34`
- `OLEAUT32!__imp_SysAllocString` at `0x14002cd34`
- `OLEAUT32!__imp_SysFreeString` at `0x14002cd5a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002cd5a`

## pseudocode

```c

```
