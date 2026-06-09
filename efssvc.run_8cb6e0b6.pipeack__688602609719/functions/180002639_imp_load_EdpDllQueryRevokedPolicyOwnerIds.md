# __imp_load_EdpDllQueryRevokedPolicyOwnerIds

- ea: `0x180002639`
- end: `0x180002645`
- name: `__imp_load_EdpDllQueryRevokedPolicyOwnerIds`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllQueryRevokedPolicyOwnerIds` at `0x180002639`

## pseudocode

```c
__int64 load_EdpDllQueryRevokedPolicyOwnerIds()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002639  lea     rax, __imp_EdpDllQueryRevokedPolicyOwnerIds
0x180002640  jmp     __tailMerge_efscore_dll
```
