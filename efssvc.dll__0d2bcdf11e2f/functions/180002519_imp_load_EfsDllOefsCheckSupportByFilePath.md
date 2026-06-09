# __imp_load_EfsDllOefsCheckSupportByFilePath

- ea: `0x180002519`
- end: `0x180002525`
- name: `__imp_load_EfsDllOefsCheckSupportByFilePath`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x180002519`

## pseudocode

```c
__int64 __fastcall load_EfsDllOefsCheckSupportByFilePath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002519  lea     rax, __imp_EfsDllOefsCheckSupportByFilePath
0x180002520  jmp     __tailMerge_efscore_dll
```
