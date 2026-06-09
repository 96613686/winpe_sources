# __imp_load_EdpDllDplUserUnlockStart

- ea: `0x180002675`
- end: `0x180002681`
- name: `__imp_load_EdpDllDplUserUnlockStart`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockStart` at `0x180002675`

## pseudocode

```c
__int64 load_EdpDllDplUserUnlockStart()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002675  lea     rax, __imp_EdpDllDplUserUnlockStart
0x18000267c  jmp     __tailMerge_efscore_dll
```
