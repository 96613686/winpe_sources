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
__int64 __fastcall load_EdpDllCredentialQuery(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000277d  lea     rax, __imp_EdpDllCredentialQuery
0x180002784  jmp     __tailMerge_efscore_dll
```
