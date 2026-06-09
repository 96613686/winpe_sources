# __imp_load_EfsDllValidateEfsStream

- ea: `0x18000295f`
- end: `0x18000296b`
- name: `__imp_load_EfsDllValidateEfsStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllValidateEfsStream` at `0x18000295f`

## pseudocode

```c
__int64 load_EfsDllValidateEfsStream()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000295f  lea     rax, __imp_EfsDllValidateEfsStream
0x180002966  jmp     __tailMerge_efscore_dll
```
