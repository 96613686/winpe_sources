# CFveApiBase::CommitChangesHelper(bool,_FVE_COMMIT_SCENARIO_TYPE,ulong)

- ea: `0x180058cdc`
- end: `0x180059c7c`
- name: `?CommitChangesHelper@CFveApiBase@@AEAAJ_NW4_FVE_COMMIT_SCENARIO_TYPE@@K@Z`
- size: `4000`
- prototype: `__int64 __fastcall(__int64, char, unsigned int, unsigned int)`
- caller_count: `21`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180019b60`
- `0x1800403f0`
- `0x180053e94`
- `0x180054f2c`
- `0x180057ab0`
- `0x180058a40`
- `0x18005b494`
- `0x180063d20`
- `0x180067050`
- `0x18006c5e0`
- `0x18006cb80`
- `0x1800ac05c`
- `0x1800aced8`
- `0x1800bd808`
- `0x1800c1820`
- `0x1800c9cf4`
- `0x1800cbe60`
- `0x1800cf510`
- `0x1800cfca4`
- `0x1800d074c`
- `0x1800d0898`

## callees

- `0x180001968`
- `0x180008d70`
- `0x1800090c0`
- `0x18000ab88`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x18001e9e0`
- `0x180037edc`
- `0x1800430a8`
- `0x180043b20`
- `0x180046a90`
- `0x180049aa0`
- `0x18004a484`
- `0x18004a66c`
- `0x18004ad74`
- `0x18004fc2c`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180058cdc`
- `0x18006e21c`
- `0x18006f470`
- `0x180070820`
- `0x1800711d4`
- `0x180071210`
- `0x180077a30`
- `0x180079124`
- `0x18007d328`
- `0x18007e218`
- `0x1800d7c74`
- `0x18011f010`
- `0x180129010`

## string_xrefs

- `0x180059524`: `VolumePath`
- `0x180059754`: `VolumePath`
- `0x18005997c`: `VolumePath`
- `0x180121647`: `VolumePath`
- `0x18012187d`: `VolumePath`
- `0x180121aa7`: `VolumePath`
- `0x180058f78`: `CheckOpenWrite`
- `0x180058fc2`: `LockDismountFileSystem`
- `0x1800590dd`: `FveDatumUpdateCreate`
- `0x180059221`: `RemoveDEVolumeFromDEManagement`
- `0x18005939f`: `Reopen`

## pseudocode

```c
__int64 __fastcall CFveApiBase::CommitChangesHelper(__int64 a1, char a2, unsigned int a3, unsigned int a4)
{
  const wchar_t *v7; // rsi
  __int64 v8; // r13
  int v9; // ebx
  __int64 v10; // r8
  bool v11; // r9
  __int64 v12; // r15
  int v13; // r12d
  __int64 v14; // rdx
  int v15; // r13d
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  PVOID *v19; // rcx
  int First; // eax
  int v21; // eax
  char IsEnabled; // al
  char v23; // cl
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  int updated; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int appended; // eax
  int v32; // eax
  int v33; // eax
  int IsValid; // eax
  int v35; // eax
  _DWORD *v36; // r8
  int v37; // eax
  char v38; // dl
  __int64 v39; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v41; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v43; // rdx
  struct _FVEAPI_EVENT_DATA_COLLECTION *v44; // rdx
  const unsigned __int16 *v45; // rax
  const unsigned __int16 *v46; // rdx
  const unsigned __int16 *v47; // rax
  const unsigned __int16 *v48; // rdx
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // rdx
  const unsigned __int16 *v51; // rax
  const unsigned __int16 *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  unsigned __int8 *v57; // [rsp+78h] [rbp-418h]
  unsigned int v58; // [rsp+78h] [rbp-418h]
  unsigned int v59; // [rsp+78h] [rbp-418h]
  unsigned int v60; // [rsp+78h] [rbp-418h]
  _BYTE v61[4]; // [rsp+C4h] [rbp-3CCh] BYREF
  const wchar_t *v62; // [rsp+C8h] [rbp-3C8h]
  __int64 v63; // [rsp+D0h] [rbp-3C0h] BYREF
  __int64 v64; // [rsp+D8h] [rbp-3B8h] BYREF
  int v65; // [rsp+E0h] [rbp-3B0h]
  _QWORD v66[3]; // [rsp+E8h] [rbp-3A8h] BYREF
  unsigned int v67; // [rsp+100h] [rbp-390h]
  unsigned int v68; // [rsp+104h] [rbp-38Ch] BYREF
  int v69; // [rsp+108h] [rbp-388h] BYREF
  int v70; // [rsp+10Ch] [rbp-384h] BYREF
  int v71; // [rsp+110h] [rbp-380h] BYREF
  const wchar_t *v72; // [rsp+118h] [rbp-378h] BYREF
  _QWORD v73[8]; // [rsp+120h] [rbp-370h] BYREF
  __int64 v74; // [rsp+160h] [rbp-330h] BYREF
  __int64 *v75; // [rsp+168h] [rbp-328h]
  _QWORD *v76; // [rsp+170h] [rbp-320h] BYREF
  _QWORD *v77; // [rsp+178h] [rbp-318h]
  __int64 v78; // [rsp+180h] [rbp-310h] BYREF
  __int64 *v79; // [rsp+188h] [rbp-308h]
  _QWORD *v80; // [rsp+190h] [rbp-300h] BYREF
  _QWORD **v81; // [rsp+198h] [rbp-2F8h]
  __int64 v82; // [rsp+1A0h] [rbp-2F0h] BYREF
  __int64 *v83; // [rsp+1A8h] [rbp-2E8h]
  _QWORD *v84; // [rsp+1B0h] [rbp-2E0h] BYREF
  _QWORD **v85; // [rsp+1B8h] [rbp-2D8h]
  char v86; // [rsp+1C0h] [rbp-2D0h] BYREF
  unsigned __int8 v87; // [rsp+1C1h] [rbp-2CFh] BYREF
  int v88; // [rsp+1C4h] [rbp-2CCh] BYREF
  int v89; // [rsp+1C8h] [rbp-2C8h] BYREF
  int v90; // [rsp+1CCh] [rbp-2C4h] BYREF
  __int128 v91; // [rsp+1D8h] [rbp-2B8h] BYREF
  unsigned int v92; // [rsp+1E8h] [rbp-2A8h] BYREF
  _OWORD v93[3]; // [rsp+1F0h] [rbp-2A0h] BYREF
  _OWORD v94[3]; // [rsp+220h] [rbp-270h] BYREF
  _OWORD v95[3]; // [rsp+250h] [rbp-240h] BYREF
  _QWORD v96[6]; // [rsp+280h] [rbp-210h] BYREF
  _QWORD v97[6]; // [rsp+2B0h] [rbp-1E0h] BYREF
  _QWORD v98[6]; // [rsp+2E0h] [rbp-1B0h] BYREF
  _OWORD v99[3]; // [rsp+310h] [rbp-180h] BYREF
  _QWORD v100[6]; // [rsp+340h] [rbp-150h] BYREF
  _OWORD v101[3]; // [rsp+370h] [rbp-120h] BYREF
  _QWORD v102[6]; // [rsp+3A0h] [rbp-F0h] BYREF
  _OWORD v103[3]; // [rsp+3D0h] [rbp-C0h] BYREF
  _QWORD v104[7]; // [rsp+400h] [rbp-90h] BYREF
  struct _GUID v105; // [rsp+438h] [rbp-58h] BYREF

  v67 = a3;
  v73[7] = a1;
  LODWORD(v72) = a3;
  v7 = L"NA";
  v62 = L"NA";
  v8 = 0;
  v63 = 0;
  v64 = 0;
  v86 = 0;
  v65 = 0;
  v105 = 0;
  v91 = 0;
  v87 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids);
  v9 = CFveApiBase::CheckNumberLimitForRecoveryPassword((CFveApiBase *)a1);
  if ( v9 < 0 )
  {
    v7 = L"CheckNumberLimitForRecoveryPassword";
LABEL_6:
    v62 = v7;
    v12 = v64;
    v13 = 0;
LABEL_103:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_104;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 144LL))(a1, &v86);
  if ( v9 < 0 )
  {
    v7 = L"WorksetHasClearKey";
    goto LABEL_6;
  }
  v15 = *(_DWORD *)(a1 + 108) & 2;
  if ( a2 && (*(_BYTE *)(a1 + 104) & 2) == 0 && !v86 )
  {
    v9 = CFveApiBase::GpCheckForRequiredProtectors((CFveApiBase *)a1);
    if ( v9 < 0 )
    {
      v7 = L"GpCheckForRequiredProtectors";
LABEL_14:
      v62 = v7;
LABEL_15:
      v12 = v64;
      goto LABEL_16;
    }
    if ( (*(_DWORD *)(a1 + 108) & 0x10000001) != 0 )
    {
      v9 = CFveApiBase::CheckOSVolumeForRequiredProtectors((CFveApiBase *)a1);
      if ( v9 < 0 )
      {
        v7 = L"CheckOSVolumeForRequiredProtectors";
        goto LABEL_14;
      }
    }
  }
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl'::`2'::impl,
    v14);
  if ( v15 && !v86 && (a4 & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids, v67, a4);
    v57 = &v87;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)a1 + 288LL))(
            a1,
            a4,
            v67,
            &v105);
    v65 = v16;
    if ( v16 < 0 )
    {
      v7 = L"BackUpRecoveryPasswordOnResume";
      v62 = L"BackUpRecoveryPasswordOnResume";
      v9 = v16;
      goto LABEL_15;
    }
  }
  v17 = CFveApiBase::CheckOpenWrite((CFveApiBase *)a1);
  v9 = v17;
  if ( v17 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v17);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"CheckOpenWrite";
