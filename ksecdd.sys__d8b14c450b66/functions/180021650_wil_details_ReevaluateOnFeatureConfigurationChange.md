# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x180021650`
- end: `0x180021664`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180021424`
- `0x1800216f0`

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
0x180021650  sub     rsp, 28h
0x180021654  call    wil_details_UpdateFeatureConfiguredStates
0x180021659  call    wil_details_EvaluateFeatureDependencies
0x18002165e  add     rsp, 28h
0x180021662  retn
```
