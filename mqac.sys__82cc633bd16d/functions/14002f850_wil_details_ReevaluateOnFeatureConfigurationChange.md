# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14002f850`
- end: `0x14002f864`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002f5cc`
- `0x14002f8f0`

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
0x14002f850  sub     rsp, 28h
0x14002f854  call    wil_details_UpdateFeatureConfiguredStates
0x14002f859  call    wil_details_EvaluateFeatureDependencies
0x14002f85e  add     rsp, 28h
0x14002f862  retn
```
