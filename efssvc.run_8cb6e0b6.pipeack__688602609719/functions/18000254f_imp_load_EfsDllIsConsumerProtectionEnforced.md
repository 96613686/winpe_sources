# __imp_load_EfsDllIsConsumerProtectionEnforced

- ea: `0x18000254f`
- end: `0x18000255b`
- name: `__imp_load_EfsDllIsConsumerProtectionEnforced`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x18000254f`

## pseudocode

```c
__int64 load_EfsDllIsConsumerProtectionEnforced()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000254f  lea     rax, __imp_EfsDllIsConsumerProtectionEnforced
0x180002556  jmp     __tailMerge_efscore_dll
```
