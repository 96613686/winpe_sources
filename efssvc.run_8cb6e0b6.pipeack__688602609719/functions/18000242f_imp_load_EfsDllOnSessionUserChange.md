# __imp_load_EfsDllOnSessionUserChange

- ea: `0x18000242f`
- end: `0x18000243b`
- name: `__imp_load_EfsDllOnSessionUserChange`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionUserChange` at `0x18000242f`

## pseudocode

```c
__int64 load_EfsDllOnSessionUserChange()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000242f  lea     rax, __imp_EfsDllOnSessionUserChange
0x180002436  jmp     __tailMerge_efscore_dll
```
