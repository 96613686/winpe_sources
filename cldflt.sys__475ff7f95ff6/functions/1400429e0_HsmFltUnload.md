# HsmFltUnload

- ea: `0x1400429e0`
- end: `0x140042b84`
- name: `HsmFltUnload`
- size: `420`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140087490`

## callees

- `0x140011cf0`
- `0x1400136fc`
- `0x140014e04`
- `0x140014e3c`
- `0x140015634`
- `0x14001bac8`
- `0x14001e2a0`
- `0x140037534`
- `0x1400429e0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140042b5b`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140042b5b`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140042a36`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140042a36`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140042b38`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140042b38`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042ab7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042aca`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042add`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042af0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042ab7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042aca`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042add`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042af0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a1e`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042a6a`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042a87`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042aa4`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042a6a`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042a87`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042aa4`
- `FLTMGR!FltUnregisterFilter` at `0x140042a01`
- `FLTMGR!FltUnregisterFilter` at `0x140042a01`

## pseudocode

```c
__int64 HsmFltUnload()
{
  __int64 v0; // rcx

  if ( qword_140029690 )
    qword_140029690();
  if ( Filter )
    FltUnregisterFilter(Filter);
  if ( String1.Buffer )
    ExFreePoolWithTag(String1.Buffer, 0x73557348u);
  if ( qword_1400294C8 )
    ExUnsubscribeWnfStateChange(qword_1400294C8);
  TlmUninitialize();
  HsmFileCacheUninitialize();
  if ( byte_140029108 )
  {
    FltDeleteExtraCreateParameterLookasideList(Filter, qword_140029240, 0);
    FltDeleteExtraCreateParameterLookasideList(Filter, qword_1400291C0, 0);
    FltDeleteExtraCreateParameterLookasideList(Filter, qword_140029140, 0);
    ExDeletePagedLookasideList(&stru_1400292C0);
    ExDeletePagedLookasideList(&stru_140029340);
    ExDeletePagedLookasideList(&stru_1400293C0);
    ExDeletePagedLookasideList(&stru_140029440);
  }
  HsmOsStopWppTracing(&dword_140029674);
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 2) != 0 )
    McTemplateK0_EtwWriteTransfer(v0, CldFltUnloadSuccessful);
  McGenEventUnregister_EtwUnregister();
  WppCleanupKm();
  UninitializeTelemetryAssertsKM();
  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  WPP_MAIN_CB.ActiveThreadCount = 0;
  return 0;
}

```

## disassembly

```asm
0x1400429e0  sub     rsp, 28h
0x1400429e4  mov     rax, cs:qword_140029690
0x1400429eb  test    rax, rax
0x1400429ee  jz      short loc_1400429F5
0x1400429f0  call    _guard_dispatch_icall
0x1400429f5  mov     rcx, cs:Filter; Filter
0x1400429fc  test    rcx, rcx
0x1400429ff  jz      short loc_140042A0D
0x140042a01  call    cs:__imp_FltUnregisterFilter
0x140042a08  nop     dword ptr [rax+rax+00h]
0x140042a0d  mov     rcx, cs:String1.Buffer; P
0x140042a14  test    rcx, rcx
0x140042a17  jz      short loc_140042A2A
0x140042a19  mov     edx, 73557348h; Tag
0x140042a1e  call    cs:__imp_ExFreePoolWithTag
0x140042a25  nop     dword ptr [rax+rax+00h]
0x140042a2a  mov     rcx, cs:qword_1400294C8
0x140042a31  test    rcx, rcx
0x140042a34  jz      short loc_140042A42
0x140042a36  call    cs:__imp_ExUnsubscribeWnfStateChange
0x140042a3d  nop     dword ptr [rax+rax+00h]
0x140042a42  call    TlmUninitialize
0x140042a47  call    HsmFileCacheUninitialize
0x140042a4c  cmp     cs:byte_140029108, 0
0x140042a53  jz      loc_140042AFC
0x140042a59  mov     rcx, cs:Filter; Filter
0x140042a60  lea     rdx, qword_140029240; Lookaside
0x140042a67  xor     r8d, r8d; Flags
0x140042a6a  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x140042a71  nop     dword ptr [rax+rax+00h]
0x140042a76  mov     rcx, cs:Filter; Filter
0x140042a7d  lea     rdx, qword_1400291C0; Lookaside
0x140042a84  xor     r8d, r8d; Flags
0x140042a87  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x140042a8e  nop     dword ptr [rax+rax+00h]
0x140042a93  mov     rcx, cs:Filter; Filter
0x140042a9a  lea     rdx, qword_140029140; Lookaside
0x140042aa1  xor     r8d, r8d; Flags
0x140042aa4  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x140042aab  nop     dword ptr [rax+rax+00h]
0x140042ab0  lea     rcx, stru_1400292C0; Lookaside
0x140042ab7  call    cs:__imp_ExDeletePagedLookasideList
0x140042abe  nop     dword ptr [rax+rax+00h]
0x140042ac3  lea     rcx, stru_140029340; Lookaside
0x140042aca  call    cs:__imp_ExDeletePagedLookasideList
0x140042ad1  nop     dword ptr [rax+rax+00h]
0x140042ad6  lea     rcx, stru_1400293C0; Lookaside
0x140042add  call    cs:__imp_ExDeletePagedLookasideList
0x140042ae4  nop     dword ptr [rax+rax+00h]
0x140042ae9  lea     rcx, stru_140029440; Lookaside
0x140042af0  call    cs:__imp_ExDeletePagedLookasideList
0x140042af7  nop     dword ptr [rax+rax+00h]
0x140042afc  lea     rcx, dword_140029674
0x140042b03  call    HsmOsStopWppTracing
0x140042b08  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 2
0x140042b0f  jz      short loc_140042B1D
0x140042b11  lea     rdx, CldFltUnloadSuccessful
0x140042b18  call    McTemplateK0_EtwWriteTransfer
0x140042b1d  call    McGenEventUnregister_EtwUnregister
0x140042b22  call    WppCleanupKm
0x140042b27  call    UninitializeTelemetryAssertsKM
0x140042b2c  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140042b33  test    rcx, rcx
0x140042b36  jz      short loc_140042B4F
0x140042b38  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140042b3f  nop     dword ptr [rax+rax+00h]
0x140042b44  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x140042b4f  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140042b56  test    rcx, rcx
0x140042b59  jz      short loc_140042B72
0x140042b5b  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140042b62  nop     dword ptr [rax+rax+00h]
0x140042b67  mov     cs:g_wil_details_featureUsageProvider, 0
0x140042b72  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x140042b7c  xor     eax, eax
0x140042b7e  add     rsp, 28h
0x140042b82  retn
```
