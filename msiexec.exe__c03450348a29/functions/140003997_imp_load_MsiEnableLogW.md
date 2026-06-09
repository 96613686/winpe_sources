# __imp_load_MsiEnableLogW

- ea: `0x140003997`
- end: `0x1400039a3`
- name: `__imp_load_MsiEnableLogW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiEnableLogW` at `0x140003997`

## pseudocode

```c
__int64 load_MsiEnableLogW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x140003997  lea     rax, __imp_MsiEnableLogW
0x14000399e  jmp     __tailMerge_msi_dll
```
