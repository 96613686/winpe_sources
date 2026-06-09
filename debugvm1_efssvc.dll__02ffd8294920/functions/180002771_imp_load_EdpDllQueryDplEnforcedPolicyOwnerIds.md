# __imp_load_EdpDllQueryDplEnforcedPolicyOwnerIds

- ea: `0x180002771`
- end: `0x18000277d`
- name: `__imp_load_EdpDllQueryDplEnforcedPolicyOwnerIds`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllQueryDplEnforcedPolicyOwnerIds` at `0x180002771`

## pseudocode

```c
__int64 load_EdpDllQueryDplEnforcedPolicyOwnerIds()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002771  lea     rax, __imp_EdpDllQueryDplEnforcedPolicyOwnerIds
0x180002778  jmp     __tailMerge_efscore_dll
```
