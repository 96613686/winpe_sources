# __imp_load_EfsDllReadFileRaw

- ea: `0x180002489`
- end: `0x180002495`
- name: `__imp_load_EfsDllReadFileRaw`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllReadFileRaw` at `0x180002489`

## pseudocode

```c
__int64 __fastcall load_EfsDllReadFileRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002489  lea     rax, __imp_EfsDllReadFileRaw
0x180002490  jmp     __tailMerge_efscore_dll
```
