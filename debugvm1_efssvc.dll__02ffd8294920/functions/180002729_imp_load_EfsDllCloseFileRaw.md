# __imp_load_EfsDllCloseFileRaw

- ea: `0x180002729`
- end: `0x180002735`
- name: `__imp_load_EfsDllCloseFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x180002729`

## pseudocode

```c
__int64 load_EfsDllCloseFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002729  lea     rax, __imp_EfsDllCloseFileRaw
0x180002730  jmp     __tailMerge_efscore_dll
```
