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
__int64 load_EdpDllDplUserCredentialsSet()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025cd  lea     rax, __imp_EdpDllDplUserCredentialsSet
0x1800025d4  jmp     __tailMerge_efscore_dll
```
