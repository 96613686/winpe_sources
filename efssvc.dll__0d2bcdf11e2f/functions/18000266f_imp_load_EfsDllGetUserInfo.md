# __imp_load_EfsDllGetUserInfo

- ea: `0x18000266f`
- end: `0x18000267b`
- name: `__imp_load_EfsDllGetUserInfo`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllGetUserInfo` at `0x18000266f`

## pseudocode

```c
__int64 __fastcall load_EfsDllGetUserInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000266f  lea     rax, __imp_EfsDllGetUserInfo
0x180002676  jmp     __tailMerge_efscore_dll
```
