# __imp_load_MsiCloseHandle

- ea: `0x140003973`
- end: `0x14000397f`
- name: `__imp_load_MsiCloseHandle`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x140003973`

## pseudocode

```c
__int64 load_MsiCloseHandle()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003973  lea     rax, __imp_MsiCloseHandle
0x14000397a  jmp     __tailMerge_msi_dll
```
