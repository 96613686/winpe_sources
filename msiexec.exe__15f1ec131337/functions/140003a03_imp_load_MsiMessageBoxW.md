# __imp_load_MsiMessageBoxW

- ea: `0x140003a03`
- end: `0x140003a0f`
- name: `__imp_load_MsiMessageBoxW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiMessageBoxW` at `0x140003a03`

## pseudocode

```c
__int64 load_MsiMessageBoxW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a03  lea     rax, __imp_MsiMessageBoxW
0x140003a0a  jmp     __tailMerge_msi_dll
```
