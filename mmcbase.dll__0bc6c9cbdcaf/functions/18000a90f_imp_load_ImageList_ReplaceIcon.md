# __imp_load_ImageList_ReplaceIcon

- ea: `0x18000a90f`
- end: `0x18000a91b`
- name: `__imp_load_ImageList_ReplaceIcon`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a890`

## import_xrefs

- `COMCTL32!ImageList_ReplaceIcon` at `0x18000a90f`

## pseudocode

```c
__int64 load_ImageList_ReplaceIcon()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000a90f  lea     rax, __imp_ImageList_ReplaceIcon
0x18000a916  jmp     __tailMerge_comctl32_dll
```
