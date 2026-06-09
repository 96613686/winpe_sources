# __imp_load_EfsDllOnSessionUserChange

- ea: `0x1800023ff`
- end: `0x18000240b`
- name: `__imp_load_EfsDllOnSessionUserChange`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionUserChange` at `0x1800023ff`

## pseudocode

```c
__int64 load_EfsDllOnSessionUserChange()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800023ff  lea     rax, __imp_EfsDllOnSessionUserChange
0x180002406  jmp     __tailMerge_efscore_dll
```
