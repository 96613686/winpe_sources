# __imp_load_FDICreate

- ea: `0x18000219e`
- end: `0x1800021aa`
- name: `__imp_load_FDICreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000210d`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18000219e`

## pseudocode

```c
__int64 load_FDICreate()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x18000219e  lea     rax, __imp_FDICreate
0x1800021a5  jmp     __tailMerge_cabinet_dll
```
