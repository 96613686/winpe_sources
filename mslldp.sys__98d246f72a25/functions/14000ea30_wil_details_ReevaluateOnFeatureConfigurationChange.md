# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000ea30`
- end: `0x14000ea44`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14000e7a0`
- `0x14000ead0`

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
0x14000ea30  sub     rsp, 28h
0x14000ea34  call    wil_details_UpdateFeatureConfiguredStates
0x14000ea39  call    wil_details_EvaluateFeatureDependencies
0x14000ea3e  add     rsp, 28h
0x14000ea42  retn
```
