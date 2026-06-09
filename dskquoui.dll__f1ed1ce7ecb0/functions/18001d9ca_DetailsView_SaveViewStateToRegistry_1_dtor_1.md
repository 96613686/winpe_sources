# _DetailsView::SaveViewStateToRegistry_::_1_::dtor$1

- ea: `0x18001d9ca`
- end: `0x18001d9d6`
- name: `_DetailsView::SaveViewStateToRegistry_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007700`

## pseudocode

```c
void __fastcall DetailsView::SaveViewStateToRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CArray<COwnerListFile>::~CArray<COwnerListFile>(a2 + 64);
}

```

## disassembly

```asm
0x18001d9ca  lea     rcx, [rdx+40h]
0x18001d9d1  jmp     ??1?$CArray@VCOwnerListFile@@@@UEAA@XZ; CArray<COwnerListFile>::~CArray<COwnerListFile>(void)
```
