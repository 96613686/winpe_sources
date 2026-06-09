# __imp_load_EdpDllDplUserCredentialsSet

- ea: `0x18000259d`
- end: `0x1800025a9`
- name: `__imp_load_EdpDllDplUserCredentialsSet`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllDplUserCredentialsSet` at `0x18000259d`

## pseudocode

```c
__int64 load_EdpDllDplUserCredentialsSet()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000259d  lea     rax, __imp_EdpDllDplUserCredentialsSet
0x1800025a4  jmp     __tailMerge_efscore_dll
```
