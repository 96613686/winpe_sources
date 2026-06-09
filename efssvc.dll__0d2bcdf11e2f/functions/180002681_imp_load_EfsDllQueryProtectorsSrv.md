# __imp_load_EfsDllQueryProtectorsSrv

- ea: `0x180002681`
- end: `0x18000268d`
- name: `__imp_load_EfsDllQueryProtectorsSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180002681`

## pseudocode

```c
__int64 __fastcall load_EfsDllQueryProtectorsSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002681  lea     rax, __imp_EfsDllQueryProtectorsSrv
0x180002688  jmp     __tailMerge_efscore_dll
```
