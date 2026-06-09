# __imp_load_EdpWriteAppLearningLog

- ea: `0x180002983`
- end: `0x18000298f`
- name: `__imp_load_EdpWriteAppLearningLog`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpWriteAppLearningLog` at `0x180002983`

## pseudocode

```c
__int64 load_EdpWriteAppLearningLog()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002983  lea     rax, __imp_EdpWriteAppLearningLog
0x18000298a  jmp     __tailMerge_efscore_dll
```
