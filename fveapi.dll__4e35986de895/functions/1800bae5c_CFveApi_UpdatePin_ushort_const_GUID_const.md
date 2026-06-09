# CFveApi::UpdatePin(ushort const *,_GUID const *)

- ea: `0x1800bae5c`
- end: `0x1800bbee6`
- name: `?UpdatePin@CFveApi@@QEAAJPEBGPEBU_GUID@@@Z`
- size: `4234`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006c6d0`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x18000ba30`
- `0x180018b10`
- `0x180019128`
- `0x18001ac58`
- `0x18001b260`
- `0x18001c470`
- `0x18001de20`
- `0x18001eaf4`
- `0x18001f010`
- `0x180021220`
- `0x180021c90`
- `0x180022800`
- `0x180022f90`
- `0x180023800`
- `0x180037f50`
- `0x18003a314`
- `0x18003e7a8`
- `0x18003ed0c`
- `0x180042cc4`
- `0x180046094`
- `0x180046a90`
- `0x180048ecc`
- `0x18004dba8`
- `0x18004e554`
- `0x18004fa04`
- `0x180050154`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180069180`
- `0x180076b1c`
- `0x180076dd0`
- `0x18007dfc8`
- `0x1800921e0`
- `0x180098cf8`
- `0x18009f544`
- `0x18009f6ec`
- `0x1800a111c`
- `0x1800a2cb4`
- `0x1800ad18c`
- `0x1800b04b8`
- `0x1800b072c`
- `0x1800baaf0`
- `0x1800bae5c`
- `0x18010dff4`

## import_xrefs

- `pcrpf!PpfFreePredictions` at `0x1800bbe3c`
- `pcrpf!PpfFreePredictions` at `0x180126bf0`
- `pcrpf!PpfFreePredictions` at `0x1800bbe3c`
- `pcrpf!PpfFreePredictions` at `0x180126bf0`

## string_xrefs

- `0x1800bbbb7`: `VolumePath`
- `0x180126944`: `VolumePath`
- `0x1800bb3d3`: `FveDatumUnicodeCreate`
- `0x1800bb4a1`: `CreateTpmContext`
- `0x1800bb589`: `FveQueryConsiderTpmProtectorVersionUpgradeImpl`
- `0x1800bb782`: `CreateTpmProtectorBindingDigestSourceData`
- `0x1800bb9fe`: `FveDatasetCompress`

## pseudocode

```c
__int64 __fastcall CFveApi::UpdatePin(CFveApi *this, unsigned __int16 *a2, const struct _GUID *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r12
  unsigned int v8; // r15d
  __int64 v9; // r9
  int Vmk; // ebx
  const char *v11; // rax
  __int64 v12; // rdx
  int Next; // ecx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int IsEnhancedPinOrEnhancedCrypto; // eax
  int v21; // eax
  char v22; // r14
  unsigned __int16 *v23; // r13
  __int64 v24; // rdx
  int v25; // eax
  const char *v26; // rax
  __int64 v27; // rdx
  int UsesPBKDF2; // eax
  int v29; // eax
  int TpmProtectorVersion; // eax
  PVOID *v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // edx
  __int64 v36; // r8
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int appended; // eax
  __int64 v43; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v47; // rdx
  unsigned int v49; // [rsp+20h] [rbp-438h]
  unsigned int v50; // [rsp+20h] [rbp-438h]
  char *v51; // [rsp+28h] [rbp-430h]
  char *v52; // [rsp+28h] [rbp-430h]
  char v53; // [rsp+84h] [rbp-3D4h] BYREF
  bool v54; // [rsp+85h] [rbp-3D3h] BYREF
  _BYTE v55[2]; // [rsp+86h] [rbp-3D2h] BYREF
  unsigned int v56; // [rsp+88h] [rbp-3D0h] BYREF
  int v57; // [rsp+8Ch] [rbp-3CCh] BYREF
  __int64 v58; // [rsp+90h] [rbp-3C8h] BYREF
  CFveTpm *v59; // [rsp+98h] [rbp-3C0h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-3B8h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-3B0h] BYREF
  void *lpMem; // [rsp+B0h] [rbp-3A8h] BYREF
  unsigned int v63; // [rsp+B8h] [rbp-3A0h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-398h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-390h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-388h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-380h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-378h] BYREF
  struct _GUID v69; // [rsp+E8h] [rbp-370h] BYREF
  __int64 v70; // [rsp+F8h] [rbp-360h]
  unsigned __int16 *v71; // [rsp+100h] [rbp-358h]
  unsigned __int64 v72[8]; // [rsp+108h] [rbp-350h] BYREF
  __int64 v73; // [rsp+148h] [rbp-310h] BYREF
  __int64 *v74; // [rsp+150h] [rbp-308h]
  _QWORD *v75; // [rsp+158h] [rbp-300h] BYREF
  _QWORD **v76; // [rsp+160h] [rbp-2F8h]
  __int64 v77; // [rsp+168h] [rbp-2F0h] BYREF
  void *v78; // [rsp+170h] [rbp-2E8h] BYREF
  __int64 v79; // [rsp+178h] [rbp-2E0h] BYREF
  __int128 v80; // [rsp+180h] [rbp-2D8h] BYREF
  __int128 v81; // [rsp+190h] [rbp-2C8h]
  __int128 v82; // [rsp+1A0h] [rbp-2B8h]
  _OWORD v83[3]; // [rsp+1B0h] [rbp-2A8h] BYREF
  unsigned __int16 v84[2]; // [rsp+1E0h] [rbp-278h] BYREF
  int v85; // [rsp+1E4h] [rbp-274h] BYREF
  _OWORD v86[3]; // [rsp+1E8h] [rbp-270h] BYREF
  _QWORD v87[6]; // [rsp+218h] [rbp-240h] BYREF
  _OWORD v88[3]; // [rsp+248h] [rbp-210h] BYREF
  _QWORD v89[6]; // [rsp+278h] [rbp-1E0h] BYREF
  __int128 v90; // [rsp+2A8h] [rbp-1B0h] BYREF
  _BYTE v91[336]; // [rsp+2C0h] [rbp-198h] BYREF
  __int128 v92; // [rsp+410h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  v71 = a2;
  v72[1] = (unsigned __int64)this;
  v72[0] = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v90 = 0;
  v63 = -1;
  v56 = 0;
  v6 = 0;
  v61 = 0;
  v77 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v60 = 0;
  v7 = 0;
  v58 = 0;
  v67 = 0;
  v53 = 0;
  v54 = 0;
  v59 = 0;
  v8 = 0;
  v55[0] = 0;
  v68 = 0;
  v85 = 1;
  v57 = 1;
  v84[0] = 0;
  v78 = 0;
  v79 = 0;
  *(_QWORD *)&v69.Data1 = 0;
  lpMem = 0;
  v92 = 0;
  memset(v83, 0, 44);
  BitLockerFveapiProvider::BitLockerChangePinActivity::Start<>((BitLockerFveapiProvider::BitLockerChangePinActivity *)v91);
  if ( !a2 )
  {
    v9 = 2147942487LL;
    Vmk = -2147024809;
    v11 = "ArgCheckNewPin";
    v12 = 6339;
LABEL_117:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)v9,
      (int)v11,
      v51);
    goto LABEL_118;
  }
  if ( !a3 )
  {
    v9 = 2147942487LL;
    Vmk = -2147024809;
    v11 = "ArgCheckProtectorGuid";
    v12 = 6344;
    goto LABEL_117;
  }
  Vmk = CFveApiBase::CheckInited(this);
  if ( Vmk < 0 )
  {
    v11 = "CheckInited";
    v9 = (unsigned int)Vmk;
    v12 = 6350;
    goto LABEL_117;
  }
  Vmk = EnsureNoBootableCdDvdInserted();
  if ( Vmk < 0 )
  {
    v11 = "EnsureNoBootableCdDvdInserted";
    v9 = (unsigned int)Vmk;
    v12 = 6360;
    goto LABEL_117;
  }
  while ( 1 )
  {
    Next = FveDatasetGetNext(*((_QWORD *)this + 146), 2, 8, v56, (__int64)&v56);
    if ( Next < 0 )
      break;
    Next = FveDatasetGetDatum(*((_QWORD *)this + 146), v56, &v61);
    if ( Next < 0 )
    {
      Vmk = FromNtStatus(Next);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x18EB,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
        (const char *)(unsigned int)Vmk,
        (int)"FveDatasetGetDatum",
        v51);
      v6 = v61;
      goto LABEL_118;
    }
    v6 = v61;
    if ( *(_QWORD *)(v61 + 8) == *(_QWORD *)&a3->Data1 && *(_QWORD *)(v61 + 16) == *(_QWORD *)a3->Data4 )
      break;
    FveDatumFree(v61);
    v6 = 0;
    v61 = 0;
  }
  if ( Next < 0 )
  {
    Vmk = FromNtStatus(Next);
    v11 = "ProtectorNotFound";
    v12 = 6395;
LABEL_116:
    v9 = (unsigned int)Vmk;
    goto LABEL_117;
  }
  v16 = FveDatumVmkQueryTpmEncBlob(v6, &v64);
  if ( v16 < 0 )
  {
    Vmk = FromNtStatus(v16);
    v11 = "FveDatumVmkQueryTpmEncBlob";
    v12 = 6406;
    goto LABEL_116;
  }
  v17 = FveDatumVmkQueryUseKey(v6, 8194, &v65);
  if ( (int)(v17 + 0x80000000) >= 0 && v17 != -1073741275 )
  {
    Vmk = FromNtStatus(v17);
    v11 = "FveDatumVmkQueryUseKey";
    v12 = 6414;
    goto LABEL_116;
  }
  v18 = FveDatumVmkQueryLabel(v6, &v67);
  if ( ((v18 + 0x80000000) & 0x80000000) == 0 && v18 != -1073741275 )
  {
    Vmk = FromNtStatus(v18);
    v11 = "FveDatumVmkQueryLabel";
    v12 = 6421;
    goto LABEL_116;
  }
  v19 = FveDatumVmkQueryStretchKey(v6, 8196, &v66);
  if ( v19 == -1073741275 )
    v19 = FveDatumVmkQueryUseKey(v6, 8196, &v66);
  if ( v19 < 0 )
  {
    Vmk = FromNtStatus(v19);
    v11 = "FveDatumVmkQuery";
    v12 = 6444;
    goto LABEL_116;
  }
  IsEnhancedPinOrEnhancedCrypto = FveDatumVmkQueryIsEnhancedPinOrEnhancedCrypto(v6, &v53, 0);
  if ( IsEnhancedPinOrEnhancedCrypto < 0 )
  {
    Vmk = FromNtStatus(IsEnhancedPinOrEnhancedCrypto);
    v11 = "FveDatumVmkQueryIsEnhancedPin";
    v12 = 6457;
    goto LABEL_116;
  }
  Vmk = CFveApiBase::OkToExportKey();
  if ( Vmk < 0 )
  {
    v11 = "OkToExportKey";
    v9 = (unsigned int)Vmk;
    v12 = 6468;
    goto LABEL_117;
  }
  Vmk = CFveApiBase::GetVmk(this);
  if ( Vmk < 0 )
    goto LABEL_118;
  if ( v65 )
  {
    v21 = FveDatumVmkQueryUseKeyWithParams(v65, *((_QWORD *)this + 149), &v60);
    if ( v21 < 0 )
    {
      Vmk = FromNtStatus(v21);
      v11 = "FveDatumVmkQueryUseKeyWithParams";
      v12 = 6485;
      goto LABEL_116;
    }
    *(_QWORD *)&v92 = v60;
    v8 = 1;
  }
  v22 = v53;
  v23 = v71;
  if ( (int)CFveApiBase::ArePinCharactersValid(v71, v53 != 0, &v54) < 0 || !v54 )
  {
    Vmk = -2144272230;
    if ( v22 != 1 )
      Vmk = -2144272180;
    v11 = "ArePinCharactersValid";
    v12 = 6500;
    goto LABEL_116;
  }
  LOBYTE(v24) = v22;
  v25 = FveDatumFromPin(v23, v24, &v58);
  if ( v25 < 0 )
  {
    Vmk = FromNtStatus(v25);
    v26 = "FveDatumFromPin";
    v27 = 6507;
LABEL_42:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)(unsigned int)Vmk,
      (int)v26,
      v51);
    v7 = v58;
    goto LABEL_118;
  }
  UsesPBKDF2 = FveDatumVmkQueryUsesPBKDF2(v6, v55);
  if ( UsesPBKDF2 < 0 )
  {
    Vmk = FromNtStatus(UsesPBKDF2);
    v26 = "FveDatumVmkQueryUsesPBKDF2";
    v27 = 6521;
    goto LABEL_42;
  }
  if ( v55[0] )
  {
    v29 = FveDatumUnicodeCreate(L"PBKDF2_HMAC_SHA256", &v68);
    if ( v29 < 0 )
    {
      Vmk = FromNtStatus(v29);
      v26 = "FveDatumUnicodeCreate";
      v27 = 6531;
      goto LABEL_42;
    }
    *(_QWORD *)((char *)v83 + 12) = v68;
    v7 = v58;
    *(_WORD *)(v58 + 10) |= 0x40u;
  }
  else
  {
    *(_QWORD *)((char *)v83 + 12) = 0;
    v7 = v58;
  }
  *(_QWORD *)&v83[0] = v7;
  DWORD2(v83[0]) = 1;
  *(_QWORD *)((char *)&v83[1] + 4) = v7;
  *((_QWORD *)&v92 + v8) = v83;
  Vmk = CFveApiBase::GetPolicy(this, (struct CFvePolicy **)&v69);
  if ( Vmk < 0 )
  {
    v11 = "GetFvePolicy";
    v9 = (unsigned int)Vmk;
    v12 = 6556;
    goto LABEL_117;
  }
  Vmk = CFveApiBase::CreateTpmContext(this, *(struct CFvePolicy **)&v69.Data1, &v59);
  if ( Vmk < 0 )
  {
    v11 = "CreateTpmContext";
    v9 = (unsigned int)Vmk;
    v12 = 6562;
    goto LABEL_117;
  }
  TpmProtectorVersion = CFveApiBase::GetTpmProtectorVersion(this, 0, (enum _FVE_TPM_PROTECTOR_VERSION *)&v57);
  if ( TpmProtectorVersion >= 0 )
    goto LABEL_59;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x19B1,
    (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
    (const char *)(unsigned int)TpmProtectorVersion,
    (int)"GetTpmProtectorVersion",
    v51);
  v31 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
