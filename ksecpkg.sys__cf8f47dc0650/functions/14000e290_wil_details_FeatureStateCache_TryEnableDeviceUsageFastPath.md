# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14000e290`
- end: `0x14000e29c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000dd78`

## pseudocode

```c
int *wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath()
{
  int *result; // rax

  result = wil_details_featureDescriptors_a;
  _InterlockedOr(wil_details_featureDescriptors_a, 0x10u);
  return result;
}

```

## disassembly

```asm
0x14000e290  mov     rax, cs:wil_details_featureDescriptors_a
0x14000e297  lock or dword ptr [rax], 10h
0x14000e29b  retn
```
