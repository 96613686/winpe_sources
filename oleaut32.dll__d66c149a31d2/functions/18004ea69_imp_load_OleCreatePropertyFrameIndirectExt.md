# __imp_load_OleCreatePropertyFrameIndirectExt

- ea: `0x18004ea69`
- end: `0x18004ea75`
- name: `__imp_load_OleCreatePropertyFrameIndirectExt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreatePropertyFrameIndirectExt` at `0x18004ea69`

## pseudocode

```c
__int64 load_OleCreatePropertyFrameIndirectExt()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004ea69  lea     rax, __imp_OleCreatePropertyFrameIndirectExt
0x18004ea70  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```
