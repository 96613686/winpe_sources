# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140016b60`
- end: `0x140016b74`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001692c`
- `0x140016c00`

## pseudocode

```c
__int64 *wil_details_ReevaluateOnFeatureConfigurationChange()
{
  wil_details_UpdateFeatureConfiguredStates();
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x140016b60  sub     rsp, 28h
0x140016b64  call    wil_details_UpdateFeatureConfiguredStates
0x140016b69  call    wil_details_EvaluateFeatureDependencies
0x140016b6e  add     rsp, 28h
0x140016b72  retn
```
