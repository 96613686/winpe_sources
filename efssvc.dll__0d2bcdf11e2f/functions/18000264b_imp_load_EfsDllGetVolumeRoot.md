# __imp_load_EfsDllGetVolumeRoot

- ea: `0x18000264b`
- end: `0x180002657`
- name: `__imp_load_EfsDllGetVolumeRoot`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllGetVolumeRoot` at `0x18000264b`

## pseudocode

```c
__int64 __fastcall load_EfsDllGetVolumeRoot(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000264b  lea     rax, __imp_EfsDllGetVolumeRoot
0x180002652  jmp     __tailMerge_efscore_dll
```