LABEL_33:
    v62 = v7;
    v12 = v64;
    goto LABEL_34;
  }
  if ( *(_BYTE *)(a1 + 1159) )
  {
    LOBYTE(v18) = 1;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 160LL))(a1, v18);
    if ( v9 < 0 )
    {
      v7 = L"LockDismountFileSystem";
      goto LABEL_14;
    }
  }
  if ( *(_BYTE *)(a1 + 1162) )
    *(_DWORD *)(*(_QWORD *)(a1 + 1168) + 32LL) = *(_DWORD *)(a1 + 1208);
  First = FveDatasetGetFirst(*(_QWORD *)(a1 + 1168), 8, 10, &v63);
  v21 = FromNtStatus(First);
  v9 = v21;
  if ( v21 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v21);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"FveDatasetGetFirst";
    goto LABEL_33;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::GetImpl'::`2'::impl);
  v23 = *(_BYTE *)(a1 + 1160);
  if ( IsEnabled )
  {
    if ( v23 )
      v24 = *(_QWORD *)(a1 + 1192);
    else
      v24 = 0;
    v25 = v63;
    v26 = *(unsigned int *)(v63 + 8);
  }
  else
  {
    if ( v23 )
      v24 = *(_QWORD *)(a1 + 1192);
    else
      v24 = 0;
    v26 = 0;
    v25 = v63;
  }
  updated = FveDatumUpdateCreate(v25, v26, v24, &v64);
  v28 = FromNtStatus(updated);
  v9 = v28;
  if ( v28 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v28);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"FveDatumUpdateCreate";
    goto LABEL_33;
  }
  v29 = FveDatasetEraseAll(*(_QWORD *)(a1 + 1168), 8, 0xFFFF);
  v30 = FromNtStatus(v29);
  v9 = v30;
  if ( v30 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v30);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"FveDatasetEraseAll";
    goto LABEL_33;
  }
  v12 = v64;
  appended = FveDatasetAppendDatum(*(_QWORD *)(a1 + 1168), v64, 8);
  v32 = FromNtStatus(appended);
  v9 = v32;
  if ( v32 >= 0 )
  {
    if ( *(_BYTE *)(a1 + 1161) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids);
      v33 = CFveApiBase::RemoveDEVolumeFromDEManagement((CFveApiBase *)a1);
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
            (unsigned int)v33);
        v7 = L"RemoveDEVolumeFromDEManagement";
        v62 = L"RemoveDEVolumeFromDEManagement";
      }
      else
      {
        *(_BYTE *)(a1 + 1161) = 0;
      }
    }
    LOBYTE(v10) = 1;
    IsValid = FveDatasetIsValidEx(*(_QWORD *)(a1 + 1168), **(unsigned int **)(a1 + 1168), v10);
    v35 = FromNtStatus(IsValid);
    v9 = v35;
    if ( v35 >= 0 )
    {
      v36 = *(_DWORD **)(a1 + 1168);
      if ( *(_BYTE *)(a1 + 1225) )
      {
        v92 = 0;
        v37 = CFveApiBase::DeviceIoctlEDrv((CFveApiBase *)a1, 0x4556D087u, v36, *v36, 0, 0, &v92);
      }
      else
      {
        v37 = CFveApiBase::DeviceIoctl((CFveApiBase *)a1, 0x4556D087u, v36, *v36);
      }
      v9 = v37;
      if ( v37 >= 0 )
      {
        v13 = CFveApiBase::CheckRecoveryPasswordDifferenceAndSubmitAADDeletionRequests(
                (CFveApiBase *)a1,
                *(const struct _FVE_DATASET **)(a1 + 1176),
                *(const struct _FVE_DATASET **)(a1 + 1168),
                5,
                1);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              43,
              WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
              (unsigned int)v13);
          v7 = L"CheckAndSubmitForAADDeletionRq";
          v62 = L"CheckAndSubmitForAADDeletionRq";
        }
        *(_BYTE *)(a1 + 1160) = 0;
        if ( (*(_DWORD *)(a1 + 108) & 0x10000001) != 0 && v15 && !v86 )
          FveClearSetupSuspendedBitLockerState();
        v9 = CFveApiBase::ReOpen((CFveApiBase *)a1);
        if ( v9 < 0 )
        {
          v38 = 1;
          v7 = L"Reopen";
          v62 = L"Reopen";
          v19 = (PVOID *)WPP_GLOBAL_Control;
          v8 = v63;
          goto LABEL_105;
        }
        CFveApiBase::LogMetadataSpaceInfo((CFveApiBase *)a1);
        goto LABEL_102;
      }
      v7 = L"DeviceIoctlEDrv";
      v62 = L"DeviceIoctlEDrv";
