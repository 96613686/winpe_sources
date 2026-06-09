# wil_UninitializeFeatureStaging

- ea: `0x140017b4c`
- end: `0x140017ba6`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017410`
- `0x140021078`

## callees

- `0x140017b4c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017b7f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017b7f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017b5c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017b5c`

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
0x140017b4c  sub     rsp, 28h
0x140017b50  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140017b57  test    rcx, rcx
0x140017b5a  jz      short loc_140017B73
0x140017b5c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140017b63  nop     dword ptr [rax+rax+00h]
0x140017b68  mov     cs:g_wil_details_featureChangeNotification, 0
0x140017b73  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140017b7a  test    rcx, rcx
0x140017b7d  jz      short loc_140017B96
0x140017b7f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140017b86  nop     dword ptr [rax+rax+00h]
0x140017b8b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140017b96  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140017ba0  add     rsp, 28h
0x140017ba4  retn
```
