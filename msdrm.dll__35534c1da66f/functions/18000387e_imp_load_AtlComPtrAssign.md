# __imp_load_AtlComPtrAssign

- ea: `0x18000387e`
- end: `0x18000388a`
- name: `__imp_load_AtlComPtrAssign`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037ff`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000387e`

## pseudocode

```c
__int64 load_AtlComPtrAssign()
{
  return _tailMerge_atl_dll();
}

```

## disassembly

```asm
0x18000387e  lea     rax, __imp_AtlComPtrAssign
0x180003885  jmp     __tailMerge_atl_dll
```
