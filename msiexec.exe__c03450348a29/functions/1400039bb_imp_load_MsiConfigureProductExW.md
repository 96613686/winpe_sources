# __imp_load_MsiConfigureProductExW

- ea: `0x1400039bb`
- end: `0x1400039c7`
- name: `__imp_load_MsiConfigureProductExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1400038d0`

## import_xrefs

- `msi!__imp_MsiConfigureProductExW` at `0x1400039bb`

## pseudocode

```c
__int64 load_MsiConfigureProductExW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x1400039bb  lea     rax, __imp_MsiConfigureProductExW
0x1400039c2  jmp     __tailMerge_msi_dll
```
