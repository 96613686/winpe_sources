# _CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$1

- ea: `0x18001de6f`
- end: `0x18001de7b`
- name: `_CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011dd0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(a2 + 192);
}

```

## disassembly

```asm
0x18001de6f  lea     rcx, [rdx+0C0h]
0x18001de76  jmp     ??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ; CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)
```
