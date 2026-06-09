# FwPlumber::Initialize(void)

- ea: `0x180068860`
- end: `0x180068de4`
- name: `?Initialize@FwPlumber@@YAXXZ`
- size: `1412`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e05b4`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180017110`
- `0x18001a4e4`
- `0x18001f830`
- `0x180021584`
- `0x180066254`
- `0x180068860`
- `0x180068dec`
- `0x180068e50`
- `0x180068ff4`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800688dc`
- `ntdll!EtwEventWrite` at `0x18006891f`
- `ntdll!EtwEventWrite` at `0x1800688dc`
- `ntdll!EtwEventWrite` at `0x18006891f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180068cc1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180068cc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068c95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068c95`
- `RPCRT4!UuidCreate` at `0x180068959`
- `RPCRT4!UuidCreate` at `0x1800689c1`
- `RPCRT4!UuidCreate` at `0x180068a22`
- `RPCRT4!UuidCreate` at `0x180068959`
- `RPCRT4!UuidCreate` at `0x1800689c1`
- `RPCRT4!UuidCreate` at `0x180068a22`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068ce1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068d01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068ce1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068d01`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800688fe`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800688fe`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068a9f`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068b03`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068b62`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068bb5`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068c08`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068c5b`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068a9f`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068b03`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068b62`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068bb5`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068c08`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x180068c5b`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18006898e`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800689f6`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180068a57`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18006898e`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800689f6`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180068a57`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180068d63`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180068d9f`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180068d63`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180068d9f`

## pseudocode

