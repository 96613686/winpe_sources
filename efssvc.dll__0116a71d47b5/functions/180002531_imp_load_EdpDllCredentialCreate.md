# __imp_load_EdpDllCredentialCreate

- ea: `0x180002531`
- end: `0x18000253d`
- name: `__imp_load_EdpDllCredentialCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllCredentialCreate` at `0x180002531`

## pseudocode

```c
__int64 load_EdpDllCredentialCreate()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002531  lea     rax, __imp_EdpDllCredentialCreate
0x180002538  jmp     __tailMerge_efscore_dll
```
