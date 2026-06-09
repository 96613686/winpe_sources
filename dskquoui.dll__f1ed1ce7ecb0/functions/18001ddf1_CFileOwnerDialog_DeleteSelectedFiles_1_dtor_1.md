# _CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor$1

- ea: `0x18001ddf1`
- end: `0x18001ddfd`
- name: `_CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011dd0`

## pseudocode

```c
void __fastcall CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(a2 + 128);
}

```

## disassembly

```asm
0x18001ddf1  lea     rcx, [rdx+80h]
0x18001ddf8  jmp     ??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ; CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)
```
