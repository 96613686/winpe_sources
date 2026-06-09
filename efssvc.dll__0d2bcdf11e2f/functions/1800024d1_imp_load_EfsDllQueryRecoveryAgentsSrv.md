# __imp_load_EfsDllQueryRecoveryAgentsSrv

- ea: `0x1800024d1`
- end: `0x1800024dd`
- name: `__imp_load_EfsDllQueryRecoveryAgentsSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x1800024d1`

## pseudocode

```c
__int64 __fastcall load_EfsDllQueryRecoveryAgentsSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024d1  lea     rax, __imp_EfsDllQueryRecoveryAgentsSrv
0x1800024d8  jmp     __tailMerge_efscore_dll
```
