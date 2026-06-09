# __imp_load_EdpDllGetLockSessionUnwrappedKey

- ea: `0x18000265d`
- end: `0x180002669`
- name: `__imp_load_EdpDllGetLockSessionUnwrappedKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x18000265d`

## pseudocode

```c
__int64 load_EdpDllGetLockSessionUnwrappedKey()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000265d  lea     rax, __imp_EdpDllGetLockSessionUnwrappedKey
0x180002664  jmp     __tailMerge_efscore_dll
```
