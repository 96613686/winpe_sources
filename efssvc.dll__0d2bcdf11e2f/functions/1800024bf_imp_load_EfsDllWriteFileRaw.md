# __imp_load_EfsDllWriteFileRaw

- ea: `0x1800024bf`
- end: `0x1800024cb`
- name: `__imp_load_EfsDllWriteFileRaw`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllWriteFileRaw` at `0x1800024bf`

## pseudocode

```c
__int64 __fastcall load_EfsDllWriteFileRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024bf  lea     rax, __imp_EfsDllWriteFileRaw
0x1800024c6  jmp     __tailMerge_efscore_dll
```
