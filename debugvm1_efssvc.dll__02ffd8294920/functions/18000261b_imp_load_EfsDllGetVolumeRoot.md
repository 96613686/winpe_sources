# __imp_load_EfsDllGetVolumeRoot

- ea: `0x18000261b`
- end: `0x180002627`
- name: `__imp_load_EfsDllGetVolumeRoot`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllGetVolumeRoot` at `0x18000261b`

## pseudocode

```c
__int64 load_EfsDllGetVolumeRoot()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000261b  lea     rax, __imp_EfsDllGetVolumeRoot
0x180002622  jmp     __tailMerge_efscore_dll
```
