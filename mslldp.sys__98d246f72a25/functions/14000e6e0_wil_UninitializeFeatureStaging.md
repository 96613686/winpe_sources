# wil_UninitializeFeatureStaging

- ea: `0x14000e6e0`
- end: `0x14000e73a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e670`
- `0x140013350`

## callees

- `0x14000e6e0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000e713`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000e713`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000e6f0`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000e6f0`

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
0x14000e6e0  sub     rsp, 28h
0x14000e6e4  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000e6eb  test    rcx, rcx
0x14000e6ee  jz      short loc_14000E707
0x14000e6f0  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000e6f7  nop     dword ptr [rax+rax+00h]
0x14000e6fc  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000e707  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000e70e  test    rcx, rcx
0x14000e711  jz      short loc_14000E72A
0x14000e713  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000e71a  nop     dword ptr [rax+rax+00h]
0x14000e71f  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000e72a  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000e734  add     rsp, 28h
0x14000e738  retn
```
