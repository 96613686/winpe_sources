# __imp_load_EdpDllRmsClearKeys

- ea: `0x1800025f1`
- end: `0x1800025fd`
- name: `__imp_load_EdpDllRmsClearKeys`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllRmsClearKeys` at `0x1800025f1`

## pseudocode

```c
__int64 load_EdpDllRmsClearKeys()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025f1  lea     rax, __imp_EdpDllRmsClearKeys
0x1800025f8  jmp     __tailMerge_efscore_dll
```