```c
void __fastcall FwPlumber::Initialize(FwPlumber *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  unsigned int v5; // edx
  DWORD v6; // ebx
  void *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // edx
  DWORD v12; // ebx
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // edx
  DWORD v16; // ebx
  unsigned int v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // edx
  DWORD v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  FwPlumber *v28; // rcx
  int v29; // r8d
  unsigned int WellKnownSid; // eax
  int v31; // edx
  unsigned int v32; // eax
  int v33; // edx
  unsigned int v34; // eax
  int v35; // edx
  DWORD v36; // eax
  DWORD v37; // eax
  __int64 v38; // rdx
  DWORD cbSid[4]; // [rsp+30h] [rbp-59h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+40h] [rbp-49h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 109, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  if ( dword_180131DA0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, a2, a3, a4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Enter, 0, 0);
  v6 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Exit, 0, 0);
  if ( v6 )
    FwPlumber::ThrowWin32((FwPlumber *)v6, v5);
  FwPlumber::CreateCallouts();
  v8 = IpsecApiInitialize(v7);
  if ( v8 )
    FwPlumber::ThrowWin32((FwPlumber *)v8, v9);
  dword_180131DA0 = 1;
  v10 = UuidCreate(&Uuid);
  if ( v10 )
    FwPlumber::ThrowWin32((FwPlumber *)v10, v11);
  FwPlumber::LSMProviderCtxtID = 0;
  v12 = FwpmProviderContextAdd0(engineHandle, (const FWPM_PROVIDER_CONTEXT0 *)&Uuid, 0, &FwPlumber::LSMProviderCtxtID);
  FwPlumberTrackObjError(v12, off_18012A250, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  if ( v12 )
    FwPlumber::ThrowWin32((FwPlumber *)v12, v13);
  v14 = UuidCreate(&stru_18012A150);
  if ( v14 )
    FwPlumber::ThrowWin32((FwPlumber *)v14, v15);
  FwPlumber::LOMProviderCtxtID = 0;
  v16 = FwpmProviderContextAdd0(
          engineHandle,
          (const FWPM_PROVIDER_CONTEXT0 *)&stru_18012A150,
          0,
          &FwPlumber::LOMProviderCtxtID);
  FwPlumberTrackObjError(v16, off_18012A160, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  if ( v16 )
    FwPlumber::ThrowWin32((FwPlumber *)v16, v17);
  v18 = UuidCreate(&stru_18012A2A0);
  if ( v18 )
    FwPlumber::ThrowWin32((FwPlumber *)v18, v19);
  FwPlumber::PolicySilentModeProviderCtxtID = 0;
  v20 = FwpmProviderContextAdd0(
          engineHandle,
          (const FWPM_PROVIDER_CONTEXT0 *)&stru_18012A2A0,
          0,
          &FwPlumber::PolicySilentModeProviderCtxtID);
  FwPlumberTrackObjError(v20, off_18012A2B0, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  if ( v20 )
    FwPlumber::ThrowWin32((FwPlumber *)v20, v21);
  FwPlumber::QuarantineProviderCtxtID = 0;
  v22 = FwpmProviderContextAdd3(engineHandle, qword_18012A5B0, 0, &FwPlumber::QuarantineProviderCtxtID);
  if ( v22 == -2144206839 )
  {
    FwPlumber::QuarantineProviderContextExists = 1;
  }
  else if ( !v22 )
  {
    goto LABEL_32;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 110, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v22);
LABEL_32:
  FwPlumber::BootProviderCtxtID = 0;
  v23 = FwpmProviderContextAdd3(engineHandle, qword_18012A8A0, 0, &FwPlumber::BootProviderCtxtID);
  if ( v23 == -2144206839 )
  {
    FwPlumber::BootProviderContextExists = 1;
  }
  else if ( !v23 )
  {
    goto LABEL_38;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 111, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v23);
LABEL_38:
  FwPlumber::WshProviderCtxtID = 0;
  v24 = FwpmProviderContextAdd3(engineHandle, qword_18012A7A0, 0, &FwPlumber::WshProviderCtxtID);
  if ( v24 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 112, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v24);
  FwPlumber::QueryUserProviderCtxtID = 0;
  v25 = FwpmProviderContextAdd3(engineHandle, qword_18012A970, 0, &FwPlumber::QueryUserProviderCtxtID);
  if ( v25 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 113, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v25);
  FwPlumber::AppCLoopbackProviderCtxtID = 0;
  v26 = FwpmProviderContextAdd3(engineHandle, qword_18012A670, 0, &FwPlumber::AppCLoopbackProviderCtxtID);
  if ( v26 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 114, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v26);
  FwPlumber::StealthProviderCtxtID = 0;
  v27 = FwpmProviderContextAdd3(engineHandle, qword_18012A900, 0, &FwPlumber::StealthProviderCtxtID);
  if ( v27 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 115, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v27);
  cbSid[0] = 68;
  FwPlumber::m_pNullSID = LocalAlloc(0, 0x44u);
  LOBYTE(v28) = FwPlumber::m_pNullSID == 0;
  FwPlumber::ThrowIf(v28, 14, v29);
  WellKnownSid = CreateWellKnownSid(WinNullSid, 0, FwPlumber::m_pNullSID, cbSid);
  FwPlumber::ThrowIf32Bool((FwPlumber *)WellKnownSid, v31);
  v32 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSD:(A;;CC;;;S-1-15-3-3)(A;;CC;;;WD)(A;;CC;;;AN)",
          1u,
          &FwPlumber::m_pIntranetAppCLoopbackSd,
          0);
  FwPlumber::ThrowIf32Bool((FwPlumber *)v32, v33);
  v34 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSD:(A;;CC;;;AC)(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1-15-3-3)(A;;CC;;;S-1-15-3-4214768333-133"
           "4025770-122408079-3919188833)(A;;CC;;;WD)(A;;CC;;;AN)",
          1u,
          &FwPlumber::m_pAllAppContainersSd,
          0);
  FwPlumber::ThrowIf32Bool((FwPlumber *)v34, v35);
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  callout.flags = 0x20000;
  callout.calloutKey = stru_18012B8E0;
  callout.displayData.name = (wchar_t *)L"Interface Binding Callout";
  callout.providerKey = (GUID *)&xmmword_18012BB20;
  callout.applicableLayer = FWPM_LAYER_ALE_BIND_REDIRECT_V4;
  v36 = FwpmCalloutAdd0(engineHandle, &callout, 0, 0);
  FwPlumberTrackObjError(
    v36,
    L"Interface Binding Callout",
    (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  callout.calloutKey = (GUID)xmmword_18012B8C8;
  callout.applicableLayer = FWPM_LAYER_ALE_BIND_REDIRECT_V6;
  v37 = FwpmCalloutAdd0(engineHandle, &callout, 0, 0);
  FwPlumberTrackObjError(
    v37,
    L"Interface Binding Callout",
    (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  LOBYTE(v38) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppIsolationSeparateSublayer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppIsolationSeparateSublayer>::GetImpl'::`2'::impl,
    v38);
  dword_18012B8D8 = 1;
}

