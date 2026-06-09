# __imp_load_EdpDllDplUserUnlockStart

- ea: `0x1800026a5`
- end: `0x1800026b1`
- name: `__imp_load_EdpDllDplUserUnlockStart`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockStart` at `0x1800026a5`

## pseudocode

```c
__int64 load_EdpDllDplUserUnlockStart()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026a5  lea     rax, __imp_EdpDllDplUserUnlockStart
0x1800026ac  jmp     __tailMerge_efscore_dll
```
