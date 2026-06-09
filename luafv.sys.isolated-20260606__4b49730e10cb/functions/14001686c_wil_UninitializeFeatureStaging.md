# wil_UninitializeFeatureStaging

- ea: `0x14001686c`
- end: `0x1400168c6`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140016670`
- `0x1400291a8`

## callees

- `0x14001686c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001689f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001689f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001687c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001687c`

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
0x14001686c  sub     rsp, 28h
0x140016870  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140016877  test    rcx, rcx
0x14001687a  jz      short loc_140016893
0x14001687c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140016883  nop     dword ptr [rax+rax+00h]
0x140016888  mov     cs:g_wil_details_featureChangeNotification, 0
0x140016893  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14001689a  test    rcx, rcx
0x14001689d  jz      short loc_1400168B6
0x14001689f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400168a6  nop     dword ptr [rax+rax+00h]
0x1400168ab  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400168b6  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400168c0  add     rsp, 28h
0x1400168c4  retn
```
