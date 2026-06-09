# _CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s2__

- ea: `0x18001e2b0`
- end: `0x18001e2ca`
- name: `_CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s2__`
- size: `26`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s2__()
{
  qword_1800286C0 = &CPath::`vftable';
  CString::~CString((CString *)&qword_1800286C0);
}

```

## disassembly

```asm
0x18001e2b0  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x18001e2b7  lea     rcx, qword_1800286C0; this
0x18001e2be  mov     cs:qword_1800286C0, rax
0x18001e2c5  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
