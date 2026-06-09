# HsmFltUnload

- ea: `0x1400428f0`
- end: `0x140042a94`
- name: `HsmFltUnload`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140087490`

## callees

- `0x140011c70`
- `0x14001367c`
- `0x140014d84`
- `0x140014dbc`
- `0x1400155b4`
- `0x14001ba48`
- `0x14001e220`
- `0x140037514`
- `0x1400428f0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140042a6b`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140042a6b`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140042946`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140042946`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140042a48`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140042a48`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429c7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429da`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429ed`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042a00`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429c7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429da`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400429ed`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140042a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004292e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004292e`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x14004297a`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042997`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400429b4`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x14004297a`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x140042997`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400429b4`
- `FLTMGR!FltUnregisterFilter` at `0x140042911`
- `FLTMGR!FltUnregisterFilter` at `0x140042911`

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
0x1400428f0  sub     rsp, 28h
0x1400428f4  mov     rax, cs:qword_140029690
0x1400428fb  test    rax, rax
0x1400428fe  jz      short loc_140042905
0x140042900  call    _guard_dispatch_icall
0x140042905  mov     rcx, cs:Filter; Filter
0x14004290c  test    rcx, rcx
0x14004290f  jz      short loc_14004291D
0x140042911  call    cs:__imp_FltUnregisterFilter
0x140042918  nop     dword ptr [rax+rax+00h]
0x14004291d  mov     rcx, cs:String1.Buffer; P
0x140042924  test    rcx, rcx
0x140042927  jz      short loc_14004293A
0x140042929  mov     edx, 73557348h; Tag
0x14004292e  call    cs:__imp_ExFreePoolWithTag
0x140042935  nop     dword ptr [rax+rax+00h]
0x14004293a  mov     rcx, cs:qword_1400294C8
0x140042941  test    rcx, rcx
0x140042944  jz      short loc_140042952
0x140042946  call    cs:__imp_ExUnsubscribeWnfStateChange
0x14004294d  nop     dword ptr [rax+rax+00h]
0x140042952  call    TlmUninitialize
0x140042957  call    HsmFileCacheUninitialize
0x14004295c  cmp     cs:byte_140029108, 0
0x140042963  jz      loc_140042A0C
0x140042969  mov     rcx, cs:Filter; Filter
0x140042970  lea     rdx, qword_140029240; Lookaside
0x140042977  xor     r8d, r8d; Flags
0x14004297a  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x140042981  nop     dword ptr [rax+rax+00h]
0x140042986  mov     rcx, cs:Filter; Filter
0x14004298d  lea     rdx, qword_1400291C0; Lookaside
0x140042994  xor     r8d, r8d; Flags
0x140042997  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x14004299e  nop     dword ptr [rax+rax+00h]
0x1400429a3  mov     rcx, cs:Filter; Filter
0x1400429aa  lea     rdx, qword_140029140; Lookaside
0x1400429b1  xor     r8d, r8d; Flags
0x1400429b4  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x1400429bb  nop     dword ptr [rax+rax+00h]
0x1400429c0  lea     rcx, stru_1400292C0; Lookaside
0x1400429c7  call    cs:__imp_ExDeletePagedLookasideList
0x1400429ce  nop     dword ptr [rax+rax+00h]
0x1400429d3  lea     rcx, stru_140029340; Lookaside
0x1400429da  call    cs:__imp_ExDeletePagedLookasideList
0x1400429e1  nop     dword ptr [rax+rax+00h]
0x1400429e6  lea     rcx, stru_1400293C0; Lookaside
0x1400429ed  call    cs:__imp_ExDeletePagedLookasideList
0x1400429f4  nop     dword ptr [rax+rax+00h]
0x1400429f9  lea     rcx, stru_140029440; Lookaside
0x140042a00  call    cs:__imp_ExDeletePagedLookasideList
0x140042a07  nop     dword ptr [rax+rax+00h]
0x140042a0c  lea     rcx, dword_140029674
0x140042a13  call    HsmOsStopWppTracing
0x140042a18  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 2
0x140042a1f  jz      short loc_140042A2D
0x140042a21  lea     rdx, CldFltUnloadSuccessful
0x140042a28  call    McTemplateK0_EtwWriteTransfer
0x140042a2d  call    McGenEventUnregister_EtwUnregister
0x140042a32  call    WppCleanupKm
0x140042a37  call    UninitializeTelemetryAssertsKM
0x140042a3c  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140042a43  test    rcx, rcx
0x140042a46  jz      short loc_140042A5F
0x140042a48  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140042a4f  nop     dword ptr [rax+rax+00h]
0x140042a54  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x140042a5f  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140042a66  test    rcx, rcx
0x140042a69  jz      short loc_140042A82
0x140042a6b  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140042a72  nop     dword ptr [rax+rax+00h]
0x140042a77  mov     cs:g_wil_details_featureUsageProvider, 0
0x140042a82  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x140042a8c  xor     eax, eax
0x140042a8e  add     rsp, 28h
0x140042a92  retn
```
