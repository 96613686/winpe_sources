# __imp_load_EdpWriteSiteLearningLog

- ea: `0x180002507`
- end: `0x180002513`
- name: `__imp_load_EdpWriteSiteLearningLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpWriteSiteLearningLog` at `0x180002507`

## pseudocode

```c
__int64 load_EdpWriteSiteLearningLog()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002507  lea     rax, __imp_EdpWriteSiteLearningLog
0x18000250e  jmp     __tailMerge_efscore_dll
```
