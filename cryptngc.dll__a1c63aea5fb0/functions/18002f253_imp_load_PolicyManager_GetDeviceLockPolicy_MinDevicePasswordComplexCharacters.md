# __imp_load_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters

- ea: `0x18002f253`
- end: `0x18002f25f`
- name: `__imp_load_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002f19e`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters` at `0x18002f253`

## pseudocode

```c
__int64 load_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters()
{
  return _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002f253  lea     rax, __imp_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters
0x18002f25a  jmp     __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll
```
