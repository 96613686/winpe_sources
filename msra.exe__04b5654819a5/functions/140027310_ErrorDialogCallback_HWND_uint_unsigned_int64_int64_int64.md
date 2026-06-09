# ErrorDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x140027310`
- end: `0x14002739d`
- name: `?ErrorDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `141`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140027310`
- `0x14002c3b8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14002732f`
- `KERNEL32!WaitForSingleObject` at `0x14002732f`
- `USER32!MessageBeep` at `0x140027351`
- `USER32!MessageBeep` at `0x140027351`
- `USER32!SetForegroundWindow` at `0x140027342`
- `USER32!SetForegroundWindow` at `0x140027342`
- `OLEAUT32!__imp_SysAllocString` at `0x140027362`
- `OLEAUT32!__imp_SysAllocString` at `0x140027362`
- `OLEAUT32!__imp_SysFreeString` at `0x140027388`
- `OLEAUT32!__imp_SysFreeString` at `0x140027388`

## string_xrefs

- `0x140027376`: `REMOTE_ASSISTANCE_CREATE_FIREWALL_EXCEPTION`

## pseudocode

```c

```
