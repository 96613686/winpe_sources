# __imp_load_ImageList_Create

- ea: `0x18000b533`
- end: `0x18000b53f`
- name: `__imp_load_ImageList_Create`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af5e`

## import_xrefs

- `COMCTL32!ImageList_Create` at `0x18000b533`

## pseudocode

```c
__int64 load_ImageList_Create()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000b533  lea     rax, __imp_ImageList_Create
0x18000b53a  jmp     __tailMerge_comctl32_dll
```
