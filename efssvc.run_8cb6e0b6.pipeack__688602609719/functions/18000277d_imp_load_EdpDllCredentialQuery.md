# __imp_load_EdpDllCredentialQuery

- ea: `0x18000277d`
- end: `0x180002789`
- name: `__imp_load_EdpDllCredentialQuery`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllCredentialQuery` at `0x18000277d`

## pseudocode

```c
__int64 load_EdpDllCredentialQuery()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000277d  lea     rax, __imp_EdpDllCredentialQuery
0x180002784  jmp     __tailMerge_efscore_dll
```
