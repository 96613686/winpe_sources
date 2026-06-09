# CFveApi::RefreshTpmBindings(void)

- ea: `0x1800d32ac`
- end: `0x1800d3c5e`
- name: `?RefreshTpmBindings@CFveApi@@QEAAJXZ`
- size: `2482`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c60fc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x18000ba30`
- `0x180018b10`
- `0x180019128`
- `0x18001f010`
- `0x180037f50`
- `0x18003e7a8`
- `0x18003ed0c`
- `0x180048ecc`
- `0x18004dba8`
- `0x180050154`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180076b1c`
- `0x18007dfc8`
- `0x1800921e0`
- `0x180098cf8`
- `0x18009f544`
- `0x18009f6ec`
- `0x1800a111c`
- `0x1800a21e0`
- `0x1800a2cb4`
- `0x1800a30d4`
- `0x1800ad18c`
- `0x1800d206c`
- `0x1800d20d0`
- `0x1800d32ac`
- `0x1800d4550`
- `0x180111098`
- `0x18011a4dc`
- `0x18011f010`

## import_xrefs

- `pcrpf!PpfFreePredictions` at `0x1800d3b66`
- `pcrpf!PpfFreePredictions` at `0x18012894a`
- `pcrpf!PpfFreePredictions` at `0x1800d3b66`
- `pcrpf!PpfFreePredictions` at `0x18012894a`

## string_xrefs

- `0x1800d39ff`: `VolumePath`
- `0x1800d34d3`: `FveQueryConsiderTpmProtectorVersionUpgradeImpl`
- `0x1800d3780`: `CreateTpmProtectorBindingDigestSourceData`
- `0x1800d33f2`: `CreateTPMContext`

## pseudocode

