# __imp_load_EdpDllQueryDplEnforcedPolicyOwnerIds

- ea: `0x1800027a1`
- end: `0x1800027ad`
- name: `__imp_load_EdpDllQueryDplEnforcedPolicyOwnerIds`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x1800027a1`

## pseudocode

```c
__int64 load_EdpDllQueryDplEnforcedPolicyOwnerIds()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027a1  lea     rax, __imp_EdpDllQueryDplEnforcedPolicyOwnerIds
0x1800027a8  jmp     __tailMerge_efscore_dll
```
