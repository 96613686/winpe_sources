# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x180039470`
- end: `0x180039484`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x18003923c`
- `0x180039510`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  wil_details_UpdateFeatureConfiguredStates();
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x180039470  sub     rsp, 28h
0x180039474  call    wil_details_UpdateFeatureConfiguredStates
0x180039479  call    wil_details_EvaluateFeatureDependencies
0x18003947e  add     rsp, 28h
0x180039482  retn
```