```c
__int64 __fastcall CFveApi::RefreshTpmBindings(CFveApi *this)
{
  int Policy; // ebx
  const char *v3; // rax
  __int64 v4; // rdx
  unsigned int v5; // edx
  int TpmProtectorVersion; // ebx
  PVOID *v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  struct _FVE_NONCE *v12; // rax
  __int64 v13; // rdx
  int refreshed; // eax
  __int64 v15; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v19; // rdx
  struct _FVE_TPM_BINDING_CENSUS **v20; // rcx
  unsigned __int16 v21; // di
  unsigned __int16 i; // dx
  unsigned int v24; // [rsp+20h] [rbp-348h]
  unsigned int v25; // [rsp+20h] [rbp-348h]
  char *v26; // [rsp+28h] [rbp-340h]
  char *v27; // [rsp+28h] [rbp-340h]
  __int64 v28; // [rsp+30h] [rbp-338h]
  int v29[3]; // [rsp+54h] [rbp-314h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-308h] BYREF
  void *lpMem; // [rsp+68h] [rbp-300h] BYREF
  struct _GUID v32; // [rsp+70h] [rbp-2F8h] BYREF
  __int64 v33; // [rsp+80h] [rbp-2E8h]
  __int128 v34; // [rsp+88h] [rbp-2E0h]
  const wchar_t *v35; // [rsp+98h] [rbp-2D0h]
  const wchar_t *v36; // [rsp+A0h] [rbp-2C8h]
  __int64 v37; // [rsp+A8h] [rbp-2C0h]
  int v38; // [rsp+B0h] [rbp-2B8h]
  struct _FVE_TPM_BINDING_CENSUS **v39; // [rsp+B8h] [rbp-2B0h] BYREF
  void *v40; // [rsp+C0h] [rbp-2A8h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-2A0h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-298h] BYREF
  _QWORD *v43; // [rsp+E0h] [rbp-288h] BYREF
  _QWORD **v44; // [rsp+E8h] [rbp-280h]
  __int128 v45; // [rsp+F0h] [rbp-278h] BYREF
  __int128 v46; // [rsp+100h] [rbp-268h]
  __int128 v47; // [rsp+110h] [rbp-258h]
  unsigned __int16 v48[2]; // [rsp+120h] [rbp-248h] BYREF
  unsigned __int16 v49; // [rsp+124h] [rbp-244h] BYREF
  int v50; // [rsp+128h] [rbp-240h] BYREF
  __int128 v51; // [rsp+130h] [rbp-238h] BYREF
  _QWORD v52[6]; // [rsp+140h] [rbp-228h] BYREF
  _OWORD v53[3]; // [rsp+170h] [rbp-1F8h] BYREF
  _OWORD v54[3]; // [rsp+1A0h] [rbp-1C8h] BYREF
  _BYTE v55[336]; // [rsp+1D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  v45 = 0;
  v46 = 0;
  v47 = 0;
  v51 = 0;
  v30 = -1;
  *(_QWORD *)&v29[1] = 0;
  v50 = 1;
  v29[0] = 1;
  v49 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v48[0] = 0;
  *(_QWORD *)&v32.Data1 = 0;
  lpMem = 0;
  BitLockerFveapiProvider::RefreshTPMBindingsActivity::Start<>((BitLockerFveapiProvider::RefreshTPMBindingsActivity *)v55);
  Policy = CFveApiBase::CheckInited(this);
  if ( Policy < 0 )
  {
    v3 = "CheckInited";
    v4 = 81;
LABEL_3:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)Policy,
      (int)v3,
      v26);
    goto LABEL_71;
  }
  Policy = CFveApiBase::PrepareNonce(this);
  if ( Policy < 0 )
  {
    v3 = "PrepareNonce";
    v4 = 87;
    goto LABEL_3;
  }
  Policy = CFveApiBase::GetPolicy(this, (struct CFvePolicy **)&v32);
  if ( Policy < 0 )
  {
    v3 = "GetFvePolicy";
    v4 = 93;
    goto LABEL_3;
  }
  Policy = CFveApiBase::CreateTpmContext(this, *(struct CFvePolicy **)&v32.Data1, (struct CFveTpm **)&v29[1]);
  if ( Policy < 0 )
  {
    v3 = "CreateTPMContext";
    v4 = 99;
    goto LABEL_3;
  }
  TpmProtectorVersion = CFveApiBase::GetTpmProtectorVersion(this, 0, (enum _FVE_TPM_PROTECTOR_VERSION *)v29);
  if ( TpmProtectorVersion >= 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)TpmProtectorVersion,
      (int)"GetTpmProtectorVersion",
      v26);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids,
        (unsigned int)TpmProtectorVersion);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_D(v7[2], 11, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, (unsigned int)v29[0]);
  Policy = CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl((enum _FVE_DATA_TPM_PROTECTOR_VERSION *)&v50);
  if ( Policy < 0 )
  {
    v3 = "FveQueryConsiderTpmProtectorVersionUpgradeImpl";
    v4 = 120;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids,
      (unsigned int)v50);
  Policy = CFveApiBase::GetTpmProtectorBindingCensus(this, 0, 0, v48, &v39);
  if ( Policy < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)Policy,
      (int)"GetTpmProtectorBindingCensus",
      v26);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 13;
LABEL_28:
      WPP_SF_d(v8[2], v9, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, (unsigned int)Policy);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  if ( !v48[0] )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v11 = 14;
LABEL_33:
    WPP_SF_(v10[2], v11, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids);
LABEL_34:
    Policy = -2147418113;
    goto LABEL_71;
  }
  if ( !*(_WORD *)*v39 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v11 = 15;
    goto LABEL_33;
  }
  Policy = CFveApi::GetDefaultPcrProfile(this, &v32, &v30);
  if ( Policy < 0 )
  {
    v3 = "GetDefaultPcrProfile";
    v4 = 154;
    goto LABEL_3;
  }
  if ( v30 != -1 )
  {
    Policy = CFveTpm::SetCallerSuppliedPcrBitmap(*(_QWORD *)&v29[1], v30, 9);
    if ( Policy < 0 )
    {
      v3 = "SetCallerSuppliedPcrBitmap";
      v4 = 163;
      goto LABEL_3;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
    || (*((_DWORD *)this + 27) & 0x10000001) != 0 )
  {
LABEL_54:
    Policy = CreateTpmProtectorBindingDigestSourceData(
               *(CFveTpm **)&v29[1],
               (unsigned int)v50,
               0,
               0,
               (unsigned int *)*v39 + 10,
               (unsigned __int16 *)lpMem,
               &v49,
               &v40,
               &v41);
    if ( Policy >= 0 )
    {
      LODWORD(v45) = v50;
      *((_QWORD *)&v45 + 1) = v40;
      *(_QWORD *)&v46 = *(_QWORD *)&v29[1];
      DWORD2(v46) = 2;
      *(_QWORD *)&v47 = *((_QWORD *)this + 146);
      WORD4(v47) = v49;
      v12 = CFveApiBase::GetAndUseNonce(this);
      refreshed = FveWorksetRefreshTpmBindings(v12, v13, &v45, &v51);
      Policy = FromNtStatus(refreshed);
      if ( Policy >= 0 )
      {
        v42 = 0;
        *(_QWORD *)&v32.Data1 = 0;
        *(_QWORD *)v32.Data4 = 0;
        v33 = 0;
        v44 = &v43;
        v43 = &v43;
        v15 = *((_QWORD *)this + 146);
        v34 = 0;
        v35 = L"IdentityGuid";
        v36 = L"GUID";
        v37 = v15 + 16;
        v38 = 16;
        v52[2] = L"IdentityGuid";
        v52[3] = L"GUID";
        v52[4] = v15 + 16;
        v52[5] = 16;
        v52[0] = &v43;
        v52[1] = &v43;
        v43 = v52;
        v44 = (_QWORD **)v52;
        memset(v53, 0, sizeof(v53));
        LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v53, v17, L"VolumePath", LoggingVolumePath, v24);
        if ( *v44 != &v43 )
          __fastfail(3u);
        *(_QWORD *)&v53[0] = &v43;
        *((_QWORD *)&v53[0] + 1) = v44;
        *v44 = v53;
        v44 = (_QWORD **)v53;
        memset(v54, 0, sizeof(v54));
        LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
        FveApiEventLogDeclareWSTRING(
          (struct _FVEAPI_EVENT_DATA *)v54,
          v19,
          L"VolumeDriveLetter",
          LoggingVolumeDriveLetter,
          v25);
        if ( *v44 != &v43 )
          __fastfail(3u);
        *(_QWORD *)&v54[0] = &v43;
        *((_QWORD *)&v54[0] + 1) = v44;
        *v44 = v54;
        v44 = (_QWORD **)v54;
        *((_QWORD *)&v42 + 1) = FVEAPI_OP_BOOT_SETTINGS_RESEAL_TPM;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v32, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v42);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v32);
        CFveApiBase::LogTpmProtectorBindingCensus(this, 0);
      }
      else
      {
        if ( Policy == (unsigned int)FromNtStatus(-1071579052) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, v51);
        }
        else if ( *(int *)(*(_QWORD *)&v29[1] + 44LL) < 0 )
        {
          Policy = *(_DWORD *)(*(_QWORD *)&v29[1] + 44LL);
        }
        LODWORD(v28) = v50;
        LODWORD(v27) = v29[0];
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xF4,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
          (const char *)(unsigned int)Policy,
          (int)"FveWorksetRefreshTpmBindings Prev TPMP version %d TPMP version to upgrade to %d",
          v27,
          v28);
      }
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
        (const char *)(unsigned int)Policy,
        (int)"CreateTpmProtectorBindingDigestSourceData",
        v27);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 18;
        goto LABEL_28;
      }
    }
    goto LABEL_71;
  }
  Policy = CFveApiBase::GetPredictionInstanceMapping(this, (unsigned __int16 **)&lpMem);
  if ( Policy >= 0 )
  {
    if ( lpMem && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, lpMem);
    goto LABEL_54;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xB2,
    (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
    (const char *)(unsigned int)Policy,
    (int)"GetPredictionInstanceMapping",
    v26);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 16;
    goto LABEL_28;
  }
LABEL_71:
  if ( *(_QWORD *)&v29[1] )
    CFveTpm::`scalar deleting destructor'(*(CFveTpm **)&v29[1], v5);
  if ( v40 )
  {
    CFveApiBase::ZeroFree(v40, 584LL * v49);
    v40 = 0;
  }
  if ( v41 )
  {
    PpfFreePredictions(v41);
    v41 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
    && lpMem )
  {
    CFveApiBase::FastFree(lpMem);
  }
  v20 = v39;
  if ( v39 )
  {
    v21 = 0;
    for ( i = v48[0]; v21 < i; ++v21 )
    {
      if ( v20[v21] )
      {
        FveFreeTpmBindingCensus(v20[v21]);
        v39[v21] = 0;
        v20 = v39;
        i = v48[0];
      }
    }
    CFveApiBase::ZeroFree(v20, 8LL * i);
    v39 = 0;
  }
  BitLockerFveapiProvider::RefreshTPMBindingsActivity::StopActivity(
    (BitLockerFveapiProvider::RefreshTPMBindingsActivity *)v55,
    Policy,
    v29[0],
    v50,
    v49);
  BitLockerFveapiProvider::RefreshTPMBindingsActivity::~RefreshTPMBindingsActivity((BitLockerFveapiProvider::RefreshTPMBindingsActivity *)v55);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x1800d32ac  mov     r11, rsp
