# _DetailsView::CreateVolumeDisplayName_::_1_::dtor$0

- ea: `0x18001d3e5`
- end: `0x18001d3f1`
- name: `_DetailsView::CreateVolumeDisplayName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005bf0`

## pseudocode

```c
void **__fastcall DetailsView::CreateVolumeDisplayName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(a2 + 184);
}

```

## disassembly

```asm
0x18001d3e5  lea     rcx, [rdx+0B8h]
0x18001d3ec  jmp     ??1?$com_autoptr@UIShellFolder@@@@UEAA@XZ; com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(void)
```
