# __imp_load_DiUninstallDevice

- ea: `0x180002a82`
- end: `0x180002a8e`
- name: `__imp_load_DiUninstallDevice`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002a03`

## import_xrefs

- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x180002a82`

## pseudocode

```c
__int64 load_DiUninstallDevice()
{
  return _tailMerge_ext_ms_win_newdev_config_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002a82  lea     rax, __imp_DiUninstallDevice
0x180002a89  jmp     __tailMerge_ext_ms_win_newdev_config_l1_1_0_dll
```
