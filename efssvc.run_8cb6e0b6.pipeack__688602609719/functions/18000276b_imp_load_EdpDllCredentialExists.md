# __imp_load_EdpDllCredentialExists

- ea: `0x18000276b`
- end: `0x180002777`
- name: `__imp_load_EdpDllCredentialExists`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllCredentialExists` at `0x18000276b`

## pseudocode

```c
__int64 load_EdpDllCredentialExists()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000276b  lea     rax, __imp_EdpDllCredentialExists
0x180002772  jmp     __tailMerge_efscore_dll
```
