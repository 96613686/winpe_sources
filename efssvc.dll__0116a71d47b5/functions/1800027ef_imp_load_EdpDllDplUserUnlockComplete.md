# __imp_load_EdpDllDplUserUnlockComplete

- ea: `0x1800027ef`
- end: `0x1800027fb`
- name: `__imp_load_EdpDllDplUserUnlockComplete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x1800027ef`

## pseudocode

```c
__int64 load_EdpDllDplUserUnlockComplete()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027ef  lea     rax, __imp_EdpDllDplUserUnlockComplete
0x1800027f6  jmp     __tailMerge_efscore_dll
```
