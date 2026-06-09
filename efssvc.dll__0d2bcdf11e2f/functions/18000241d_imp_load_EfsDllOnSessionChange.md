# __imp_load_EfsDllOnSessionChange

- ea: `0x18000241d`
- end: `0x180002429`
- name: `__imp_load_EfsDllOnSessionChange`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionChange` at `0x18000241d`

## pseudocode

```c
__int64 __fastcall load_EfsDllOnSessionChange(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000241d  lea     rax, __imp_EfsDllOnSessionChange
0x180002424  jmp     __tailMerge_efscore_dll
```
