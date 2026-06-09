# _CFileOwnerDialog::InitializeOwnerCombo_::_1_::dtor$1

- ea: `0x18001d4fe`
- end: `0x18001d50a`
- name: `_CFileOwnerDialog::InitializeOwnerCombo_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::InitializeOwnerCombo_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CString::~CString((CString *)(a2 + 80));
}

```

## disassembly

```asm
0x18001d4fe  lea     rcx, [rdx+50h]; this
0x18001d505  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
