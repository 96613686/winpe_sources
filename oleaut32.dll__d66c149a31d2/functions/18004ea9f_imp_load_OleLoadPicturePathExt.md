# __imp_load_OleLoadPicturePathExt

- ea: `0x18004ea9f`
- end: `0x18004eaab`
- name: `__imp_load_OleLoadPicturePathExt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleLoadPicturePathExt` at `0x18004ea9f`

## pseudocode

```c
__int64 load_OleLoadPicturePathExt()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004ea9f  lea     rax, __imp_OleLoadPicturePathExt
0x18004eaa6  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```
