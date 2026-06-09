# __imp_load_EdpDllGetCredServiceState

- ea: `0x180002747`
- end: `0x180002753`
- name: `__imp_load_EdpDllGetCredServiceState`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllGetCredServiceState` at `0x180002747`

## pseudocode

```c
__int64 load_EdpDllGetCredServiceState()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002747  lea     rax, __imp_EdpDllGetCredServiceState
0x18000274e  jmp     __tailMerge_efscore_dll
```
