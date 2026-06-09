# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140018860`
- end: `0x140018874`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400185dc`
- `0x140018900`

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
0x140018860  sub     rsp, 28h
0x140018864  call    wil_details_UpdateFeatureConfiguredStates
0x140018869  call    wil_details_EvaluateFeatureDependencies
0x14001886e  add     rsp, 28h
0x140018872  retn
```
