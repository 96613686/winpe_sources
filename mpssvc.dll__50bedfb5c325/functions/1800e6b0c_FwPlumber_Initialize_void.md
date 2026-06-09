# FwPlumber::Initialize(void)

- ea: `0x1800e6b0c`
- end: `0x1800e70e7`
- name: `?Initialize@FwPlumber@@YAXXZ`
- size: `1499`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e74a4`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x1800192e0`
- `0x18001c814`
- `0x180021b80`
- `0x1800238f4`
- `0x180023910`
- `0x180069a44`
- `0x1800729c0`
- `0x180073488`
- `0x1800d9958`
- `0x1800e63f0`
- `0x1800e6b0c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800e6b88`
- `ntdll!EtwEventWrite` at `0x1800e6bd7`
- `ntdll!EtwEventWrite` at `0x1800e6b88`
- `ntdll!EtwEventWrite` at `0x1800e6bd7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e6fa5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e6fa5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e6f73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e6f73`
- `RPCRT4!UuidCreate` at `0x1800e6c0d`
- `RPCRT4!UuidCreate` at `0x1800e6c77`
- `RPCRT4!UuidCreate` at `0x1800e6cda`
- `RPCRT4!UuidCreate` at `0x1800e6c0d`
- `RPCRT4!UuidCreate` at `0x1800e6c77`
- `RPCRT4!UuidCreate` at `0x1800e6cda`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e6fcb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e6ff1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e6fcb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e6ff1`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e6bb0`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e6bb0`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6d59`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6dc3`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6e28`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6e81`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6eda`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6f33`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6d59`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6dc3`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6e28`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6e81`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6eda`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800e6f33`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6c43`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6cad`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6d10`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6c43`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6cad`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800e6d10`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e7059`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e709b`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e7059`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e709b`

## pseudocode

```c
void __fastcall FwPlumber::Initialize(FwPlumber *this)
{
  unsigned int v1; // edx
  DWORD v2; // ebx
  void *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // edx
  unsigned int v6; // eax
  unsigned int v7; // edx
  DWORD v8; // ebx
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
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  FwPlumber *v24; // rcx
  int v25; // r8d
  unsigned int WellKnownSid; // eax
  int v27; // edx
  unsigned int v28; // eax
  int v29; // edx
  unsigned int v30; // eax
  int v31; // edx
  DWORD v32; // eax
  DWORD v33; // eax
  __int64 v34; // rdx
  DWORD cbSid[4]; // [rsp+30h] [rbp-59h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+40h] [rbp-49h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 109, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
  if ( dword_180137F38 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Enter, 0, 0);
  v2 = FwpmEngineOpen0(0, 0xAu, 0, &stru_1800F9C50, &engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Exit, 0, 0);
  FwPlumber::ThrowIf32Error((FwPlumber *)v2, v1);
  FwPlumber::CreateCallouts();
  v4 = IpsecApiInitialize(v3);
  FwPlumber::ThrowIf32Error((FwPlumber *)v4, v5);
  dword_180137F38 = 1;
  v6 = UuidCreate(&Uuid);
  FwPlumber::ThrowIf32Error((FwPlumber *)v6, v7);
  FwPlumber::LSMProviderCtxtID = 0;
  v8 = FwpmProviderContextAdd0(engineHandle, (const FWPM_PROVIDER_CONTEXT0 *)&Uuid, 0, &FwPlumber::LSMProviderCtxtID);
  FwPlumberTrackObjError(v8, off_180130340, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  FwPlumber::ThrowIf32Error((FwPlumber *)v8, v9);
  v10 = UuidCreate(&stru_180130250);
  FwPlumber::ThrowIf32Error((FwPlumber *)v10, v11);
  FwPlumber::LOMProviderCtxtID = 0;
  v12 = FwpmProviderContextAdd0(
          engineHandle,
          (const FWPM_PROVIDER_CONTEXT0 *)&stru_180130250,
          0,
          &FwPlumber::LOMProviderCtxtID);
  FwPlumberTrackObjError(v12, off_180130260, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  FwPlumber::ThrowIf32Error((FwPlumber *)v12, v13);
  v14 = UuidCreate(&stru_180130390);
  FwPlumber::ThrowIf32Error((FwPlumber *)v14, v15);
  FwPlumber::PolicySilentModeProviderCtxtID = 0;
  v16 = FwpmProviderContextAdd0(
          engineHandle,
          (const FWPM_PROVIDER_CONTEXT0 *)&stru_180130390,
          0,
          &FwPlumber::PolicySilentModeProviderCtxtID);
  FwPlumberTrackObjError(v16, off_1801303A0, (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  FwPlumber::ThrowIf32Error((FwPlumber *)v16, v17);
  FwPlumber::QuarantineProviderCtxtID = 0;
  v18 = FwpmProviderContextAdd3(engineHandle, qword_180130780, 0, &FwPlumber::QuarantineProviderCtxtID);
  if ( v18 == -2144206839 )
  {
    FwPlumber::QuarantineProviderContextExists = 1;
  }
  else if ( !v18 )
  {
    goto LABEL_16;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 110, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v18);
LABEL_16:
  FwPlumber::BootProviderCtxtID = 0;
  v19 = FwpmProviderContextAdd3(engineHandle, qword_180130A70, 0, &FwPlumber::BootProviderCtxtID);
  if ( v19 == -2144206839 )
  {
    FwPlumber::BootProviderContextExists = 1;
  }
  else if ( !v19 )
  {
    goto LABEL_22;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 111, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v19);
LABEL_22:
  FwPlumber::WshProviderCtxtID = 0;
  v20 = FwpmProviderContextAdd3(engineHandle, qword_180130970, 0, &FwPlumber::WshProviderCtxtID);
  if ( v20 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 112, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v20);
  FwPlumber::QueryUserProviderCtxtID = 0;
  v21 = FwpmProviderContextAdd3(engineHandle, qword_180130B40, 0, &FwPlumber::QueryUserProviderCtxtID);
  if ( v21 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 113, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v21);
  FwPlumber::AppCLoopbackProviderCtxtID = 0;
  v22 = FwpmProviderContextAdd3(engineHandle, qword_180130840, 0, &FwPlumber::AppCLoopbackProviderCtxtID);
  if ( v22 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 114, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v22);
  FwPlumber::StealthProviderCtxtID = 0;
  v23 = FwpmProviderContextAdd3(engineHandle, qword_180130AD0, 0, &FwPlumber::StealthProviderCtxtID);
  if ( v23 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 115, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, v23);
  cbSid[0] = 68;
  FwPlumber::m_pNullSID = LocalAlloc(0, 0x44u);
  LOBYTE(v24) = FwPlumber::m_pNullSID == 0;
  FwPlumber::ThrowIf(v24, 14, v25);
  WellKnownSid = CreateWellKnownSid(WinNullSid, 0, FwPlumber::m_pNullSID, cbSid);
  FwPlumber::ThrowIf32Bool((FwPlumber *)WellKnownSid, v27);
  v28 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSD:(A;;CC;;;S-1-15-3-3)(A;;CC;;;WD)(A;;CC;;;AN)",
          1u,
          &FwPlumber::m_pIntranetAppCLoopbackSd,
          0);
  FwPlumber::ThrowIf32Bool((FwPlumber *)v28, v29);
  v30 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSD:(A;;CC;;;AC)(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1-15-3-3)(A;;CC;;;S-1-15-3-4214768333-133"
           "4025770-122408079-3919188833)(A;;CC;;;WD)(A;;CC;;;AN)",
          1u,
          &FwPlumber::m_pAllAppContainersSd,
          0);
  FwPlumber::ThrowIf32Bool((FwPlumber *)v30, v31);
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  callout.flags = 0x20000;
  callout.calloutKey = stru_180131AD8;
  callout.displayData.name = (wchar_t *)L"Interface Binding Callout";
  callout.providerKey = (GUID *)&xmmword_180131D10;
  callout.applicableLayer = FWPM_LAYER_ALE_BIND_REDIRECT_V4;
  v32 = FwpmCalloutAdd0(engineHandle, &callout, 0, 0);
  FwPlumberTrackObjError(
    v32,
    L"Interface Binding Callout",
    (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  callout.calloutKey = (GUID)xmmword_180131AC0;
  callout.applicableLayer = FWPM_LAYER_ALE_BIND_REDIRECT_V6;
  v33 = FwpmCalloutAdd0(engineHandle, &callout, 0, 0);
  FwPlumberTrackObjError(
    v33,
    L"Interface Binding Callout",
    (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
  LOBYTE(v34) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppIsolationSeparateSublayer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppIsolationSeparateSublayer>::GetImpl'::`2'::impl,
    v34);
  dword_180131AD0 = 1;
}

```

## disassembly

```asm
0x1800e6b0c  push    rbp
0x1800e6b0e  push    rbx
0x1800e6b0f  push    rsi
0x1800e6b10  push    r12
0x1800e6b12  push    r14
0x1800e6b14  push    r15
0x1800e6b16  lea     rbp, [rsp-2Fh]
0x1800e6b1b  sub     rsp, 0B8h
0x1800e6b22  mov     rax, cs:__security_cookie
0x1800e6b29  xor     rax, rsp
0x1800e6b2c  mov     [rbp+57h+var_40], rax
0x1800e6b30  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6b37  lea     r14, WPP_GLOBAL_Control
0x1800e6b3e  lea     r15, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800e6b45  cmp     rcx, r14
0x1800e6b48  jz      short loc_1800E6B61
0x1800e6b4a  test    byte ptr [rcx+1Ch], 8
0x1800e6b4e  jz      short loc_1800E6B61
0x1800e6b50  mov     rcx, [rcx+10h]
0x1800e6b54  mov     edx, 6Dh ; 'm'
0x1800e6b59  mov     r8, r15
0x1800e6b5c  call    WPP_SF_
0x1800e6b61  cmp     cs:dword_180137F38, 0
0x1800e6b68  jz      short loc_1800E6B6F
0x1800e6b6a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE == IpsecInitialized")
0x1800e6b6f  mov     rcx, cs:g_Provider
0x1800e6b76  test    rcx, rcx
0x1800e6b79  jz      short loc_1800E6B94
0x1800e6b7b  xor     r9d, r9d
0x1800e6b7e  lea     rdx, MPS_SVC_BFE_EngineOpen_Enter
0x1800e6b85  xor     r8d, r8d
0x1800e6b88  call    cs:__imp_EtwEventWrite
0x1800e6b8f  nop     dword ptr [rax+rax+00h]
0x1800e6b94  xor     r8d, r8d; authIdentity
0x1800e6b97  lea     rax, engineHandle
0x1800e6b9e  lea     r9, stru_1800F9C50; session
0x1800e6ba5  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800e6baa  xor     ecx, ecx; serverName
0x1800e6bac  lea     edx, [r8+0Ah]; authnService
0x1800e6bb0  call    cs:__imp_FwpmEngineOpen0
0x1800e6bb7  nop     dword ptr [rax+rax+00h]
0x1800e6bbc  mov     rcx, cs:g_Provider
0x1800e6bc3  mov     ebx, eax
0x1800e6bc5  test    rcx, rcx
0x1800e6bc8  jz      short loc_1800E6BE3
0x1800e6bca  xor     r9d, r9d
0x1800e6bcd  lea     rdx, MPS_SVC_BFE_EngineOpen_Exit
0x1800e6bd4  xor     r8d, r8d
0x1800e6bd7  call    cs:__imp_EtwEventWrite
0x1800e6bde  nop     dword ptr [rax+rax+00h]
0x1800e6be3  mov     ecx, ebx; this
0x1800e6be5  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6bea  call    FwPlumber__CreateCallouts
0x1800e6bef  call    ?IpsecApiInitialize@@YAKPEAX@Z; IpsecApiInitialize(void *)
0x1800e6bf4  mov     ecx, eax; this
0x1800e6bf6  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6bfb  mov     esi, 1
0x1800e6c00  lea     rcx, Uuid; Uuid
0x1800e6c07  mov     cs:dword_180137F38, esi
0x1800e6c0d  call    cs:__imp_UuidCreate
0x1800e6c14  nop     dword ptr [rax+rax+00h]
0x1800e6c19  mov     ecx, eax; this
0x1800e6c1b  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6c20  mov     rcx, cs:engineHandle; engineHandle
0x1800e6c27  lea     r9, ?LSMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e6c2e  xor     r8d, r8d; sd
0x1800e6c31  mov     cs:?LSMProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::LSMProviderCtxtID
0x1800e6c3c  lea     rdx, Uuid; providerContext
0x1800e6c43  call    cs:__imp_FwpmProviderContextAdd0
0x1800e6c4a  nop     dword ptr [rax+rax+00h]
0x1800e6c4f  mov     rdx, cs:off_180130340; unsigned __int16 *
0x1800e6c56  lea     r12, ?g_FwProvCtxError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST g_FwProvCtxError
0x1800e6c5d  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e6c60  mov     ecx, eax; unsigned int
0x1800e6c62  mov     ebx, eax
0x1800e6c64  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e6c69  mov     ecx, ebx; this
0x1800e6c6b  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6c70  lea     rcx, stru_180130250; Uuid
0x1800e6c77  call    cs:__imp_UuidCreate
0x1800e6c7e  nop     dword ptr [rax+rax+00h]
0x1800e6c83  mov     ecx, eax; this
0x1800e6c85  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6c8a  mov     rcx, cs:engineHandle; engineHandle
0x1800e6c91  lea     r9, ?LOMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e6c98  xor     r8d, r8d; sd
0x1800e6c9b  mov     cs:?LOMProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::LOMProviderCtxtID
0x1800e6ca6  lea     rdx, stru_180130250; providerContext
0x1800e6cad  call    cs:__imp_FwpmProviderContextAdd0
0x1800e6cb4  nop     dword ptr [rax+rax+00h]
0x1800e6cb9  mov     rdx, cs:off_180130260; unsigned __int16 *
0x1800e6cc0  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e6cc3  mov     ecx, eax; unsigned int
0x1800e6cc5  mov     ebx, eax
0x1800e6cc7  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e6ccc  mov     ecx, ebx; this
0x1800e6cce  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6cd3  lea     rcx, stru_180130390; Uuid
0x1800e6cda  call    cs:__imp_UuidCreate
0x1800e6ce1  nop     dword ptr [rax+rax+00h]
0x1800e6ce6  mov     ecx, eax; this
0x1800e6ce8  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6ced  mov     rcx, cs:engineHandle; engineHandle
0x1800e6cf4  lea     r9, ?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA; id
0x1800e6cfb  xor     r8d, r8d; sd
0x1800e6cfe  mov     cs:?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::PolicySilentModeProviderCtxtID
0x1800e6d09  lea     rdx, stru_180130390; providerContext
0x1800e6d10  call    cs:__imp_FwpmProviderContextAdd0
0x1800e6d17  nop     dword ptr [rax+rax+00h]
0x1800e6d1c  mov     rdx, cs:off_1801303A0; unsigned __int16 *
0x1800e6d23  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e6d26  mov     ecx, eax; unsigned int
0x1800e6d28  mov     ebx, eax
0x1800e6d2a  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e6d2f  mov     ecx, ebx; this
0x1800e6d31  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6d36  mov     rcx, cs:engineHandle
0x1800e6d3d  lea     r9, ?QuarantineProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::QuarantineProviderCtxtID
0x1800e6d44  xor     r8d, r8d
0x1800e6d47  mov     cs:?QuarantineProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::QuarantineProviderCtxtID
0x1800e6d52  lea     rdx, qword_180130780
0x1800e6d59  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6d60  nop     dword ptr [rax+rax+00h]
0x1800e6d65  mov     ebx, 80320009h
0x1800e6d6a  cmp     eax, ebx
0x1800e6d6c  jnz     short loc_1800E6D76
0x1800e6d6e  mov     cs:?QuarantineProviderContextExists@FwPlumber@@3HA, esi; int FwPlumber::QuarantineProviderContextExists
0x1800e6d74  jmp     short loc_1800E6D7A
0x1800e6d76  test    eax, eax
0x1800e6d78  jz      short loc_1800E6DA0
0x1800e6d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6d81  cmp     rcx, r14
0x1800e6d84  jz      short loc_1800E6DA0
0x1800e6d86  test    [rcx+1Ch], sil
0x1800e6d8a  jz      short loc_1800E6DA0
0x1800e6d8c  mov     rcx, [rcx+10h]
0x1800e6d90  mov     edx, 6Eh ; 'n'
0x1800e6d95  mov     r9d, eax
0x1800e6d98  mov     r8, r15
0x1800e6d9b  call    WPP_SF_d
0x1800e6da0  mov     rcx, cs:engineHandle
0x1800e6da7  lea     r9, ?BootProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::BootProviderCtxtID
0x1800e6dae  xor     r8d, r8d
0x1800e6db1  mov     cs:?BootProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::BootProviderCtxtID
0x1800e6dbc  lea     rdx, qword_180130A70
0x1800e6dc3  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6dca  nop     dword ptr [rax+rax+00h]
0x1800e6dcf  cmp     eax, ebx
0x1800e6dd1  jnz     short loc_1800E6DDB
0x1800e6dd3  mov     cs:?BootProviderContextExists@FwPlumber@@3HA, esi; int FwPlumber::BootProviderContextExists
0x1800e6dd9  jmp     short loc_1800E6DDF
0x1800e6ddb  test    eax, eax
0x1800e6ddd  jz      short loc_1800E6E05
0x1800e6ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6de6  cmp     rcx, r14
0x1800e6de9  jz      short loc_1800E6E05
0x1800e6deb  test    [rcx+1Ch], sil
0x1800e6def  jz      short loc_1800E6E05
0x1800e6df1  mov     rcx, [rcx+10h]
0x1800e6df5  mov     edx, 6Fh ; 'o'
0x1800e6dfa  mov     r9d, eax
0x1800e6dfd  mov     r8, r15
0x1800e6e00  call    WPP_SF_d
0x1800e6e05  mov     rcx, cs:engineHandle
0x1800e6e0c  lea     r9, ?WshProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::WshProviderCtxtID
0x1800e6e13  xor     r8d, r8d
0x1800e6e16  mov     cs:?WshProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::WshProviderCtxtID
0x1800e6e21  lea     rdx, qword_180130970
0x1800e6e28  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6e2f  nop     dword ptr [rax+rax+00h]
0x1800e6e34  test    eax, eax
0x1800e6e36  jz      short loc_1800E6E5E
0x1800e6e38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6e3f  cmp     rcx, r14
0x1800e6e42  jz      short loc_1800E6E5E
0x1800e6e44  test    [rcx+1Ch], sil
0x1800e6e48  jz      short loc_1800E6E5E
0x1800e6e4a  mov     rcx, [rcx+10h]
0x1800e6e4e  mov     edx, 70h ; 'p'
0x1800e6e53  mov     r9d, eax
0x1800e6e56  mov     r8, r15
0x1800e6e59  call    WPP_SF_d
0x1800e6e5e  mov     rcx, cs:engineHandle
0x1800e6e65  lea     r9, ?QueryUserProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::QueryUserProviderCtxtID
0x1800e6e6c  xor     r8d, r8d
0x1800e6e6f  mov     cs:?QueryUserProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::QueryUserProviderCtxtID
0x1800e6e7a  lea     rdx, qword_180130B40
0x1800e6e81  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6e88  nop     dword ptr [rax+rax+00h]
0x1800e6e8d  test    eax, eax
0x1800e6e8f  jz      short loc_1800E6EB7
0x1800e6e91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6e98  cmp     rcx, r14
0x1800e6e9b  jz      short loc_1800E6EB7
0x1800e6e9d  test    [rcx+1Ch], sil
0x1800e6ea1  jz      short loc_1800E6EB7
0x1800e6ea3  mov     rcx, [rcx+10h]
0x1800e6ea7  mov     edx, 71h ; 'q'
0x1800e6eac  mov     r9d, eax
0x1800e6eaf  mov     r8, r15
0x1800e6eb2  call    WPP_SF_d
0x1800e6eb7  mov     rcx, cs:engineHandle
0x1800e6ebe  lea     r9, ?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::AppCLoopbackProviderCtxtID
0x1800e6ec5  xor     r8d, r8d
0x1800e6ec8  mov     cs:?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::AppCLoopbackProviderCtxtID
0x1800e6ed3  lea     rdx, qword_180130840
0x1800e6eda  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6ee1  nop     dword ptr [rax+rax+00h]
0x1800e6ee6  test    eax, eax
0x1800e6ee8  jz      short loc_1800E6F10
0x1800e6eea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6ef1  cmp     rcx, r14
0x1800e6ef4  jz      short loc_1800E6F10
0x1800e6ef6  test    [rcx+1Ch], sil
0x1800e6efa  jz      short loc_1800E6F10
0x1800e6efc  mov     rcx, [rcx+10h]
0x1800e6f00  mov     edx, 72h ; 'r'
0x1800e6f05  mov     r9d, eax
0x1800e6f08  mov     r8, r15
0x1800e6f0b  call    WPP_SF_d
0x1800e6f10  mov     rcx, cs:engineHandle
0x1800e6f17  lea     r9, ?StealthProviderCtxtID@FwPlumber@@3_KA; unsigned __int64 FwPlumber::StealthProviderCtxtID
0x1800e6f1e  xor     r8d, r8d
0x1800e6f21  mov     cs:?StealthProviderCtxtID@FwPlumber@@3_KA, 0; unsigned __int64 FwPlumber::StealthProviderCtxtID
0x1800e6f2c  lea     rdx, qword_180130AD0
0x1800e6f33  call    cs:__imp_FwpmProviderContextAdd3
0x1800e6f3a  nop     dword ptr [rax+rax+00h]
0x1800e6f3f  test    eax, eax
0x1800e6f41  jz      short loc_1800E6F69
0x1800e6f43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6f4a  cmp     rcx, r14
0x1800e6f4d  jz      short loc_1800E6F69
0x1800e6f4f  test    [rcx+1Ch], sil
0x1800e6f53  jz      short loc_1800E6F69
0x1800e6f55  mov     rcx, [rcx+10h]
0x1800e6f59  mov     edx, 73h ; 's'
0x1800e6f5e  mov     r9d, eax
0x1800e6f61  mov     r8, r15
0x1800e6f64  call    WPP_SF_d
0x1800e6f69  mov     edx, 44h ; 'D'; uBytes
0x1800e6f6e  xor     ecx, ecx; uFlags
0x1800e6f70  mov     [rbp+57h+cbSid], edx
0x1800e6f73  call    cs:__imp_LocalAlloc
0x1800e6f7a  nop     dword ptr [rax+rax+00h]
0x1800e6f7f  test    rax, rax
0x1800e6f82  mov     cs:?m_pNullSID@FwPlumber@@3PEAXEA, rax; void * FwPlumber::m_pNullSID
0x1800e6f89  mov     edx, 8007000Eh; bool
0x1800e6f8e  setz    cl; this
0x1800e6f91  call    ?ThrowIf@FwPlumber@@YAX_NJ@Z; FwPlumber::ThrowIf(bool,long)
0x1800e6f96  mov     r8, cs:?m_pNullSID@FwPlumber@@3PEAXEA; pSid
0x1800e6f9d  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800e6fa1  xor     edx, edx; DomainSid
0x1800e6fa3  xor     ecx, ecx; WellKnownSidType
0x1800e6fa5  call    cs:__imp_CreateWellKnownSid
0x1800e6fac  nop     dword ptr [rax+rax+00h]
0x1800e6fb1  mov     ecx, eax; this
0x1800e6fb3  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x1800e6fb8  xor     r9d, r9d; SecurityDescriptorSize
0x1800e6fbb  lea     r8, ?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA; SecurityDescriptor
0x1800e6fc2  mov     edx, esi; StringSDRevision
0x1800e6fc4  lea     rcx, aOLsdACcS11533A; "O:LSD:(A;;CC;;;S-1-15-3-3)(A;;CC;;;WD)("...
0x1800e6fcb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800e6fd2  nop     dword ptr [rax+rax+00h]
0x1800e6fd7  mov     ecx, eax; this
0x1800e6fd9  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x1800e6fde  xor     r9d, r9d; SecurityDescriptorSize
0x1800e6fe1  lea     r8, ?m_pAllAppContainersSd@FwPlumber@@3PEAXEA; SecurityDescriptor
0x1800e6fe8  mov     edx, esi; StringSDRevision
0x1800e6fea  lea     rcx, aOLsdACcAcACcS1; "O:LSD:(A;;CC;;;AC)(A;;CC;;;S-1-15-3-1)("...
0x1800e6ff1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800e6ff8  nop     dword ptr [rax+rax+00h]
0x1800e6ffd  mov     ecx, eax; this
0x1800e6fff  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x1800e7004  xor     edx, edx; Val
0x1800e7006  lea     rcx, [rbp+57h+callout.calloutKey.Data2]; void *
0x1800e700a  lea     r8d, [rdx+54h]; Size
0x1800e700e  call    memset_0
0x1800e7013  movups  xmm0, xmmword ptr cs:stru_180131AD8.Data1
0x1800e701a  mov     rcx, cs:engineHandle; engineHandle
0x1800e7021  lea     rax, xmmword_180131D10
0x1800e7028  lea     rbx, aInterfaceBindi; "Interface Binding Callout"
0x1800e702f  mov     [rbp+57h+callout.flags], 20000h
0x1800e7036  movdqu  xmmword ptr [rbp-49h], xmm0
0x1800e703b  xor     r9d, r9d; id
0x1800e703e  xor     r8d, r8d; sd
0x1800e7041  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V4.Data1
0x1800e7048  lea     rdx, [rbp+57h+callout]; callout
0x1800e704c  mov     [rbp+57h+callout.displayData.name], rbx
0x1800e7050  mov     [rbp+57h+callout.providerKey], rax
0x1800e7054  movdqu  xmmword ptr [rbp+57h+callout.applicableLayer.Data1], xmm0
0x1800e7059  call    cs:__imp_FwpmCalloutAdd0
0x1800e7060  nop     dword ptr [rax+rax+00h]
0x1800e7065  mov     r8, r12; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e7068  mov     rdx, rbx; unsigned __int16 *
0x1800e706b  mov     ecx, eax; unsigned int
0x1800e706d  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e7072  movups  xmm0, cs:xmmword_180131AC0
0x1800e7079  mov     rcx, cs:engineHandle; engineHandle
0x1800e7080  xor     r9d, r9d; id
0x1800e7083  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V6.Data1
  ... truncated ...
```
