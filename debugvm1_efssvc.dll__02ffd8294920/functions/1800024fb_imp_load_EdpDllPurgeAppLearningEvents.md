# __imp_load_EdpDllPurgeAppLearningEvents

- ea: `0x1800024fb`
- end: `0x180002507`
- name: `__imp_load_EdpDllPurgeAppLearningEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x1800024fb`

## pseudocode

```c
__int64 load_EdpDllPurgeAppLearningEvents()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024fb  lea     rax, __imp_EdpDllPurgeAppLearningEvents
0x180002502  jmp     __tailMerge_efscore_dll
```
