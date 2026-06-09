# __imp_load_EdpDllDplUserUnlockComplete

- ea: `0x18000281f`
- end: `0x18000282b`
- name: `__imp_load_EdpDllDplUserUnlockComplete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x18000281f`

## pseudocode

```c
__int64 load_EdpDllDplUserUnlockComplete()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000281f  lea     rax, __imp_EdpDllDplUserUnlockComplete
0x180002826  jmp     __tailMerge_efscore_dll
```
