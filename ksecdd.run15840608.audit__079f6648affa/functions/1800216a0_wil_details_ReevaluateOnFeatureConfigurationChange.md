# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1800216a0`
- end: `0x1800216b4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180021424`
- `0x180021740`

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
0x1800216a0  sub     rsp, 28h
0x1800216a4  call    wil_details_UpdateFeatureConfiguredStates
0x1800216a9  call    wil_details_EvaluateFeatureDependencies
0x1800216ae  add     rsp, 28h
0x1800216b2  retn
```
