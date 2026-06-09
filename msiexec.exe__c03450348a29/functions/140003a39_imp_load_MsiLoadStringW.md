# __imp_load_MsiLoadStringW

- ea: `0x140003a39`
- end: `0x140003a45`
- name: `__imp_load_MsiLoadStringW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiLoadStringW` at `0x140003a39`

## pseudocode

```c
__int64 load_MsiLoadStringW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003a39  lea     rax, __imp_MsiLoadStringW
0x140003a40  jmp     __tailMerge_msi_dll
```
