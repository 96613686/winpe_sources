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
__int64 __fastcall load_EdpDllGetTfaCache(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024ad  lea     rax, __imp_EdpDllGetTfaCache
0x1800024b4  jmp     __tailMerge_efscore_dll
```