LABEL_59:
    v31 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 8) != 0 )
    WPP_SF_D(v31[2], 155, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, (unsigned int)v57);
  Vmk = CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl((enum _FVE_DATA_TPM_PROTECTOR_VERSION *)&v85);
  if ( Vmk < 0 )
  {
    v11 = "FveQueryConsiderTpmProtectorVersionUpgradeImpl";
    v9 = (unsigned int)Vmk;
    v12 = 6585;
    goto LABEL_117;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      156,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      (unsigned int)v85);
  Vmk = CFveApi::GetDefaultPcrProfile(this, &v69, &v63);
  if ( Vmk < 0 )
  {
    v11 = "GetDefaultPcrProfile";
    v9 = (unsigned int)Vmk;
    v12 = 6596;
    goto LABEL_117;
  }
  if ( v63 != -1 )
  {
    Vmk = CFveTpm::SetCallerSuppliedPcrBitmap(v59, v63, 9);
    if ( Vmk < 0 )
    {
      v11 = "SetCallerSuppliedPcrBitmap";
      v9 = (unsigned int)Vmk;
      v12 = 6605;
      goto LABEL_117;
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
        (void *)0x19DC,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
        (const char *)(unsigned int)Vmk,
        (int)"GetPredictionInstanceMapping",
        v51);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v33 = 157;
LABEL_79:
        WPP_SF_d(v32[2], v33, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, (unsigned int)Vmk);
        goto LABEL_118;
      }
      goto LABEL_118;
    }
    if ( lpMem && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, lpMem);
  }
  Vmk = CreateTpmProtectorBindingDigestSourceData(
          v59,
          (unsigned int)v85,
          0,
          0,
          (unsigned int *)(v64 + 8),
          (unsigned __int16 *)lpMem,
          v84,
          &v78,
          &v79);
  if ( Vmk >= 0 )
  {
    LODWORD(v80) = v85;
    *((_QWORD *)&v80 + 1) = v78;
    *(_QWORD *)&v81 = v59;
    DWORD2(v81) = 4;
    *(_QWORD *)&v82 = *((_QWORD *)this + 146);
    WORD4(v82) = v84[0];
    Vmk = CFveApiBase::PrepareNonce(this);
    v15 = 0;
    if ( Vmk < 0 )
      goto LABEL_118;
    v34 = (unsigned int)CFveApiBase::GetAndUseNonce(this);
    v37 = FveBuildVmkInfoEx(
            v34,
            v35,
            v6,
            (unsigned int)&v92,
            v8 + 1,
            v36,
            v67,
            v36,
            v36,
            v36,
            v36,
            (__int64)&v80,
            2,
            (__int64)&v77,
            (__int64)&v90);
    if ( v37 < 0 )
    {
      Vmk = FromNtStatus(v37);
      if ( Vmk == (unsigned int)FromNtStatus(-1071579052) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, v90);
      }
      else if ( *((int *)v59 + 11) < 0 )
      {
        Vmk = *((_DWORD *)v59 + 11);
      }
      v11 = "FveBuildVmkInfo";
      v9 = (unsigned int)Vmk;
      v12 = 6697;
      goto LABEL_117;
    }
    if ( (*(_WORD *)(v6 + 34) & 0x100) != 0 )
    {
      v38 = FveDatasetEraseDigestDatumsOfVmkInfo(*((_QWORD *)this + 146), v56);
      v39 = FromNtStatus(v38);
      Vmk = v39;
      if ( v39 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            161,
            WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
            (unsigned int)v39);
        v11 = "FveDatasetEraseDigestDatumsOfVmkInfo";
        v9 = (unsigned int)Vmk;
        v12 = 6718;
        goto LABEL_117;
      }
    }
    v40 = FveDatasetEraseDatum(*((_QWORD *)this + 146), v56);
    if ( v40 < 0 )
    {
      Vmk = FromNtStatus(v40);
      v11 = "FveDatasetEraseDatum";
      v12 = 6731;
      goto LABEL_116;
    }
    v41 = FveDatasetCompress(*((_QWORD *)this + 146));
    Vmk = FromNtStatus(v41);
    if ( Vmk < 0 )
    {
      v11 = "FveDatasetCompress";
      v9 = (unsigned int)Vmk;
      v12 = 6737;
      goto LABEL_117;
    }
    appended = FveDatasetAppendDatum(*((_QWORD *)this + 146), v77, 2);
    if ( appended < 0 )
    {
      Vmk = FromNtStatus(appended);
      v11 = "FveDatasetAppendDatum";
      v12 = 6746;
      goto LABEL_116;
    }
    Vmk = StringCchLengthW(v71, 0x7FFFFFFFu, v72);
    if ( Vmk < 0 )
    {
      v11 = "StringCchLengthW";
      v9 = (unsigned int)Vmk;
      v12 = 6752;
      goto LABEL_117;
    }
    if ( v72[0] < 6 )
      FveResetTpmDictionaryAttackParameters();
  }
  else
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x19F1,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)(unsigned int)Vmk,
      (int)"CreateTpmProtectorBindingDigestSourceData",
      v52);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v33 = 159;
      goto LABEL_79;
    }
  }
