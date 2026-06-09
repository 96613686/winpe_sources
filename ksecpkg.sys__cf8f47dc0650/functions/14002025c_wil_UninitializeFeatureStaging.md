# wil_UninitializeFeatureStaging

- ea: `0x14002025c`
- end: `0x1400202b6`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140032078`

## callees

- `0x14002025c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002028f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002028f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002026c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002026c`

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
0x14002025c  sub     rsp, 28h
0x140020260  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140020267  test    rcx, rcx
0x14002026a  jz      short loc_140020283
0x14002026c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140020273  nop     dword ptr [rax+rax+00h]
0x140020278  mov     cs:g_wil_details_featureChangeNotification, 0
0x140020283  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002028a  test    rcx, rcx
0x14002028d  jz      short loc_1400202A6
0x14002028f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140020296  nop     dword ptr [rax+rax+00h]
0x14002029b  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400202a6  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400202b0  add     rsp, 28h
0x1400202b4  retn
```
