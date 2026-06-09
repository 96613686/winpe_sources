# DllInitialize

- ea: `0x140024470`
- end: `0x1400244f7`
- name: `DllInitialize`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140001714`
- `0x140024470`
- `0x140024640`
- `0x140028088`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400244cd`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400244cd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400244aa`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400244aa`

## pseudocode

```c
__int64 DllInitialize()
{
  int v0; // ebx

  wil_InitializeFeatureStaging();
  TraceLoggingRegister_EtwRegister_EtwSetInformation();
  v0 = VmbusTlInitializeObject(8, 0x68u, 3, (int *)&HvSocketModule);
  if ( v0 < 0 )
  {
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
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140024470  push    rbx
0x140024472  sub     rsp, 20h
0x140024476  call    wil_InitializeFeatureStaging
0x14002447b  call    TraceLoggingRegister_EtwRegister_EtwSetInformation
0x140024480  mov     edx, 68h ; 'h'
0x140024485  lea     r9, HvSocketModule
0x14002448c  lea     ecx, [rdx-60h]
0x14002448f  lea     r8d, [rdx-65h]
0x140024493  call    VmbusTlInitializeObject
0x140024498  mov     ebx, eax
0x14002449a  test    eax, eax
0x14002449c  jns     short loc_1400244EE
0x14002449e  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400244a5  test    rcx, rcx
0x1400244a8  jz      short loc_1400244C1
0x1400244aa  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400244b1  nop     dword ptr [rax+rax+00h]
0x1400244b6  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400244c1  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400244c8  test    rcx, rcx
0x1400244cb  jz      short loc_1400244E4
0x1400244cd  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400244d4  nop     dword ptr [rax+rax+00h]
0x1400244d9  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400244e4  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400244ee  mov     eax, ebx
0x1400244f0  add     rsp, 20h
0x1400244f4  pop     rbx
0x1400244f5  retn
```
