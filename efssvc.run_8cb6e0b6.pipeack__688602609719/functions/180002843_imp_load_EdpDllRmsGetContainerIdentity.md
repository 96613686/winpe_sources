# __imp_load_EdpDllRmsGetContainerIdentity

- ea: `0x180002843`
- end: `0x18000284f`
- name: `__imp_load_EdpDllRmsGetContainerIdentity`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllRmsGetContainerIdentity` at `0x180002843`

## pseudocode

```c
__int64 load_EdpDllRmsGetContainerIdentity()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002843  lea     rax, __imp_EdpDllRmsGetContainerIdentity
0x18000284a  jmp     __tailMerge_efscore_dll
```
