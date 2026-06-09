# _CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$3

- ea: `0x18001dcf5`
- end: `0x18001dd01`
- name: `_CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011e90`

## pseudocode

```c
void __fastcall CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  COwnerListFile::~COwnerListFile((COwnerListFile *)(a2 + 80));
}

```

## disassembly

```asm
0x18001dcf5  lea     rcx, [rdx+50h]; this
0x18001dcfc  jmp     ??1COwnerListFile@@UEAA@XZ; COwnerListFile::~COwnerListFile(void)
```
