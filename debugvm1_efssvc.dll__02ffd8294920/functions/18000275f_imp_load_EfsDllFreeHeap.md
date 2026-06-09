# __imp_load_EfsDllFreeHeap

- ea: `0x18000275f`
- end: `0x18000276b`
- name: `__imp_load_EfsDllFreeHeap`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllFreeHeap` at `0x18000275f`

## pseudocode

```c
__int64 load_EfsDllFreeHeap()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000275f  lea     rax, __imp_EfsDllFreeHeap
0x180002766  jmp     __tailMerge_efscore_dll
```
