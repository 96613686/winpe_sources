# __imp_load_JetComputeStats

- ea: `0x180002d36`
- end: `0x180002d42`
- name: `__imp_load_JetComputeStats`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetComputeStats` at `0x180002d36`

## pseudocode

```c
__int64 load_JetComputeStats()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002d36  lea     rax, __imp_JetComputeStats
0x180002d3d  jmp     __tailMerge_esent_dll
```
