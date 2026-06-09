# __imp_load_AtlModuleExtractCreateWndData

- ea: `0x1800038c6`
- end: `0x1800038d2`
- name: `__imp_load_AtlModuleExtractCreateWndData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800037ff`

## import_xrefs

- `ATL!__imp_AtlModuleExtractCreateWndData` at `0x1800038c6`

## pseudocode

```c
__int64 load_AtlModuleExtractCreateWndData()
{
  return _tailMerge_atl_dll();
}

```

## disassembly

```asm
0x1800038c6  lea     rax, __imp_AtlModuleExtractCreateWndData
0x1800038cd  jmp     __tailMerge_atl_dll
```
