# CddDriverUnload(_DRIVER_OBJECT *)

- ea: `0x140029dd0`
- end: `0x140029e6a`
- name: `?CddDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `154`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140047080`

## callees

- `0x140029dd0`
- `0x140044fac`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140029e20`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140029e20`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140029e43`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140029e43`
- `ntoskrnl!IoDeleteDevice` at `0x140029de0`
- `ntoskrnl!IoDeleteDevice` at `0x140029de0`

## pseudocode

```c
void __fastcall CddDriverUnload(struct _DRIVER_OBJECT *a1)
{
  if ( g_pDeviceObject )
  {
    IoDeleteDevice(g_pDeviceObject);
    g_pDeviceObject = 0;
  }
  if ( _InterlockedExchangeAdd(&g_iTelemetryProviderRef, 0xFFFFFFFF) == 1 )
    TraceLoggingUnregister_EtwUnregister();
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
}

```

## disassembly

```asm
0x140029dd0  sub     rsp, 28h
0x140029dd4  mov     rcx, cs:?g_pDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; DeviceObject
0x140029ddb  test    rcx, rcx
0x140029dde  jz      short loc_140029DF7
0x140029de0  call    cs:__imp_IoDeleteDevice
0x140029de7  nop     dword ptr [rax+rax+00h]
0x140029dec  mov     cs:?g_pDeviceObject@@3PEAU_DEVICE_OBJECT@@EA, 0; _DEVICE_OBJECT * g_pDeviceObject
0x140029df7  or      eax, 0FFFFFFFFh
0x140029dfa  lock xadd cs:?g_iTelemetryProviderRef@@3JA, eax; long g_iTelemetryProviderRef
0x140029e02  cmp     eax, 1
0x140029e05  jnz     short loc_140029E0C
0x140029e07  call    TraceLoggingUnregister_EtwUnregister
0x140029e0c  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140029e13  mov     [rsp+28h+arg_8], 0
0x140029e1b  test    rcx, rcx
0x140029e1e  jz      short loc_140029E37
0x140029e20  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140029e27  nop     dword ptr [rax+rax+00h]
0x140029e2c  mov     cs:g_wil_details_featureChangeNotification, 0
0x140029e37  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140029e3e  test    rcx, rcx
0x140029e41  jz      short loc_140029E5A
0x140029e43  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140029e4a  nop     dword ptr [rax+rax+00h]
0x140029e4f  mov     cs:g_wil_details_featureUsageProvider, 0
0x140029e5a  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140029e64  add     rsp, 28h
0x140029e68  retn
```
