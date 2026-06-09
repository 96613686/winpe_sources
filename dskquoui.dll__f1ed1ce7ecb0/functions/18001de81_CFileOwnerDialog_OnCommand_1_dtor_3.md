# _CFileOwnerDialog::OnCommand_::_1_::dtor$3

- ea: `0x18001de81`
- end: `0x18001de8d`
- name: `_CFileOwnerDialog::OnCommand_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011e90`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OnCommand_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  COwnerListFile::~COwnerListFile((COwnerListFile *)(a2 + 64));
}

```

## disassembly

```asm
0x18001de81  lea     rcx, [rdx+40h]; this
0x18001de88  jmp     ??1COwnerListFile@@UEAA@XZ; COwnerListFile::~COwnerListFile(void)
```
