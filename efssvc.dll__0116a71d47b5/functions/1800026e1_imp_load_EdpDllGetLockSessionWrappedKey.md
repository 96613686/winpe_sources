# __imp_load_EdpDllGetLockSessionWrappedKey

- ea: `0x1800026e1`
- end: `0x1800026ed`
- name: `__imp_load_EdpDllGetLockSessionWrappedKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x1800026e1`

## pseudocode

```c
__int64 load_EdpDllGetLockSessionWrappedKey()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026e1  lea     rax, __imp_EdpDllGetLockSessionWrappedKey
0x1800026e8  jmp     __tailMerge_efscore_dll
```
