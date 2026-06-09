# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140011fa0`
- end: `0x140011fb4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140011d1c`
- `0x140012040`

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
0x140011fa0  sub     rsp, 28h
0x140011fa4  call    wil_details_UpdateFeatureConfiguredStates
0x140011fa9  call    wil_details_EvaluateFeatureDependencies
0x140011fae  add     rsp, 28h
0x140011fb2  retn
```