LABEL_16:
      v13 = 0;
LABEL_102:
      v8 = v63;
      goto LABEL_103;
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v35);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"FveDatasetIsValidEx";
  }
  else
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
        (unsigned int)v32);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = L"FveDatasetAppendDatum";
  }
  v62 = v7;
LABEL_34:
  v8 = v63;
  v13 = 0;
LABEL_104:
  v38 = 0;
LABEL_105:
  v39 = *(_QWORD *)(a1 + 1168);
  if ( v39 )
    v91 = *(_OWORD *)(v39 + 16);
  if ( v9 < 0 && !v38 && v87 )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
      WPP_SF_DDD(v19[2], 44, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids, 0, v87, v9);
    CFveApiBase::SubmitAADDeletionRequest((CFveApiBase *)a1, &v105, v10, v11);
  }
  memset(v66, 0, sizeof(v66));
  if ( v9 == -2144272146 )
  {
    v74 = 0;
    v75 = 0;
    v96[2] = L"IdentityGuid";
    v96[3] = L"GUID";
    v96[4] = &v91;
    v96[5] = 16;
    v96[0] = &v76;
    v96[1] = &v76;
    v76 = v96;
    v77 = v96;
    memset(v99, 0, sizeof(v99));
    LoggingVolumePath = CFveApiBase::GetLoggingVolumePath((CFveApiBase *)a1);
    FveApiEventLogDeclareWSTRING(
      (struct _FVEAPI_EVENT_DATA *)v99,
      v41,
      L"VolumePath",
      LoggingVolumePath,
      (unsigned int)v57);
    if ( (_QWORD **)*v77 == &v76 )
    {
      *(_QWORD *)&v99[0] = &v76;
      *((_QWORD *)&v99[0] + 1) = v77;
      *v77 = v99;
      v77 = v99;
      memset(v93, 0, sizeof(v93));
      LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter((CFveApiBase *)a1);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)v93,
        v43,
        L"VolumeDriveLetter",
        LoggingVolumeDriveLetter,
        v58);
      if ( (_QWORD **)*v77 == &v76 )
      {
        *(_QWORD *)&v93[0] = &v76;
        *((_QWORD *)&v93[0] + 1) = v77;
        *v77 = v93;
        v88 = -2144272146;
        v100[2] = L"hr";
        v100[3] = L"HRESULT";
        v100[4] = &v88;
        v100[5] = 4;
        if ( *(_QWORD ***)&v93[0] == &v76 )
        {
          v100[0] = &v76;
          v100[1] = v93;
          *(_QWORD *)&v93[0] = v100;
          v77 = v100;
          v75 = FVEAPI_OP_ADD_PASSWORD_REACH_LIMIT_FAILURE;
          v44 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v74;
          goto LABEL_128;
        }
      }
    }
