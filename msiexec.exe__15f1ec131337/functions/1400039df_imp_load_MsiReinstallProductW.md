# __imp_load_MsiReinstallProductW

- ea: `0x1400039df`
- end: `0x1400039eb`
- name: `__imp_load_MsiReinstallProductW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiReinstallProductW` at `0x1400039df`

## pseudocode

```c
__int64 load_MsiReinstallProductW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x1400039df  lea     rax, __imp_MsiReinstallProductW
0x1400039e6  jmp     __tailMerge_msi_dll
```
