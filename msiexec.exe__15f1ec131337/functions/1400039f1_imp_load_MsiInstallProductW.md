# __imp_load_MsiInstallProductW

- ea: `0x1400039f1`
- end: `0x1400039fd`
- name: `__imp_load_MsiInstallProductW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiInstallProductW` at `0x1400039f1`

## pseudocode

```c
__int64 load_MsiInstallProductW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x1400039f1  lea     rax, __imp_MsiInstallProductW
0x1400039f8  jmp     __tailMerge_msi_dll
```
