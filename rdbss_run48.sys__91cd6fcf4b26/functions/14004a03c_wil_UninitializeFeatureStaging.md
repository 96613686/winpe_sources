# wil_UninitializeFeatureStaging

- ea: `0x14004a03c`
- end: `0x14004a096`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400499a0`
- `0x14008321c`

## callees

- `0x14004a03c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14004a06f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14004a06f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14004a04c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14004a04c`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x14004a03c  sub     rsp, 28h
0x14004a040  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14004a047  test    rcx, rcx
0x14004a04a  jz      short loc_14004A063
0x14004a04c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14004a053  nop     dword ptr [rax+rax+00h]
0x14004a058  mov     cs:g_wil_details_featureChangeNotification, 0
0x14004a063  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14004a06a  test    rcx, rcx
0x14004a06d  jz      short loc_14004A086
0x14004a06f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14004a076  nop     dword ptr [rax+rax+00h]
0x14004a07b  mov     cs:g_wil_details_featureUsageProvider, 0
0x14004a086  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14004a090  add     rsp, 28h
0x14004a094  retn
```
