# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400433e0`
- end: `0x1400433f4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140043168`
- `0x140043480`

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
0x1400433e0  sub     rsp, 28h
0x1400433e4  call    wil_details_UpdateFeatureConfiguredStates
0x1400433e9  call    wil_details_EvaluateFeatureDependencies
0x1400433ee  add     rsp, 28h
0x1400433f2  retn
```
