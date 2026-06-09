# __imp_load_EdpDllCredentialQuery

- ea: `0x18000274d`
- end: `0x180002759`
- name: `__imp_load_EdpDllCredentialQuery`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllCredentialQuery` at `0x18000274d`

## pseudocode

```c
__int64 load_EdpDllCredentialQuery()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000274d  lea     rax, __imp_EdpDllCredentialQuery
0x180002754  jmp     __tailMerge_efscore_dll
```
