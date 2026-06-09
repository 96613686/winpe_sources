# _DetailsView::CreateToolBar_::_1_::dtor$3

- ea: `0x18001d39d`
- end: `0x18001d3a9`
- name: `_DetailsView::CreateToolBar_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007788`

## pseudocode

```c
__int64 __fastcall DetailsView::CreateToolBar_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return array_autoptr<unsigned short>::~array_autoptr<unsigned short>(a2 + 224);
}

```

## disassembly

```asm
0x18001d39d  lea     rcx, [rdx+0E0h]
0x18001d3a4  jmp     ??1?$array_autoptr@G@@UEAA@XZ; array_autoptr<ushort>::~array_autoptr<ushort>(void)
```