```

## disassembly

```asm
0x180068860  push    rbp
0x180068862  push    rbx
0x180068863  push    rsi
0x180068864  push    r12
0x180068866  push    r14
0x180068868  push    r15
0x18006886a  lea     rbp, [rsp-2Fh]
0x18006886f  sub     rsp, 0B8h
0x180068876  mov     rax, cs:__security_cookie
0x18006887d  xor     rax, rsp
0x180068880  mov     [rbp+57h+var_40], rax
0x180068884  mov     rcx, cs:WPP_GLOBAL_Control
0x18006888b  lea     r14, WPP_GLOBAL_Control
0x180068892  lea     r15, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x180068899  cmp     rcx, r14
0x18006889c  jz      short loc_1800688B5
0x18006889e  test    byte ptr [rcx+1Ch], 8
0x1800688a2  jz      short loc_1800688B5
0x1800688a4  mov     rcx, [rcx+10h]
0x1800688a8  mov     edx, 6Dh ; 'm'
0x1800688ad  mov     r8, r15
0x1800688b0  call    WPP_SF_
0x1800688b5  cmp     cs:dword_180131DA0, 0
0x1800688bc  jz      short loc_1800688C3
0x1800688be  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800688c3  mov     rcx, cs:g_Provider
0x1800688ca  test    rcx, rcx
0x1800688cd  jz      short loc_1800688E2
0x1800688cf  xor     r9d, r9d
0x1800688d2  lea     rdx, MPS_SVC_BFE_EngineOpen_Enter
0x1800688d9  xor     r8d, r8d
0x1800688dc  call    cs:__imp_EtwEventWrite
0x1800688e2  xor     r8d, r8d; authIdentity
0x1800688e5  lea     rax, engineHandle
0x1800688ec  lea     r9, session; session
0x1800688f3  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800688f8  xor     ecx, ecx; serverName
0x1800688fa  lea     edx, [r8+0Ah]; authnService
0x1800688fe  call    cs:__imp_FwpmEngineOpen0
0x180068904  mov     rcx, cs:g_Provider
0x18006890b  mov     ebx, eax
0x18006890d  test    rcx, rcx
0x180068910  jz      short loc_180068925
0x180068912  xor     r9d, r9d
0x180068915  lea     rdx, MPS_SVC_BFE_EngineOpen_Exit
0x18006891c  xor     r8d, r8d
0x18006891f  call    cs:__imp_EtwEventWrite
0x180068925  test    ebx, ebx
0x180068927  jz      short loc_180068931
0x180068929  mov     ecx, ebx; this
0x18006892b  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068931  call    FwPlumber__CreateCallouts
0x180068936  call    ?IpsecApiInitialize@@YAKPEAX@Z; IpsecApiInitialize(void *)
0x18006893b  test    eax, eax
0x18006893d  jz      short loc_180068947
0x18006893f  mov     ecx, eax; this
0x180068941  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068947  mov     esi, 1
0x18006894c  lea     rcx, Uuid; Uuid
0x180068953  mov     cs:dword_180131DA0, esi
0x180068959  call    cs:__imp_UuidCreate
0x18006895f  test    eax, eax
0x180068961  jz      short loc_18006896B
0x180068963  mov     ecx, eax; this
0x180068965  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x18006896b  mov     rcx, cs:engineHandle; engineHandle
0x180068972  lea     r9, ?LSMProviderCtxtID@FwPlumber@@3_KA; id
0x180068979  xor     r8d, r8d; sd
0x18006897c  mov     cs:?LSMProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::LSMProviderCtxtID
0x180068987  lea     rdx, Uuid; providerContext
0x18006898e  call    cs:__imp_FwpmProviderContextAdd0
0x180068994  mov     rdx, cs:off_18012A250; unsigned __int16 *
0x18006899b  lea     r12, ?g_FwProvCtxError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST g_FwProvCtxError
0x1800689a2  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800689a5  mov     ecx, eax; unsigned int
0x1800689a7  mov     ebx, eax
0x1800689a9  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800689ae  test    ebx, ebx
0x1800689b0  jz      short loc_1800689BA
0x1800689b2  mov     ecx, ebx; this
0x1800689b4  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x1800689ba  lea     rcx, stru_18012A150; Uuid
0x1800689c1  call    cs:__imp_UuidCreate
0x1800689c7  test    eax, eax
0x1800689c9  jz      short loc_1800689D3
0x1800689cb  mov     ecx, eax; this
0x1800689cd  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x1800689d3  mov     rcx, cs:engineHandle; engineHandle
0x1800689da  lea     r9, ?LOMProviderCtxtID@FwPlumber@@3_KA; id
0x1800689e1  xor     r8d, r8d; sd
0x1800689e4  mov     cs:?LOMProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::LOMProviderCtxtID
0x1800689ef  lea     rdx, stru_18012A150; providerContext
0x1800689f6  call    cs:__imp_FwpmProviderContextAdd0
0x1800689fc  mov     rdx, cs:off_18012A160; unsigned __int16 *
0x180068a03  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x180068a06  mov     ecx, eax; unsigned int
0x180068a08  mov     ebx, eax
0x180068a0a  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x180068a0f  test    ebx, ebx
0x180068a11  jz      short loc_180068A1B
0x180068a13  mov     ecx, ebx; this
0x180068a15  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068a1b  lea     rcx, stru_18012A2A0; Uuid
0x180068a22  call    cs:__imp_UuidCreate
0x180068a28  test    eax, eax
0x180068a2a  jz      short loc_180068A34
0x180068a2c  mov     ecx, eax; this
0x180068a2e  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068a34  mov     rcx, cs:engineHandle; engineHandle
0x180068a3b  lea     r9, ?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA; id
0x180068a42  xor     r8d, r8d; sd
0x180068a45  mov     cs:?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::PolicySilentModeProviderCtxtID
0x180068a50  lea     rdx, stru_18012A2A0; providerContext
0x180068a57  call    cs:__imp_FwpmProviderContextAdd0
0x180068a5d  mov     rdx, cs:off_18012A2B0; unsigned __int16 *
0x180068a64  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x180068a67  mov     ecx, eax; unsigned int
0x180068a69  mov     ebx, eax
0x180068a6b  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x180068a70  test    ebx, ebx
0x180068a72  jz      short loc_180068A7C
0x180068a74  mov     ecx, ebx; this
0x180068a76  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068a7c  mov     rcx, cs:engineHandle
0x180068a83  lea     r9, ?QuarantineProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::QuarantineProviderCtxtID
0x180068a8a  xor     r8d, r8d
0x180068a8d  mov     cs:?QuarantineProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::QuarantineProviderCtxtID
0x180068a98  lea     rdx, qword_18012A5B0
0x180068a9f  call    cs:__imp_FwpmProviderContextAdd3
0x180068aa5  mov     ebx, 80320009h
0x180068aaa  cmp     eax, ebx
0x180068aac  jnz     short loc_180068AB6
0x180068aae  mov     cs:?QuarantineProviderContextExists@FwPlumber@@3HA, esi; int FwPlumber::QuarantineProviderContextExists
0x180068ab4  jmp     short loc_180068ABA
0x180068ab6  test    eax, eax
0x180068ab8  jz      short loc_180068AE0
0x180068aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180068ac1  cmp     rcx, r14
0x180068ac4  jz      short loc_180068AE0
0x180068ac6  test    [rcx+1Ch], sil
0x180068aca  jz      short loc_180068AE0
0x180068acc  mov     rcx, [rcx+10h]
0x180068ad0  mov     edx, 6Eh ; 'n'
0x180068ad5  mov     r9d, eax
0x180068ad8  mov     r8, r15
0x180068adb  call    WPP_SF_d
0x180068ae0  mov     rcx, cs:engineHandle
0x180068ae7  lea     r9, ?BootProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::BootProviderCtxtID
0x180068aee  xor     r8d, r8d
0x180068af1  mov     cs:?BootProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::BootProviderCtxtID
0x180068afc  lea     rdx, qword_18012A8A0
0x180068b03  call    cs:__imp_FwpmProviderContextAdd3
0x180068b09  cmp     eax, ebx
0x180068b0b  jnz     short loc_180068B15
0x180068b0d  mov     cs:?BootProviderContextExists@FwPlumber@@3HA, esi; int FwPlumber::BootProviderContextExists
0x180068b13  jmp     short loc_180068B19
0x180068b15  test    eax, eax
0x180068b17  jz      short loc_180068B3F
0x180068b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b20  cmp     rcx, r14
0x180068b23  jz      short loc_180068B3F
0x180068b25  test    [rcx+1Ch], sil
0x180068b29  jz      short loc_180068B3F
0x180068b2b  mov     rcx, [rcx+10h]
0x180068b2f  mov     edx, 6Fh ; 'o'
0x180068b34  mov     r9d, eax
0x180068b37  mov     r8, r15
0x180068b3a  call    WPP_SF_d
0x180068b3f  mov     rcx, cs:engineHandle
0x180068b46  lea     r9, ?WshProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::WshProviderCtxtID
0x180068b4d  xor     r8d, r8d
0x180068b50  mov     cs:?WshProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::WshProviderCtxtID
0x180068b5b  lea     rdx, qword_18012A7A0
0x180068b62  call    cs:__imp_FwpmProviderContextAdd3
0x180068b68  test    eax, eax
0x180068b6a  jz      short loc_180068B92
0x180068b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b73  cmp     rcx, r14
0x180068b76  jz      short loc_180068B92
0x180068b78  test    [rcx+1Ch], sil
0x180068b7c  jz      short loc_180068B92
0x180068b7e  mov     rcx, [rcx+10h]
0x180068b82  mov     edx, 70h ; 'p'
0x180068b87  mov     r9d, eax
0x180068b8a  mov     r8, r15
0x180068b8d  call    WPP_SF_d
0x180068b92  mov     rcx, cs:engineHandle
0x180068b99  lea     r9, ?QueryUserProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::QueryUserProviderCtxtID
0x180068ba0  xor     r8d, r8d
0x180068ba3  mov     cs:?QueryUserProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::QueryUserProviderCtxtID
0x180068bae  lea     rdx, qword_18012A970
0x180068bb5  call    cs:__imp_FwpmProviderContextAdd3
0x180068bbb  test    eax, eax
0x180068bbd  jz      short loc_180068BE5
0x180068bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180068bc6  cmp     rcx, r14
0x180068bc9  jz      short loc_180068BE5
0x180068bcb  test    [rcx+1Ch], sil
0x180068bcf  jz      short loc_180068BE5
0x180068bd1  mov     rcx, [rcx+10h]
0x180068bd5  mov     edx, 71h ; 'q'
0x180068bda  mov     r9d, eax
0x180068bdd  mov     r8, r15
0x180068be0  call    WPP_SF_d
0x180068be5  mov     rcx, cs:engineHandle
0x180068bec  lea     r9, ?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::AppCLoopbackProviderCtxtID
0x180068bf3  xor     r8d, r8d
0x180068bf6  mov     cs:?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::AppCLoopbackProviderCtxtID
0x180068c01  lea     rdx, qword_18012A670
0x180068c08  call    cs:__imp_FwpmProviderContextAdd3
0x180068c0e  test    eax, eax
0x180068c10  jz      short loc_180068C38
0x180068c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c19  cmp     rcx, r14
0x180068c1c  jz      short loc_180068C38
0x180068c1e  test    [rcx+1Ch], sil
0x180068c22  jz      short loc_180068C38
0x180068c24  mov     rcx, [rcx+10h]
0x180068c28  mov     edx, 72h ; 'r'
0x180068c2d  mov     r9d, eax
0x180068c30  mov     r8, r15
0x180068c33  call    WPP_SF_d
0x180068c38  mov     rcx, cs:engineHandle
0x180068c3f  lea     r9, ?StealthProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::StealthProviderCtxtID
0x180068c46  xor     r8d, r8d
0x180068c49  mov     cs:?StealthProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::StealthProviderCtxtID
0x180068c54  lea     rdx, qword_18012A900
0x180068c5b  call    cs:__imp_FwpmProviderContextAdd3
0x180068c61  test    eax, eax
0x180068c63  jz      short loc_180068C8B
0x180068c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c6c  cmp     rcx, r14
0x180068c6f  jz      short loc_180068C8B
0x180068c71  test    [rcx+1Ch], sil
0x180068c75  jz      short loc_180068C8B
0x180068c77  mov     rcx, [rcx+10h]
0x180068c7b  mov     edx, 73h ; 's'
0x180068c80  mov     r9d, eax
0x180068c83  mov     r8, r15
0x180068c86  call    WPP_SF_d
0x180068c8b  mov     edx, 44h ; 'D'; uBytes
0x180068c90  xor     ecx, ecx; uFlags
0x180068c92  mov     [rbp+57h+cbSid], edx
0x180068c95  call    cs:__imp_LocalAlloc
0x180068c9b  test    rax, rax
0x180068c9e  mov     cs:?m_pNullSID@FwPlumber@@3PEAXEA, rax; void * FwPlumber::m_pNullSID
0x180068ca5  mov     edx, 8007000Eh; bool
0x180068caa  setz    cl; this
0x180068cad  call    ?ThrowIf@FwPlumber@@YAX_NJ@Z; FwPlumber::ThrowIf(bool,long)
0x180068cb2  mov     r8, cs:?m_pNullSID@FwPlumber@@3PEAXEA; pSid
0x180068cb9  lea     r9, [rbp+57h+cbSid]; cbSid
0x180068cbd  xor     edx, edx; DomainSid
0x180068cbf  xor     ecx, ecx; WellKnownSidType
0x180068cc1  call    cs:__imp_CreateWellKnownSid
0x180068cc7  mov     ecx, eax; this
0x180068cc9  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x180068cce  xor     r9d, r9d; SecurityDescriptorSize
0x180068cd1  lea     r8, ?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA; SecurityDescriptor
0x180068cd8  mov     edx, esi; StringSDRevision
0x180068cda  lea     rcx, aOLsdACcS11533A; "O:LSD:(A;;CC;;;S-1-15-3-3)(A;;CC;;;WD)("...
0x180068ce1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180068ce7  mov     ecx, eax; this
0x180068ce9  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x180068cee  xor     r9d, r9d; SecurityDescriptorSize
0x180068cf1  lea     r8, ?m_pAllAppContainersSd@FwPlumber@@3PEAXEA; SecurityDescriptor
0x180068cf8  mov     edx, esi; StringSDRevision
0x180068cfa  lea     rcx, aOLsdACcAcACcS1; "O:LSD:(A;;CC;;;AC)(A;;CC;;;S-1-15-3-1)("...
0x180068d01  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180068d07  mov     ecx, eax; this
0x180068d09  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x180068d0e  xor     edx, edx; Val
0x180068d10  lea     rcx, [rbp+57h+callout.calloutKey.Data2]; void *
0x180068d14  lea     r8d, [rdx+54h]; Size
0x180068d18  call    memset_0
0x180068d1d  movups  xmm0, xmmword ptr cs:stru_18012B8E0.Data1
0x180068d24  mov     rcx, cs:engineHandle; engineHandle
0x180068d2b  lea     rax, xmmword_18012BB20
0x180068d32  lea     rbx, aInterfaceBindi; "Interface Binding Callout"
0x180068d39  mov     [rbp+57h+callout.flags], 20000h
0x180068d40  movdqu  xmmword ptr [rbp-49h], xmm0
0x180068d45  xor     r9d, r9d; id
0x180068d48  xor     r8d, r8d; sd
0x180068d4b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V4.Data1
0x180068d52  lea     rdx, [rbp+57h+callout]; callout
0x180068d56  mov     [rbp+57h+callout.displayData.name], rbx
0x180068d5a  mov     [rbp+57h+callout.providerKey], rax
0x180068d5e  movdqu  xmmword ptr [rbp+57h+callout.applicableLayer.Data1], xmm0
0x180068d63  call    cs:__imp_FwpmCalloutAdd0
0x180068d69  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x180068d6c  mov     rdx, rbx; unsigned __int16 *
0x180068d6f  mov     ecx, eax; unsigned int
0x180068d71  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x180068d76  movups  xmm0, cs:xmmword_18012B8C8
0x180068d7d  mov     rcx, cs:engineHandle; engineHandle
0x180068d84  xor     r9d, r9d; id
0x180068d87  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V6.Data1
0x180068d8e  xor     r8d, r8d; sd
0x180068d91  lea     rdx, [rbp+57h+callout]; callout
0x180068d95  movdqu  xmmword ptr [rbp+57h+callout.calloutKey.Data1], xmm0
0x180068d9a  movdqu  xmmword ptr [rbp+57h+callout.applicableLayer.Data1], xmm1
  ... truncated ...
```
