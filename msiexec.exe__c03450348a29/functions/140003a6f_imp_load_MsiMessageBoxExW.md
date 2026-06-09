# __imp_load_MsiMessageBoxExW

- ea: `0x140003a6f`
- end: `0x140003a7b`
- name: `__imp_load_MsiMessageBoxExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiMessageBoxExW` at `0x140003a6f`

## pseudocode

```c
__int64 load_MsiMessageBoxExW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a6f  lea     rax, __imp_MsiMessageBoxExW
0x140003a76  jmp     __tailMerge_msi_dll
```
