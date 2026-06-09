# CFveApi::DeleteAuthMethod(_GUID const *,bool)

- ea: `0x1800b6964`
- end: `0x1800b7be0`
- name: `?DeleteAuthMethod@CFveApi@@QEAAJPEBU_GUID@@_N@Z`
- size: `4732`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, const struct _GUID *, bool)`
- caller_count: `5`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d0b0`
- `0x1800403f0`
- `0x180058a40`
- `0x180066dd0`
- `0x1800af7fc`

## callees

- `0x1800030a0`
- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x180019128`
- `0x18001ac58`
- `0x18001b260`
- `0x18001c470`
- `0x18001de20`
- `0x18001eaf4`
- `0x18001f010`
- `0x18001f154`
- `0x180022360`
- `0x1800301c8`
- `0x180037f50`
- `0x18003d000`
- `0x180047570`
- `0x180047a48`
- `0x18004ad74`
- `0x18004dba8`
- `0x18004fa04`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180055c44`
- `0x180060196`
- `0x18007e388`
- `0x180083efc`
- `0x18009f384`
- `0x1800b6964`
- `0x1800ba714`
- `0x1800c60fc`
- `0x1800d62b8`
- `0x18010e7fc`
- `0x18011f010`
- `0x180129010`

## string_xrefs

- `0x1800b7224`: `VolumePath`
- `0x1800b7594`: `VolumePath`
- `0x1800b79a5`: `VolumePath`
- `0x18012612a`: `VolumePath`
- `0x180126483`: `VolumePath`
- `0x1800b7778`: `ServiceName`
- `0x18012632a`: `ServiceName`
- `0x1800b6cad`: `DeleteNotAllowed`
- `0x1800b6e15`: `OkToEnableSecurityPerPolicy`
- `0x1800b6fa5`: `FveDatasetCompress`

## pseudocode

