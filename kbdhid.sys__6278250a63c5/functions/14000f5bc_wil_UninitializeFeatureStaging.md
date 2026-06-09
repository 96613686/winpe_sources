# wil_UninitializeFeatureStaging

- ea: `0x14000f5bc`
- end: `0x14000f616`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f0e0`
- `0x140011168`

## callees

- `0x14000f5bc`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000f5cc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000f5cc`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000f5ef`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000f5ef`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( WPP_MAIN_CB.Dpc.DpcData )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DpcData = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.SecurityDescriptor) = 0;
  return result;
}

```

## disassembly

```asm
0x14000f5bc  sub     rsp, 28h
0x14000f5c0  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcData
0x14000f5c7  test    rcx, rcx
0x14000f5ca  jz      short loc_14000F5E3
0x14000f5cc  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000f5d3  nop     dword ptr [rax+rax+00h]
0x14000f5d8  mov     cs:WPP_MAIN_CB.Dpc.DpcData, 0
0x14000f5e3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000f5ea  test    rcx, rcx
0x14000f5ed  jz      short loc_14000F606
0x14000f5ef  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000f5f6  nop     dword ptr [rax+rax+00h]
0x14000f5fb  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000f606  mov     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x14000f610  add     rsp, 28h
0x14000f614  retn
```
