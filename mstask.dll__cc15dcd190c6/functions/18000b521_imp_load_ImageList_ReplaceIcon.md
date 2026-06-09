# __imp_load_ImageList_ReplaceIcon

- ea: `0x18000b521`
- end: `0x18000b52d`
- name: `__imp_load_ImageList_ReplaceIcon`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af5e`

## import_xrefs

- `COMCTL32!ImageList_ReplaceIcon` at `0x18000b521`

## pseudocode

```c
__int64 load_ImageList_ReplaceIcon()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000b521  lea     rax, __imp_ImageList_ReplaceIcon
0x18000b528  jmp     __tailMerge_comctl32_dll
```
