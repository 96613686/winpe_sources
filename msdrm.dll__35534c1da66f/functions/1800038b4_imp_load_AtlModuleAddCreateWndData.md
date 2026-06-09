# __imp_load_AtlModuleAddCreateWndData

- ea: `0x1800038b4`
- end: `0x1800038c0`
- name: `__imp_load_AtlModuleAddCreateWndData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800037ff`

## import_xrefs

- `ATL!__imp_AtlModuleAddCreateWndData` at `0x1800038b4`

## pseudocode

```c
__int64 load_AtlModuleAddCreateWndData()
{
  return _tailMerge_atl_dll();
}

```

## disassembly

```asm
0x1800038b4  lea     rax, __imp_AtlModuleAddCreateWndData
0x1800038bb  jmp     __tailMerge_atl_dll
```