LABEL_142:
    __fastfail(3u);
  }
  if ( v9 >= 0 )
  {
    v82 = 0;
    v83 = 0;
    v98[2] = L"IdentityGuid";
    v98[3] = L"GUID";
    v98[4] = &v91;
    v98[5] = 16;
    v98[0] = &v84;
    v98[1] = &v84;
    v84 = v98;
    v85 = (_QWORD **)v98;
    memset(v103, 0, sizeof(v103));
    v49 = CFveApiBase::GetLoggingVolumePath((CFveApiBase *)a1);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v103, v50, L"VolumePath", v49, (unsigned int)v57);
    if ( *v85 != &v84 )
      goto LABEL_142;
    *(_QWORD *)&v103[0] = &v84;
    *((_QWORD *)&v103[0] + 1) = v85;
    *v85 = v103;
    v85 = (_QWORD **)v103;
    memset(v95, 0, sizeof(v95));
    v51 = CFveApiBase::GetLoggingVolumeDriveLetter((CFveApiBase *)a1);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v95, v52, L"VolumeDriveLetter", v51, v60);
    if ( *v85 != &v84 )
      goto LABEL_142;
    *(_QWORD *)&v95[0] = &v84;
    *((_QWORD *)&v95[0] + 1) = v85;
    *v85 = v95;
    v90 = v9;
    v104[2] = L"hr";
    v104[3] = L"HRESULT";
    v104[4] = &v90;
    v104[5] = 4;
    if ( *(_QWORD ***)&v95[0] != &v84 )
      goto LABEL_142;
    v104[0] = &v84;
    v104[1] = v95;
    *(_QWORD *)&v95[0] = v104;
    v85 = (_QWORD **)v104;
    v83 = FVEAPI_OP_METADATA_COMMIT_SUCCESS;
    v44 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v82;
  }
  else
  {
    v78 = 0;
    v79 = 0;
    v97[2] = L"IdentityGuid";
    v97[3] = L"GUID";
    v97[4] = &v91;
    v97[5] = 16;
    v97[0] = &v80;
    v97[1] = &v80;
    v80 = v97;
    v81 = (_QWORD **)v97;
    memset(v101, 0, sizeof(v101));
    v45 = CFveApiBase::GetLoggingVolumePath((CFveApiBase *)a1);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v101, v46, L"VolumePath", v45, (unsigned int)v57);
    if ( *v81 != &v80 )
      goto LABEL_142;
    *(_QWORD *)&v101[0] = &v80;
    *((_QWORD *)&v101[0] + 1) = v81;
    *v81 = v101;
    v81 = (_QWORD **)v101;
    memset(v94, 0, sizeof(v94));
    v47 = CFveApiBase::GetLoggingVolumeDriveLetter((CFveApiBase *)a1);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v94, v48, L"VolumeDriveLetter", v47, v59);
    if ( *v81 != &v80 )
      goto LABEL_142;
    *(_QWORD *)&v94[0] = &v80;
    *((_QWORD *)&v94[0] + 1) = v81;
    *v81 = v94;
    v89 = v9;
    v102[2] = L"hr";
    v102[3] = L"HRESULT";
    v102[4] = &v89;
    v102[5] = 4;
    if ( *(_QWORD ***)&v94[0] != &v80 )
      goto LABEL_142;
    v102[0] = &v80;
    v102[1] = v94;
    *(_QWORD *)&v94[0] = v102;
    v81 = (_QWORD **)v102;
    v79 = FVEAPI_OP_METADATA_COMMIT_FAILURE;
    v44 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v78;
  }
