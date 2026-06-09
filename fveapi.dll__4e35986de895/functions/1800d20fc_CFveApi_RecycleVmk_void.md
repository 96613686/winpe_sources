# CFveApi::RecycleVmk(void)

- ea: `0x1800d20fc`
- end: `0x1800d2c20`
- name: `?RecycleVmk@CFveApi@@QEAAJXZ`
- size: `2852`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `39`
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
- `0x18001ac58`
- `0x18001b260`
- `0x18001f010`
- `0x180037f50`
- `0x18003e7a8`
- `0x18003ed0c`
- `0x180048db4`
- `0x180048ecc`
- `0x18004dba8`
- `0x180050154`
- `0x1800569c4`
- `0x180076b1c`
- `0x18007dfc8`
- `0x18007fd64`
- `0x1800921e0`
- `0x180098cf8`
- `0x18009f544`
- `0x18009f6ec`
- `0x1800a111c`
- `0x1800a21e0`
- `0x1800a2cb4`
- `0x1800a30d4`
- `0x1800ad18c`
- `0x1800d2034`
- `0x1800d20a4`
- `0x1800d20fc`
- `0x1800d2c28`
- `0x1800d4020`
- `0x180111bb8`
- `0x18011a4dc`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `pcrpf!PpfFreePredictions` at `0x1800d2aee`
- `pcrpf!PpfFreePredictions` at `0x18012883e`
- `pcrpf!PpfFreePredictions` at `0x1800d2aee`
- `pcrpf!PpfFreePredictions` at `0x18012883e`

## string_xrefs

- `0x1800d23bb`: `CreateTpmContext`
- `0x1800d2862`: `CreateTpmContext`
- `0x1800d2488`: `FveQueryConsiderTpmProtectorVersionUpgradeImpl`
- `0x1800d276b`: `CreateTpmProtectorBindingDigestSourceData`
- `0x1800d22fd`: `FveDatumVmkCreate`
- `0x1800d28ee`: `ReadFipsSetting`

## pseudocode

