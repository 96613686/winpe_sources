# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400205a0`
- end: `0x1400205b4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002031c`
- `0x140020640`

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
0x1400205a0  sub     rsp, 28h
0x1400205a4  call    wil_details_UpdateFeatureConfiguredStates
0x1400205a9  call    wil_details_EvaluateFeatureDependencies
0x1400205ae  add     rsp, 28h
0x1400205b2  retn
```
