# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140044fd0`
- end: `0x140044fe4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140044d40`
- `0x140045070`

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
0x140044fd0  sub     rsp, 28h
0x140044fd4  call    wil_details_UpdateFeatureConfiguredStates
0x140044fd9  call    wil_details_EvaluateFeatureDependencies
0x140044fde  add     rsp, 28h
0x140044fe2  retn
```
