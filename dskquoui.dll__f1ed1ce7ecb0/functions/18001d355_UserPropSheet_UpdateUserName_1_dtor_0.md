# _UserPropSheet::UpdateUserName_::_1_::dtor$0

- ea: `0x18001d355`
- end: `0x18001d361`
- name: `_UserPropSheet::UpdateUserName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall UserPropSheet::UpdateUserName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CString::~CString((CString *)(a2 + 72));
}

```

## disassembly

```asm
0x18001d355  lea     rcx, [rdx+48h]; this
0x18001d35c  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```
