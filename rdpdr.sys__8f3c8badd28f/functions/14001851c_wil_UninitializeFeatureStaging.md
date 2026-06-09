# wil_UninitializeFeatureStaging

- ea: `0x14001851c`
- end: `0x140018576`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017cac`
- `0x14002e078`

## callees

- `0x14001851c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001854f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001854f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001852c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001852c`

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
0x14001851c  sub     rsp, 28h
0x140018520  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140018527  test    rcx, rcx
0x14001852a  jz      short loc_140018543
0x14001852c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140018533  nop     dword ptr [rax+rax+00h]
0x140018538  mov     cs:g_wil_details_featureChangeNotification, 0
0x140018543  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14001854a  test    rcx, rcx
0x14001854d  jz      short loc_140018566
0x14001854f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140018556  nop     dword ptr [rax+rax+00h]
0x14001855b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140018566  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140018570  add     rsp, 28h
0x140018574  retn
```
