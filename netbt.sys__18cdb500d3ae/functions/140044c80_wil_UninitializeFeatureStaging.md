# wil_UninitializeFeatureStaging

- ea: `0x140044c80`
- end: `0x140044cda`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002cbc4`
- `0x140053828`

## callees

- `0x140044c80`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140044cb3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140044cb3`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140044c90`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140044c90`

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
0x140044c80  sub     rsp, 28h
0x140044c84  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140044c8b  test    rcx, rcx
0x140044c8e  jz      short loc_140044CA7
0x140044c90  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140044c97  nop     dword ptr [rax+rax+00h]
0x140044c9c  mov     cs:g_wil_details_featureChangeNotification, 0
0x140044ca7  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140044cae  test    rcx, rcx
0x140044cb1  jz      short loc_140044CCA
0x140044cb3  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140044cba  nop     dword ptr [rax+rax+00h]
0x140044cbf  mov     cs:g_wil_details_featureUsageProvider, 0
0x140044cca  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140044cd4  add     rsp, 28h
0x140044cd8  retn
```