LABEL_128:
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v66, v44);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v66);
  if ( (v9 < 0 || v13 < 0 || v65 < 0)
    && (unsigned int)dword_1801724E0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1801724E0, 0x400000000000LL) )
  {
    v73[0] = 0x1000000;
    v68 = v67;
    v72 = v7;
    v61[0] = *(_BYTE *)(a1 + 1225);
    v69 = v54;
    v70 = v13;
    v71 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v53,
      (int)byte_18015CDC5,
      v54,
      v55,
      (__int64)&v71,
      (__int64)&v70,
      (__int64)&v69,
      (__int64)v61,
      (const size_t **)&v72,
      (__int64)&v68,
      (__int64)v73);
  }
  if ( v8 )
    FveDatumFree(v8);
  if ( v12 )
    FveDatumFree(v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180058cdc  mov     r11, rsp
0x180058cdf  push    rbx
0x180058ce0  push    rsi
0x180058ce1  push    rdi
0x180058ce2  push    r12
0x180058ce4  push    r13
0x180058ce6  push    r14
0x180058ce8  push    r15
0x180058cea  sub     rsp, 400h
0x180058cf1  mov     rax, cs:__security_cookie
0x180058cf8  xor     rax, rsp
0x180058cfb  mov     [rsp+438h+var_48], rax
0x180058d03  mov     r15d, r9d
0x180058d06  mov     eax, r8d
0x180058d09  mov     [rsp+438h+var_390], eax
0x180058d10  mov     r12b, dl
0x180058d13  mov     rdi, rcx
0x180058d16  mov     [rsp+438h+var_338], rcx
0x180058d1e  mov     dword ptr [rsp+438h+var_378], eax
0x180058d25  lea     rsi, aNa; "NA"
0x180058d2c  mov     [rsp+438h+var_3C8], rsi
0x180058d31  mov     [rsp+438h+var_3D4], 8000FFFFh
0x180058d39  xor     eax, eax
0x180058d3b  mov     r13d, eax
0x180058d3e  mov     [rsp+438h+var_3C0], rax
0x180058d43  mov     [r11-3B8h], rax
0x180058d4a  mov     [rsp+438h+var_2D0], al
0x180058d51  mov     [rsp+438h+var_3D0], eax
0x180058d55  mov     [rsp+438h+var_3B0], eax
0x180058d5c  xorps   xmm0, xmm0
0x180058d5f  movdqa  xmmword ptr [r11-58h], xmm0
0x180058d65  xorps   xmm1, xmm1
0x180058d68  movdqa  [rsp+438h+var_2B8], xmm1
0x180058d71  mov     [rsp+438h+var_2CF], al
0x180058d78  mov     [rsp+438h+var_3D8], al
0x180058d7c  lea     rax, WPP_GLOBAL_Control
0x180058d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180058d8a  lea     r14, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids
0x180058d91  cmp     rcx, rax
0x180058d94  jz      short loc_180058DAD
0x180058d96  test    byte ptr [rcx+1Ch], 20h
0x180058d9a  jz      short loc_180058DAD
0x180058d9c  lea     edx, [r13+21h]
0x180058da0  mov     r8, r14
0x180058da3  mov     rcx, [rcx+10h]
0x180058da7  call    WPP_SF_
0x180058dac  nop
0x180058dad  mov     rcx, rdi; this
0x180058db0  call    ?CheckNumberLimitForRecoveryPassword@CFveApiBase@@QEAAJXZ; CFveApiBase::CheckNumberLimitForRecoveryPassword(void)
0x180058db5  mov     ebx, eax
0x180058db7  mov     [rsp+438h+var_3D4], eax
0x180058dbb  test    eax, eax
0x180058dbd  jns     short loc_180058DDD
0x180058dbf  lea     rsi, aChecknumberlim; "CheckNumberLimitForRecoveryPassword"
0x180058dc6  mov     [rsp+438h+var_3C8], rsi
0x180058dcb  mov     r15, [rsp+438h+var_3B8]
0x180058dd3  mov     r12d, [rsp+438h+var_3D0]
0x180058dd8  jmp     loc_1800593C6
0x180058ddd  mov     rax, [rdi]
0x180058de0  lea     rdx, [rsp+438h+var_2D0]
0x180058de8  mov     rcx, rdi
0x180058deb  mov     rax, [rax+90h]
0x180058df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058df7  mov     ebx, eax
0x180058df9  mov     [rsp+438h+var_3D4], eax
0x180058dfd  test    eax, eax
0x180058dff  jns     short loc_180058E0A
0x180058e01  lea     rsi, aWorksethasclea; "WorksetHasClearKey"
0x180058e08  jmp     short loc_180058DC6
0x180058e0a  mov     r13d, [rdi+6Ch]
0x180058e0e  and     r13d, 2
0x180058e12  test    r12b, r12b
0x180058e15  jz      short loc_180058E7B
0x180058e17  test    byte ptr [rdi+68h], 2
0x180058e1b  jnz     short loc_180058E7B
0x180058e1d  cmp     [rsp+438h+var_2D0], 0
0x180058e25  jnz     short loc_180058E7B
0x180058e27  mov     rcx, rdi; this
0x180058e2a  call    ?GpCheckForRequiredProtectors@CFveApiBase@@QEAAJXZ; CFveApiBase::GpCheckForRequiredProtectors(void)
0x180058e2f  mov     ebx, eax
0x180058e31  mov     [rsp+438h+var_3D4], eax
0x180058e35  test    eax, eax
0x180058e37  jns     short loc_180058E57
0x180058e39  lea     rsi, aGpcheckforrequ; "GpCheckForRequiredProtectors"
0x180058e40  mov     [rsp+438h+var_3C8], rsi
0x180058e45  mov     r15, [rsp+438h+var_3B8]
0x180058e4d  mov     r12d, [rsp+438h+var_3D0]
0x180058e52  jmp     loc_1800593C1
0x180058e57  test    dword ptr [rdi+6Ch], 10000001h
0x180058e5e  jz      short loc_180058E7B
0x180058e60  mov     rcx, rdi; this
0x180058e63  call    ?CheckOSVolumeForRequiredProtectors@CFveApiBase@@AEAAJXZ; CFveApiBase::CheckOSVolumeForRequiredProtectors(void)
0x180058e68  mov     ebx, eax
0x180058e6a  mov     [rsp+438h+var_3D4], eax
0x180058e6e  test    eax, eax
0x180058e70  jns     short loc_180058E7B
0x180058e72  lea     rsi, aCheckosvolumef; "CheckOSVolumeForRequiredProtectors"
0x180058e79  jmp     short loc_180058E40
0x180058e7b  mov     dl, 1
0x180058e7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl(void)'::`2'::impl
0x180058e84  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180058e89  test    r13d, r13d
0x180058e8c  jz      loc_180058F32
0x180058e92  cmp     [rsp+438h+var_2D0], 0
0x180058e9a  jnz     loc_180058F32
0x180058ea0  test    r15b, 10h
0x180058ea4  jnz     loc_180058F32
0x180058eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180058eb1  lea     r12, WPP_GLOBAL_Control
0x180058eb8  mov     ebx, [rsp+438h+var_390]
0x180058ebf  cmp     rcx, r12
0x180058ec2  jz      short loc_180058EE3
0x180058ec4  test    byte ptr [rcx+1Ch], 8
0x180058ec8  jz      short loc_180058EE3
0x180058eca  mov     edx, 22h ; '"'
0x180058ecf  mov     dword ptr [rsp+438h+var_418], r15d
0x180058ed4  mov     r9d, ebx
0x180058ed7  mov     r8, r14
0x180058eda  mov     rcx, [rcx+10h]
0x180058ede  call    WPP_SF_Dd
0x180058ee3  mov     rax, [rdi]
0x180058ee6  lea     rcx, [rsp+438h+var_2CF]
0x180058eee  mov     [rsp+438h+var_418], rcx
0x180058ef3  lea     r9, [rsp+438h+var_58]
0x180058efb  mov     r8d, ebx
0x180058efe  mov     edx, r15d
0x180058f01  mov     rcx, rdi
0x180058f04  mov     rax, [rax+120h]
0x180058f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f10  mov     [rsp+438h+var_3B0], eax
0x180058f17  test    eax, eax
0x180058f19  jns     short loc_180058F39
0x180058f1b  lea     rsi, aBackuprecovery; "BackUpRecoveryPasswordOnResume"
0x180058f22  mov     [rsp+438h+var_3C8], rsi
0x180058f27  mov     ebx, eax
0x180058f29  mov     [rsp+438h+var_3D4], eax
0x180058f2d  jmp     loc_180058E45
0x180058f32  lea     r12, WPP_GLOBAL_Control
0x180058f39  mov     rcx, rdi; this
0x180058f3c  call    ?CheckOpenWrite@CFveApiBase@@IEAAJXZ; CFveApiBase::CheckOpenWrite(void)
0x180058f41  mov     ebx, eax
0x180058f43  mov     [rsp+438h+var_3D4], eax
0x180058f47  test    eax, eax
0x180058f49  jns     short loc_180058F9B
0x180058f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f52  cmp     rcx, r12
0x180058f55  jz      short loc_180058F78
0x180058f57  test    byte ptr [rcx+1Ch], 2
0x180058f5b  jz      short loc_180058F78
0x180058f5d  mov     edx, 23h ; '#'
0x180058f62  mov     r9d, eax
0x180058f65  mov     r8, r14
0x180058f68  mov     rcx, [rcx+10h]
0x180058f6c  call    WPP_SF_d
0x180058f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f78  lea     rsi, aCheckopenwrite; "CheckOpenWrite"
0x180058f7f  mov     [rsp+438h+var_3C8], rsi
0x180058f84  mov     r15, [rsp+438h+var_3B8]
0x180058f8c  mov     r13, [rsp+438h+var_3C0]
0x180058f91  mov     r12d, [rsp+438h+var_3D0]
0x180058f96  jmp     loc_1800593CD
0x180058f9b  cmp     byte ptr [rdi+487h], 0
0x180058fa2  jz      short loc_180058FCE
0x180058fa4  mov     rax, [rdi]
0x180058fa7  mov     dl, 1
0x180058fa9  mov     rcx, rdi
0x180058fac  mov     rax, [rax+0A0h]
0x180058fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fb8  mov     ebx, eax
0x180058fba  mov     [rsp+438h+var_3D4], eax
0x180058fbe  test    eax, eax
0x180058fc0  jns     short loc_180058FCE
0x180058fc2  lea     rsi, aLockdismountfi; "LockDismountFileSystem"
0x180058fc9  jmp     loc_180058E40
0x180058fce  cmp     byte ptr [rdi+48Ah], 0
0x180058fd5  jz      short loc_180058FE7
0x180058fd7  mov     rcx, [rdi+490h]
0x180058fde  mov     eax, [rdi+4B8h]
0x180058fe4  mov     [rcx+20h], eax
0x180058fe7  mov     edx, 8
0x180058fec  lea     r8d, [rdx+2]
0x180058ff0  lea     r9, [rsp+438h+var_3C0]
0x180058ff5  mov     rcx, [rdi+490h]
0x180058ffc  call    FveDatasetGetFirst
0x180059001  mov     ecx, eax; int
0x180059003  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180059008  mov     ebx, eax
0x18005900a  mov     [rsp+438h+var_3D4], eax
0x18005900e  test    eax, eax
0x180059010  jns     short loc_18005904B
0x180059012  mov     rcx, cs:WPP_GLOBAL_Control
0x180059019  cmp     rcx, r12
0x18005901c  jz      short loc_18005903F
0x18005901e  test    byte ptr [rcx+1Ch], 2
0x180059022  jz      short loc_18005903F
0x180059024  mov     edx, 24h ; '$'
0x180059029  mov     r9d, eax
0x18005902c  mov     r8, r14
0x18005902f  mov     rcx, [rcx+10h]
0x180059033  call    WPP_SF_d
0x180059038  mov     rcx, cs:WPP_GLOBAL_Control
0x18005903f  lea     rsi, aFvedatasetgetf; "FveDatasetGetFirst"
0x180059046  jmp     loc_180058F7F
0x18005904b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine> `wil::Feature<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::GetImpl(void)'::`2'::impl
0x180059052  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::__private_IsEnabled(void)
0x180059057  mov     cl, [rdi+488h]
0x18005905d  test    al, al
0x18005905f  jz      short loc_18005907B
0x180059061  test    cl, cl
0x180059063  jz      short loc_18005906E
0x180059065  mov     r8, [rdi+4A8h]
0x18005906c  jmp     short loc_180059071
0x18005906e  xor     r8d, r8d
0x180059071  mov     rcx, [rsp+438h+var_3C0]
0x180059076  mov     edx, [rcx+8]
0x180059079  jmp     short loc_180059092
0x18005907b  test    cl, cl
0x18005907d  jz      short loc_180059088
0x18005907f  mov     r8, [rdi+4A8h]
0x180059086  jmp     short loc_18005908B
0x180059088  xor     r8d, r8d
0x18005908b  xor     edx, edx
0x18005908d  mov     rcx, [rsp+438h+var_3C0]
0x180059092  lea     r9, [rsp+438h+var_3B8]
0x18005909a  call    FveDatumUpdateCreate
0x18005909f  mov     ecx, eax; int
0x1800590a1  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800590a6  mov     [rsp+438h+var_3D4], eax
0x1800590aa  mov     ebx, eax
0x1800590ac  test    eax, eax
0x1800590ae  jns     short loc_1800590E9
0x1800590b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800590b7  cmp     rcx, r12
0x1800590ba  jz      short loc_1800590DD
0x1800590bc  test    byte ptr [rcx+1Ch], 2
0x1800590c0  jz      short loc_1800590DD
0x1800590c2  mov     edx, 25h ; '%'
0x1800590c7  mov     r9d, eax
0x1800590ca  mov     r8, r14
0x1800590cd  mov     rcx, [rcx+10h]
0x1800590d1  call    WPP_SF_d
0x1800590d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800590dd  lea     rsi, aFvedatumupdate; "FveDatumUpdateCreate"
0x1800590e4  jmp     loc_180058F7F
0x1800590e9  mov     edx, 8
0x1800590ee  mov     r8d, 0FFFFh
0x1800590f4  mov     rcx, [rdi+490h]
0x1800590fb  call    FveDatasetEraseAll
0x180059100  mov     ecx, eax; int
0x180059102  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180059107  mov     ebx, eax
0x180059109  mov     [rsp+438h+var_3D4], eax
0x18005910d  test    eax, eax
0x18005910f  jns     short loc_18005914A
0x180059111  mov     rcx, cs:WPP_GLOBAL_Control
0x180059118  cmp     rcx, r12
0x18005911b  jz      short loc_18005913E
0x18005911d  test    byte ptr [rcx+1Ch], 2
0x180059121  jz      short loc_18005913E
0x180059123  mov     edx, 26h ; '&'
0x180059128  mov     r9d, eax
0x18005912b  mov     r8, r14
0x18005912e  mov     rcx, [rcx+10h]
0x180059132  call    WPP_SF_d
0x180059137  mov     rcx, cs:WPP_GLOBAL_Control
0x18005913e  lea     rsi, aFvedataseteras; "FveDatasetEraseAll"
0x180059145  jmp     loc_180058F7F
0x18005914a  mov     r8d, 8
0x180059150  mov     r15, [rsp+438h+var_3B8]
0x180059158  mov     rdx, r15
0x18005915b  mov     rcx, [rdi+490h]
0x180059162  call    FveDatasetAppendDatum
0x180059167  mov     ecx, eax; int
0x180059169  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18005916e  mov     ebx, eax
0x180059170  mov     [rsp+438h+var_3D4], eax
0x180059174  test    eax, eax
0x180059176  jns     short loc_1800591B6
0x180059178  mov     rcx, cs:WPP_GLOBAL_Control
0x18005917f  cmp     rcx, r12
0x180059182  jz      short loc_1800591A5
0x180059184  test    byte ptr [rcx+1Ch], 2
0x180059188  jz      short loc_1800591A5
0x18005918a  mov     edx, 27h ; '''
0x18005918f  mov     r9d, eax
0x180059192  mov     r8, r14
0x180059195  mov     rcx, [rcx+10h]
0x180059199  call    WPP_SF_d
0x18005919e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591a5  lea     rsi, aFvedatasetappe; "FveDatasetAppendDatum"
0x1800591ac  mov     [rsp+438h+var_3C8], rsi
0x1800591b1  jmp     loc_180058F8C
0x1800591b6  cmp     byte ptr [rdi+489h], 0
0x1800591bd  jz      short loc_180059235
0x1800591bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591c6  cmp     rcx, r12
0x1800591c9  jz      short loc_1800591E2
0x1800591cb  test    byte ptr [rcx+1Ch], 8
0x1800591cf  jz      short loc_1800591E2
0x1800591d1  mov     edx, 28h ; '('
  ... truncated ...
```
