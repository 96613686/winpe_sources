# __imp_load_ProcessGroupPolicyCompletedInternal

- ea: `0x18001233e`
- end: `0x18001234a`
- name: `__imp_load_ProcessGroupPolicyCompletedInternal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012245`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedInternal` at `0x18001233e`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompletedInternal()
{
  return _tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001233e  lea     rax, __imp_ProcessGroupPolicyCompletedInternal
0x180012345  jmp     __tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll
```
