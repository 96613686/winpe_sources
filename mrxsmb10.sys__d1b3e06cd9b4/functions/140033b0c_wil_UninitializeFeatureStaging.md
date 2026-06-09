# wil_UninitializeFeatureStaging

- ea: `0x140033b0c`
- end: `0x140033b66`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003108c`
- `0x140032a30`

## callees

- `0x140033b0c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140033b3f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140033b3f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140033b1c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140033b1c`

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
0x140033b0c  sub     rsp, 28h
0x140033b10  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140033b17  test    rcx, rcx
0x140033b1a  jz      short loc_140033B33
0x140033b1c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140033b23  nop     dword ptr [rax+rax+00h]
0x140033b28  mov     cs:g_wil_details_featureChangeNotification, 0
0x140033b33  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140033b3a  test    rcx, rcx
0x140033b3d  jz      short loc_140033B56
0x140033b3f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140033b46  nop     dword ptr [rax+rax+00h]
0x140033b4b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140033b56  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140033b60  add     rsp, 28h
0x140033b64  retn
```