```c
__int64 __fastcall CFveApi::DeleteAuthMethod(CFveApi *this, const struct _GUID *a2, char a3)
{
  const wchar_t *v6; // rdi
  __int64 v7; // r13
  __int64 v8; // rcx
  int HaveAutoUnlockMasterKey; // ebx
  __int64 v10; // r8
  char v11; // r9
  __int64 *v12; // r10
  int Next; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int Datum; // eax
  unsigned __int16 v17; // bx
  bool v18; // r15
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  char v23; // r15
  int v24; // eax
  int v25; // eax
  int Count; // eax
  unsigned __int64 v27; // rcx
  _DWORD *v28; // rax
  _DWORD *v29; // r15
  int v30; // eax
  __int64 v31; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v33; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v35; // rdx
  __int16 v36; // r12
  __int64 v37; // rax
  const unsigned __int16 *v38; // rax
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // rax
  const unsigned __int16 *v41; // rdx
  const unsigned __int16 *LoggingServiceName; // rax
  const unsigned __int16 *v43; // rdx
  struct _FVEAPI_EVENT_DATA_COLLECTION *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rax
  __int128 *v49; // rax
  __int64 v50; // rax
  const unsigned __int16 *v51; // rax
  const unsigned __int16 *v52; // rdx
  const unsigned __int16 *v53; // rax
  const unsigned __int16 *v54; // rdx
  unsigned int v56; // [rsp+70h] [rbp-478h]
  unsigned int v57; // [rsp+70h] [rbp-478h]
  unsigned int v58; // [rsp+70h] [rbp-478h]
  unsigned int v59; // [rsp+70h] [rbp-478h]
  unsigned int v60; // [rsp+70h] [rbp-478h]
  const char *v61; // [rsp+78h] [rbp-470h]
  char v62; // [rsp+C0h] [rbp-428h]
  char v63; // [rsp+C1h] [rbp-427h]
  char v64; // [rsp+C8h] [rbp-420h]
  char v65; // [rsp+C9h] [rbp-41Fh] BYREF
  char v66; // [rsp+CAh] [rbp-41Eh] BYREF
  char v67; // [rsp+CBh] [rbp-41Dh] BYREF
  bool v68[4]; // [rsp+CCh] [rbp-41Ch] BYREF
  __int128 *v69; // [rsp+D0h] [rbp-418h] BYREF
  bool v70; // [rsp+D8h] [rbp-410h] BYREF
  const wchar_t *v71; // [rsp+E0h] [rbp-408h]
  unsigned int v72[4]; // [rsp+E8h] [rbp-400h] BYREF
  struct _GUID v73; // [rsp+F8h] [rbp-3F0h] BYREF
  __int64 *v74; // [rsp+108h] [rbp-3E0h]
  const wchar_t *v75; // [rsp+110h] [rbp-3D8h] BYREF
  int v76; // [rsp+118h] [rbp-3D0h] BYREF
  int v77; // [rsp+11Ch] [rbp-3CCh] BYREF
  int v78; // [rsp+120h] [rbp-3C8h] BYREF
  void *lpMem; // [rsp+128h] [rbp-3C0h]
  int v80; // [rsp+130h] [rbp-3B8h] BYREF
  __int64 v81[3]; // [rsp+138h] [rbp-3B0h] BYREF
  __int128 v82; // [rsp+150h] [rbp-398h]
  __int128 v83; // [rsp+160h] [rbp-388h]
  __int128 v84; // [rsp+170h] [rbp-378h]
  const wchar_t *v85; // [rsp+180h] [rbp-368h]
  const wchar_t *v86; // [rsp+188h] [rbp-360h]
  __int64 v87; // [rsp+190h] [rbp-358h]
  int v88; // [rsp+198h] [rbp-350h]
  __int64 *v89; // [rsp+1A0h] [rbp-348h] BYREF
  __int64 *v90; // [rsp+1A8h] [rbp-340h]
  _QWORD *v91; // [rsp+1B0h] [rbp-338h] BYREF
  _QWORD **v92; // [rsp+1B8h] [rbp-330h]
  __int64 *v93; // [rsp+1C0h] [rbp-328h] BYREF
  __int64 *v94; // [rsp+1C8h] [rbp-320h]
  _QWORD *v95; // [rsp+1D0h] [rbp-318h] BYREF
  _QWORD *v96; // [rsp+1D8h] [rbp-310h]
  __int128 v97; // [rsp+1E0h] [rbp-308h] BYREF
  _QWORD *v98; // [rsp+1F0h] [rbp-2F8h] BYREF
  _QWORD **v99; // [rsp+1F8h] [rbp-2F0h]
  __int16 v100; // [rsp+200h] [rbp-2E8h] BYREF
  int v101; // [rsp+204h] [rbp-2E4h] BYREF
  _OWORD v102[3]; // [rsp+208h] [rbp-2E0h] BYREF
  _OWORD v103[3]; // [rsp+238h] [rbp-2B0h] BYREF
  _OWORD v104[3]; // [rsp+268h] [rbp-280h] BYREF
  _QWORD v105[6]; // [rsp+298h] [rbp-250h] BYREF
  _QWORD v106[6]; // [rsp+2C8h] [rbp-220h] BYREF
  _QWORD v107[6]; // [rsp+2F8h] [rbp-1F0h] BYREF
  _QWORD v108[6]; // [rsp+328h] [rbp-1C0h] BYREF
  _OWORD v109[3]; // [rsp+358h] [rbp-190h] BYREF
  _OWORD v110[3]; // [rsp+388h] [rbp-160h] BYREF
  _QWORD v111[6]; // [rsp+3B8h] [rbp-130h] BYREF
  _OWORD v112[3]; // [rsp+3E8h] [rbp-100h] BYREF
  _OWORD v113[3]; // [rsp+418h] [rbp-D0h] BYREF
  __int128 v114; // [rsp+448h] [rbp-A0h] BYREF
  _QWORD v115[6]; // [rsp+458h] [rbp-90h] BYREF
  _OWORD v116[3]; // [rsp+488h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+0h]

  v75 = (const wchar_t *)this;
  v101 = 0;
  v73 = 0;
  v114 = 0;
  v80 = 0;
  v6 = L"NA";
  v71 = L"NA";
  lpMem = 0;
  memset(&v72[1], 0, 12);
  v7 = 0;
  v69 = 0;
  v64 = 0;
  v68[0] = 0;
  v62 = 0;
  v70 = 0;
  v63 = 0;
  HaveAutoUnlockMasterKey = CFveApiBase::CheckInited(this);
  if ( HaveAutoUnlockMasterKey < 0 )
  {
    v6 = L"CheckInited";
    v71 = L"CheckInited";
    goto LABEL_120;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 56LL))(v8) )
  {
    HaveAutoUnlockMasterKey = CFveApiBase::EnsureWeHaveAutoUnlockMasterKey(this, v68);
    v12 = 0;
    if ( HaveAutoUnlockMasterKey < 0 )
    {
      v6 = L"EnsureWeHaveAutoUnlockMasterKey";
      goto LABEL_8;
    }
  }
  else
  {
    HaveAutoUnlockMasterKey = CFveApiBase::VerifyBindDataVolume(this, 1, v68, &v73);
    v12 = 0;
    if ( HaveAutoUnlockMasterKey == -2144272352 )
      HaveAutoUnlockMasterKey = 0;
    if ( HaveAutoUnlockMasterKey < 0 )
    {
      v6 = L"VerifyBindDataVolume";
LABEL_8:
      v71 = v6;
LABEL_118:
      v11 = v62;
      goto LABEL_119;
    }
    if ( !a2 )
    {
LABEL_10:
      HaveAutoUnlockMasterKey = -2147024809;
      v6 = L"InvalidArgAuthGuid";
      goto LABEL_8;
    }
    if ( v68[0] && *(_QWORD *)&v73.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)v73.Data4 == *(_QWORD *)a2->Data4 )
    {
      HaveAutoUnlockMasterKey = -2144272353;
      v6 = L"AuthAutoUnlock";
      goto LABEL_8;
    }
  }
  HaveAutoUnlockMasterKey = CFveApiBase::GetVmk(this);
  v12 = 0;
  if ( HaveAutoUnlockMasterKey < 0 )
  {
    v6 = L"GetVmk";
    goto LABEL_8;
  }
  if ( !a2 )
    goto LABEL_10;
  v72[0] = 0;
  while ( 1 )
  {
    Next = FveDatasetGetNext(*((_QWORD *)this + 146), 2, 8, v72[0], (__int64)v72);
    v15 = (unsigned int)Next;
    if ( Next < 0 )
      break;
    Datum = FveDatasetGetDatum(*((_QWORD *)this + 146), v72[0], &v72[2]);
    v15 = (unsigned int)Datum;
    if ( Datum < 0 )
    {
      HaveAutoUnlockMasterKey = FromNtStatus(Datum);
      v6 = L"FveDatasetGetDatum";
      v71 = L"FveDatasetGetDatum";
      v7 = *(_QWORD *)&v72[2];
LABEL_24:
      v12 = 0;
      goto LABEL_118;
    }
    v7 = *(_QWORD *)&v72[2];
    if ( *(_OWORD *)(*(_QWORD *)&v72[2] + 8LL) == *(_OWORD *)a2 )
      break;
    FveDatumFree(*(_QWORD *)&v72[2]);
    v7 = 0;
    *(_QWORD *)&v72[2] = 0;
  }
  if ( (int)v15 < 0 )
  {
    HaveAutoUnlockMasterKey = FromNtStatus(v15);
    v6 = L"ItemNotFound";
LABEL_29:
    v71 = v6;
    goto LABEL_24;
  }
  v17 = *(_WORD *)(v7 + 34) & 0xFF00;
  if ( a3 || !v17 )
  {
    v63 = 1;
  }
  else
  {
    if ( v17 == 2048 )
    {
      v18 = (unsigned int)CFveApiBase::LicenseCheck(this, (wchar_t *)L"SecureStartupFeature-Enabled-DeviceEncryption") == 0;
      v63 = v18;
    }
    else
    {
      v18 = 0;
    }
    if ( !v18 )
    {
      HaveAutoUnlockMasterKey = NgscbpDoesRegKeyExist(v15, v14, &v80);
      v12 = 0;
      if ( HaveAutoUnlockMasterKey >= 0 )
        HaveAutoUnlockMasterKey = v80 != 0 ? -2144272301 : -2144272294;
      v6 = L"DeleteNotAllowed";
      goto LABEL_8;
    }
  }
  if ( (*((_BYTE *)this + 224) & 0x10) != 0 && v17 == 2048 || ((v17 - 256) & 0xFEFF) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF__guid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        v7 + 8,
        v17);
    *((_BYTE *)this + 1161) = 1;
  }
  if ( (*(_WORD *)(v7 + 34) & 0x100) != 0 )
  {
    v19 = FveDatasetEraseDigestDatumsOfVmkInfo(*((_QWORD *)this + 146), v72[0]);
    v20 = FromNtStatus(v19);
    HaveAutoUnlockMasterKey = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)v20);
      v6 = L"FveDatasetEraseDigestDatumsOfVmkInfo";
      v71 = L"FveDatasetEraseDigestDatumsOfVmkInfo";
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1515,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
        (const char *)(unsigned int)HaveAutoUnlockMasterKey,
        (int)"FveDatasetEraseDigestDatumsOfVmkInfo",
        v61);
      goto LABEL_24;
    }
  }
  v21 = FveDatasetEraseDatum(*((_QWORD *)this + 146), v72[0]);
  HaveAutoUnlockMasterKey = FromNtStatus(v21);
  v12 = 0;
  if ( HaveAutoUnlockMasterKey < 0 )
  {
    v6 = L"FveDatasetEraseDatum";
    goto LABEL_8;
  }
  if ( (*(_WORD *)(v7 + 34) & 0xFF00) == 0 )
  {
    HaveAutoUnlockMasterKey = CFveApiBase::OkToEnableSecurityPerPolicy(this);
    v12 = 0;
    if ( HaveAutoUnlockMasterKey < 0 )
    {
      v6 = L"OkToEnableSecurityPerPolicy";
      goto LABEL_8;
    }
    v22 = FveDatumNestedExtractFirst(v7, 0xFFFF, 36, &v69);
    HaveAutoUnlockMasterKey = FromNtStatus(v22);
    if ( HaveAutoUnlockMasterKey < 0 && HaveAutoUnlockMasterKey != (unsigned int)FromNtStatus(-1073741275) )
    {
      v6 = L"ClearKeyAdditionalInfoDatum";
      goto LABEL_29;
    }
    if ( v69 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        *((unsigned __int16 *)v69 + 5));
    CFveApi::SqmOnDeleteClearKey(this, *(unsigned __int16 *)(v7 + 6));
    v62 = 1;
    if ( (*(_BYTE *)(v7 + 6) & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v23 = 1;
      v64 = 1;
      goto LABEL_82;
    }
LABEL_81:
    v23 = 0;
    goto LABEL_82;
  }
  v24 = NgscbCheckRecycleKeysOnAuthMethodDeletion(&v70);
  HaveAutoUnlockMasterKey = v24;
  v12 = 0;
  if ( v24 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)v24);
      v12 = 0;
    }
    v6 = L"NgscbCheckRecycleKeysOnAuthMethodDeletion";
    goto LABEL_8;
  }
  if ( !v70 )
    goto LABEL_81;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
  v62 = 1;
  v23 = 0;
  v64 = 0;
LABEL_82:
  v25 = FveDatasetCompress(*((_QWORD *)this + 146));
  HaveAutoUnlockMasterKey = FromNtStatus(v25);
  v12 = 0;
  if ( HaveAutoUnlockMasterKey < 0 )
  {
    v6 = L"FveDatasetCompress";
    goto LABEL_8;
  }
  Count = FveDatasetGetCount(*((_QWORD *)this + 146), 2, 8, &v101);
  HaveAutoUnlockMasterKey = FromNtStatus(Count);
  v12 = 0;
  if ( HaveAutoUnlockMasterKey < 0 )
  {
    v6 = L"FveDatasetGetCount";
    goto LABEL_8;
  }
  if ( !v101 && *((_DWORD *)this + 26) != 0x8000 && (*((_BYTE *)this + 104) & 2) == 0 )
  {
    HaveAutoUnlockMasterKey = -2144272355;
    v6 = L"MustHaveOneKey";
    goto LABEL_8;
  }
  v11 = v62;
  if ( !v62 )
  {
LABEL_119:
    v10 = (__int64)v69;
    goto LABEL_120;
  }
  if ( v23 && (v27 = *((unsigned int *)this + 296), (unsigned int)v27 >= **((_DWORD **)this + 146)) )
  {
    v28 = CFveApiBase::ZeroAlloc(v27);
    v29 = v28;
    lpMem = v28;
    if ( v28 )
    {
      memcpy_0(v28, *((const void **)this + 146), *((unsigned int *)this + 296));
      *v29 = **((_DWORD **)this + 146);
      v72[1] = *((_DWORD *)this + 296);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
    }
  }
  else
  {
    v29 = lpMem;
  }
  v30 = CFveApi::KeyManagement(this, 0x4Au, 0);
  HaveAutoUnlockMasterKey = v30;
  v12 = 0;
  if ( v30 >= 0 )
  {
    if ( v30 == 1 )
      HaveAutoUnlockMasterKey = 0;
    goto LABEL_118;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      (unsigned int)v30);
    v12 = 0;
  }
  if ( !v64 || !v29 )
  {
    v6 = L"FailedClearKeyDeletion";
    goto LABEL_8;
  }
  v97 = 0;
  *(_QWORD *)&v73.Data1 = 0;
  *(_QWORD *)v73.Data4 = 0;
  v74 = 0;
  v99 = &v98;
  v98 = &v98;
  v31 = *((_QWORD *)this + 146);
  v84 = 0;
  v85 = L"IdentityGuid";
  v86 = L"GUID";
  v87 = v31 + 16;
  v88 = 16;
  v115[2] = L"IdentityGuid";
  v115[3] = L"GUID";
  v115[4] = v31 + 16;
  v115[5] = 16;
  v115[0] = &v98;
  v115[1] = &v98;
  v98 = v115;
  v99 = (_QWORD **)v115;
  memset(v116, 0, sizeof(v116));
  LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v116, v33, L"VolumePath", LoggingVolumePath, v56);
  if ( *v99 != &v98 )
    __fastfail(3u);
  *(_QWORD *)&v116[0] = &v98;
  *((_QWORD *)&v116[0] + 1) = v99;
  *v99 = v116;
  v99 = (_QWORD **)v116;
  memset(v113, 0, sizeof(v113));
  LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
  FveApiEventLogDeclareWSTRING(
    (struct _FVEAPI_EVENT_DATA *)v113,
    v35,
    L"VolumeDriveLetter",
    LoggingVolumeDriveLetter,
    v57);
  if ( *v99 != &v98 )
    __fastfail(3u);
  *(_QWORD *)&v113[0] = &v98;
  *((_QWORD *)&v113[0] + 1) = v99;
  *v99 = v113;
  v99 = (_QWORD **)v113;
  v101 = HaveAutoUnlockMasterKey;
  *(_QWORD *)&v82 = L"hr";
  *((_QWORD *)&v82 + 1) = L"HRESULT";
  *(_QWORD *)&v83 = &v101;
  *((_QWORD *)&v83 + 1) = 4;
  v104[0] = 0;
  v104[1] = v82;
  v104[2] = v83;
  if ( *(_QWORD ***)&v113[0] != &v98 )
    __fastfail(3u);
  *(_QWORD *)&v104[0] = &v98;
  *((_QWORD *)&v104[0] + 1) = v113;
  *(_QWORD *)&v113[0] = v104;
  v99 = (_QWORD **)v104;
  *((_QWORD *)&v97 + 1) = FVEAPI_OP_VMK_NOT_ROLLED_ON_CLEARKEY_REMOVAL;
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v73, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v97);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v73);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
  CFveApiBase::ZeroFree(*((void **)this + 146), *((unsigned int *)this + 296));
  *((_QWORD *)this + 146) = lpMem;
  v12 = 0;
  lpMem = 0;
  *((_DWORD *)this + 296) = v72[1];
  v72[1] = 0;
  HaveAutoUnlockMasterKey = 0;
  v10 = (__int64)v69;
  v11 = v62;
LABEL_120:
  if ( HaveAutoUnlockMasterKey < 0 )
    goto LABEL_130;
  if ( !v11 )
  {
    v93 = v12;
    v94 = v12;
    *(_QWORD *)&v73.Data1 = v12;
    *(_QWORD *)v73.Data4 = v12;
    v74 = v12;
    v50 = *((_QWORD *)this + 146);
    v107[2] = L"IdentityGuid";
    v107[3] = L"GUID";
    v107[4] = v50 + 16;
    v107[5] = 16;
    v107[0] = &v95;
    v107[1] = &v95;
    v95 = v107;
    v96 = v107;
    memset(v110, 0, sizeof(v110));
    v51 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v110, v52, L"VolumePath", v51, v56);
    if ( (_QWORD **)*v96 == &v95 )
    {
      *(_QWORD *)&v110[0] = &v95;
      *((_QWORD *)&v110[0] + 1) = v96;
      *v96 = v110;
      v96 = v110;
      memset(v103, 0, sizeof(v103));
      v53 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v103, v54, L"VolumeDriveLetter", v53, v60);
      if ( (_QWORD **)*v96 == &v95 )
      {
        *(_QWORD *)&v103[0] = &v95;
        *((_QWORD *)&v103[0] + 1) = v96;
        *v96 = v103;
        v111[2] = L"ProtectorGUID";
        v111[3] = L"GUID";
        v111[4] = v7 + 8;
        v111[5] = 16;
        if ( *(_QWORD ***)&v103[0] == &v95 )
        {
          v111[0] = &v95;
          v111[1] = v103;
          *(_QWORD *)&v103[0] = v111;
          v96 = v111;
          v94 = FVEAPI_OP_PROTECTOR_REMOVED;
          v44 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v93;
          goto LABEL_129;
        }
      }
    }
LABEL_144:
    __fastfail(3u);
  }
  v36 = (__int16)v12;
  if ( v10 )
    v36 = *(_WORD *)(v10 + 10);
  v89 = v12;
  v90 = v12;
  *(_QWORD *)&v73.Data1 = v12;
  *(_QWORD *)v73.Data4 = v12;
  v74 = v12;
  v37 = *((_QWORD *)this + 146);
  v105[2] = L"IdentityGuid";
  v105[3] = L"GUID";
  v105[4] = v37 + 16;
  v105[5] = 16;
  v105[0] = &v91;
  v105[1] = &v91;
  v91 = v105;
  v92 = (_QWORD **)v105;
  memset(v112, 0, sizeof(v112));
  v38 = CFveApiBase::GetLoggingVolumePath(this);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v112, v39, L"VolumePath", v38, v56);
  if ( *v92 != &v91 )
    goto LABEL_144;
  *(_QWORD *)&v112[0] = &v91;
  *((_QWORD *)&v112[0] + 1) = v92;
  *v92 = v112;
  v92 = (_QWORD **)v112;
  memset(v102, 0, sizeof(v102));
  v40 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v102, v41, L"VolumeDriveLetter", v40, v58);
  if ( *v92 != &v91 )
    goto LABEL_144;
  *(_QWORD *)&v102[0] = &v91;
  *((_QWORD *)&v102[0] + 1) = v92;
  *v92 = v102;
  v108[2] = L"ProtectorGUID";
  v108[3] = L"GUID";
  v108[4] = v7 + 8;
  v108[5] = 16;
  if ( *(_QWORD ***)&v102[0] != &v91 )
    goto LABEL_144;
  v108[1] = v102;
  *(_QWORD *)&v102[0] = v108;
  v100 = v36;
  v106[2] = L"ClearKeyScenario";
  v106[3] = L"USHORT";
  v106[4] = &v100;
  v106[5] = 2;
  v106[0] = &v91;
  v106[1] = v108;
  v108[0] = v106;
  v92 = (_QWORD **)v106;
  memset(v109, 0, sizeof(v109));
  LoggingServiceName = CFveApiBase::GetLoggingServiceName(this);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v109, v43, L"ServiceName", LoggingServiceName, v59);
  if ( *v92 != &v91 )
    goto LABEL_144;
  *(_QWORD *)&v109[0] = &v91;
  *((_QWORD *)&v109[0] + 1) = v92;
  *v92 = v109;
  v92 = (_QWORD **)v109;
  v90 = FVEAPI_OP_PROTECTION_RESUME;
  v44 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v89;
LABEL_129:
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v73, v44);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v73);
LABEL_130:
  if ( v7 )
    FveDatumFree(v7);
  if ( v69 )
    FveDatumFree(v69);
  if ( lpMem )
    CFveApiBase::ZeroFree(lpMem, v72[1]);
  if ( (unsigned int)dword_1801724E0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801724E0, 0x400000000000LL) )
  {
    v81[0] = 0x1000000;
    v76 = HaveAutoUnlockMasterKey;
    v77 = 1;
    v75 = v6;
    v65 = v63;
    v66 = *((_BYTE *)this + 1161);
    v78 = *((_DWORD *)this + 26);
    v67 = v62;
    *(_QWORD *)&v72[2] = a2;
    v48 = *((_QWORD *)this + 146);
    if ( v48 )
      v49 = (__int128 *)(v48 + 16);
    else
      v49 = &v114;
    v69 = v49;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v45,
      (int)&dword_18015EEFC,
      v46,
      v47,
      (__int64 *)&v69,
      (__int64 *)&v72[2],
      (__int64)&v67,
      (__int64)&v78,
      (__int64)&v66,
      (__int64)&v65,
      (const size_t **)&v75,
      (__int64)&v77,
      (__int64)&v76,
      (__int64)v81);
  }
  return (unsigned int)HaveAutoUnlockMasterKey;
}

```

