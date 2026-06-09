# __imp_load_EfsDllValidateEfsStream

- ea: `0x18000298f`
- end: `0x18000299b`
- name: `__imp_load_EfsDllValidateEfsStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllValidateEfsStream` at `0x18000298f`

## pseudocode

```c
__int64 load_EfsDllValidateEfsStream()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000298f  lea     rax, __imp_EfsDllValidateEfsStream
0x180002996  jmp     __tailMerge_efscore_dll
```
