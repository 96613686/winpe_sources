# wil_UninitializeFeatureStaging

- ea: `0x1400374cc`
- end: `0x140037526`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140026c00`
- `0x140039008`

## callees

- `0x1400374cc`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400374ff`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400374ff`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400374dc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400374dc`

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
0x1400374cc  sub     rsp, 28h
0x1400374d0  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400374d7  test    rcx, rcx
0x1400374da  jz      short loc_1400374F3
0x1400374dc  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400374e3  nop     dword ptr [rax+rax+00h]
0x1400374e8  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400374f3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400374fa  test    rcx, rcx
0x1400374fd  jz      short loc_140037516
0x1400374ff  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140037506  nop     dword ptr [rax+rax+00h]
0x14003750b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140037516  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140037520  add     rsp, 28h
0x140037524  retn
```