```c
__int64 __fastcall CFveApi::RecycleVmk(CFveApi *this)
{
  int v2; // r15d
  int Vmk; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  unsigned int v6; // edx
  int v7; // eax
  bool v8; // r14
  int TpmProtectorVersion; // ebx
  PVOID *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  unsigned __int16 i; // di
  char *v22; // [rsp+28h] [rbp-4B0h]
  __int64 v23; // [rsp+30h] [rbp-4A8h]
  bool v24; // [rsp+54h] [rbp-484h] BYREF
  bool v25; // [rsp+55h] [rbp-483h] BYREF
  bool v26; // [rsp+56h] [rbp-482h] BYREF
  char *v27; // [rsp+58h] [rbp-480h] BYREF
  CFveTpm *v28; // [rsp+60h] [rbp-478h] BYREF
  struct _FVE_DATUM *v29; // [rsp+68h] [rbp-470h] BYREF
  unsigned int v30; // [rsp+70h] [rbp-468h] BYREF
  void *lpMem; // [rsp+78h] [rbp-460h] BYREF
  struct CFvePolicy *v32; // [rsp+80h] [rbp-458h] BYREF
  struct _GUID v33; // [rsp+88h] [rbp-450h] BYREF
  struct _FVE_TPM_BINDING_CENSUS **v34; // [rsp+98h] [rbp-440h] BYREF
  void *v35; // [rsp+A0h] [rbp-438h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-430h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-428h] BYREF
  __int128 v38; // [rsp+C0h] [rbp-418h]
  __int128 v39; // [rsp+D0h] [rbp-408h]
  unsigned __int16 v40[2]; // [rsp+E0h] [rbp-3F8h] BYREF
  _BYTE v41[4]; // [rsp+E4h] [rbp-3F4h] BYREF
  unsigned __int16 v42[2]; // [rsp+E8h] [rbp-3F0h] BYREF
  int v43; // [rsp+ECh] [rbp-3ECh] BYREF
  __int128 v44; // [rsp+F0h] [rbp-3E8h] BYREF
  _BYTE v45[336]; // [rsp+100h] [rbp-3D8h] BYREF
  _BYTE v46[12]; // [rsp+250h] [rbp-288h] BYREF
  __int16 v47; // [rsp+25Ch] [rbp-27Ch]
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+0h]

  v41[0] = 0;
  v43 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  memset_0(v46, 0, 0x248u);
  v42[0] = 0;
  v35 = 0;
  v36 = 0;
  v44 = 0;
  v34 = 0;
  v40[0] = 0;
  v30 = -1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids);
  v24 = 0;
  v26 = 0;
  v25 = 0;
  v41[0] = 0;
  v2 = 0;
  v28 = 0;
  v29 = 0;
  LODWORD(v27) = 1;
  v43 = 1;
  v42[0] = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v40[0] = 0;
  v32 = 0;
  lpMem = 0;
  BitLockerFveapiProvider::RecycleVmkActivity::Start<>((BitLockerFveapiProvider::RecycleVmkActivity *)v45);
  Vmk = CFveApiBase::CheckInited(this);
  if ( Vmk < 0 )
  {
    v4 = "CheckInited";
    v5 = 587;
LABEL_6:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)Vmk,
      (int)v4,
      v22);
    goto LABEL_101;
  }
  Vmk = CFveApiBase::PrepareNonce(this);
  if ( Vmk < 0 )
  {
    v4 = "PrepareNonce";
    v5 = 593;
    goto LABEL_6;
  }
  Vmk = CFveApiBase::GetVmk(this);
  if ( Vmk < 0 )
  {
    v4 = "GetVmk";
    v5 = 599;
    goto LABEL_6;
  }
  v7 = FveDatumKeyCreate(8195, 0, 32, &v29);
  Vmk = FromNtStatus(v7);
  if ( Vmk < 0 )
  {
    v4 = "FveDatumVmkCreate";
    v5 = 605;
    goto LABEL_6;
  }
  Vmk = CFveApiBase::HasObfuscatedKey(this, &v26, &v25);
  if ( Vmk < 0 )
  {
    v4 = "HasObfuscatedKey";
    v5 = 611;
    goto LABEL_6;
  }
  Vmk = CFveApiBase::HasTpmSecureKey(this, &v24);
  if ( Vmk < 0 )
  {
    v4 = "HasTpmSecureKey";
    v5 = 617;
    goto LABEL_6;
  }
  v8 = v24;
  if ( !v24 )
    goto LABEL_73;
  Vmk = CFveApiBase::GetPolicy(this, &v32);
  if ( Vmk < 0 )
  {
    v4 = "GetFvePolicy";
    v5 = 625;
    goto LABEL_6;
  }
  Vmk = CFveApiBase::CreateTpmContext(this, v32, &v28);
  if ( Vmk < 0 )
  {
    v4 = "CreateTpmContext";
    v5 = 631;
    goto LABEL_6;
  }
  TpmProtectorVersion = CFveApiBase::GetTpmProtectorVersion(this, 0, (enum _FVE_TPM_PROTECTOR_VERSION *)&v27);
  if ( TpmProtectorVersion >= 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x282,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)TpmProtectorVersion,
      (int)"GetTpmProtectorVersion",
      v22);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids,
        (unsigned int)TpmProtectorVersion);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_D(v10[2], 38, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, (unsigned int)v27);
  Vmk = CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl((enum _FVE_DATA_TPM_PROTECTOR_VERSION *)&v43);
  if ( Vmk < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x28D,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
      (const char *)(unsigned int)Vmk,
      (int)"FveQueryConsiderTpmProtectorVersionUpgradeImpl",
      v22);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 39;
LABEL_35:
      WPP_SF_d(v11[2], v12, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, (unsigned int)Vmk);
      goto LABEL_101;
    }
    goto LABEL_101;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids,
      (unsigned int)v43);
  Vmk = CFveApiBase::GetTpmProtectorBindingCensus(this, 0, 0, v40, &v34);
  if ( Vmk >= 0 )
  {
    if ( !v40[0] )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_48;
      v14 = 42;
LABEL_47:
      WPP_SF_(v13[2], v14, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids);
LABEL_48:
      Vmk = -2147418113;
      goto LABEL_101;
    }
    if ( !*(_WORD *)*v34 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_48;
      v14 = 43;
      goto LABEL_47;
    }
    Vmk = CFveApi::GetDefaultPcrProfile(this, &v33, &v30);
    if ( Vmk < 0 )
    {
      v4 = "GetDefaultPcrProfile";
      v5 = 688;
      goto LABEL_6;
    }
    if ( v30 != -1 )
    {
      Vmk = CFveTpm::SetCallerSuppliedPcrBitmap(v28, v30, 9);
      if ( Vmk < 0 )
      {
        v4 = "SetCallerSuppliedPcrBitmap";
        v5 = 697;
        goto LABEL_6;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
      && (*((_DWORD *)this + 27) & 0x10000001) == 0 )
    {
      Vmk = CFveApiBase::GetPredictionInstanceMapping(this, (unsigned __int16 **)&lpMem);
      if ( Vmk < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x2C8,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
          (const char *)(unsigned int)Vmk,
          (int)"GetPredictionInstanceMapping",
          v22);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v12 = 44;
          goto LABEL_35;
        }
        goto LABEL_101;
      }
      if ( lpMem && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, lpMem);
    }
    Vmk = CreateTpmProtectorBindingDigestSourceData(
            v28,
            (unsigned int)v43,
            0,
            0,
            (unsigned int *)*v34 + 10,
            (unsigned __int16 *)lpMem,
            v42,
            &v35,
            &v36);
    if ( Vmk < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x2E3,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
        (const char *)(unsigned int)Vmk,
        (int)"CreateTpmProtectorBindingDigestSourceData",
        v22);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 46;
        goto LABEL_35;
      }
      goto LABEL_101;
    }
    LODWORD(v37) = v43;
    *((_QWORD *)&v37 + 1) = v35;
    *(_QWORD *)&v38 = v28;
    DWORD2(v38) = 2;
    *(_QWORD *)&v39 = *((_QWORD *)this + 146);
    WORD4(v39) = v42[0];
LABEL_73:
    if ( v25 && !v8 )
    {
      Vmk = CFveApiBase::GetPolicy(this, &v32);
      if ( Vmk < 0 )
      {
        v4 = "GetFvePolicy";
        v5 = 756;
        goto LABEL_6;
      }
      Vmk = CFveApiBase::CreateTpmContext(this, v32, &v28);
      if ( Vmk < 0 )
      {
        v4 = "CreateTpmContext";
        v5 = 762;
        goto LABEL_6;
      }
      v47 = 10;
      LODWORD(v37) = 1;
      *((_QWORD *)&v37 + 1) = v46;
      *(_QWORD *)&v38 = v28;
      DWORD2(v38) = 0;
      *(_QWORD *)&v39 = 0;
      WORD4(v39) = 0;
    }
    Vmk = (*(__int64 (__fastcall **)(CFveApi *, _BYTE *))(*(_QWORD *)this + 136LL))(this, v41);
    if ( Vmk < 0 )
    {
      v4 = "ReadFipsSetting";
      v5 = 778;
      goto LABEL_6;
    }
    if ( v41[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids);
      v2 = 1;
    }
    v15 = (unsigned int)CFveApiBase::GetAndUseNonce(this);
    v18 = FveWorksetMigrateVmk(v15, v16, v17, (_DWORD)v29, (__int64)&v37, v2, (__int64)&v44);
    Vmk = FromNtStatus(v18);
    if ( Vmk >= 0 )
    {
      Vmk = CFveApi::RecycleVmkUsedInWorkset2(this, v29);
      if ( Vmk < 0 )
      {
        v4 = "RecycleVmkUsedInWorkset2";
        v5 = 828;
        goto LABEL_6;
      }
      v19 = FveDatumFree(*((_QWORD *)this + 149));
      Vmk = FromNtStatus(v19);
      if ( Vmk < 0 )
      {
        v4 = "FveDatumFree";
        v5 = 837;
        goto LABEL_6;
      }
      *((_QWORD *)this + 149) = v29;
      *((_BYTE *)this + 1160) = 1;
      v29 = 0;
      CFveApiBase::LogTpmProtectorBindingCensus(this, 0);
    }
    else
    {
      if ( Vmk == (unsigned int)FromNtStatus(-1071579052) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids, v44);
      }
      else if ( v28 && *((int *)v28 + 11) < 0 )
      {
        Vmk = *((_DWORD *)v28 + 11);
      }
      LODWORD(v23) = v43;
      LODWORD(v22) = (_DWORD)v27;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x332,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
        (const char *)(unsigned int)Vmk,
        (int)"FveWorksetMigrateVmk failed. Prev TPMP version %d TPMP version to upgrade to %d",
        v22,
        v23);
    }
    goto LABEL_101;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x29C,
    (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\keys.cpp",
    (const char *)(unsigned int)Vmk,
    (int)"GetTpmProtectorBindingCensus",
    v22);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 41;
    goto LABEL_35;
  }
LABEL_101:
  if ( v28 )
    CFveTpm::`scalar deleting destructor'(v28, v6);
  if ( v29 )
    FveDatumFree(v29);
  if ( v35 )
  {
    CFveApiBase::ZeroFree(v35, 584LL * v42[0]);
    v35 = 0;
  }
  if ( v36 )
  {
    PpfFreePredictions(v36);
    v36 = 0;
  }
  if ( v34 )
  {
    for ( i = 0; i < v40[0]; ++i )
    {
      if ( v34[i] )
      {
        FveFreeTpmBindingCensus();
        v34[i] = 0;
      }
    }
    CFveApiBase::ZeroFree(v34, 8LL * v40[0]);
    v34 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
    && lpMem )
  {
    CFveApiBase::FastFree(lpMem);
  }
  BitLockerFveapiProvider::RecycleVmkActivity::StopActivity(
    (BitLockerFveapiProvider::RecycleVmkActivity *)v45,
    Vmk,
    (int)v27,
    v43,
    v42[0]);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids,
      (unsigned int)Vmk);
  BitLockerFveapiProvider::RecycleVmkActivity::~RecycleVmkActivity((BitLockerFveapiProvider::RecycleVmkActivity *)v45);
  return (unsigned int)Vmk;
}

