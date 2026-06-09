# __imp_load_EdpDllPurgeAppLearningEvents

- ea: `0x18000252b`
- end: `0x180002537`
- name: `__imp_load_EdpDllPurgeAppLearningEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x18000252b`

## pseudocode

```c
__int64 load_EdpDllPurgeAppLearningEvents()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000252b  lea     rax, __imp_EdpDllPurgeAppLearningEvents
0x180002532  jmp     __tailMerge_efscore_dll
```
