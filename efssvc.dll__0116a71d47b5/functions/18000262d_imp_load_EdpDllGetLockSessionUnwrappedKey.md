# __imp_load_EdpDllGetLockSessionUnwrappedKey

- ea: `0x18000262d`
- end: `0x180002639`
- name: `__imp_load_EdpDllGetLockSessionUnwrappedKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x18000262d`

## pseudocode

```c
__int64 load_EdpDllGetLockSessionUnwrappedKey()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000262d  lea     rax, __imp_EdpDllGetLockSessionUnwrappedKey
0x180002634  jmp     __tailMerge_efscore_dll
```