```

## disassembly

```asm
0x1800d20fc  mov     r11, rsp
0x1800d20ff  mov     [r11+10h], rbx
0x1800d2103  mov     [r11+18h], rsi
0x1800d2107  push    rdi
0x1800d2108  push    r12
0x1800d210a  push    r13
0x1800d210c  push    r14
0x1800d210e  push    r15
0x1800d2110  sub     rsp, 4B0h
0x1800d2117  mov     rax, cs:__security_cookie
0x1800d211e  xor     rax, rsp
0x1800d2121  mov     [rsp+4D8h+var_38], rax
0x1800d2129  mov     rdi, rcx
0x1800d212c  xor     r12d, r12d
0x1800d212f  mov     [r11-3F4h], r12b
0x1800d2136  mov     [r11-3ECh], r12d
0x1800d213d  xorps   xmm0, xmm0
0x1800d2140  movups  [rsp+4D8h+var_428], xmm0
0x1800d2148  movups  [rsp+4D8h+var_418], xmm0
0x1800d2150  movups  [rsp+4D8h+var_408], xmm0
0x1800d2158  xor     edx, edx; Val
0x1800d215a  mov     r8d, 248h; Size
0x1800d2160  lea     rcx, [r11-288h]; void *
0x1800d2167  call    memset_0
0x1800d216c  mov     [rsp+4D8h+var_3F0], r12w
0x1800d2175  mov     [rsp+4D8h+var_438], r12
0x1800d217d  mov     [rsp+4D8h+var_430], r12
0x1800d2185  xorps   xmm0, xmm0
0x1800d2188  movups  [rsp+4D8h+var_3E8], xmm0
0x1800d2190  mov     [rsp+4D8h+var_440], r12
0x1800d2198  mov     [rsp+4D8h+var_3F8], r12w
0x1800d21a1  mov     [rsp+4D8h+var_468], 0FFFFFFFFh
0x1800d21a9  lea     r13, WPP_GLOBAL_Control
0x1800d21b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d21b7  lea     rsi, WPP_c7fc66ef30e9383fd52b1be89aecd64d_Traceguids
0x1800d21be  cmp     rcx, r13
0x1800d21c1  jz      short loc_1800D21DA
0x1800d21c3  test    byte ptr [rcx+1Ch], 20h
0x1800d21c7  jz      short loc_1800D21DA
0x1800d21c9  lea     edx, [r12+24h]
0x1800d21ce  mov     r8, rsi
0x1800d21d1  mov     rcx, [rcx+10h]
0x1800d21d5  call    WPP_SF_
0x1800d21da  mov     [rsp+4D8h+var_484], r12b
0x1800d21df  mov     [rsp+4D8h+var_482], r12b
0x1800d21e4  mov     [rsp+4D8h+var_483], r12b
0x1800d21e9  mov     [rsp+4D8h+var_3F4], r12b
0x1800d21f1  mov     r15d, r12d
0x1800d21f4  mov     [rsp+4D8h+var_478], r12
0x1800d21f9  mov     [rsp+4D8h+var_470], r12
0x1800d21fe  mov     r14d, 1
0x1800d2204  mov     dword ptr [rsp+4D8h+var_480], r14d
0x1800d2209  mov     [rsp+4D8h+var_3EC], r14d
0x1800d2211  mov     [rsp+4D8h+var_3F0], r12w
0x1800d221a  mov     [rsp+4D8h+var_430], r12
0x1800d2222  mov     [rsp+4D8h+var_438], r12
0x1800d222a  mov     [rsp+4D8h+var_440], r12
0x1800d2232  mov     [rsp+4D8h+var_3F8], r12w
0x1800d223b  mov     [rsp+4D8h+var_458], r12
0x1800d2243  mov     [rsp+4D8h+lpMem], r12
0x1800d2248  lea     rcx, [rsp+4D8h+var_3D8]; this
0x1800d2250  call    ??$Start@$$V@RecycleVmkActivity@BitLockerFveapiProvider@@SA?AV01@XZ; BitLockerFveapiProvider::RecycleVmkActivity::Start<>(void)
0x1800d2255  nop
0x1800d2256  mov     rcx, rdi; this
0x1800d2259  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800d225e  mov     ebx, eax
0x1800d2260  mov     [rsp+4D8h+var_488], eax
0x1800d2264  test    eax, eax
0x1800d2266  jns     short loc_1800D2295
0x1800d2268  lea     rax, aCheckinited_0; "CheckInited"
0x1800d226f  mov     edx, 24Bh; void *
0x1800d2274  mov     rcx, [rsp+4D8h]; this
0x1800d227c  mov     [rsp+4D8h+var_4B8], rax; int
0x1800d2281  mov     r9d, ebx; char *
0x1800d2284  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d228b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d2290  jmp     loc_1800D2A9A
0x1800d2295  mov     rcx, rdi; this
0x1800d2298  call    ?PrepareNonce@CFveApiBase@@QEAAJXZ; CFveApiBase::PrepareNonce(void)
0x1800d229d  mov     ebx, eax
0x1800d229f  mov     [rsp+4D8h+var_488], eax
0x1800d22a3  test    eax, eax
0x1800d22a5  jns     short loc_1800D22B5
0x1800d22a7  lea     rax, aPreparenonce; "PrepareNonce"
0x1800d22ae  mov     edx, 251h
0x1800d22b3  jmp     short loc_1800D2274
0x1800d22b5  mov     rcx, rdi; this
0x1800d22b8  call    ?GetVmk@CFveApiBase@@QEBAJXZ; CFveApiBase::GetVmk(void)
0x1800d22bd  mov     ebx, eax
0x1800d22bf  mov     [rsp+4D8h+var_488], eax
0x1800d22c3  test    eax, eax
0x1800d22c5  jns     short loc_1800D22D5
0x1800d22c7  lea     rax, aGetvmk_0; "GetVmk"
0x1800d22ce  mov     edx, 257h
0x1800d22d3  jmp     short loc_1800D2274
0x1800d22d5  mov     ecx, 2003h
0x1800d22da  mov     r8d, 20h ; ' '
0x1800d22e0  lea     r9, [rsp+4D8h+var_470]
0x1800d22e5  xor     edx, edx
0x1800d22e7  call    FveDatumKeyCreate
0x1800d22ec  mov     ecx, eax; int
0x1800d22ee  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800d22f3  mov     ebx, eax
0x1800d22f5  mov     [rsp+4D8h+var_488], eax
0x1800d22f9  test    eax, eax
0x1800d22fb  jns     short loc_1800D230E
0x1800d22fd  lea     rax, aFvedatumvmkcre; "FveDatumVmkCreate"
0x1800d2304  mov     edx, 25Dh
0x1800d2309  jmp     loc_1800D2274
0x1800d230e  lea     r8, [rsp+4D8h+var_483]; bool *
0x1800d2313  lea     rdx, [rsp+4D8h+var_482]; bool *
0x1800d2318  mov     rcx, rdi; this
0x1800d231b  call    ?HasObfuscatedKey@CFveApiBase@@QEAAJPEA_N0@Z; CFveApiBase::HasObfuscatedKey(bool *,bool *)
0x1800d2320  mov     ebx, eax
0x1800d2322  mov     [rsp+4D8h+var_488], eax
0x1800d2326  test    eax, eax
0x1800d2328  jns     short loc_1800D233B
0x1800d232a  lea     rax, aHasobfuscatedk_0; "HasObfuscatedKey"
0x1800d2331  mov     edx, 263h
0x1800d2336  jmp     loc_1800D2274
0x1800d233b  lea     rdx, [rsp+4D8h+var_484]; bool *
0x1800d2340  mov     rcx, rdi; this
0x1800d2343  call    ?HasTpmSecureKey@CFveApiBase@@QEAAJPEA_N@Z; CFveApiBase::HasTpmSecureKey(bool *)
0x1800d2348  mov     ebx, eax
0x1800d234a  mov     [rsp+4D8h+var_488], eax
0x1800d234e  test    eax, eax
0x1800d2350  jns     short loc_1800D2363
0x1800d2352  lea     rax, aHastpmsecureke; "HasTpmSecureKey"
0x1800d2359  mov     edx, 269h
0x1800d235e  jmp     loc_1800D2274
0x1800d2363  mov     r14b, [rsp+4D8h+var_484]
0x1800d2368  test    r14b, r14b
0x1800d236b  jz      loc_1800D2804
0x1800d2371  lea     rdx, [rsp+4D8h+var_458]; struct CFvePolicy **
0x1800d2379  mov     rcx, rdi; this
0x1800d237c  call    ?GetPolicy@CFveApiBase@@IEAAJPEAPEAVCFvePolicy@@@Z; CFveApiBase::GetPolicy(CFvePolicy * *)
0x1800d2381  mov     ebx, eax
0x1800d2383  mov     [rsp+4D8h+var_488], eax
0x1800d2387  test    eax, eax
0x1800d2389  jns     short loc_1800D239C
0x1800d238b  lea     rax, aGetfvepolicy; "GetFvePolicy"
0x1800d2392  mov     edx, 271h
0x1800d2397  jmp     loc_1800D2274
0x1800d239c  lea     r8, [rsp+4D8h+var_478]; struct CFveTpm **
0x1800d23a1  mov     rdx, [rsp+4D8h+var_458]; struct CFvePolicy *
0x1800d23a9  mov     rcx, rdi; this
0x1800d23ac  call    ?CreateTpmContext@CFveApiBase@@QEAAJPEAVCFvePolicy@@PEAPEAVCFveTpm@@@Z; CFveApiBase::CreateTpmContext(CFvePolicy *,CFveTpm * *)
0x1800d23b1  mov     ebx, eax
0x1800d23b3  mov     [rsp+4D8h+var_488], eax
0x1800d23b7  test    eax, eax
0x1800d23b9  jns     short loc_1800D23CC
0x1800d23bb  lea     rax, aCreatetpmconte_2; "CreateTpmContext"
0x1800d23c2  mov     edx, 277h
0x1800d23c7  jmp     loc_1800D2274
0x1800d23cc  lea     r8, [rsp+4D8h+var_480]; enum _FVE_TPM_PROTECTOR_VERSION *
0x1800d23d1  xor     edx, edx; struct _GUID *
0x1800d23d3  mov     rcx, rdi; this
0x1800d23d6  call    ?GetTpmProtectorVersion@CFveApiBase@@QEAAJPEBU_GUID@@PEAW4_FVE_TPM_PROTECTOR_VERSION@@@Z; CFveApiBase::GetTpmProtectorVersion(_GUID const *,_FVE_TPM_PROTECTOR_VERSION *)
0x1800d23db  mov     ebx, eax
0x1800d23dd  mov     [rsp+4D8h+var_488], eax
0x1800d23e1  test    eax, eax
0x1800d23e3  jns     short loc_1800D2441
0x1800d23e5  mov     rcx, [rsp+4D8h]; this
0x1800d23ed  lea     rax, aGettpmprotecto; "GetTpmProtectorVersion"
0x1800d23f4  mov     [rsp+4D8h+var_4B8], rax; int
0x1800d23f9  mov     r9d, ebx; char *
0x1800d23fc  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d2403  mov     edx, 282h; void *
0x1800d2408  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d240d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2414  cmp     rcx, r13
0x1800d2417  jz      short loc_1800D243A
0x1800d2419  test    byte ptr [rcx+1Ch], 8
0x1800d241d  jz      short loc_1800D243A
0x1800d241f  mov     edx, 25h ; '%'
0x1800d2424  mov     r9d, ebx
0x1800d2427  mov     r8, rsi
0x1800d242a  mov     rcx, [rcx+10h]
0x1800d242e  call    WPP_SF_d
0x1800d2433  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d243a  mov     [rsp+4D8h+var_488], r12d
0x1800d243f  jmp     short loc_1800D2448
0x1800d2441  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2448  cmp     rcx, r13
0x1800d244b  jz      short loc_1800D2469
0x1800d244d  test    byte ptr [rcx+1Ch], 8
0x1800d2451  jz      short loc_1800D2469
0x1800d2453  mov     edx, 26h ; '&'
0x1800d2458  mov     r9d, dword ptr [rsp+4D8h+var_480]
0x1800d245d  mov     r8, rsi
0x1800d2460  mov     rcx, [rcx+10h]
0x1800d2464  call    WPP_SF_D
0x1800d2469  lea     rcx, [rsp+4D8h+var_3EC]; enum _FVE_DATA_TPM_PROTECTOR_VERSION *
0x1800d2471  call    ?FveQueryConsiderTpmProtectorVersionUpgradeImpl@CFveApiBase@@SAJPEAW4_FVE_DATA_TPM_PROTECTOR_VERSION@@@Z; CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl(_FVE_DATA_TPM_PROTECTOR_VERSION *)
0x1800d2476  mov     ebx, eax
0x1800d2478  mov     [rsp+4D8h+var_488], eax
0x1800d247c  test    eax, eax
0x1800d247e  jns     short loc_1800D24DB
0x1800d2480  mov     rcx, [rsp+4D8h]; this
0x1800d2488  lea     rax, aFvequeryconsid; "FveQueryConsiderTpmProtectorVersionUpgr"...
0x1800d248f  mov     [rsp+4D8h+var_4B8], rax; int
0x1800d2494  mov     r9d, ebx; char *
0x1800d2497  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d249e  mov     edx, 28Dh; void *
0x1800d24a3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d24a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d24af  cmp     rcx, r13
0x1800d24b2  jz      loc_1800D2A9A
0x1800d24b8  test    byte ptr [rcx+1Ch], 2
0x1800d24bc  jz      loc_1800D2A9A
0x1800d24c2  mov     edx, 27h ; '''
0x1800d24c7  mov     r9d, ebx
0x1800d24ca  mov     r8, rsi
0x1800d24cd  mov     rcx, [rcx+10h]
0x1800d24d1  call    WPP_SF_d
0x1800d24d6  jmp     loc_1800D2A9A
0x1800d24db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d24e2  cmp     rcx, r13
0x1800d24e5  jz      short loc_1800D2506
0x1800d24e7  test    byte ptr [rcx+1Ch], 8
0x1800d24eb  jz      short loc_1800D2506
0x1800d24ed  mov     edx, 28h ; '('
0x1800d24f2  mov     r9d, [rsp+4D8h+var_3EC]
0x1800d24fa  mov     r8, rsi
0x1800d24fd  mov     rcx, [rcx+10h]
0x1800d2501  call    WPP_SF_D
0x1800d2506  lea     rax, [rsp+4D8h+var_440]
0x1800d250e  mov     [rsp+4D8h+var_4B8], rax; struct _FVE_TPM_BINDING_CENSUS ***
0x1800d2513  lea     r9, [rsp+4D8h+var_3F8]; unsigned __int16 *
0x1800d251b  xor     r8d, r8d; unsigned __int8
0x1800d251e  xor     edx, edx; struct _GUID *
0x1800d2520  mov     rcx, rdi; this
0x1800d2523  call    ?GetTpmProtectorBindingCensus@CFveApiBase@@QEAAJPEBU_GUID@@EPEAGPEAPEAPEAU_FVE_TPM_BINDING_CENSUS@@@Z; CFveApiBase::GetTpmProtectorBindingCensus(_GUID const *,uchar,ushort *,_FVE_TPM_BINDING_CENSUS * * *)
0x1800d2528  mov     ebx, eax
0x1800d252a  mov     [rsp+4D8h+var_488], eax
0x1800d252e  test    eax, eax
0x1800d2530  jns     short loc_1800D257E
0x1800d2532  mov     rcx, [rsp+4D8h]; this
0x1800d253a  lea     rax, aGettpmprotecto_0; "GetTpmProtectorBindingCensus"
0x1800d2541  mov     [rsp+4D8h+var_4B8], rax; int
0x1800d2546  mov     r9d, ebx; char *
0x1800d2549  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800d2550  mov     edx, 29Ch; void *
0x1800d2555  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d255a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2561  cmp     rcx, r13
0x1800d2564  jz      loc_1800D2A9A
0x1800d256a  test    byte ptr [rcx+1Ch], 2
0x1800d256e  jz      loc_1800D2A9A
0x1800d2574  mov     edx, 29h ; ')'
0x1800d2579  jmp     loc_1800D24C7
0x1800d257e  cmp     [rsp+4D8h+var_3F8], r12w
0x1800d2587  jnz     short loc_1800D25BA
0x1800d2589  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2590  cmp     rcx, r13
0x1800d2593  jz      short loc_1800D25AC
0x1800d2595  test    byte ptr [rcx+1Ch], 2
0x1800d2599  jz      short loc_1800D25AC
0x1800d259b  mov     edx, 2Ah ; '*'
0x1800d25a0  mov     r8, rsi
0x1800d25a3  mov     rcx, [rcx+10h]
0x1800d25a7  call    WPP_SF_
0x1800d25ac  mov     ebx, 8000FFFFh
0x1800d25b1  mov     [rsp+4D8h+var_488], ebx
0x1800d25b5  jmp     loc_1800D2A9A
0x1800d25ba  mov     rax, [rsp+4D8h+var_440]
0x1800d25c2  mov     rcx, [rax]
0x1800d25c5  cmp     [rcx], r12w
0x1800d25c9  jnz     short loc_1800D25E4
0x1800d25cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d25d2  cmp     rcx, r13
0x1800d25d5  jz      short loc_1800D25AC
0x1800d25d7  test    byte ptr [rcx+1Ch], 2
0x1800d25db  jz      short loc_1800D25AC
0x1800d25dd  mov     edx, 2Bh ; '+'
0x1800d25e2  jmp     short loc_1800D25A0
0x1800d25e4  lea     r8, [rsp+4D8h+var_468]; unsigned int *
0x1800d25e9  lea     rdx, [rsp+4D8h+var_450]; struct _GUID *
0x1800d25f1  mov     rcx, rdi; this
0x1800d25f4  call    ?GetDefaultPcrProfile@CFveApi@@QEAAJPEAU_GUID@@PEAK@Z; CFveApi::GetDefaultPcrProfile(_GUID *,ulong *)
0x1800d25f9  mov     ebx, eax
0x1800d25fb  mov     [rsp+4D8h+var_488], eax
0x1800d25ff  test    eax, eax
0x1800d2601  jns     short loc_1800D2614
0x1800d2603  lea     rax, aGetdefaultpcrp_0; "GetDefaultPcrProfile"
0x1800d260a  mov     edx, 2B0h
0x1800d260f  jmp     loc_1800D2274
0x1800d2614  mov     edx, [rsp+4D8h+var_468]
0x1800d2618  cmp     edx, 0FFFFFFFFh
0x1800d261b  jz      short loc_1800D2649
0x1800d261d  xor     r9d, r9d
0x1800d2620  lea     r8d, [r9+9]
0x1800d2624  mov     rcx, [rsp+4D8h+var_478]
0x1800d2629  call    ?SetCallerSuppliedPcrBitmap@CFveTpm@@QEAAJKW4ePcrBitmapSource@@_N@Z; CFveTpm::SetCallerSuppliedPcrBitmap(ulong,ePcrBitmapSource,bool)
0x1800d262e  mov     ebx, eax
0x1800d2630  mov     [rsp+4D8h+var_488], eax
0x1800d2634  test    eax, eax
0x1800d2636  jns     short loc_1800D2649
0x1800d2638  lea     rax, aSetcallersuppl_0; "SetCallerSuppliedPcrBitmap"
0x1800d263f  mov     edx, 2B9h
  ... truncated ...
```