LABEL_118:
  if ( Vmk >= 0 )
  {
    v73 = 0;
    v74 = 0;
    *(_QWORD *)&v69.Data1 = 0;
    *(_QWORD *)v69.Data4 = 0;
    v70 = 0;
    v43 = *((_QWORD *)this + 146);
    v87[2] = L"IdentityGuid";
    v87[3] = L"GUID";
    v87[4] = v43 + 16;
    v87[5] = 16;
    v87[0] = &v75;
    v87[1] = &v75;
    v75 = v87;
    v76 = (_QWORD **)v87;
    memset(v88, 0, sizeof(v88));
    LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v88, v45, L"VolumePath", LoggingVolumePath, v49);
    if ( *v76 != &v75 )
      goto LABEL_151;
    *(_QWORD *)&v88[0] = &v75;
    *((_QWORD *)&v88[0] + 1) = v76;
    *v76 = v88;
    v76 = (_QWORD **)v88;
    memset(v86, 0, sizeof(v86));
    LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
    FveApiEventLogDeclareWSTRING(
      (struct _FVEAPI_EVENT_DATA *)v86,
      v47,
      L"VolumeDriveLetter",
      LoggingVolumeDriveLetter,
      v50);
    if ( *v76 != &v75
      || (*(_QWORD *)&v86[0] = &v75,
          *((_QWORD *)&v86[0] + 1) = v76,
          *v76 = v86,
          v89[2] = L"ProtectorGUID",
          v89[3] = L"GUID",
          v89[4] = v6 + 8,
          v89[5] = 16,
          *(_QWORD ***)&v86[0] != &v75) )
    {
LABEL_151:
      __fastfail(3u);
    }
    v89[0] = &v75;
    v89[1] = v86;
    *(_QWORD *)&v86[0] = v89;
    v76 = (_QWORD **)v89;
    v74 = FVEAPI_OP_UPDATE_PIN;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v69, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v73);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v69);
  }
  if ( v6 )
    FveDatumFree(v6);
  if ( v77 )
  {
    FveDatumFree(v77);
    v77 = 0;
  }
  if ( v64 )
    FveDatumFree(v64);
  if ( v65 )
    FveDatumFree(v65);
  if ( v66 )
    FveDatumFree(v66);
  if ( v7 )
    FveDatumFree(v7);
  if ( v60 )
    FveDatumKeyWithParamsFree(&v60, v14, v15);
  if ( v67 )
    FveDatumFree(v67);
  if ( v59 )
    CFveTpm::`scalar deleting destructor'(v59, v14);
  if ( v68 )
    FveDatumFree(v68);
  if ( v78 )
  {
    CFveApiBase::ZeroFree(v78, 584LL * v84[0]);
    v78 = 0;
  }
  if ( v79 )
  {
    PpfFreePredictions(v79);
    v79 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
    && lpMem )
  {
    CFveApiBase::FastFree(lpMem);
  }
  BitLockerFveapiProvider::BitLockerChangePinActivity::StopActivity(
    (BitLockerFveapiProvider::BitLockerChangePinActivity *)v91,
    Vmk,
    v57,
    v85,
    v84[0]);
  BitLockerFveapiProvider::BitLockerChangePinActivity::~BitLockerChangePinActivity((BitLockerFveapiProvider::BitLockerChangePinActivity *)v91);
  return (unsigned int)Vmk;
}

```

