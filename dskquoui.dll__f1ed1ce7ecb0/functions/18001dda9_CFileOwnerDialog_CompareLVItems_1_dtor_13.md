# _CFileOwnerDialog::CompareLVItems_::_1_::dtor$13

- ea: `0x18001dda9`
- end: `0x18001ddb5`
- name: `_CFileOwnerDialog::CompareLVItems_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011e90`

## pseudocode

```c
void __fastcall CFileOwnerDialog::CompareLVItems_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  COwnerListFile::~COwnerListFile((COwnerListFile *)(a2 + 40));
}

```

## disassembly

```asm
0x18001dda9  lea     rcx, [rdx+28h]; this
0x18001ddb0  jmp     ??1COwnerListFile@@UEAA@XZ; COwnerListFile::~COwnerListFile(void)
```
