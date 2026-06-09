# __imp_load_EdpDllCredentialCreate

- ea: `0x180002561`
- end: `0x18000256d`
- name: `__imp_load_EdpDllCredentialCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllCredentialCreate` at `0x180002561`

## pseudocode

```c
__int64 __fastcall load_EdpDllCredentialCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002561  lea     rax, __imp_EdpDllCredentialCreate
0x180002568  jmp     __tailMerge_efscore_dll
```
