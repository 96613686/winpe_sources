# __imp_load_FDICopy

- ea: `0x1800021f8`
- end: `0x180002204`
- name: `__imp_load_FDICopy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000210d`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x1800021f8`

## pseudocode

```c
__int64 load_FDICopy()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x1800021f8  lea     rax, __imp_FDICopy
0x1800021ff  jmp     __tailMerge_cabinet_dll
```
