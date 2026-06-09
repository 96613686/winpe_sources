# DllUnload

- ea: `0x180012cc0`
- end: `0x180012d35`
- name: `DllUnload`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180012cc0`
- `0x180012d7c`
- `0x180019958`
- `0x180039ef0`
- `0x180045c9c`
- `0x180073714`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180012d0c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180012d0c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180012ce9`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180012ce9`

## pseudocode

```c
__int64 DllUnload()
{
  KspDeinitNotification();
  WppCleanupKm();
  McGenEventUnregister_EtwUnregister();
  KsVerifierUninitialize();
  UninitializeTelemetryAssertsKM();
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return 0;
}

```

## disassembly

```asm
0x180012cc0  sub     rsp, 28h
0x180012cc4  call    KspDeinitNotification
0x180012cc9  call    WppCleanupKm
0x180012cce  call    McGenEventUnregister_EtwUnregister
0x180012cd3  call    KsVerifierUninitialize
0x180012cd8  call    UninitializeTelemetryAssertsKM
0x180012cdd  mov     rcx, cs:g_wil_details_featureChangeNotification
0x180012ce4  test    rcx, rcx
0x180012ce7  jz      short loc_180012D00
0x180012ce9  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x180012cf0  nop     dword ptr [rax+rax+00h]
0x180012cf5  mov     cs:g_wil_details_featureChangeNotification, 0
0x180012d00  mov     rcx, cs:g_wil_details_featureUsageProvider
0x180012d07  test    rcx, rcx
0x180012d0a  jz      short loc_180012D23
0x180012d0c  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x180012d13  nop     dword ptr [rax+rax+00h]
0x180012d18  mov     cs:g_wil_details_featureUsageProvider, 0
0x180012d23  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x180012d2d  xor     eax, eax
0x180012d2f  add     rsp, 28h
0x180012d33  retn
```
