# _DetailsView::CreateVolumeDisplayName_::_1_::dtor$2

- ea: `0x18001d409`
- end: `0x18001d415`
- name: `_DetailsView::CreateVolumeDisplayName_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005bf0`

## pseudocode

```c
void **__fastcall DetailsView::CreateVolumeDisplayName_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(a2 + 96);
}

```

## disassembly

```asm
0x18001d409  lea     rcx, [rdx+60h]
0x18001d410  jmp     ??1?$com_autoptr@UIShellFolder@@@@UEAA@XZ; com_autoptr<IShellFolder>::~com_autoptr<IShellFolder>(void)
```
