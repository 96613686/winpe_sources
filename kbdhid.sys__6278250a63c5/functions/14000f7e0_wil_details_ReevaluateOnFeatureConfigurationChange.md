# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000f7e0`
- end: `0x14000f7f4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14000f010`
- `0x14000f7fc`

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
0x14000f7e0  sub     rsp, 28h
0x14000f7e4  call    wil_details_UpdateFeatureConfiguredStates
0x14000f7e9  call    wil_details_EvaluateFeatureDependencies
0x14000f7ee  add     rsp, 28h
0x14000f7f2  retn
```
