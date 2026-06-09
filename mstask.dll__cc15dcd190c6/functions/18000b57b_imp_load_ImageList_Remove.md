# __imp_load_ImageList_Remove

- ea: `0x18000b57b`
- end: `0x18000b587`
- name: `__imp_load_ImageList_Remove`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af5e`

## import_xrefs

- `COMCTL32!ImageList_Remove` at `0x18000b57b`

## pseudocode

```c
__int64 load_ImageList_Remove()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000b57b  lea     rax, __imp_ImageList_Remove
0x18000b582  jmp     __tailMerge_comctl32_dll
```
