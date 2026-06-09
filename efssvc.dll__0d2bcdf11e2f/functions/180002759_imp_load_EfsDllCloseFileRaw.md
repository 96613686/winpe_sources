# __imp_load_EfsDllCloseFileRaw

- ea: `0x180002759`
- end: `0x180002765`
- name: `__imp_load_EfsDllCloseFileRaw`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x180002759`

## pseudocode

```c
__int64 __fastcall load_EfsDllCloseFileRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002759  lea     rax, __imp_EfsDllCloseFileRaw
0x180002760  jmp     __tailMerge_efscore_dll
```
