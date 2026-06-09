# _CFileOwnerDialog::OnLVN_GetDispInfo_::_2_::_dynamic_atexit_destructor_for__strPath__

- ea: `0x18001e2f0`
- end: `0x18001e30a`
- name: `_CFileOwnerDialog::OnLVN_GetDispInfo_::_2_::_dynamic_atexit_destructor_for__strPath__`
- size: `26`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OnLVN_GetDispInfo_::_2_::_dynamic_atexit_destructor_for__strPath__()
{
  qword_180028678 = &CPath::`vftable';
  CString::~CString((CString *)&qword_180028678);
}

```

## disassembly

```asm
0x18001e2f0  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x18001e2f7  lea     rcx, qword_180028678; this
0x18001e2fe  mov     cs:qword_180028678, rax
0x18001e305  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
