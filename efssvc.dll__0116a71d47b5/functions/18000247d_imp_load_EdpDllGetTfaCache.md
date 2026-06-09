# __imp_load_EdpDllGetTfaCache

- ea: `0x18000247d`
- end: `0x180002489`
- name: `__imp_load_EdpDllGetTfaCache`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllGetTfaCache` at `0x18000247d`

## pseudocode

```c
__int64 load_EdpDllGetTfaCache()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000247d  lea     rax, __imp_EdpDllGetTfaCache
0x180002484  jmp     __tailMerge_efscore_dll
```
