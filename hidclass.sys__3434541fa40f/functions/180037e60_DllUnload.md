# DllUnload

- ea: `0x180037e60`
- end: `0x180037f45`
- name: `DllUnload`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18001b744`
- `0x18001d2c0`
- `0x180026fe8`
- `0x180037e60`
- `0x180037f4c`
- `0x180038b50`
- `0x180038b84`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180037f1c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180037f1c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180037ef9`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180037ef9`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180037ed1`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x180037ed1`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x180037e7c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x180037e7c`

## pseudocode

```c
__int64 DllUnload()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9

  if ( _InterlockedExchange(&g_SleepstudyInitialized, 0) && g_SleepstudyLibraryHandle )
    SleepstudyHelper_Uninitialize();
  if ( _InterlockedExchange(&g_WppInitialized, 0) )
  {
    UninitializeTelemetryAssertsKM();
    if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v1, v0, v2, v3) )
      TlgUnregisterAggregateProvider();
    else
      TraceLoggingUnregister_EtwUnregister(&dword_1800310D8);
    McGenEventUnregister_EtwUnregister();
    if ( g_RecorderLog )
    {
      imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
      g_RecorderLog = 0;
    }
    WppCleanupKm();
    if ( WPP_MAIN_CB.DeviceObjectExtension )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      WPP_MAIN_CB.DeviceObjectExtension = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180037e60  sub     rsp, 28h
0x180037e64  xor     eax, eax
0x180037e66  xchg    eax, cs:g_SleepstudyInitialized
0x180037e6c  test    eax, eax
0x180037e6e  jz      short loc_180037E88
0x180037e70  mov     rcx, cs:g_SleepstudyLibraryHandle
0x180037e77  test    rcx, rcx
0x180037e7a  jz      short loc_180037E88
0x180037e7c  call    cs:__imp_SleepstudyHelper_Uninitialize
0x180037e83  nop     dword ptr [rax+rax+00h]
0x180037e88  xor     eax, eax
0x180037e8a  xchg    eax, cs:g_WppInitialized
0x180037e90  test    eax, eax
0x180037e92  jz      loc_180037F3D
0x180037e98  call    UninitializeTelemetryAssertsKM
0x180037e9d  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x180037ea2  test    eax, eax
0x180037ea4  jz      short loc_180037EAD
0x180037ea6  call    TlgUnregisterAggregateProvider
0x180037eab  jmp     short loc_180037EB9
0x180037ead  lea     rcx, dword_1800310D8
0x180037eb4  call    TraceLoggingUnregister_EtwUnregister
0x180037eb9  call    McGenEventUnregister_EtwUnregister
0x180037ebe  mov     rdx, cs:g_RecorderLog
0x180037ec5  test    rdx, rdx
0x180037ec8  jz      short loc_180037EE8
0x180037eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ed1  call    cs:__imp_imp_WppRecorderLogDelete
0x180037ed8  nop     dword ptr [rax+rax+00h]
0x180037edd  mov     cs:g_RecorderLog, 0
0x180037ee8  call    WppCleanupKm
0x180037eed  mov     rcx, cs:WPP_MAIN_CB.DeviceObjectExtension
0x180037ef4  test    rcx, rcx
0x180037ef7  jz      short loc_180037F10
0x180037ef9  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x180037f00  nop     dword ptr [rax+rax+00h]
0x180037f05  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, 0
0x180037f10  mov     rcx, cs:g_wil_details_featureUsageProvider
0x180037f17  test    rcx, rcx
0x180037f1a  jz      short loc_180037F33
0x180037f1c  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x180037f23  nop     dword ptr [rax+rax+00h]
0x180037f28  mov     cs:g_wil_details_featureUsageProvider, 0
0x180037f33  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x180037f3d  xor     eax, eax
0x180037f3f  add     rsp, 28h
0x180037f43  retn
```
