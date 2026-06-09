# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140011f50`
- end: `0x140011f64`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140011d1c`
- `0x140011ff0`

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
0x140011f50  sub     rsp, 28h
0x140011f54  call    wil_details_UpdateFeatureConfiguredStates
0x140011f59  call    wil_details_EvaluateFeatureDependencies
0x140011f5e  add     rsp, 28h
0x140011f62  retn
```
