# __imp_load_EfsDllIsConsumerProtectionEnforced

- ea: `0x18000251f`
- end: `0x18000252b`
- name: `__imp_load_EfsDllIsConsumerProtectionEnforced`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllIsConsumerProtectionEnforced` at `0x18000251f`

## pseudocode

```c
__int64 load_EfsDllIsConsumerProtectionEnforced()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000251f  lea     rax, __imp_EfsDllIsConsumerProtectionEnforced
0x180002526  jmp     __tailMerge_efscore_dll
```
