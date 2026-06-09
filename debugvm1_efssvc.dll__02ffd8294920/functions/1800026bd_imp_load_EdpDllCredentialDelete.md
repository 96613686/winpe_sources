# __imp_load_EdpDllCredentialDelete

- ea: `0x1800026bd`
- end: `0x1800026c9`
- name: `__imp_load_EdpDllCredentialDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllCredentialDelete` at `0x1800026bd`

## pseudocode

```c
__int64 load_EdpDllCredentialDelete()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026bd  lea     rax, __imp_EdpDllCredentialDelete
0x1800026c4  jmp     __tailMerge_efscore_dll
```
