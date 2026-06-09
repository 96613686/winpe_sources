# wil_UninitializeFeatureStaging

- ea: `0x14002f50c`
- end: `0x14002f566`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400113c0`
- `0x14001143c`

## callees

- `0x14002f50c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002f51c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002f51c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002f53f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002f53f`

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
0x14002f50c  sub     rsp, 28h
0x14002f510  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14002f517  test    rcx, rcx
0x14002f51a  jz      short loc_14002F533
0x14002f51c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002f523  nop     dword ptr [rax+rax+00h]
0x14002f528  mov     cs:g_wil_details_featureChangeNotification, 0
0x14002f533  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002f53a  test    rcx, rcx
0x14002f53d  jz      short loc_14002F556
0x14002f53f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002f546  nop     dword ptr [rax+rax+00h]
0x14002f54b  mov     cs:g_wil_details_featureUsageProvider, 0
0x14002f556  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002f560  add     rsp, 28h
0x14002f564  retn
```
