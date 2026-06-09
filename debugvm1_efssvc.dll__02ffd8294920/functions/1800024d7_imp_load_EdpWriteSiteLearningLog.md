# __imp_load_EdpWriteSiteLearningLog

- ea: `0x1800024d7`
- end: `0x1800024e3`
- name: `__imp_load_EdpWriteSiteLearningLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpWriteSiteLearningLog` at `0x1800024d7`

## pseudocode

```c
__int64 load_EdpWriteSiteLearningLog()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024d7  lea     rax, __imp_EdpWriteSiteLearningLog
0x1800024de  jmp     __tailMerge_efscore_dll
```
