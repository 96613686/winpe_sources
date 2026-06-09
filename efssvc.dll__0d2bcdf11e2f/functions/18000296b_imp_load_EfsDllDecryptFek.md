# __imp_load_EfsDllDecryptFek

- ea: `0x18000296b`
- end: `0x180002977`
- name: `__imp_load_EfsDllDecryptFek`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllDecryptFek` at `0x18000296b`

## pseudocode

```c
__int64 __fastcall load_EfsDllDecryptFek(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000296b  lea     rax, __imp_EfsDllDecryptFek
0x180002972  jmp     __tailMerge_efscore_dll
```
