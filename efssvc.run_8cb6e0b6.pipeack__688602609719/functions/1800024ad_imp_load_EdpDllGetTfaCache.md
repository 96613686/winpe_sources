# __imp_load_EdpDllGetTfaCache

- ea: `0x1800024ad`
- end: `0x1800024b9`
- name: `__imp_load_EdpDllGetTfaCache`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllGetTfaCache` at `0x1800024ad`

## pseudocode

```c
__int64 load_EdpDllGetTfaCache()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024ad  lea     rax, __imp_EdpDllGetTfaCache
0x1800024b4  jmp     __tailMerge_efscore_dll
```
