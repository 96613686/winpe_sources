# _CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s1__

- ea: `0x18001e290`
- end: `0x18001e2aa`
- name: `_CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s1__`
- size: `26`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s1__()
{
  qword_1800286A8 = &CPath::`vftable';
  CString::~CString((CString *)&qword_1800286A8);
}

```

## disassembly

```asm
0x18001e290  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x18001e297  lea     rcx, qword_1800286A8; this
0x18001e29e  mov     cs:qword_1800286A8, rax
0x18001e2a5  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