## disassembly

```asm
0x1800b6964  mov     r11, rsp
0x1800b6967  mov     [r11+18h], rbx
0x1800b696b  mov     [r11+20h], rsi
0x1800b696f  mov     [r11+10h], rdx
0x1800b6973  push    rdi
0x1800b6974  push    r12
0x1800b6976  push    r13
0x1800b6978  push    r14
0x1800b697a  push    r15
0x1800b697c  sub     rsp, 470h
0x1800b6983  mov     rax, cs:__security_cookie
0x1800b698a  xor     rax, rsp
0x1800b698d  mov     [rsp+498h+var_30], rax
0x1800b6995  mov     r14b, r8b
0x1800b6998  mov     r12, rdx
0x1800b699b  mov     rsi, rcx
0x1800b699e  mov     [rsp+498h+var_3D8], rcx
0x1800b69a6  xor     r10d, r10d
0x1800b69a9  mov     [r11-2E4h], r10d
0x1800b69b0  xorps   xmm0, xmm0
0x1800b69b3  movups  xmmword ptr [rsp+498h+var_3F0.Data1], xmm0
0x1800b69bb  xorps   xmm1, xmm1
0x1800b69be  movups  [rsp+498h+var_A0], xmm1
0x1800b69c6  mov     [r11-3B8h], r10d
0x1800b69cd  lea     rdi, aNa; "NA"
0x1800b69d4  mov     [r11-408h], rdi
0x1800b69db  mov     [rsp+498h+var_424], r10d
0x1800b69e0  mov     [r11-3C0h], r10
0x1800b69e7  mov     [r11-3FCh], r10d
0x1800b69ee  mov     r13d, r10d
0x1800b69f1  mov     [r11-3F8h], r10
0x1800b69f8  mov     r8d, r10d
0x1800b69fb  mov     [r11-418h], r10
0x1800b6a02  mov     [rsp+498h+var_420], r10b
0x1800b6a07  mov     [rsp+498h+var_41C], r10b
0x1800b6a0c  mov     r9b, r10b
0x1800b6a0f  mov     [rsp+498h+var_428], r10b
0x1800b6a14  mov     [r11-410h], r10b
0x1800b6a1b  mov     [rsp+498h+var_427], r10b
0x1800b6a20  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800b6a25  mov     ebx, eax
0x1800b6a27  mov     [rsp+498h+var_424], eax
0x1800b6a2b  test    eax, eax
0x1800b6a2d  jns     short loc_1800B6A43
0x1800b6a2f  lea     rdi, aCheckinited; "CheckInited"
0x1800b6a36  mov     [rsp+498h+var_408], rdi
0x1800b6a3e  jmp     loc_1800B74AB
0x1800b6a43  mov     rax, [rcx]
0x1800b6a46  mov     rax, [rax+38h]
0x1800b6a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a4f  mov     rcx, rsi; this
0x1800b6a52  test    al, al
0x1800b6a54  jnz     loc_1800B6AE9
0x1800b6a5a  lea     r9, [rsp+498h+var_3F0]; struct _GUID *
0x1800b6a62  lea     r8, [rsp+498h+var_41C]; bool *
0x1800b6a67  mov     dl, 1; bool
0x1800b6a69  call    ?VerifyBindDataVolume@CFveApiBase@@QEAAJ_NPEA_NPEAU_GUID@@@Z; CFveApiBase::VerifyBindDataVolume(bool,bool *,_GUID *)
0x1800b6a6e  mov     ebx, eax
0x1800b6a70  mov     [rsp+498h+var_424], eax
0x1800b6a74  xor     r10d, r10d
0x1800b6a77  cmp     eax, 80310020h
0x1800b6a7c  cmovz   ebx, r10d
0x1800b6a80  mov     [rsp+498h+var_424], ebx
0x1800b6a84  test    ebx, ebx
0x1800b6a86  jns     short loc_1800B6A9C
0x1800b6a88  lea     rdi, aVerifybinddata; "VerifyBindDataVolume"
0x1800b6a8f  mov     [rsp+498h+var_408], rdi
0x1800b6a97  jmp     loc_1800B749E
0x1800b6a9c  test    r12, r12
0x1800b6a9f  jnz     short loc_1800B6AB3
0x1800b6aa1  mov     ebx, 80070057h
0x1800b6aa6  mov     [rsp+498h+var_424], ebx
0x1800b6aaa  lea     rdi, aInvalidargauth_0; "InvalidArgAuthGuid"
0x1800b6ab1  jmp     short loc_1800B6A8F
0x1800b6ab3  cmp     [rsp+498h+var_41C], r10b
0x1800b6ab8  jz      short loc_1800B6B09
0x1800b6aba  mov     rax, qword ptr [rsp+498h+var_3F0.Data1]
0x1800b6ac2  cmp     rax, [r12]
0x1800b6ac6  jnz     short loc_1800B6B09
0x1800b6ac8  mov     rax, qword ptr [rsp+498h+var_3F0.Data4]
0x1800b6ad0  cmp     rax, [r12+8]
0x1800b6ad5  jnz     short loc_1800B6B09
0x1800b6ad7  mov     ebx, 8031001Fh
0x1800b6adc  mov     [rsp+498h+var_424], ebx
0x1800b6ae0  lea     rdi, aAuthautounlock; "AuthAutoUnlock"
0x1800b6ae7  jmp     short loc_1800B6A8F
0x1800b6ae9  lea     rdx, [rsp+498h+var_41C]; bool *
0x1800b6aee  call    ?EnsureWeHaveAutoUnlockMasterKey@CFveApiBase@@QEAAJPEA_N@Z; CFveApiBase::EnsureWeHaveAutoUnlockMasterKey(bool *)
0x1800b6af3  mov     ebx, eax
0x1800b6af5  mov     [rsp+498h+var_424], eax
0x1800b6af9  xor     r10d, r10d
0x1800b6afc  test    eax, eax
0x1800b6afe  jns     short loc_1800B6B09
0x1800b6b00  lea     rdi, aEnsurewehaveau_0; "EnsureWeHaveAutoUnlockMasterKey"
0x1800b6b07  jmp     short loc_1800B6A8F
0x1800b6b09  mov     rcx, rsi; this
0x1800b6b0c  call    ?GetVmk@CFveApiBase@@QEBAJXZ; CFveApiBase::GetVmk(void)
0x1800b6b11  mov     ebx, eax
0x1800b6b13  mov     [rsp+498h+var_424], eax
0x1800b6b17  xor     r10d, r10d
0x1800b6b1a  test    eax, eax
0x1800b6b1c  jns     short loc_1800B6B2A
0x1800b6b1e  lea     rdi, aGetvmk; "GetVmk"
0x1800b6b25  jmp     loc_1800B6A8F
0x1800b6b2a  test    r12, r12
0x1800b6b2d  jz      loc_1800B6AA1
0x1800b6b33  mov     [rsp+498h+var_400], r10d
0x1800b6b3b  xor     r15d, r15d
0x1800b6b3e  mov     edx, 2
0x1800b6b43  lea     r8d, [rdx+6]
0x1800b6b47  lea     rax, [rsp+498h+var_400]
0x1800b6b4f  mov     qword ptr [rsp+498h+var_478], rax; unsigned int
0x1800b6b54  mov     r9d, [rsp+498h+var_400]
0x1800b6b5c  mov     rcx, [rsi+490h]
0x1800b6b63  call    FveDatasetGetNext
0x1800b6b68  mov     ecx, eax; int
0x1800b6b6a  test    eax, eax
0x1800b6b6c  js      loc_1800B6BF2
0x1800b6b72  lea     r8, [rsp+498h+var_3FC+4]
0x1800b6b7a  mov     edx, [rsp+498h+var_400]
0x1800b6b81  mov     rcx, [rsi+490h]
0x1800b6b88  call    FveDatasetGetDatum
0x1800b6b8d  mov     ecx, eax; int
0x1800b6b8f  test    eax, eax
0x1800b6b91  jns     short loc_1800B6BBD
0x1800b6b93  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6b98  mov     ebx, eax
0x1800b6b9a  mov     [rsp+498h+var_424], eax
0x1800b6b9e  lea     rdi, aFvedatasetgetd; "FveDatasetGetDatum"
0x1800b6ba5  mov     [rsp+498h+var_408], rdi
0x1800b6bad  mov     r13, qword ptr [rsp+498h+var_3FC+4]
0x1800b6bb5  xor     r10d, r10d
0x1800b6bb8  jmp     loc_1800B749E
0x1800b6bbd  mov     r13, qword ptr [rsp+498h+var_3FC+4]
0x1800b6bc5  mov     rax, [r13+8]
0x1800b6bc9  cmp     rax, [r12]
0x1800b6bcd  jnz     short loc_1800B6BDA
0x1800b6bcf  mov     rax, [r13+10h]
0x1800b6bd3  cmp     rax, [r12+8]
0x1800b6bd8  jz      short loc_1800B6BF2
0x1800b6bda  mov     rcx, r13
0x1800b6bdd  call    FveDatumFree
0x1800b6be2  mov     r13, r15
0x1800b6be5  mov     qword ptr [rsp+498h+var_3FC+4], r15
0x1800b6bed  jmp     loc_1800B6B3E
0x1800b6bf2  test    ecx, ecx
0x1800b6bf4  jns     short loc_1800B6C12
0x1800b6bf6  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6bfb  mov     ebx, eax
0x1800b6bfd  mov     [rsp+498h+var_424], eax
0x1800b6c01  lea     rdi, aItemnotfound; "ItemNotFound"
0x1800b6c08  mov     [rsp+498h+var_408], rdi
0x1800b6c10  jmp     short loc_1800B6BB5
0x1800b6c12  mov     ebx, 0FF00h
0x1800b6c17  and     bx, [r13+22h]
0x1800b6c1c  test    r14b, r14b
0x1800b6c1f  mov     r14d, 800h
0x1800b6c25  jz      short loc_1800B6C4A
0x1800b6c27  mov     [rsp+498h+var_427], 1
0x1800b6c2c  test    byte ptr [rsi+0E0h], 10h
0x1800b6c33  jz      loc_1800B6CB9
0x1800b6c39  cmp     bx, r14w
0x1800b6c3d  jnz     short loc_1800B6CB9
0x1800b6c3f  mov     r15d, 100h
0x1800b6c45  jmp     loc_1800B6CD0
0x1800b6c4a  test    bx, bx
0x1800b6c4d  jz      short loc_1800B6C27
0x1800b6c4f  cmp     bx, r14w
0x1800b6c53  jnz     short loc_1800B6C71
0x1800b6c55  lea     rdx, aSecurestartupf_2; "SecureStartupFeature-Enabled-DeviceEncr"...
0x1800b6c5c  mov     rcx, rsi; this
0x1800b6c5f  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x1800b6c64  test    eax, eax
0x1800b6c66  setz    r15b
0x1800b6c6a  mov     [rsp+498h+var_427], r15b
0x1800b6c6f  jmp     short loc_1800B6C76
0x1800b6c71  mov     r15b, [rsp+498h+var_427]
0x1800b6c76  test    r15b, r15b
0x1800b6c79  jnz     short loc_1800B6C2C
0x1800b6c7b  lea     r8, [rsp+498h+var_3B8]
0x1800b6c83  call    NgscbpDoesRegKeyExist
0x1800b6c88  mov     ebx, eax
0x1800b6c8a  mov     [rsp+498h+var_424], eax
0x1800b6c8e  xor     r10d, r10d
0x1800b6c91  test    eax, eax
0x1800b6c93  js      short loc_1800B6CAD
0x1800b6c95  mov     eax, [rsp+498h+var_3B8]
0x1800b6c9c  neg     eax
0x1800b6c9e  sbb     ebx, ebx
0x1800b6ca0  and     ebx, 0FFFFFFF9h
0x1800b6ca3  add     ebx, 8031005Ah
0x1800b6ca9  mov     [rsp+498h+var_424], ebx
0x1800b6cad  lea     rdi, aDeletenotallow; "DeleteNotAllowed"
0x1800b6cb4  jmp     loc_1800B6A8F
0x1800b6cb9  mov     r15d, 100h
0x1800b6cbf  movzx   eax, bx
0x1800b6cc2  sub     ax, r15w
0x1800b6cc6  mov     ecx, 0FEFFh
0x1800b6ccb  test    cx, ax
0x1800b6cce  jnz     short loc_1800B6D1E
0x1800b6cd0  lea     r14, WPP_GLOBAL_Control
0x1800b6cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6cde  cmp     rcx, r14
0x1800b6ce1  jz      short loc_1800B6D0E
0x1800b6ce3  test    byte ptr [rcx+1Ch], 8
0x1800b6ce7  jz      short loc_1800B6D0E
0x1800b6ce9  movzx   eax, bx
0x1800b6cec  lea     r9, [r13+8]
0x1800b6cf0  mov     edx, 69h ; 'i'
0x1800b6cf5  mov     [rsp+498h+var_478], eax
0x1800b6cf9  lea     r12, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids
0x1800b6d00  mov     r8, r12
0x1800b6d03  mov     rcx, [rcx+10h]
0x1800b6d07  call    WPP_SF__guid_D
0x1800b6d0c  jmp     short loc_1800B6D15
0x1800b6d0e  lea     r12, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids
0x1800b6d15  mov     byte ptr [rsi+489h], 1
0x1800b6d1c  jmp     short loc_1800B6D2C
0x1800b6d1e  lea     r14, WPP_GLOBAL_Control
0x1800b6d25  lea     r12, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids
0x1800b6d2c  test    [r13+22h], r15w
0x1800b6d31  jz      loc_1800B6DBD
0x1800b6d37  mov     edx, [rsp+498h+var_400]
0x1800b6d3e  mov     rcx, [rsi+490h]
0x1800b6d45  call    FveDatasetEraseDigestDatumsOfVmkInfo
0x1800b6d4a  mov     ecx, eax; int
0x1800b6d4c  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6d51  mov     ebx, eax
0x1800b6d53  mov     [rsp+498h+var_424], eax
0x1800b6d57  test    eax, eax
0x1800b6d59  jns     short loc_1800B6DBD
0x1800b6d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6d62  cmp     rcx, r14
0x1800b6d65  jz      short loc_1800B6D81
0x1800b6d67  test    byte ptr [rcx+1Ch], 2
0x1800b6d6b  jz      short loc_1800B6D81
0x1800b6d6d  mov     edx, 6Ah ; 'j'
0x1800b6d72  mov     r9d, eax
0x1800b6d75  mov     r8, r12
0x1800b6d78  mov     rcx, [rcx+10h]
0x1800b6d7c  call    WPP_SF_d
0x1800b6d81  lea     rdi, aFvedataseteras_0; "FveDatasetEraseDigestDatumsOfVmkInfo"
0x1800b6d88  mov     [rsp+498h+var_408], rdi
0x1800b6d90  mov     rcx, [rsp+498h]; this
0x1800b6d98  lea     rax, aFvedataseteras_2; "FveDatasetEraseDigestDatumsOfVmkInfo"
0x1800b6d9f  mov     qword ptr [rsp+498h+var_478], rax; int
0x1800b6da4  mov     r9d, ebx; char *
0x1800b6da7  lea     r8, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800b6dae  mov     edx, 1515h; void *
0x1800b6db3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b6db8  jmp     loc_1800B6BB5
0x1800b6dbd  mov     edx, [rsp+498h+var_400]
0x1800b6dc4  mov     rcx, [rsi+490h]
0x1800b6dcb  call    FveDatasetEraseDatum
0x1800b6dd0  mov     ecx, eax; int
0x1800b6dd2  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6dd7  mov     ebx, eax
0x1800b6dd9  mov     [rsp+498h+var_424], eax
0x1800b6ddd  xor     r10d, r10d
0x1800b6de0  test    eax, eax
0x1800b6de2  jns     short loc_1800B6DF0
0x1800b6de4  lea     rdi, aFvedataseteras_4; "FveDatasetEraseDatum"
0x1800b6deb  jmp     loc_1800B6A8F
0x1800b6df0  mov     eax, 0FF00h
0x1800b6df5  test    [r13+22h], ax
0x1800b6dfa  jnz     loc_1800B6EF2
0x1800b6e00  mov     rcx, rsi; this
0x1800b6e03  call    ?OkToEnableSecurityPerPolicy@CFveApiBase@@QEAAJXZ; CFveApiBase::OkToEnableSecurityPerPolicy(void)
0x1800b6e08  mov     ebx, eax
0x1800b6e0a  mov     [rsp+498h+var_424], eax
0x1800b6e0e  xor     r10d, r10d
0x1800b6e11  test    eax, eax
0x1800b6e13  jns     short loc_1800B6E21
0x1800b6e15  lea     rdi, aOktoenablesecu; "OkToEnableSecurityPerPolicy"
0x1800b6e1c  jmp     loc_1800B6A8F
0x1800b6e21  mov     edx, 0FFFFh
0x1800b6e26  mov     r8d, 24h ; '$'
0x1800b6e2c  lea     r9, [rsp+498h+var_418]
0x1800b6e34  mov     rcx, r13
0x1800b6e37  call    FveDatumNestedExtractFirst
0x1800b6e3c  mov     ecx, eax; int
0x1800b6e3e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6e43  mov     ebx, eax
0x1800b6e45  mov     [rsp+498h+var_424], eax
0x1800b6e49  xor     r15d, r15d
0x1800b6e4c  test    eax, eax
0x1800b6e4e  jns     short loc_1800B6E6A
0x1800b6e50  mov     ecx, 0C0000225h; int
0x1800b6e55  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800b6e5a  cmp     ebx, eax
0x1800b6e5c  jz      short loc_1800B6E6A
0x1800b6e5e  lea     rdi, aClearkeyadditi; "ClearKeyAdditionalInfoDatum"
0x1800b6e65  jmp     loc_1800B6C08
0x1800b6e6a  mov     [rsp+498h+var_424], r15d
0x1800b6e6f  mov     rax, [rsp+498h+var_418]
0x1800b6e77  test    rax, rax
0x1800b6e7a  jz      short loc_1800B6EA4
0x1800b6e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6e83  cmp     rcx, r14
0x1800b6e86  jz      short loc_1800B6EA4
  ... truncated ...
```
