# _CFileOwnerDialog::OnCommand_::_1_::dtor$7

- ea: `0x18001de93`
- end: `0x18001de9f`
- name: `_CFileOwnerDialog::OnCommand_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011e90`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OnCommand_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  COwnerListFile::~COwnerListFile((COwnerListFile *)(a2 + 48));
}

```

## disassembly

```asm
0x18001de93  lea     rcx, [rdx+30h]; this
0x18001de9a  jmp     ??1COwnerListFile@@UEAA@XZ; COwnerListFile::~COwnerListFile(void)
```
