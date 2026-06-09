# __imp_load_SHGetSpecialFolderPathW

- ea: `0x18000288f`
- end: `0x18000289b`
- name: `__imp_load_SHGetSpecialFolderPathW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000272b`

## import_xrefs

- `SHELL32!SHGetSpecialFolderPathW` at `0x18000288f`

## pseudocode

```c
__int64 load_SHGetSpecialFolderPathW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x18000288f  lea     rax, __imp_SHGetSpecialFolderPathW
0x180002896  jmp     __tailMerge_shell32_dll
```
