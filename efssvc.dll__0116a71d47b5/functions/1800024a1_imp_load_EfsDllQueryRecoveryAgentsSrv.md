# __imp_load_EfsDllQueryRecoveryAgentsSrv

- ea: `0x1800024a1`
- end: `0x1800024ad`
- name: `__imp_load_EfsDllQueryRecoveryAgentsSrv`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x1800024a1`

## pseudocode

```c
__int64 load_EfsDllQueryRecoveryAgentsSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024a1  lea     rax, __imp_EfsDllQueryRecoveryAgentsSrv
0x1800024a8  jmp     __tailMerge_efscore_dll
```
