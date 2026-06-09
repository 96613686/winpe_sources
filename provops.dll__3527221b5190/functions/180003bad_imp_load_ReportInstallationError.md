# __imp_load_ReportInstallationError

- ea: `0x180003bad`
- end: `0x180003bb9`
- name: `__imp_load_ReportInstallationError`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003b2e`

## import_xrefs

- `ext-ms-win-provisioning-platform-l1-1-0!ReportInstallationError` at `0x180003bad`

## pseudocode

```c
__int64 load_ReportInstallationError()
{
  return _tailMerge_ext_ms_win_provisioning_platform_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003bad  lea     rax, __imp_ReportInstallationError
0x180003bb4  jmp     __tailMerge_ext_ms_win_provisioning_platform_l1_1_0_dll
```
