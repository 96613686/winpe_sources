# __imp_load_ProcessGroupPolicyCompletedExInternal

- ea: `0x1800122c4`
- end: `0x1800122d0`
- name: `__imp_load_ProcessGroupPolicyCompletedExInternal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012245`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!ProcessGroupPolicyCompletedExInternal` at `0x1800122c4`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompletedExInternal()
{
  return _tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800122c4  lea     rax, __imp_ProcessGroupPolicyCompletedExInternal
0x1800122cb  jmp     __tailMerge_ext_ms_win_gpsvc_grouppolicy_l1_1_0_dll
```
