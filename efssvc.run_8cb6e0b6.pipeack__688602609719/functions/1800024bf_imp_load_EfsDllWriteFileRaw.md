# __imp_load_EfsDllWriteFileRaw

- ea: `0x1800024bf`
- end: `0x1800024cb`
- name: `__imp_load_EfsDllWriteFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllWriteFileRaw` at `0x1800024bf`

## pseudocode

```c
__int64 load_EfsDllWriteFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024bf  lea     rax, __imp_EfsDllWriteFileRaw
0x1800024c6  jmp     __tailMerge_efscore_dll
```
