# _DetailsView::CreateToolBar_::_1_::dtor$1

- ea: `0x18001d38b`
- end: `0x18001d397`
- name: `_DetailsView::CreateToolBar_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007700`

## pseudocode

```c
void __fastcall DetailsView::CreateToolBar_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CArray<COwnerListFile>::~CArray<COwnerListFile>(a2 + 96);
}

```

## disassembly

```asm
0x18001d38b  lea     rcx, [rdx+60h]
0x18001d392  jmp     ??1?$CArray@VCOwnerListFile@@@@UEAA@XZ; CArray<COwnerListFile>::~CArray<COwnerListFile>(void)
```
