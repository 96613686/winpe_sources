# __imp_load_EfsDllShareDecline

- ea: `0x180002735`
- end: `0x180002741`
- name: `__imp_load_EfsDllShareDecline`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllShareDecline` at `0x180002735`

## pseudocode

```c
__int64 __fastcall load_EfsDllShareDecline(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002735  lea     rax, __imp_EfsDllShareDecline
0x18000273c  jmp     __tailMerge_efscore_dll
```
