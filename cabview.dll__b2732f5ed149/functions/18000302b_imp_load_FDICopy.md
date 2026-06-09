# __imp_load_FDICopy

- ea: `0x18000302b`
- end: `0x180003037`
- name: `__imp_load_FDICopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f9a`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x18000302b`

## pseudocode

```c
__int64 load_FDICopy()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x18000302b  lea     rax, __imp_FDICopy
0x180003032  jmp     __tailMerge_cabinet_dll
```
