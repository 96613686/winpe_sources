# __imp_load_DCompositionGetFrameStatistics

- ea: `0x18000dfbf`
- end: `0x18000dfcb`
- name: `__imp_load_DCompositionGetFrameStatistics`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000df40`

## import_xrefs

- `dcomp!__imp_DCompositionGetFrameStatistics` at `0x18000dfbf`

## pseudocode

```c
__int64 load_DCompositionGetFrameStatistics()
{
  return _tailMerge_dcomp_dll();
}

```

## disassembly

```asm
0x18000dfbf  lea     rax, __imp_DCompositionGetFrameStatistics
0x18000dfc6  jmp     __tailMerge_dcomp_dll
```
