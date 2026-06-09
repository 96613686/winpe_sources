# __imp_load_ConfigureAppLaunch

- ea: `0x180003bbf`
- end: `0x180003bcb`
- name: `__imp_load_ConfigureAppLaunch`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003b2e`

## import_xrefs

- `ext-ms-win-provisioning-platform-l1-1-0!ConfigureAppLaunch` at `0x180003bbf`

## pseudocode

```c
__int64 load_ConfigureAppLaunch()
{
  return _tailMerge_ext_ms_win_provisioning_platform_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003bbf  lea     rax, __imp_ConfigureAppLaunch
0x180003bc6  jmp     __tailMerge_ext_ms_win_provisioning_platform_l1_1_0_dll
```
