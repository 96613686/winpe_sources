# _CFileOwnerDialog::OnCommand_::_1_::dtor$1

- ea: `0x18001dbba`
- end: `0x18001dbc6`
- name: `_CFileOwnerDialog::OnCommand_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OnCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CString::~CString((CString *)(a2 + 64));
}

```

## disassembly

```asm
0x18001dbba  lea     rcx, [rdx+40h]; this
0x18001dbc1  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
