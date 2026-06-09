# __imp_load_EdpDllGetLockSessionWrappedKey

- ea: `0x180002711`
- end: `0x18000271d`
- name: `__imp_load_EdpDllGetLockSessionWrappedKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x180002711`

## pseudocode

```c
__int64 load_EdpDllGetLockSessionWrappedKey()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002711  lea     rax, __imp_EdpDllGetLockSessionWrappedKey
0x180002718  jmp     __tailMerge_efscore_dll
```