0x1800d32af  push    rbx
0x1800d32b0  push    rsi
0x1800d32b1  push    rdi
0x1800d32b2  push    r13
0x1800d32b4  push    r14
0x1800d32b6  push    r15
0x1800d32b8  sub     rsp, 338h
0x1800d32bf  mov     rax, cs:__security_cookie
0x1800d32c6  xor     rax, rsp
0x1800d32c9  mov     [rsp+368h+var_48], rax
0x1800d32d1  mov     rsi, rcx
0x1800d32d4  xorps   xmm0, xmm0
0x1800d32d7  movups  [rsp+368h+var_278], xmm0
0x1800d32df  movups  [rsp+368h+var_268], xmm0
0x1800d32e7  movups  [rsp+368h+var_258], xmm0
0x1800d32ef  movups  [rsp+368h+var_238], xmm0
0x1800d32f7  mov     [rsp+368h+var_308], 0FFFFFFFFh
0x1800d32ff  xor     r15d, r15d
0x1800d3302  mov     qword ptr [rsp+368h+var_314+4], r15
0x1800d3307  lea     r13d, [r15+1]
0x1800d330b  mov     [r11-240h], r13d
0x1800d3312  mov     dword ptr [rsp+368h+var_314], r13d
0x1800d3317  mov     [r11-244h], r15w
0x1800d331f  mov     [r11-2A8h], r15
0x1800d3326  mov     [r11-2A0h], r15
0x1800d332d  mov     [r11-2B0h], r15
0x1800d3334  mov     [r11-248h], r15w
0x1800d333c  mov     qword ptr [rsp+368h+var_2F8.Data1], r15
0x1800d3341  mov     [rsp+368h+lpMem], r15
0x1800d3346  lea     rcx, [r11-198h]; this
0x1800d334d  call    ??$Start@$$V@RefreshTPMBindingsActivity@BitLockerFveapiProvider@@SA?AV01@XZ; BitLockerFveapiProvider::RefreshTPMBindingsActivity::Start<>(void)
0x1800d3352  nop
0x1800d3353  mov     rcx, rsi; this
0x1800d3356  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800d335b  mov     ebx, eax
0x1800d335d  mov     [rsp+368h+var_318], eax
0x1800d3361  test    eax, eax
0x1800d3363  jns     short loc_1800D3391
0x1800d3365  lea     rax, aCheckinited_0; "CheckInited"
0x1800d336c  lea     edx, [r15+51h]; void *
0x1800d3370  mov     rcx, [rsp+368h]; this
0x1800d3378  mov     [rsp+368h+var_348], rax; int
0x1800d337d  mov     r9d, ebx; char *
0x1800d3380  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d3387  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d338c  jmp     loc_1800D3B21
0x1800d3391  mov     rcx, rsi; this
0x1800d3394  call    ?PrepareNonce@CFveApiBase@@QEAAJXZ; CFveApiBase::PrepareNonce(void)
0x1800d3399  mov     ebx, eax
0x1800d339b  mov     [rsp+368h+var_318], eax
0x1800d339f  test    eax, eax
0x1800d33a1  jns     short loc_1800D33B1
0x1800d33a3  lea     rax, aPreparenonce; "PrepareNonce"
0x1800d33aa  mov     edx, 57h ; 'W'
0x1800d33af  jmp     short loc_1800D3370
0x1800d33b1  lea     rdx, [rsp+368h+var_2F8]; struct CFvePolicy **
0x1800d33b6  mov     rcx, rsi; this
0x1800d33b9  call    ?GetPolicy@CFveApiBase@@IEAAJPEAPEAVCFvePolicy@@@Z; CFveApiBase::GetPolicy(CFvePolicy * *)
0x1800d33be  mov     ebx, eax
0x1800d33c0  mov     [rsp+368h+var_318], eax
0x1800d33c4  test    eax, eax
0x1800d33c6  jns     short loc_1800D33D6
0x1800d33c8  lea     rax, aGetfvepolicy; "GetFvePolicy"
0x1800d33cf  mov     edx, 5Dh ; ']'
0x1800d33d4  jmp     short loc_1800D3370
0x1800d33d6  lea     r8, [rsp+368h+var_314+4]; struct CFveTpm **
0x1800d33db  mov     rdx, qword ptr [rsp+368h+var_2F8.Data1]; struct CFvePolicy *
0x1800d33e0  mov     rcx, rsi; this
0x1800d33e3  call    ?CreateTpmContext@CFveApiBase@@QEAAJPEAVCFvePolicy@@PEAPEAVCFveTpm@@@Z; CFveApiBase::CreateTpmContext(CFvePolicy *,CFveTpm * *)
0x1800d33e8  mov     ebx, eax
0x1800d33ea  mov     [rsp+368h+var_318], eax
0x1800d33ee  test    eax, eax
0x1800d33f0  jns     short loc_1800D3403
0x1800d33f2  lea     rax, aCreatetpmconte; "CreateTPMContext"
0x1800d33f9  mov     edx, 63h ; 'c'
0x1800d33fe  jmp     loc_1800D3370
0x1800d3403  lea     r8, [rsp+368h+var_314]; enum _FVE_TPM_PROTECTOR_VERSION *
0x1800d3408  xor     edx, edx; struct _GUID *
0x1800d340a  mov     rcx, rsi; this
0x1800d340d  call    ?GetTpmProtectorVersion@CFveApiBase@@QEAAJPEBU_GUID@@PEAW4_FVE_TPM_PROTECTOR_VERSION@@@Z; CFveApiBase::GetTpmProtectorVersion(_GUID const *,_FVE_TPM_PROTECTOR_VERSION *)
0x1800d3412  mov     ebx, eax
0x1800d3414  mov     [rsp+368h+var_318], eax
0x1800d3418  test    eax, eax
0x1800d341a  jns     short loc_1800D3486
0x1800d341c  mov     rcx, [rsp+368h]; this
0x1800d3424  lea     rax, aGettpmprotecto; "GetTpmProtectorVersion"
0x1800d342b  mov     [rsp+368h+var_348], rax; int
0x1800d3430  mov     r9d, ebx; char *
0x1800d3433  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d343a  mov     edx, 6Eh ; 'n'; void *
0x1800d343f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d3444  lea     r14, WPP_GLOBAL_Control
0x1800d344b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3452  lea     rdi, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids
0x1800d3459  cmp     rcx, r14
0x1800d345c  jz      short loc_1800D347F
0x1800d345e  test    byte ptr [rcx+1Ch], 8
0x1800d3462  jz      short loc_1800D347F
0x1800d3464  mov     edx, 0Ah
0x1800d3469  mov     r9d, ebx
0x1800d346c  mov     r8, rdi
0x1800d346f  mov     rcx, [rcx+10h]
0x1800d3473  call    WPP_SF_d
0x1800d3478  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d347f  mov     [rsp+368h+var_318], r15d
0x1800d3484  jmp     short loc_1800D349B
0x1800d3486  lea     r14, WPP_GLOBAL_Control
0x1800d348d  lea     rdi, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids
0x1800d3494  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d349b  cmp     rcx, r14
0x1800d349e  jz      short loc_1800D34BC
0x1800d34a0  test    byte ptr [rcx+1Ch], 8
0x1800d34a4  jz      short loc_1800D34BC
0x1800d34a6  mov     edx, 0Bh
0x1800d34ab  mov     r9d, dword ptr [rsp+368h+var_314]
0x1800d34b0  mov     r8, rdi
0x1800d34b3  mov     rcx, [rcx+10h]
0x1800d34b7  call    WPP_SF_D
0x1800d34bc  lea     rcx, [rsp+368h+var_240]; enum _FVE_DATA_TPM_PROTECTOR_VERSION *
0x1800d34c4  call    ?FveQueryConsiderTpmProtectorVersionUpgradeImpl@CFveApiBase@@SAJPEAW4_FVE_DATA_TPM_PROTECTOR_VERSION@@@Z; CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl(_FVE_DATA_TPM_PROTECTOR_VERSION *)
0x1800d34c9  mov     ebx, eax
0x1800d34cb  mov     [rsp+368h+var_318], eax
0x1800d34cf  test    eax, eax
0x1800d34d1  jns     short loc_1800D34E4
0x1800d34d3  lea     rax, aFvequeryconsid; "FveQueryConsiderTpmProtectorVersionUpgr"...
0x1800d34da  mov     edx, 78h ; 'x'
0x1800d34df  jmp     loc_1800D3370
0x1800d34e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d34eb  cmp     rcx, r14
0x1800d34ee  jz      short loc_1800D350F
0x1800d34f0  test    byte ptr [rcx+1Ch], 8
0x1800d34f4  jz      short loc_1800D350F
0x1800d34f6  mov     edx, 0Ch
0x1800d34fb  mov     r9d, [rsp+368h+var_240]
0x1800d3503  mov     r8, rdi
0x1800d3506  mov     rcx, [rcx+10h]
0x1800d350a  call    WPP_SF_D
0x1800d350f  lea     rax, [rsp+368h+var_2B0]
0x1800d3517  mov     [rsp+368h+var_348], rax; struct _FVE_TPM_BINDING_CENSUS ***
0x1800d351c  lea     r9, [rsp+368h+var_248]; unsigned __int16 *
0x1800d3524  xor     r8d, r8d; unsigned __int8
0x1800d3527  xor     edx, edx; struct _GUID *
0x1800d3529  mov     rcx, rsi; this
0x1800d352c  call    ?GetTpmProtectorBindingCensus@CFveApiBase@@QEAAJPEBU_GUID@@EPEAGPEAPEAPEAU_FVE_TPM_BINDING_CENSUS@@@Z; CFveApiBase::GetTpmProtectorBindingCensus(_GUID const *,uchar,ushort *,_FVE_TPM_BINDING_CENSUS * * *)
0x1800d3531  mov     ebx, eax
0x1800d3533  mov     [rsp+368h+var_318], eax
0x1800d3537  test    eax, eax
0x1800d3539  jns     short loc_1800D3596
0x1800d353b  mov     rcx, [rsp+368h]; this
0x1800d3543  lea     rax, aGettpmprotecto_0; "GetTpmProtectorBindingCensus"
0x1800d354a  mov     [rsp+368h+var_348], rax; int
0x1800d354f  mov     r9d, ebx; char *
0x1800d3552  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d3559  mov     edx, 86h; void *
0x1800d355e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d3563  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d356a  cmp     rcx, r14
0x1800d356d  jz      loc_1800D3B21
0x1800d3573  test    byte ptr [rcx+1Ch], 2
0x1800d3577  jz      loc_1800D3B21
0x1800d357d  mov     edx, 0Dh
0x1800d3582  mov     r9d, ebx
0x1800d3585  mov     r8, rdi
0x1800d3588  mov     rcx, [rcx+10h]
0x1800d358c  call    WPP_SF_d
0x1800d3591  jmp     loc_1800D3B21
0x1800d3596  cmp     [rsp+368h+var_248], r15w
0x1800d359f  jnz     short loc_1800D35D2
0x1800d35a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d35a8  cmp     rcx, r14
0x1800d35ab  jz      short loc_1800D35C4
0x1800d35ad  test    byte ptr [rcx+1Ch], 2
0x1800d35b1  jz      short loc_1800D35C4
0x1800d35b3  mov     edx, 0Eh
0x1800d35b8  mov     r8, rdi
0x1800d35bb  mov     rcx, [rcx+10h]
0x1800d35bf  call    WPP_SF_
0x1800d35c4  mov     ebx, 8000FFFFh
0x1800d35c9  mov     [rsp+368h+var_318], ebx
0x1800d35cd  jmp     loc_1800D3B21
0x1800d35d2  mov     rax, [rsp+368h+var_2B0]
0x1800d35da  mov     rcx, [rax]
0x1800d35dd  cmp     [rcx], r15w
0x1800d35e1  jnz     short loc_1800D35FC
0x1800d35e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d35ea  cmp     rcx, r14
0x1800d35ed  jz      short loc_1800D35C4
0x1800d35ef  test    byte ptr [rcx+1Ch], 2
0x1800d35f3  jz      short loc_1800D35C4
0x1800d35f5  mov     edx, 0Fh
0x1800d35fa  jmp     short loc_1800D35B8
0x1800d35fc  lea     r8, [rsp+368h+var_308]; unsigned int *
0x1800d3601  lea     rdx, [rsp+368h+var_2F8]; struct _GUID *
0x1800d3606  mov     rcx, rsi; this
0x1800d3609  call    ?GetDefaultPcrProfile@CFveApi@@QEAAJPEAU_GUID@@PEAK@Z; CFveApi::GetDefaultPcrProfile(_GUID *,ulong *)
0x1800d360e  mov     ebx, eax
0x1800d3610  mov     [rsp+368h+var_318], eax
0x1800d3614  test    eax, eax
0x1800d3616  jns     short loc_1800D3629
0x1800d3618  lea     rax, aGetdefaultpcrp_0; "GetDefaultPcrProfile"
0x1800d361f  mov     edx, 9Ah
0x1800d3624  jmp     loc_1800D3370
0x1800d3629  mov     edx, [rsp+368h+var_308]
0x1800d362d  cmp     edx, 0FFFFFFFFh
0x1800d3630  jz      short loc_1800D365E
0x1800d3632  xor     r9d, r9d
0x1800d3635  lea     r8d, [r9+9]
0x1800d3639  mov     rcx, qword ptr [rsp+368h+var_314+4]
0x1800d363e  call    ?SetCallerSuppliedPcrBitmap@CFveTpm@@QEAAJKW4ePcrBitmapSource@@_N@Z; CFveTpm::SetCallerSuppliedPcrBitmap(ulong,ePcrBitmapSource,bool)
0x1800d3643  mov     ebx, eax
0x1800d3645  mov     [rsp+368h+var_318], eax
0x1800d3649  test    eax, eax
0x1800d364b  jns     short loc_1800D365E
0x1800d364d  lea     rax, aSetcallersuppl_0; "SetCallerSuppliedPcrBitmap"
0x1800d3654  mov     edx, 0A3h
0x1800d3659  jmp     loc_1800D3370
0x1800d365e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800d3665  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800d366a  test    al, al
0x1800d366c  jz      loc_1800D3712
0x1800d3672  test    dword ptr [rsi+6Ch], 10000001h
0x1800d3679  jnz     loc_1800D3712
0x1800d367f  lea     rdx, [rsp+368h+lpMem]; unsigned __int16 **
0x1800d3684  mov     rcx, rsi; this
0x1800d3687  call    ?GetPredictionInstanceMapping@CFveApiBase@@QEAAJPEAPEAG@Z; CFveApiBase::GetPredictionInstanceMapping(ushort * *)
0x1800d368c  mov     ebx, eax
0x1800d368e  mov     [rsp+368h+var_318], eax
0x1800d3692  test    eax, eax
0x1800d3694  jns     short loc_1800D36E2
0x1800d3696  mov     rcx, [rsp+368h]; this
0x1800d369e  lea     rax, aGetpredictioni; "GetPredictionInstanceMapping"
0x1800d36a5  mov     [rsp+368h+var_348], rax; int
0x1800d36aa  mov     r9d, ebx; char *
0x1800d36ad  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d36b4  mov     edx, 0B2h; void *
0x1800d36b9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d36be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d36c5  cmp     rcx, r14
0x1800d36c8  jz      loc_1800D3B21
0x1800d36ce  test    byte ptr [rcx+1Ch], 2
0x1800d36d2  jz      loc_1800D3B21
0x1800d36d8  mov     edx, 10h
0x1800d36dd  jmp     loc_1800D3582
0x1800d36e2  mov     rcx, [rsp+368h+lpMem]
0x1800d36e7  test    rcx, rcx
0x1800d36ea  jz      short loc_1800D3712
0x1800d36ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800d36f3  cmp     rax, r14
0x1800d36f6  jz      short loc_1800D3712
0x1800d36f8  test    byte ptr [rax+1Ch], 8
0x1800d36fc  jz      short loc_1800D3712
0x1800d36fe  mov     edx, 11h
0x1800d3703  mov     r9, rcx
0x1800d3706  mov     r8, rdi
0x1800d3709  mov     rcx, [rax+10h]
0x1800d370d  call    WPP_SF_S
0x1800d3712  mov     rax, [rsp+368h+var_2B0]
0x1800d371a  mov     rcx, [rax]
0x1800d371d  add     rcx, 28h ; '('
0x1800d3721  lea     rax, [rsp+368h+var_2A0]
0x1800d3729  mov     [rsp+368h+var_328], rax
0x1800d372e  lea     rax, [rsp+368h+var_2A8]
0x1800d3736  mov     [rsp+368h+var_330], rax
0x1800d373b  lea     rax, [rsp+368h+var_244]
0x1800d3743  mov     [rsp+368h+var_338], rax
0x1800d3748  mov     rax, [rsp+368h+lpMem]
0x1800d374d  mov     [rsp+368h+var_340], rax; char *
0x1800d3752  mov     [rsp+368h+var_348], rcx; unsigned int
0x1800d3757  xor     r9d, r9d
0x1800d375a  xor     r8d, r8d
0x1800d375d  mov     edx, [rsp+368h+var_240]
0x1800d3764  mov     rcx, qword ptr [rsp+368h+var_314+4]
0x1800d3769  call    ?CreateTpmProtectorBindingDigestSourceData@@YAJPEAVCFveTpm@@W4_FVE_DATA_TPM_PROTECTOR_VERSION@@_NPEAU_FVE_TPM_STATE_INFO_PARAMS@@PEBKPEBGPEAGPEAPEAU_FVE_TPM_DIGEST_SOURCE_DATA@@PEAPEAUPPF_PREDICTIONS@@@Z; CreateTpmProtectorBindingDigestSourceData(CFveTpm *,_FVE_DATA_TPM_PROTECTOR_VERSION,bool,_FVE_TPM_STATE_INFO_PARAMS *,ulong const *,ushort const *,ushort *,_FVE_TPM_DIGEST_SOURCE_DATA * *,PPF_PREDICTIONS * *)
0x1800d376e  mov     ebx, eax
0x1800d3770  mov     [rsp+368h+var_318], eax
0x1800d3774  test    eax, eax
0x1800d3776  jns     short loc_1800D37C4
0x1800d3778  mov     rcx, [rsp+368h]; this
0x1800d3780  lea     rax, aCreatetpmprote; "CreateTpmProtectorBindingDigestSourceDa"...
0x1800d3787  mov     [rsp+368h+var_348], rax; int
0x1800d378c  mov     r9d, ebx; char *
0x1800d378f  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d3796  mov     edx, 0CDh; void *
0x1800d379b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d37a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d37a7  cmp     rcx, r14
0x1800d37aa  jz      loc_1800D3B21
0x1800d37b0  test    byte ptr [rcx+1Ch], 2
0x1800d37b4  jz      loc_1800D3B21
0x1800d37ba  mov     edx, 12h
0x1800d37bf  jmp     loc_1800D3582
0x1800d37c4  mov     eax, [rsp+368h+var_240]
0x1800d37cb  mov     dword ptr [rsp+368h+var_278], eax
0x1800d37d2  mov     rax, [rsp+368h+var_2A8]
0x1800d37da  mov     qword ptr [rsp+368h+var_278+8], rax
0x1800d37e2  mov     rax, qword ptr [rsp+368h+var_314+4]
0x1800d37e7  mov     qword ptr [rsp+368h+var_268], rax
0x1800d37ef  mov     dword ptr [rsp+368h+var_268+8], 2
0x1800d37fa  mov     rax, [rsi+490h]
  ... truncated ...
```
