# __imp_load_EfsDllDisabled

- ea: `0x1800025df`
- end: `0x1800025eb`
- name: `__imp_load_EfsDllDisabled`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllDisabled` at `0x1800025df`

## pseudocode

```c
__int64 __fastcall load_EfsDllDisabled(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025df  lea     rax, __imp_EfsDllDisabled
0x1800025e6  jmp     __tailMerge_efscore_dll
```