## disassembly

```asm
0x1800bae5c  mov     r11, rsp
0x1800bae5f  mov     [r11+18h], rbx
0x1800bae63  mov     [r11+20h], rsi
0x1800bae67  push    rdi
0x1800bae68  push    r12
0x1800bae6a  push    r13
0x1800bae6c  push    r14
0x1800bae6e  push    r15
0x1800bae70  sub     rsp, 430h
0x1800bae77  mov     rax, cs:__security_cookie
0x1800bae7e  xor     rax, rsp
0x1800bae81  mov     [rsp+458h+var_38], rax
0x1800bae89  mov     r14, r8
0x1800bae8c  mov     r13, rdx
0x1800bae8f  mov     [rsp+458h+var_358], rdx
0x1800bae97  mov     rsi, rcx
0x1800bae9a  mov     [rsp+458h+var_348], rcx
0x1800baea2  xor     ebx, ebx
0x1800baea4  mov     [r11-350h], rbx
0x1800baeab  xorps   xmm0, xmm0
0x1800baeae  movups  [rsp+458h+var_2D8], xmm0
0x1800baeb6  movups  [rsp+458h+var_2C8], xmm0
0x1800baebe  movups  [rsp+458h+var_2B8], xmm0
0x1800baec6  movups  [rsp+458h+var_1B0], xmm0
0x1800baece  mov     [rsp+458h+var_3A0], 0FFFFFFFFh
0x1800baed9  mov     [rsp+458h+var_3D8], ebx
0x1800baee0  mov     [rsp+458h+var_3D0], ebx
0x1800baee7  mov     edi, ebx
0x1800baee9  mov     [r11-3B0h], rbx
0x1800baef0  mov     [r11-2F0h], rbx
0x1800baef7  mov     [r11-398h], rbx
0x1800baefe  mov     [r11-390h], rbx
0x1800baf05  mov     [r11-388h], rbx
0x1800baf0c  mov     [r11-3B8h], rbx
0x1800baf13  mov     r12d, ebx
0x1800baf16  mov     [r11-3C8h], rbx
0x1800baf1d  mov     [r11-380h], rbx
0x1800baf24  mov     [rsp+458h+var_3D4], bl
0x1800baf2b  mov     [rsp+458h+var_3D3], bl
0x1800baf32  mov     [r11-3C0h], rbx
0x1800baf39  mov     r15d, ebx
0x1800baf3c  mov     [rsp+458h+var_3D2], bl
0x1800baf43  mov     [r11-378h], rbx
0x1800baf4a  lea     eax, [rbx+1]
0x1800baf4d  mov     [rsp+458h+var_274], eax
0x1800baf54  mov     [rsp+458h+var_3CC], eax
0x1800baf5b  mov     [rsp+458h+var_278], bx
0x1800baf63  mov     [r11-2E8h], rbx
0x1800baf6a  mov     [r11-2E0h], rbx
0x1800baf71  mov     [r11-370h], rbx
0x1800baf78  mov     [r11-3A8h], rbx
0x1800baf7f  movups  xmmword ptr [r11-48h], xmm0
0x1800baf84  xorps   xmm1, xmm1
0x1800baf87  movups  [rsp+458h+var_2A8], xmm1
0x1800baf8f  movups  [rsp+458h+var_298], xmm1
0x1800baf97  movups  [rsp+458h+var_298+0Ch], xmm1
0x1800baf9f  lea     rcx, [r11-198h]; this
0x1800bafa6  call    ??$Start@$$V@BitLockerChangePinActivity@BitLockerFveapiProvider@@SA?AV01@XZ; BitLockerFveapiProvider::BitLockerChangePinActivity::Start<>(void)
0x1800bafab  nop
0x1800bafac  test    r13, r13
0x1800bafaf  jnz     short loc_1800BAFCB
0x1800bafb1  mov     r9d, 80070057h
0x1800bafb7  mov     ebx, r9d
0x1800bafba  lea     rax, aArgchecknewpin; "ArgCheckNewPin"
0x1800bafc1  mov     edx, 18C3h
0x1800bafc6  jmp     loc_1800BBAAF
0x1800bafcb  test    r14, r14
0x1800bafce  jnz     short loc_1800BAFEA
0x1800bafd0  mov     r9d, 80070057h
0x1800bafd6  mov     ebx, r9d
0x1800bafd9  lea     rax, aArgcheckprotec; "ArgCheckProtectorGuid"
0x1800bafe0  mov     edx, 18C8h
0x1800bafe5  jmp     loc_1800BBAAF
0x1800bafea  mov     rcx, rsi; this
0x1800bafed  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800baff2  mov     ebx, eax
0x1800baff4  mov     [rsp+458h+var_3D8], eax
0x1800baffb  test    eax, eax
0x1800baffd  jns     short loc_1800BB013
0x1800bafff  lea     rax, aCheckinited_0; "CheckInited"
0x1800bb006  mov     r9d, ebx
0x1800bb009  mov     edx, 18CEh
0x1800bb00e  jmp     loc_1800BBAB6
0x1800bb013  call    ?EnsureNoBootableCdDvdInserted@@YAJXZ; EnsureNoBootableCdDvdInserted(void)
0x1800bb018  mov     ebx, eax
0x1800bb01a  mov     [rsp+458h+var_3D8], eax
0x1800bb021  test    eax, eax
0x1800bb023  jns     short loc_1800BB039
0x1800bb025  lea     rax, aEnsurenobootab; "EnsureNoBootableCdDvdInserted"
0x1800bb02c  mov     r9d, ebx
0x1800bb02f  mov     edx, 18D8h
0x1800bb034  jmp     loc_1800BBAB6
0x1800bb039  mov     edx, 2
0x1800bb03e  lea     r8d, [rdx+6]
0x1800bb042  lea     rax, [rsp+458h+var_3D0]
0x1800bb04a  mov     qword ptr [rsp+458h+var_438], rax
0x1800bb04f  mov     r9d, [rsp+458h+var_3D0]
0x1800bb057  mov     rcx, [rsi+490h]
0x1800bb05e  call    FveDatasetGetNext
0x1800bb063  mov     ecx, eax; int
0x1800bb065  test    eax, eax
0x1800bb067  js      loc_1800BB103
0x1800bb06d  lea     r8, [rsp+458h+var_3B0]
0x1800bb075  mov     edx, [rsp+458h+var_3D0]
0x1800bb07c  mov     rcx, [rsi+490h]
0x1800bb083  call    FveDatasetGetDatum
0x1800bb088  mov     ecx, eax; int
0x1800bb08a  test    eax, eax
0x1800bb08c  jns     short loc_1800BB0D1
0x1800bb08e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb093  mov     ebx, eax
0x1800bb095  mov     [rsp+458h+var_3D8], eax
0x1800bb09c  mov     rcx, [rsp+458h]; this
0x1800bb0a4  lea     rax, aFvedatasetgetd_0; "FveDatasetGetDatum"
0x1800bb0ab  mov     qword ptr [rsp+458h+var_438], rax; int
0x1800bb0b0  mov     r9d, ebx; char *
0x1800bb0b3  lea     r8, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800bb0ba  mov     edx, 18EBh; void *
0x1800bb0bf  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800bb0c4  mov     rdi, [rsp+458h+var_3B0]
0x1800bb0cc  jmp     loc_1800BBAD0
0x1800bb0d1  mov     rdi, [rsp+458h+var_3B0]
0x1800bb0d9  mov     rax, [rdi+8]
0x1800bb0dd  cmp     rax, [r14]
0x1800bb0e0  jnz     short loc_1800BB0EC
0x1800bb0e2  mov     rax, [rdi+10h]
0x1800bb0e6  cmp     rax, [r14+8]
0x1800bb0ea  jz      short loc_1800BB103
0x1800bb0ec  mov     rcx, rdi
0x1800bb0ef  call    FveDatumFree
0x1800bb0f4  xor     edi, edi
0x1800bb0f6  mov     [rsp+458h+var_3B0], rdi
0x1800bb0fe  jmp     loc_1800BB039
0x1800bb103  test    ecx, ecx
0x1800bb105  jns     short loc_1800BB11F
0x1800bb107  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb10c  mov     ebx, eax
0x1800bb10e  lea     rax, aProtectornotfo; "ProtectorNotFound"
0x1800bb115  mov     edx, 18FBh
0x1800bb11a  jmp     loc_1800BBAAC
0x1800bb11f  lea     rdx, [rsp+458h+var_398]
0x1800bb127  mov     rcx, rdi
0x1800bb12a  call    FveDatumVmkQueryTpmEncBlob
0x1800bb12f  test    eax, eax
0x1800bb131  jns     short loc_1800BB14D
0x1800bb133  mov     ecx, eax; int
0x1800bb135  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb13a  mov     ebx, eax
0x1800bb13c  lea     rax, aFvedatumvmkque_2; "FveDatumVmkQueryTpmEncBlob"
0x1800bb143  mov     edx, 1906h
0x1800bb148  jmp     loc_1800BBAAC
0x1800bb14d  mov     edx, 2002h
0x1800bb152  lea     r8, [rsp+458h+var_390]
0x1800bb15a  mov     rcx, rdi
0x1800bb15d  call    FveDatumVmkQueryUseKey
0x1800bb162  mov     r14d, 80000000h
0x1800bb168  lea     ecx, [rax+r14]
0x1800bb16c  mov     ebx, 0C0000225h
0x1800bb171  test    r14d, ecx
0x1800bb174  jnz     short loc_1800BB194
0x1800bb176  cmp     eax, ebx
0x1800bb178  jz      short loc_1800BB194
0x1800bb17a  mov     ecx, eax; int
0x1800bb17c  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb181  mov     ebx, eax
0x1800bb183  lea     rax, aFvedatumvmkque_5; "FveDatumVmkQueryUseKey"
0x1800bb18a  mov     edx, 190Eh
0x1800bb18f  jmp     loc_1800BBAAC
0x1800bb194  lea     rdx, [rsp+458h+var_380]
0x1800bb19c  mov     rcx, rdi
0x1800bb19f  call    FveDatumVmkQueryLabel
0x1800bb1a4  lea     ecx, [rax+r14]
0x1800bb1a8  test    r14d, ecx
0x1800bb1ab  jnz     short loc_1800BB1CB
0x1800bb1ad  cmp     eax, ebx
0x1800bb1af  jz      short loc_1800BB1CB
0x1800bb1b1  mov     ecx, eax; int
0x1800bb1b3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb1b8  mov     ebx, eax
0x1800bb1ba  lea     rax, aFvedatumvmkque_0; "FveDatumVmkQueryLabel"
0x1800bb1c1  mov     edx, 1915h
0x1800bb1c6  jmp     loc_1800BBAAC
0x1800bb1cb  mov     r14d, 2004h
0x1800bb1d1  mov     edx, r14d
0x1800bb1d4  lea     r8, [rsp+458h+var_388]
0x1800bb1dc  mov     rcx, rdi
0x1800bb1df  call    FveDatumVmkQueryStretchKey
0x1800bb1e4  cmp     eax, ebx
0x1800bb1e6  jnz     short loc_1800BB1FB
0x1800bb1e8  mov     edx, r14d
0x1800bb1eb  lea     r8, [rsp+458h+var_388]
0x1800bb1f3  mov     rcx, rdi
0x1800bb1f6  call    FveDatumVmkQueryUseKey
0x1800bb1fb  test    eax, eax
0x1800bb1fd  jns     short loc_1800BB219
0x1800bb1ff  mov     ecx, eax; int
0x1800bb201  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb206  mov     ebx, eax
0x1800bb208  lea     rax, aFvedatumvmkque; "FveDatumVmkQuery"
0x1800bb20f  mov     edx, 192Ch
0x1800bb214  jmp     loc_1800BBAAC
0x1800bb219  xor     r8d, r8d
0x1800bb21c  lea     rdx, [rsp+458h+var_3D4]
0x1800bb224  mov     rcx, rdi
0x1800bb227  call    FveDatumVmkQueryIsEnhancedPinOrEnhancedCrypto
0x1800bb22c  test    eax, eax
0x1800bb22e  jns     short loc_1800BB24A
0x1800bb230  mov     ecx, eax; int
0x1800bb232  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb237  mov     ebx, eax
0x1800bb239  lea     rax, aFvedatumvmkque_3; "FveDatumVmkQueryIsEnhancedPin"
0x1800bb240  mov     edx, 1939h
0x1800bb245  jmp     loc_1800BBAAC
0x1800bb24a  call    ?OkToExportKey@CFveApiBase@@SAJXZ; CFveApiBase::OkToExportKey(void)
0x1800bb24f  mov     ebx, eax
0x1800bb251  mov     [rsp+458h+var_3D8], eax
0x1800bb258  test    eax, eax
0x1800bb25a  jns     short loc_1800BB270
0x1800bb25c  lea     rax, aOktoexportkey; "OkToExportKey"
0x1800bb263  mov     r9d, ebx
0x1800bb266  mov     edx, 1944h
0x1800bb26b  jmp     loc_1800BBAB6
0x1800bb270  mov     rcx, rsi; this
0x1800bb273  call    ?GetVmk@CFveApiBase@@QEBAJXZ; CFveApiBase::GetVmk(void)
0x1800bb278  mov     ebx, eax
0x1800bb27a  mov     [rsp+458h+var_3D8], eax
0x1800bb281  test    eax, eax
0x1800bb283  js      loc_1800BBAD0
0x1800bb289  mov     rcx, [rsp+458h+var_390]
0x1800bb291  test    rcx, rcx
0x1800bb294  jz      short loc_1800BB2DE
0x1800bb296  lea     r8, [rsp+458h+var_3B8]
0x1800bb29e  mov     rdx, [rsi+4A8h]
0x1800bb2a5  call    FveDatumVmkQueryUseKeyWithParams
0x1800bb2aa  test    eax, eax
0x1800bb2ac  jns     short loc_1800BB2C8
0x1800bb2ae  mov     ecx, eax; int
0x1800bb2b0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb2b5  mov     ebx, eax
0x1800bb2b7  lea     rax, aFvedatumvmkque_1; "FveDatumVmkQueryUseKeyWithParams"
0x1800bb2be  mov     edx, 1955h
0x1800bb2c3  jmp     loc_1800BBAAC
0x1800bb2c8  mov     rax, [rsp+458h+var_3B8]
0x1800bb2d0  mov     [rsp+458h+var_48], rax
0x1800bb2d8  mov     r15d, 1
0x1800bb2de  mov     r14b, [rsp+458h+var_3D4]
0x1800bb2e6  test    r14b, r14b
0x1800bb2e9  setnz   dl; bool
0x1800bb2ec  lea     r8, [rsp+458h+var_3D3]; bool *
0x1800bb2f4  mov     r13, [rsp+458h+var_358]
0x1800bb2fc  mov     rcx, r13; unsigned __int16 *
0x1800bb2ff  call    ?ArePinCharactersValid@CFveApiBase@@KAJPEBG_NPEA_N@Z; CFveApiBase::ArePinCharactersValid(ushort const *,bool,bool *)
0x1800bb304  mov     [rsp+458h+var_3D8], eax
0x1800bb30b  test    eax, eax
0x1800bb30d  js      loc_1800BBA91
0x1800bb313  cmp     [rsp+458h+var_3D3], 0
0x1800bb31b  jz      loc_1800BBA91
0x1800bb321  lea     r8, [rsp+458h+var_3C8]
0x1800bb329  mov     dl, r14b
0x1800bb32c  mov     rcx, r13
0x1800bb32f  call    FveDatumFromPin
0x1800bb334  test    eax, eax
0x1800bb336  jns     short loc_1800BB37D
0x1800bb338  mov     ecx, eax; int
0x1800bb33a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb33f  mov     ebx, eax
0x1800bb341  lea     rax, aFvedatumfrompi; "FveDatumFromPin"
0x1800bb348  mov     edx, 196Bh; void *
0x1800bb34d  mov     [rsp+458h+var_3D8], ebx
0x1800bb354  mov     rcx, [rsp+458h]; this
0x1800bb35c  mov     qword ptr [rsp+458h+var_438], rax; int
0x1800bb361  mov     r9d, ebx; char *
0x1800bb364  lea     r8, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800bb36b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800bb370  mov     r12, [rsp+458h+var_3C8]
0x1800bb378  jmp     loc_1800BBAD0
0x1800bb37d  lea     rdx, [rsp+458h+var_3D2]
0x1800bb385  mov     rcx, rdi
0x1800bb388  call    FveDatumVmkQueryUsesPBKDF2
0x1800bb38d  test    eax, eax
0x1800bb38f  jns     short loc_1800BB3A8
0x1800bb391  mov     ecx, eax; int
0x1800bb393  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb398  mov     ebx, eax
0x1800bb39a  lea     rax, aFvedatumvmkque_4; "FveDatumVmkQueryUsesPBKDF2"
0x1800bb3a1  mov     edx, 1979h
0x1800bb3a6  jmp     short loc_1800BB34D
0x1800bb3a8  cmp     [rsp+458h+var_3D2], 0
0x1800bb3b0  jz      short loc_1800BB405
0x1800bb3b2  lea     rdx, [rsp+458h+var_378]
0x1800bb3ba  lea     rcx, aPbkdf2HmacSha2; "PBKDF2_HMAC_SHA256"
0x1800bb3c1  call    FveDatumUnicodeCreate
0x1800bb3c6  test    eax, eax
0x1800bb3c8  jns     short loc_1800BB3E4
0x1800bb3ca  mov     ecx, eax; int
0x1800bb3cc  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800bb3d1  mov     ebx, eax
0x1800bb3d3  lea     rax, aFvedatumunicod_0; "FveDatumUnicodeCreate"
0x1800bb3da  mov     edx, 1983h
0x1800bb3df  jmp     loc_1800BB34D
  ... truncated ...
```
