# __imp_load_EdpDllDplUserCredentialsSet

- ea: `0x1800025cd`
- end: `0x1800025d9`
- name: `__imp_load_EdpDllDplUserCredentialsSet`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x1800025cd`

## pseudocode

```c
__int64 __fastcall load_EdpDllDplUserCredentialsSet(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025cd  lea     rax, __imp_EdpDllDplUserCredentialsSet
0x1800025d4  jmp     __tailMerge_efscore_dll
```
