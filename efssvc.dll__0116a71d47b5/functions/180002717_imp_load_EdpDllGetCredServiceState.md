# __imp_load_EdpDllGetCredServiceState

- ea: `0x180002717`
- end: `0x180002723`
- name: `__imp_load_EdpDllGetCredServiceState`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllGetCredServiceState` at `0x180002717`

## pseudocode

```c
__int64 load_EdpDllGetCredServiceState()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002717  lea     rax, __imp_EdpDllGetCredServiceState
0x18000271e  jmp     __tailMerge_efscore_dll
```
