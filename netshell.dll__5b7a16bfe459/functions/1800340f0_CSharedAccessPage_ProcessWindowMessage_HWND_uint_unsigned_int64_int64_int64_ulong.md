# CSharedAccessPage::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x1800340f0`
- end: `0x180034212`
- name: `?ProcessWindowMessage@CSharedAccessPage@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `290`
- prototype: `__int64 __usercall@<rax>(CSharedAccessPage *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180033e1c`
- `0x180033fd4`
- `0x1800340f0`
- `0x180065010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x180034192`
- `USER32!SetWindowLongPtrW` at `0x180034192`
- `USER32!SendDlgItemMessageW` at `0x180034145`
- `USER32!SendDlgItemMessageW` at `0x180034145`
- `USER32!DestroyIcon` at `0x180034153`
- `USER32!DestroyIcon` at `0x180034153`

## pseudocode

```c

```
