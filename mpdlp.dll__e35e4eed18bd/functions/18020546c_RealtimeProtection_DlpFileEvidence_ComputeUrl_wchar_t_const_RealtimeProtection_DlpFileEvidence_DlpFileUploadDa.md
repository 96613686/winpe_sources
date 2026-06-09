# RealtimeProtection::DlpFileEvidence::ComputeUrl(wchar_t const *,RealtimeProtection::DlpFileEvidence::DlpFileUploadData &,wchar_t * *,bool *)

- ea: `0x18020546c`
- end: `0x180207273`
- name: `?ComputeUrl@DlpFileEvidence@RealtimeProtection@@YAJPEB_WAEAUDlpFileUploadData@12@PEAPEA_WPEA_N@Z`
- size: `7687`
- prototype: `int(RealtimeProtection::DlpFileEvidence *__hidden this, const wchar_t *, struct RealtimeProtection::DlpFileEvidence::DlpFileUploadData *, wchar_t **, bool *)`
- caller_count: `2`
- callee_count: `54`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801a1e04`
- `0x180207864`

## callees

- `0x180005c28`
- `0x18000a010`
- `0x18000acb0`
- `0x18000b584`
- `0x180024ac0`
- `0x180028a10`
- `0x180028d80`
- `0x18002c150`
- `0x180034420`
- `0x1800374f8`
- `0x180037afc`
- `0x180038450`
- `0x180046d10`
- `0x18004b3bc`
- `0x180079dc0`
- `0x180080030`
- `0x1800809d0`
- `0x1800839a0`
- `0x180089510`
- `0x1800943dc`
- `0x18009f730`
- `0x1800b1ee8`
- `0x1800b3710`
- `0x1800b7f88`
- `0x1800b8fcc`
- `0x180100b10`
- `0x180104f64`
- `0x180105f50`
- `0x180106620`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18014da1c`
- `0x18014e31c`
- `0x18014f16c`
- `0x18014f210`
- `0x180204af0`
- `0x180204e3c`
- `0x1802050d8`
- `0x1802051d4`
- `0x180205210`
- `0x18020546c`
- `0x18020749c`
- `0x180207cbc`
- `0x180208134`
- `0x180208de4`
- `0x18020b8d8`
- `0x18022bec0`
- `0x18022d2f0`
- `0x18022d504`
- `0x18022d814`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x180205724`
- `KERNEL32!GetFileAttributesExW` at `0x18020578c`
- `KERNEL32!GetFileAttributesExW` at `0x180205724`
- `KERNEL32!GetFileAttributesExW` at `0x18020578c`
- `KERNEL32!CloseHandle` at `0x1802056cc`
- `KERNEL32!CloseHandle` at `0x180205812`
- `KERNEL32!CloseHandle` at `0x18020589e`
- `KERNEL32!CloseHandle` at `0x180206212`
- `KERNEL32!CloseHandle` at `0x180206458`
- `KERNEL32!CloseHandle` at `0x180206963`
- `KERNEL32!CloseHandle` at `0x180206b91`
- `KERNEL32!CloseHandle` at `0x18020723a`
- `KERNEL32!CloseHandle` at `0x1802056cc`
- `KERNEL32!CloseHandle` at `0x180205812`
- `KERNEL32!CloseHandle` at `0x18020589e`
- `KERNEL32!CloseHandle` at `0x180206212`
- `KERNEL32!CloseHandle` at `0x180206458`
- `KERNEL32!CloseHandle` at `0x180206963`
- `KERNEL32!CloseHandle` at `0x180206b91`
- `KERNEL32!CloseHandle` at `0x18020723a`
- `ADVAPI32!RevertToSelf` at `0x1802057b5`
- `ADVAPI32!RevertToSelf` at `0x1802063ec`
- `ADVAPI32!RevertToSelf` at `0x1802057b5`
- `ADVAPI32!RevertToSelf` at `0x1802063ec`

## string_xrefs

- `0x180205bf1`: `Evidence directory size exceeded`
- `0x180205520`: `Evidence directory does not exist`
- `0x1802057d6`: `RealtimeProtection::DlpFileEvidence::ComputeUrl`
- `0x18020653e`: `RealtimeProtection::DlpFileEvidence::ComputeUrl`
- `0x180206afe`: `RealtimeProtection::DlpFileEvidence::ComputeUrl`
- `0x180206c6a`: `RealtimeProtection::DlpFileEvidence::ComputeUrl`
- `0x1802057dd`: `DLP::%hs: GetFileAttributesExW failed for file even with impersonation %ls hr=%#lx`
- `0x1802068be`: `User has no access to storage container`
- `0x180206b05`: `DLP::%hs file already exists on storage %s hash %s`
- `0x180206545`: `DLP::%hs file %ls already exists on storage hash value %ls`
- `0x180205f24`: `Copy To Evidence folder failed error_`
- `0x180205f97`: `CopyFailure`
- `0x180206fba`: `ComputeUrl Exception thrown error_`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpFileEvidence::ComputeUrl(
        RealtimeProtection::DlpFileEvidence *this,
        const wchar_t *a2,
        struct RealtimeProtection::DlpFileEvidence::DlpFileUploadData *a3,
        wchar_t **a4)
{
  unsigned int v7; // r15d
  void *v8; // rdi
  int Value; // eax
  void **v11; // rdx
  int v12; // r14d
  const wchar_t *v13; // rax
  int LastLogonImpersonationToken; // eax
  unsigned int v15; // r14d
  const WCHAR **v16; // r14
  const WCHAR *v17; // rcx
  int LastFailure; // eax
  HANDLE v19; // rbx
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rax
  const wchar_t *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rax
  const struct _FILETIME *v25; // rdx
  _QWORD *v26; // rsi
  unsigned __int64 v27; // rax
  __int64 v28; // rax
  const struct _FILETIME *v29; // rdx
  const wchar_t *v30; // r8
  void *v31; // rsi
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  const wchar_t *v35; // rdx
  CommonUtil *v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  const struct CommonUtil::EvidenceFileDetails *v38; // rdx
  const WCHAR *v39; // rcx
  signed int v40; // eax
  __int64 v41; // r8
  LPCWSTR *v42; // r9
  int v43; // r9d
  const wchar_t *v44; // rax
  LPCWSTR *v45; // r9
  int v46; // eax
  const wchar_t *v47; // rcx
  unsigned int v48; // r14d
  const struct std::nothrow_t *v49; // rdx
  int v50; // r9d
  void *v51; // rdi
  const wchar_t *v52; // r13
  char *v53; // rcx
  unsigned int v54; // esi
  __int64 v55; // rax
  int FileHashUsingEA; // esi
  __int64 v57; // rax
  int v58; // esi
  const wchar_t *v59; // rsi
  int FileHashUsingHashLib; // eax
  unsigned int v61; // r14d
  const struct std::nothrow_t *v62; // rdx
  std::_Ref_count_base *v63; // r12
  const wchar_t *v64; // r8
  char v65; // si
  const wchar_t *v66; // r9
  const wchar_t *v67; // rsi
  const wchar_t *v68; // r8
  int v69; // r9d
  const wchar_t *v70; // r13
  char v71; // r14
  bool v72; // r8
  void *v73; // rsi
  const wchar_t *v74; // r14
  const wchar_t *v75; // rcx
  const struct std::nothrow_t *v76; // rdx
  const wchar_t *v77; // rdx
  const wchar_t *v78; // r9
  const wchar_t *v79; // rcx
  const struct std::nothrow_t *v80; // rdx
  char v81; // al
  const wchar_t *v82; // r8
  const wchar_t *v83; // r13
  const wchar_t *v84; // r8
  const struct std::nothrow_t *v85; // rdx
  const wchar_t *v86; // rcx
  const wchar_t *v87; // rcx
  int v88; // r9d
  const wchar_t *v89; // r13
  const wchar_t *v90; // r9
  const wchar_t *v91; // rcx
  const struct std::nothrow_t *v92; // rdx
  int v93; // r9d
  void *v94; // rdi
  const wchar_t *v95; // r13
  int MicrosoftStorageStatus; // [rsp+B0h] [rbp-208h] BYREF
  int v97; // [rsp+B4h] [rbp-204h] BYREF
  int v98; // [rsp+B8h] [rbp-200h] BYREF
  int v99; // [rsp+BCh] [rbp-1FCh] BYREF
  int v100; // [rsp+C0h] [rbp-1F8h] BYREF
  int v101; // [rsp+C4h] [rbp-1F4h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-1F0h] BYREF
  __int64 v103; // [rsp+D0h] [rbp-1E8h] BYREF
  __int64 v104; // [rsp+D8h] [rbp-1E0h] BYREF
  __int64 v105; // [rsp+E0h] [rbp-1D8h] BYREF
  __int64 v106; // [rsp+E8h] [rbp-1D0h] BYREF
  CommonUtil *v107; // [rsp+F0h] [rbp-1C8h]
  __int64 v108; // [rsp+F8h] [rbp-1C0h] BYREF
  __int64 v109; // [rsp+100h] [rbp-1B8h] BYREF
  __int64 v110; // [rsp+108h] [rbp-1B0h] BYREF
  __int64 v111; // [rsp+110h] [rbp-1A8h] BYREF
  const wchar_t *v112; // [rsp+118h] [rbp-1A0h]
  __int64 v113; // [rsp+120h] [rbp-198h] BYREF
  __int64 v114; // [rsp+128h] [rbp-190h] BYREF
  __int64 v115; // [rsp+130h] [rbp-188h] BYREF
  __int64 v116; // [rsp+138h] [rbp-180h] BYREF
  wchar_t **v117; // [rsp+140h] [rbp-178h]
  __int64 v118[3]; // [rsp+148h] [rbp-170h] BYREF
  char v119; // [rsp+160h] [rbp-158h] BYREF
  void *v120; // [rsp+168h] [rbp-150h] BYREF
  void *v121; // [rsp+170h] [rbp-148h] BYREF
  __int128 Src; // [rsp+178h] [rbp-140h] BYREF
  __m128i si128; // [rsp+188h] [rbp-130h]
  std::_Ref_count_base *v124[2]; // [rsp+198h] [rbp-120h] BYREF
  HANDLE hObject; // [rsp+1A8h] [rbp-110h] BYREF
  wchar_t *v126[3]; // [rsp+1B0h] [rbp-108h] BYREF
  unsigned __int64 v127; // [rsp+1C8h] [rbp-F0h]
  LPCWSTR lpFileName[2]; // [rsp+1D0h] [rbp-E8h] BYREF
  __int128 v129; // [rsp+1E0h] [rbp-D8h]
  unsigned __int64 v130; // [rsp+1F0h] [rbp-C8h]
  __int64 v131; // [rsp+1F8h] [rbp-C0h]
  __int64 v132[2]; // [rsp+200h] [rbp-B8h] BYREF
  void *v133; // [rsp+220h] [rbp-98h] BYREF
  __int64 v134[2]; // [rsp+228h] [rbp-90h] BYREF
  __int128 FileInformation; // [rsp+248h] [rbp-70h] BYREF
  __int128 v136; // [rsp+258h] [rbp-60h] BYREF
  unsigned int v137; // [rsp+268h] [rbp-50h]

  v117 = a4;
  v107 = a3;
  v112 = a2;
  v103 = (__int64)this;
  v110 = (__int64)a2;
  v118[1] = (__int64)a2;
  v111 = (__int64)a3;
  v134[0] = (__int64)a4;
  v7 = 0;
  *(_QWORD *)a3 = 0;
  *(_BYTE *)a4 = 0;
  v8 = 0;
  v121 = 0;
  if ( !this )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids);
    CommonUtil::NewSprintfW(a3, (wchar_t **)L"%ls", L"Evidence directory does not exist");
    return 0;
  }
  Value = Dlp::FeatureControl::GetValue(189);
  v12 = Value;
  if ( *(_BYTE *)a2 && (unsigned int)(Value - 1) <= 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids);
    MicrosoftStorageStatus = 1;
    *(_OWORD *)v124 = 0;
    std::atomic_load<RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload>(v124);
    if ( v124[0] )
      MicrosoftStorageStatus = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::GetMicrosoftStorageStatus();
    if ( v124[1] )
      std::_Ref_count_base::_Decref(v124[1]);
    if ( MicrosoftStorageStatus == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
          v12 == 1,
          v12 == 2);
      if ( v12 == 1 )
      {
        v13 = (const wchar_t *)&qword_1803121E8;
        if ( (unsigned __int64)qword_180312200 > 7 )
          v13 = qword_1803121E8;
      }
      else
      {
        v13 = (const wchar_t *)&qword_180312208;
        if ( (unsigned __int64)qword_180312220 > 7 )
          v13 = (const wchar_t *)qword_180312208;
      }
      CommonUtil::NewSprintfW(a3, (wchar_t **)L"%ls", v13);
      return v7;
    }
  }
  hObject = 0;
  LastLogonImpersonationToken = RealtimeProtection::DlpUtils::GetLastLogonImpersonationToken(
                                  (RealtimeProtection::DlpUtils *)&hObject,
                                  v11);
  v15 = LastLogonImpersonationToken;
  if ( LastLogonImpersonationToken < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
        (unsigned int)LastLogonImpersonationToken);
    if ( hObject )
      CloseHandle(hObject);
    return v15;
  }
  FileInformation = 0;
  v136 = 0;
  v137 = 0;
  v16 = (const WCHAR **)(a2 + 176);
  v109 = (__int64)(a2 + 176);
  v124[0] = (std::_Ref_count_base *)(a2 + 176);
  v17 = a2 + 176;
  if ( *((_QWORD *)a2 + 47) > 7u )
    v17 = *v16;
  if ( GetFileAttributesExW(v17, GetFileExInfoStandard, &FileInformation) )
  {
    v19 = hObject;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    MicrosoftStorageStatus = LastFailure;
    v19 = hObject;
    if ( LastFailure == -2147024891 )
    {
      if ( !hObject )
      {
LABEL_46:
        if ( *((_QWORD *)a2 + 47) > 7u )
          v16 = (const WCHAR **)*v16;
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs: GetFileAttributesExW failed for file even with impersonation %ls hr=%#lx",
          "RealtimeProtection::DlpFileEvidence::ComputeUrl",
          v16,
          (unsigned int)LastFailure);
        CommonUtil::NewSprintfW(
          a3,
          (wchar_t **)L"%ls%#lx",
          L"Failed to get file attributes error_",
          (unsigned int)MicrosoftStorageStatus);
        if ( v19 )
          CloseHandle(v19);
        return (unsigned int)MicrosoftStorageStatus;
      }
      MicrosoftStorageStatus = 0;
      *(_OWORD *)v132 = 0;
      CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)v132, hObject);
      v20 = a2 + 176;
      if ( *((_QWORD *)a2 + 47) > 7u )
        v20 = *v16;
      if ( GetFileAttributesExW(v20, GetFileExInfoStandard, &FileInformation) )
      {
        LastFailure = MicrosoftStorageStatus;
      }
      else
      {
        LastFailure = HrGetLastFailure();
        MicrosoftStorageStatus = LastFailure;
      }
      if ( LOBYTE(v132[1]) )
      {
        RevertToSelf();
        LastFailure = MicrosoftStorageStatus;
      }
    }
    if ( LastFailure < 0 )
      goto LABEL_46;
  }
  v120 = (void *)__PAIR64__(HIDWORD(v136), v137);
  v21 = __PAIR64__(HIDWORD(v136), v137);
  *((_QWORD *)a2 + 1) = __PAIR64__(HIDWORD(v136), v137);
  if ( v21 > 0x1F400000 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids);
    CommonUtil::NewSprintfW(a3, (wchar_t **)L"%ls", L"File size greater than 500MB");
    if ( v19 )
      CloseHandle(v19);
    return v7;
  }
  v133 = 0;
  v22 = a2 + 176;
  if ( *(_BYTE *)v112 )
  {
    v23 = std::filesystem::path::filename(v22, v126);
    v24 = (_QWORD *)std::filesystem::path::operator std::wstring(v23, &Src);
    v26 = v24;
    if ( v24[3] > 7u )
      v26 = (_QWORD *)*v24;
    v27 = CommonUtil::UtilFileTimeToUlong64((CommonUtil *)((char *)&v136 + 4), v25);
    MicrosoftStorageStatus = CommonUtil::NewSprintfW(
                               (CommonUtil *)&v133,
                               (wchar_t **)L"%ls_%d_%llu_%ls",
                               L"MicrosoftManaged",
                               *((unsigned int *)a2 + 1),
                               v27,
                               v26);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
  }
  else
  {
    v28 = std::filesystem::path::filename(v22, v126);
    std::filesystem::path::operator std::wstring(v28, &Src);
    CommonUtil::UtilFileTimeToUlong64((CommonUtil *)((char *)&v136 + 4), v29);
    v30 = a2 + 64;
    if ( *((_QWORD *)a2 + 19) > 7u )
      v30 = *(const wchar_t **)v30;
    MicrosoftStorageStatus = CommonUtil::NewSprintfW((CommonUtil *)&v133, (wchar_t **)L"%ls_%ls_%d_%llu_%ls", v30);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v126);
  v31 = v133;
  v120 = (void *)std::wstring::wstring(lpFileName, v133);
  v32 = std::wstring::wstring(v132, v103);
  v33 = std::operator+<wchar_t>(v126, v32, L"\\");
  v34 = std::operator+<wchar_t>(&Src, v33, v120);
  std::wstring::operator=(a2 + 48, v34);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v126);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v132);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
  v36 = (CommonUtil *)(a2 + 48);
  if ( *((_QWORD *)a2 + 15) > 7u )
    v36 = (CommonUtil *)*((_QWORD *)a2 + 12);
  if ( (unsigned int)CommonUtil::UtilIsFileExists(v36, v35) == -2147024894 )
  {
    Src = 0;
    si128 = 0u;
    v120 = 0;
    anonymous_namespace_::GetEvidenceDirItems(v103, &v120, &Src);
    if ( (unsigned __int64)v120 >= 0x1F400000 )
    {
      v38 = (const struct CommonUtil::EvidenceFileDetails *)Src;
      if ( (_QWORD)Src != *((_QWORD *)&Src + 1) )
      {
        v120 = 0;
        while ( 1 )
        {
          CommonUtil::EvidenceFileDetails::EvidenceFileDetails((CommonUtil::EvidenceFileDetails *)lpFileName, v38);
          v39 = (const WCHAR *)&lpFileName[1];
          if ( v130 > 7 )
            v39 = lpFileName[1];
          v40 = UtilDeleteFile(v39);
          if ( v40 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v45 = &lpFileName[1];
              if ( v130 > 7 )
                LODWORD(v45) = lpFileName[1];
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                (unsigned int)&WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
                (_DWORD)v45,
                v40);
            }
          }
          else
          {
            v120 = (char *)v120 + v131;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v42 = &lpFileName[1];
              if ( v130 > 7 )
                LODWORD(v42) = lpFileName[1];
              WPP_SF_SI(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                (unsigned int)&WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
                (_DWORD)v42,
                v131);
            }
            if ( g_pcsAsimovLock )
            {
              CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
              if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
                && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
              {
                v118[0] = (__int64)L"Evidence directory size exceeded";
                v113 = v131;
                v44 = a2 + 144;
                if ( *((_QWORD *)a2 + 39) > 7u )
                  v44 = *(const wchar_t **)v44;
                v116 = (__int64)v44;
                MicrosoftStorageStatus = *((_DWORD *)g_aAsimov + 18);
                v97 = *((_DWORD *)g_aAsimov + 17);
                v98 = *((_DWORD *)g_aAsimov + 16);
                v99 = *((unsigned __int8 *)g_aAsimov + 60);
                v100 = *((unsigned __int8 *)g_aAsimov + 59);
                v101 = *((unsigned __int8 *)g_aAsimov + 58);
                LODWORD(v102) = *((unsigned __int8 *)g_aAsimov + 57);
                LODWORD(v103) = *((unsigned __int8 *)g_aAsimov + 56);
                v115 = *((_QWORD *)g_aAsimov + 6);
                v114 = *((_QWORD *)g_aAsimov + 5);
                v108 = *((_QWORD *)g_aAsimov + 4);
                v104 = *((_QWORD *)g_aAsimov + 3);
                v105 = *((_QWORD *)g_aAsimov + 2);
                v106 = *((_QWORD *)g_aAsimov + 1);
                v132[0] = 0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
                  v43,
                  (int)&dword_1802C7494,
                  (__int64)v132,
                  (__int64)&v106,
                  (__int64)&v105,
                  (__int64)&v104,
                  (__int64)&v108,
                  (__int64)&v114,
                  (__int64)&v115,
                  (__int64)&v103,
                  (__int64)&v102,
                  (__int64)&v101,
                  (__int64)&v100,
                  (__int64)&v99,
                  (__int64)&v98,
                  (__int64)&v97,
                  (__int64)&MicrosoftStorageStatus,
                  (__int64)&v116,
                  (__int64)&v113,
                  (__int64)v118);
              }
              CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
            }
          }
          LOBYTE(v41) = si128.m128i_i8[8];
          std::_Pop_heap_unchecked<CommonUtil::EvidenceFileDetails *,CommonUtil::compareTime>(
            Src,
            *((_QWORD *)&Src + 1),
            v41);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(*((_QWORD *)&Src + 1) - 40LL));
          *((_QWORD *)&Src + 1) -= 48LL;
          if ( (_QWORD)Src == *((_QWORD *)&Src + 1) || (unsigned __int64)v120 >= *((_QWORD *)a2 + 1) )
            break;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&lpFileName[1]);
          v38 = (const struct CommonUtil::EvidenceFileDetails *)Src;
        }
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&lpFileName[1]);
      }
    }
    v46 = anonymous_namespace_::CopyEvidenceFileWithRetry(a2, v19);
    MicrosoftStorageStatus = v46;
    if ( v46 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v47 = a2 + 48;
        if ( *((_QWORD *)a2 + 15) > 7u )
          v47 = *(const wchar_t **)v47;
        WPP_SF_SSL(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v47, v46);
      }
      v48 = MicrosoftStorageStatus;
      CommonUtil::NewSprintfW(
        (CommonUtil *)&v121,
        (wchar_t **)L"%ls%#lx",
        L"Copy To Evidence folder failed error_",
        (unsigned int)MicrosoftStorageStatus);
      v49 = (const struct std::nothrow_t *)g_pcsAsimovLock;
      if ( g_pcsAsimovLock )
      {
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
        if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
        {
          v51 = v121;
          v132[0] = (__int64)v121;
          v106 = (__int64)L"CopyFailure";
          v52 = a2 + 144;
          if ( *((_QWORD *)v52 + 3) > 7u )
            v52 = *(const wchar_t **)v52;
          v105 = (__int64)v52;
          LODWORD(v103) = *((_DWORD *)g_aAsimov + 18);
          LODWORD(v102) = *((_DWORD *)g_aAsimov + 17);
          v101 = *((_DWORD *)g_aAsimov + 16);
          v100 = *((unsigned __int8 *)g_aAsimov + 60);
          v99 = *((unsigned __int8 *)g_aAsimov + 59);
          v98 = *((unsigned __int8 *)g_aAsimov + 58);
          v97 = *((unsigned __int8 *)g_aAsimov + 57);
          MicrosoftStorageStatus = *((unsigned __int8 *)g_aAsimov + 56);
          v104 = *((_QWORD *)g_aAsimov + 6);
          v108 = *((_QWORD *)g_aAsimov + 5);
          v114 = *((_QWORD *)g_aAsimov + 4);
          v115 = *((_QWORD *)g_aAsimov + 3);
          v116 = *((_QWORD *)g_aAsimov + 2);
          v113 = *((_QWORD *)g_aAsimov + 1);
          v118[0] = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            v50,
            (int)&word_1802C7382,
            (__int64)v118,
            (__int64)&v113,
            (__int64)&v116,
            (__int64)&v115,
            (__int64)&v114,
            (__int64)&v108,
            (__int64)&v104,
            (__int64)&MicrosoftStorageStatus,
            (__int64)&v97,
            (__int64)&v98,
            (__int64)&v99,
            (__int64)&v100,
            (__int64)&v101,
            (__int64)&v102,
            (__int64)&v103,
            (__int64)&v105,
            (__int64)&v106,
            (__int64)v132);
        }
        else
        {
          v51 = v121;
        }
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
      }
      else
      {
        v51 = v121;
      }
      if ( (_QWORD)Src )
      {
        std::_Destroy_range<std::allocator<CommonUtil::EvidenceFileDetails>>(Src, *((_QWORD *)&Src + 1));
        std::_Deallocate<16>(Src, 16 * ((__int64)(si128.m128i_i64[0] - Src) >> 4));
        Src = 0;
        si128.m128i_i64[0] = 0;
      }
      if ( v31 )
        operator delete(v31, v49);
      if ( v19 )
        CloseHandle(v19);
      if ( v51 )
        operator delete(v51, v49);
      return v48;
    }
    v53 = (char *)Src;
    v120 = (void *)Src;
    if ( (_QWORD)Src )
    {
      v132[0] = *((_QWORD *)&Src + 1);
      if ( (_QWORD)Src != *((_QWORD *)&Src + 1) )
      {
        do
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v53 + 8);
          v53 = (char *)v120 + 48;
          v120 = v53;
        }
        while ( v53 != (char *)v132[0] );
        v53 = (char *)Src;
      }
      std::_Deallocate<16>(v53, 16 * ((si128.m128i_i64[0] - (__int64)v53) >> 4));
    }
  }
  if ( v31 )
    operator delete(v31, v37);
  v54 = MicrosoftStorageStatus;
  if ( MicrosoftStorageStatus >= 0 )
  {
    Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    v55 = std::filesystem::path::operator std::wstring(v16, lpFileName);
    FileHashUsingEA = Dlp::Utils::GetFileHashUsingEA(v55, &Src);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
    if ( FileHashUsingEA < 0 )
    {
      if ( FileHashUsingEA != -2147024891 || !v19 )
        goto LABEL_134;
      *(_OWORD *)v134 = 0;
      CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)v134, v19);
      v57 = std::filesystem::path::operator std::wstring(v124[0], lpFileName);
      v58 = Dlp::Utils::GetFileHashUsingEA(v57, &Src);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
      if ( LOBYTE(v134[1]) )
        RevertToSelf();
      if ( v58 < 0 )
      {
LABEL_134:
        v59 = a2 + 48;
        FileHashUsingHashLib = Dlp::Utils::GetFileHashUsingHashLib(a2 + 48, &Src);
        v61 = FileHashUsingHashLib;
        if ( FileHashUsingHashLib < 0 )
        {
          CommonUtil::NewSprintfW(
            v107,
            (wchar_t **)L"%ls%#lx",
            L"Unable to Obtain hash of the evidence file Error_",
            (unsigned int)FileHashUsingHashLib);
          if ( *((_QWORD *)a2 + 15) > 7u )
            v59 = *(const wchar_t **)v59;
          UtilDeleteFile(v59);
          goto LABEL_138;
        }
      }
    }
    v63 = (std::_Ref_count_base *)(a2 + 16);
    std::wstring::operator=((void *)(a2 + 16), &Src);
    if ( *(_BYTE *)v112 )
    {
      v64 = a2 + 16;
      if ( *((_QWORD *)a2 + 7) > 7u )
        v64 = *(const wchar_t **)v63;
      CommonUtil::NewSprintfW(v107, (wchar_t **)L"%ls", v64);
      *(_OWORD *)v124 = 0;
      std::atomic_load<RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload>(v124);
      if ( v124[0] )
      {
        v65 = *(_BYTE *)(RealtimeProtection::DlpLRUCache<std::wstring,unsigned __int64>::get(
                           (char *)v124[0] + 88,
                           v126,
                           &Src)
                       + 8);
        if ( v124[1] )
          std::_Ref_count_base::_Decref(v124[1]);
        if ( v65 )
        {
          v66 = a2 + 16;
          if ( *((_QWORD *)a2 + 7) > 7u )
            v66 = *(const wchar_t **)v63;
          v67 = a2 + 48;
          v68 = a2 + 48;
          if ( *((_QWORD *)a2 + 15) > 7u )
            v68 = *(const wchar_t **)v67;
          RealtimeProtection::MpLogMessageImpl(
            (RealtimeProtection *)L"DLP::%hs file %ls already exists on storage hash value %ls",
            "RealtimeProtection::DlpFileEvidence::ComputeUrl",
            v68,
            v66);
          if ( *((_QWORD *)a2 + 15) > 7u )
            v67 = *(const wchar_t **)v67;
          UtilDeleteFile(v67);
          if ( g_pcsAsimovLock )
          {
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
            if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
              && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
            {
              if ( *((_QWORD *)a2 + 7) > 7u )
                v63 = *(std::_Ref_count_base **)v63;
              v124[0] = v63;
              v70 = a2 + 144;
              if ( *((_QWORD *)v70 + 3) > 7u )
                v70 = *(const wchar_t **)v70;
              v134[0] = (__int64)v70;
              LODWORD(v103) = *((_DWORD *)g_aAsimov + 18);
              LODWORD(v102) = *((_DWORD *)g_aAsimov + 17);
              v101 = *((_DWORD *)g_aAsimov + 16);
              v100 = *((unsigned __int8 *)g_aAsimov + 60);
              v99 = *((unsigned __int8 *)g_aAsimov + 59);
              v98 = *((unsigned __int8 *)g_aAsimov + 58);
              v97 = *((unsigned __int8 *)g_aAsimov + 57);
              MicrosoftStorageStatus = *((unsigned __int8 *)g_aAsimov + 56);
              v111 = *((_QWORD *)g_aAsimov + 6);
              v110 = *((_QWORD *)g_aAsimov + 5);
              v109 = *((_QWORD *)g_aAsimov + 4);
              v132[0] = *((_QWORD *)g_aAsimov + 3);
              v106 = *((_QWORD *)g_aAsimov + 2);
              v105 = *((_QWORD *)g_aAsimov + 1);
              v104 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
                v69,
                (int)&byte_1802C76B9,
                (__int64)&v104,
                (__int64)&v105,
                (__int64)&v106,
                (__int64)v132,
                (__int64)&v109,
                (__int64)&v110,
                (__int64)&v111,
                (__int64)&MicrosoftStorageStatus,
                (__int64)&v97,
                (__int64)&v98,
                (__int64)&v99,
                (__int64)&v100,
                (__int64)&v101,
                (__int64)&v102,
                (__int64)&v103,
                (__int64)v134,
                (__int64)v124);
            }
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
          }
          goto LABEL_213;
        }
        v71 = 1;
      }
      else
      {
        v71 = 0;
        if ( v124[1] )
          std::_Ref_count_base::_Decref(v124[1]);
      }
      *(_BYTE *)v117 = v71;
LABEL_213:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
      if ( v19 )
        CloseHandle(v19);
      return 0;
    }
    v61 = g_pfnRoInitialize(1);
    if ( (v61 & 0x80000000) != 0 )
    {
      v119 = 0;
      if ( v61 != -2147417850 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids, v61);
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs g_pfnRoInitialize failed with hr=%#lx",
          "RealtimeProtection::DlpFileEvidence::ComputeUrl",
          v61);
        v87 = a2 + 48;
        if ( *((_QWORD *)a2 + 15) > 7u )
          v87 = *(const wchar_t **)v87;
        UtilDeleteFile(v87);
        CommonUtil::NewSprintfW(
          (CommonUtil *)&v121,
          (wchar_t **)L"%ls%#lx",
          L"Customer Managed:RoInitialize Failed with error_",
          v61);
        if ( g_pcsAsimovLock )
        {
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
          if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
            && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
          {
            v8 = v121;
            v124[0] = (std::_Ref_count_base *)v121;
            if ( *((_QWORD *)a2 + 7) > 7u )
              v63 = *(std::_Ref_count_base **)v63;
            v134[0] = (__int64)v63;
            v89 = a2 + 144;
            if ( *((_QWORD *)v89 + 3) > 7u )
              v89 = *(const wchar_t **)v89;
            v111 = (__int64)v89;
            LODWORD(v103) = *((_DWORD *)g_aAsimov + 18);
            LODWORD(v102) = *((_DWORD *)g_aAsimov + 17);
            v101 = *((_DWORD *)g_aAsimov + 16);
            v100 = *((unsigned __int8 *)g_aAsimov + 60);
            v99 = *((unsigned __int8 *)g_aAsimov + 59);
            v98 = *((unsigned __int8 *)g_aAsimov + 58);
            v97 = *((unsigned __int8 *)g_aAsimov + 57);
            MicrosoftStorageStatus = *((unsigned __int8 *)g_aAsimov + 56);
            v110 = *((_QWORD *)g_aAsimov + 6);
            v109 = *((_QWORD *)g_aAsimov + 5);
            v132[0] = *((_QWORD *)g_aAsimov + 4);
            v106 = *((_QWORD *)g_aAsimov + 3);
            v105 = *((_QWORD *)g_aAsimov + 2);
            v104 = *((_QWORD *)g_aAsimov + 1);
            v108 = 0x2000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
              v88,
              (int)&byte_1802C75A7,
              (__int64)&v108,
              (__int64)&v104,
              (__int64)&v105,
              (__int64)&v106,
              (__int64)v132,
              (__int64)&v109,
              (__int64)&v110,
              (__int64)&MicrosoftStorageStatus,
              (__int64)&v97,
              (__int64)&v98,
              (__int64)&v99,
              (__int64)&v100,
              (__int64)&v101,
              (__int64)&v102,
              (__int64)&v103,
              (__int64)&v111,
              (__int64)v134,
              (__int64)v124);
          }
          else
          {
            v8 = v121;
          }
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
        }
        else
        {
          v8 = v121;
        }
        goto LABEL_138;
      }
    }
    else
    {
      v119 = 1;
    }
    LOBYTE(v124[0]) = 0;
    v124[1] = (std::_Ref_count_base *)&v119;
    if ( !*(_BYTE *)v112 )
    {
      v120 = 0;
      MicrosoftStorageStatus = CommonUtil::GetAzureStorageTokenWrapper((CommonUtil *)&v120, 0, v72);
      v73 = v120;
      if ( MicrosoftStorageStatus < 0 || !v120 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids);
        v61 = MicrosoftStorageStatus;
        CommonUtil::NewSprintfW(
          v107,
          (wchar_t **)L"%ls%#lx",
          L"Authorization failed Error_",
          (unsigned int)MicrosoftStorageStatus);
        v86 = a2 + 48;
        if ( *((_QWORD *)a2 + 15) > 7u )
          v86 = *(const wchar_t **)v86;
        UtilDeleteFile(v86);
        if ( !v73 )
          goto LABEL_222;
        goto LABEL_221;
      }
      std::wstring::assign((void *)(a2 + 32), v120);
      *(_OWORD *)lpFileName = 0;
      v129 = 0;
      v130 = 0;
      CommonUtil::CAzureStorageClient::CAzureStorageClient(lpFileName, a2 + 80, a2 + 32);
      v74 = a2 + 64;
      if ( !(unsigned __int8)CommonUtil::CAzureStorageClient::ContainerExists(lpFileName, a2 + 64) )
      {
        CommonUtil::NewSprintfW(v107, (wchar_t **)L"%ls", L"User has no access to storage container");
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( *((_QWORD *)a2 + 19) > 7u )
            v74 = *(const wchar_t **)v74;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids, v74);
        }
        v75 = a2 + 48;
        if ( *((_QWORD *)a2 + 15) > 7u )
          v75 = *(const wchar_t **)v75;
        UtilDeleteFile(v75);
        CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)lpFileName);
        operator delete(v73, v76);
        CommonUtil::ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___::_ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___(v124);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
        if ( v19 )
          CloseHandle(v19);
        return (unsigned int)MicrosoftStorageStatus;
      }
      std::wstring::wstring(v126, &qword_18025C818);
      v77 = a2 + 64;
      if ( *((_QWORD *)a2 + 19) > 7u )
        v77 = *(const wchar_t **)v74;
      std::wstring::wstring(v134, v77);
      MicrosoftStorageStatus = CommonUtil::CAzureStorageClient::GetBlobFullPath(lpFileName, v134, a2 + 16, v126);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v134);
      if ( MicrosoftStorageStatus < 0 )
      {
        CommonUtil::NewSprintfW(v107, (wchar_t **)L"%ls", L"Failed to obtain url for evidence file");
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          v61 = MicrosoftStorageStatus;
        }
        else
        {
          v78 = a2 + 48;
          if ( *((_QWORD *)a2 + 15) > 7u )
            v78 = *(const wchar_t **)v78;
          v61 = MicrosoftStorageStatus;
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)&WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
            (_DWORD)v78,
            MicrosoftStorageStatus);
        }
        v79 = a2 + 48;
        if ( *((_QWORD *)a2 + 15) > 7u )
          v79 = *(const wchar_t **)v79;
        UtilDeleteFile(v79);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v126);
        CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)lpFileName);
LABEL_221:
        operator delete(v73, v80);
LABEL_222:
        CommonUtil::ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___::_ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___(v124);
LABEL_138:
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
        if ( v19 )
          CloseHandle(v19);
        if ( v8 )
          operator delete(v8, v62);
        return v61;
      }
      v81 = CommonUtil::CAzureStorageClient::BlobExists(lpFileName, a2 + 64, a2 + 16);
      v82 = (const wchar_t *)v126;
      if ( v81 )
      {
        if ( v127 > 7 )
          v82 = v126[0];
        CommonUtil::NewSprintfW(v107, (wchar_t **)L"%ls", v82);
        if ( *((_QWORD *)a2 + 7) > 7u )
          v63 = *(std::_Ref_count_base **)v63;
        v83 = a2 + 48;
        v84 = v83;
        if ( *((_QWORD *)v83 + 3) > 7u )
          v84 = *(const wchar_t **)v83;
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs file already exists on storage %s hash %s",
          "RealtimeProtection::DlpFileEvidence::ComputeUrl",
          v84,
          v63);
        if ( *((_QWORD *)v83 + 3) > 7u )
          v83 = *(const wchar_t **)v83;
        UtilDeleteFile(v83);
      }
      else
      {
        if ( v127 > 7 )
          v82 = v126[0];
        CommonUtil::NewSprintfW(v107, (wchar_t **)L"%ls", v82);
        *(_BYTE *)v117 = 1;
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v126);
      CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)lpFileName);
      operator delete(v73, v85);
    }
    CommonUtil::ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___::_ScopeGuardImpl__lambda_ecf7e322950a2161c0ba4c9175accc9d___(v124);
    goto LABEL_213;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v90 = a2 + 48;
    if ( *((_QWORD *)a2 + 15) > 7u )
      v90 = *(const wchar_t **)v90;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids,
      (_DWORD)v90,
      MicrosoftStorageStatus);
  }
  v91 = a2 + 48;
  if ( *((_QWORD *)a2 + 15) > 7u )
    v91 = *(const wchar_t **)v91;
  UtilDeleteFile(v91);
  CommonUtil::NewSprintfW((CommonUtil *)&v121, (wchar_t **)L"%ls%#lx", L"ComputeUrl Exception thrown error_", v54);
  v92 = (const struct std::nothrow_t *)g_pcsAsimovLock;
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      v94 = v121;
      v124[0] = (std::_Ref_count_base *)v121;
      v134[0] = (__int64)L"Exception case";
      v95 = a2 + 144;
      if ( *((_QWORD *)v95 + 3) > 7u )
        v95 = *(const wchar_t **)v95;
      v111 = (__int64)v95;
      LODWORD(v103) = *((_DWORD *)g_aAsimov + 18);
      LODWORD(v102) = *((_DWORD *)g_aAsimov + 17);
      v101 = *((_DWORD *)g_aAsimov + 16);
      v100 = *((unsigned __int8 *)g_aAsimov + 60);
      v99 = *((unsigned __int8 *)g_aAsimov + 59);
      v98 = *((unsigned __int8 *)g_aAsimov + 58);
      v97 = *((unsigned __int8 *)g_aAsimov + 57);
      MicrosoftStorageStatus = *((unsigned __int8 *)g_aAsimov + 56);
      v110 = *((_QWORD *)g_aAsimov + 6);
      v109 = *((_QWORD *)g_aAsimov + 5);
      v132[0] = *((_QWORD *)g_aAsimov + 4);
      v106 = *((_QWORD *)g_aAsimov + 3);
      v105 = *((_QWORD *)g_aAsimov + 2);
      v104 = *((_QWORD *)g_aAsimov + 1);
      v108 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v93,
        (int)&unk_1802C7270,
        (__int64)&v108,
        (__int64)&v104,
        (__int64)&v105,
        (__int64)&v106,
        (__int64)v132,
        (__int64)&v109,
        (__int64)&v110,
        (__int64)&MicrosoftStorageStatus,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)&v99,
        (__int64)&v100,
        (__int64)&v101,
        (__int64)&v102,
        (__int64)&v103,
        (__int64)&v111,
        (__int64)v134,
        (__int64)v124);
    }
    else
    {
      v94 = v121;
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v126);
  }
  else
  {
    v94 = v121;
  }
  if ( v19 )
    CloseHandle(v19);
  if ( v94 )
    operator delete(v94, v92);
  return v54;
}

```

## disassembly

```asm
0x18020546c  push    rbx
0x18020546e  push    rsi
0x18020546f  push    rdi
0x180205470  push    r12
0x180205472  push    r13
0x180205474  push    r14
0x180205476  push    r15
0x180205478  sub     rsp, 280h
0x18020547f  mov     rax, cs:__security_cookie
0x180205486  xor     rax, rsp
0x180205489  mov     [rsp+2B8h+var_48], rax
0x180205491  mov     [rsp+2B8h+var_178], r9
0x180205499  mov     rsi, r8
0x18020549c  mov     [rsp+2B8h+var_1C8], r8
0x1802054a4  mov     rbx, rdx
0x1802054a7  mov     [rsp+2B8h+var_1A0], rdx
0x1802054af  mov     [rsp+2B8h+var_1E8], rcx
0x1802054b7  mov     [rsp+2B8h+var_1B0], rdx
0x1802054bf  mov     r13, rdx
0x1802054c2  mov     [rsp+2B8h+var_168], rdx
0x1802054ca  mov     [rsp+2B8h+var_1A8], r8
0x1802054d2  mov     [rsp+2B8h+var_90], r9
0x1802054da  xor     r15d, r15d
0x1802054dd  mov     [r8], r15
0x1802054e0  mov     [r9], r15b
0x1802054e3  mov     edi, r15d
0x1802054e6  mov     [rsp+2B8h+var_148], r15
0x1802054ee  test    rcx, rcx
0x1802054f1  jnz     short loc_18020553E
0x1802054f3  lea     rax, WPP_GLOBAL_Control
0x1802054fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180205501  cmp     rcx, rax
0x180205504  jz      short loc_180205520
0x180205506  test    byte ptr [rcx+1Ch], 4
0x18020550a  jz      short loc_180205520
0x18020550c  lea     edx, [r15+13h]
0x180205510  lea     r8, WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids
0x180205517  mov     rcx, [rcx+10h]
0x18020551b  call    WPP_SF_
0x180205520  lea     r8, aEvidenceDirect_1; "Evidence directory does not exist"
0x180205527  lea     rdx, aLs_0; "%ls"
0x18020552e  mov     rcx, rsi; this
0x180205531  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x180205536  nop
0x180205537  xor     eax, eax
0x180205539  jmp     loc_180207250
0x18020553e  mov     ecx, 0BDh
0x180205543  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x180205548  mov     r14d, eax
0x18020554b  cmp     [rbx], r15b
0x18020554e  mov     ebx, 1
0x180205553  jz      loc_180205672
0x180205559  dec     eax
0x18020555b  cmp     eax, ebx
0x18020555d  ja      loc_180205672
0x180205563  lea     r12, WPP_GLOBAL_Control
0x18020556a  mov     rcx, cs:WPP_GLOBAL_Control
0x180205571  cmp     rcx, r12
0x180205574  jz      short loc_18020558F
0x180205576  test    byte ptr [rcx+1Ch], 10h
0x18020557a  jz      short loc_18020558F
0x18020557c  lea     edx, [rbx+13h]
0x18020557f  lea     r8, WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids
0x180205586  mov     rcx, [rcx+10h]
0x18020558a  call    WPP_SF_
0x18020558f  mov     dword ptr [rsp+2B8h+var_208], ebx
0x180205596  xorps   xmm0, xmm0
0x180205599  movups  xmmword ptr [rsp+2B8h+var_120], xmm0
0x1802055a1  lea     rcx, [rsp+2B8h+var_120]
0x1802055a9  call    ??$atomic_load@VDlpFileEvidenceUpload@DlpFileEvidence@RealtimeProtection@@@std@@YA?AV?$shared_ptr@VDlpFileEvidenceUpload@DlpFileEvidence@RealtimeProtection@@@0@PEBV10@@Z; std::atomic_load<RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload>(std::shared_ptr<RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload> const *)
0x1802055ae  mov     rcx, [rsp+2B8h+var_120]
0x1802055b6  test    rcx, rcx
0x1802055b9  jz      short loc_1802055C7
0x1802055bb  call    ?GetMicrosoftStorageStatus@DlpFileEvidenceUpload@DlpFileEvidence@RealtimeProtection@@QEAA?AW4FileEvidenceMSStorageStatus@23@XZ; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::GetMicrosoftStorageStatus(void)
0x1802055c0  mov     dword ptr [rsp+2B8h+var_208], eax
0x1802055c7  mov     rcx, [rsp+2B8h+var_120+8]; this
0x1802055cf  test    rcx, rcx
0x1802055d2  jz      short loc_1802055D9
0x1802055d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802055d9  cmp     dword ptr [rsp+2B8h+var_208], 2
0x1802055e1  jnz     loc_180205679
0x1802055e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1802055ee  cmp     rcx, r12
0x1802055f1  jz      short loc_180205626
0x1802055f3  test    byte ptr [rcx+1Ch], 4
0x1802055f7  jz      short loc_180205626
0x1802055f9  mov     eax, r15d
0x1802055fc  cmp     r14d, 2
0x180205600  setz    al
0x180205603  mov     r9d, r15d
0x180205606  cmp     r14d, ebx
0x180205609  setz    r9b
0x18020560d  mov     edx, 15h
0x180205612  mov     dword ptr [rsp+2B8h+var_298], eax
0x180205616  lea     r8, WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids
0x18020561d  mov     rcx, [rcx+10h]
0x180205621  call    WPP_SF_Dd
0x180205626  cmp     r14d, ebx
0x180205629  jnz     short loc_180205644
0x18020562b  lea     rax, qword_1803121E8
0x180205632  cmp     cs:qword_180312200, 7
0x18020563a  cmova   rax, cs:qword_1803121E8
0x180205642  jmp     short loc_18020565B
0x180205644  lea     rax, qword_180312208
0x18020564b  cmp     cs:qword_180312220, 7
0x180205653  cmova   rax, cs:qword_180312208
0x18020565b  mov     r8, rax; wchar_t *
0x18020565e  lea     rdx, aLs_0; "%ls"
0x180205665  mov     rcx, rsi; this
0x180205668  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18020566d  jmp     loc_1802058A5
0x180205672  lea     r12, WPP_GLOBAL_Control
0x180205679  mov     [rsp+2B8h+hObject], r15
0x180205681  lea     rcx, [rsp+2B8h+hObject]; this
0x180205689  call    ?GetLastLogonImpersonationToken@DlpUtils@RealtimeProtection@@YAJPEAPEAX@Z; RealtimeProtection::DlpUtils::GetLastLogonImpersonationToken(void * *)
0x18020568e  mov     r14d, eax
0x180205691  test    eax, eax
0x180205693  jns     short loc_1802056DA
0x180205695  mov     rcx, cs:WPP_GLOBAL_Control
0x18020569c  cmp     rcx, r12
0x18020569f  jz      short loc_1802056BF
0x1802056a1  test    [rcx+1Ch], bl
0x1802056a4  jz      short loc_1802056BF
0x1802056a6  mov     edx, 16h
0x1802056ab  mov     r9d, eax
0x1802056ae  lea     r8, WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids
0x1802056b5  mov     rcx, [rcx+10h]
0x1802056b9  call    WPP_SF_d
0x1802056be  nop
0x1802056bf  mov     rcx, [rsp+2B8h+hObject]; hObject
0x1802056c7  test    rcx, rcx
0x1802056ca  jz      short loc_1802056D2
0x1802056cc  call    cs:__imp_CloseHandle
0x1802056d2  mov     r15d, r14d
0x1802056d5  jmp     loc_1802058A5
0x1802056da  xorps   xmm0, xmm0
0x1802056dd  xor     eax, eax
0x1802056df  movups  [rsp+2B8h+FileInformation], xmm0
0x1802056e7  movups  [rsp+2B8h+var_60], xmm0
0x1802056ef  mov     [rsp+2B8h+var_50], eax
0x1802056f6  lea     r14, [r13+160h]
0x1802056fd  mov     [rsp+2B8h+var_1B8], r14
0x180205705  mov     [rsp+2B8h+var_120], r14
0x18020570d  mov     rcx, r14
0x180205710  cmp     qword ptr [r14+18h], 7
0x180205715  jbe     short loc_18020571A
0x180205717  mov     rcx, [r14]; lpFileName
0x18020571a  lea     r8, [rsp+2B8h+FileInformation]; lpFileInformation
0x180205722  xor     edx, edx; fInfoLevelId
0x180205724  call    cs:__imp_GetFileAttributesExW
0x18020572a  test    eax, eax
0x18020572c  jnz     loc_180205820
0x180205732  call    HrGetLastFailure
0x180205737  mov     dword ptr [rsp+2B8h+var_208], eax
0x18020573e  mov     rbx, [rsp+2B8h+hObject]
0x180205746  cmp     eax, 80070005h
0x18020574b  jnz     short loc_1802057C2
0x18020574d  test    rbx, rbx
0x180205750  jz      short loc_1802057C6
0x180205752  mov     dword ptr [rsp+2B8h+var_208], r15d
0x18020575a  xorps   xmm0, xmm0
0x18020575d  movups  xmmword ptr [rsp+2B8h+var_B8], xmm0
0x180205765  mov     rdx, rbx; void *
0x180205768  lea     rcx, [rsp+2B8h+var_B8]; this
0x180205770  call    ??0CAutoImpersonateToken@CommonUtil@@QEAA@PEAX@Z; CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken(void *)
0x180205775  mov     rcx, r14
0x180205778  cmp     qword ptr [r14+18h], 7
0x18020577d  jbe     short loc_180205782
0x18020577f  mov     rcx, [r14]; lpFileName
0x180205782  lea     r8, [rsp+2B8h+FileInformation]; lpFileInformation
0x18020578a  xor     edx, edx; fInfoLevelId
0x18020578c  call    cs:__imp_GetFileAttributesExW
0x180205792  test    eax, eax
0x180205794  jnz     short loc_1802057A4
0x180205796  call    HrGetLastFailure
0x18020579b  mov     dword ptr [rsp+2B8h+var_208], eax
0x1802057a2  jmp     short loc_1802057AB
0x1802057a4  mov     eax, dword ptr [rsp+2B8h+var_208]
0x1802057ab  cmp     byte ptr [rsp+2B8h+var_B8+8], r15b
0x1802057b3  jz      short loc_1802057C2
0x1802057b5  call    cs:__imp_RevertToSelf
0x1802057bb  mov     eax, dword ptr [rsp+2B8h+var_208]
0x1802057c2  test    eax, eax
0x1802057c4  jns     short loc_180205828
0x1802057c6  cmp     qword ptr [r14+18h], 7
0x1802057cb  jbe     short loc_1802057D0
0x1802057cd  mov     r14, [r14]
0x1802057d0  mov     r9d, eax
0x1802057d3  mov     r8, r14
0x1802057d6  lea     rdx, aRealtimeprotec_8; "RealtimeProtection::DlpFileEvidence::Co"...
0x1802057dd  lea     rcx, aDlpHsGetfileat; "DLP::%hs: GetFileAttributesExW failed f"...
0x1802057e4  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1802057e9  mov     edi, dword ptr [rsp+2B8h+var_208]
0x1802057f0  mov     r9d, edi
0x1802057f3  lea     r8, aFailedToGetFil; "Failed to get file attributes error_"
0x1802057fa  lea     rdx, aLsLx; "%ls%#lx"
0x180205801  mov     rcx, rsi; this
0x180205804  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x180205809  nop
0x18020580a  test    rbx, rbx
0x18020580d  jz      short loc_180205818
0x18020580f  mov     rcx, rbx; hObject
0x180205812  call    cs:__imp_CloseHandle
0x180205818  mov     r15d, edi
0x18020581b  jmp     loc_1802058A5
0x180205820  mov     rbx, [rsp+2B8h+hObject]
0x180205828  mov     eax, [rsp+2B8h+var_50]
0x18020582f  mov     dword ptr [rsp+2B8h+var_150], eax
0x180205836  mov     eax, dword ptr [rsp+2B8h+var_60+0Ch]
0x18020583d  mov     dword ptr [rsp+2B8h+var_150+4], eax
0x180205844  mov     rax, [rsp+2B8h+var_150]
0x18020584c  mov     [r13+8], rax
0x180205850  cmp     rax, 1F400000h
0x180205856  jbe     short loc_1802058AD
0x180205858  mov     rcx, cs:WPP_GLOBAL_Control
0x18020585f  cmp     rcx, r12
0x180205862  jz      short loc_18020587F
0x180205864  test    byte ptr [rcx+1Ch], 4
0x180205868  jz      short loc_18020587F
0x18020586a  mov     edx, 17h
0x18020586f  lea     r8, WPP_3da74a7d715f339e616f2b8b860ea5eb_Traceguids
0x180205876  mov     rcx, [rcx+10h]
0x18020587a  call    WPP_SF_
0x18020587f  lea     r8, aFileSizeGreate; "File size greater than 500MB"
0x180205886  lea     rdx, aLs_0; "%ls"
0x18020588d  mov     rcx, rsi; this
0x180205890  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x180205895  nop
0x180205896  test    rbx, rbx
0x180205899  jz      short loc_1802058A5
0x18020589b  mov     rcx, rbx; hObject
0x18020589e  call    cs:__imp_CloseHandle
0x1802058a4  nop
0x1802058a5  mov     eax, r15d
0x1802058a8  jmp     loc_180207250
0x1802058ad  mov     [rsp+2B8h+var_98], r15
0x1802058b5  mov     rax, [rsp+2B8h+var_1A0]
0x1802058bd  lea     rdx, [rsp+2B8h+var_108]
0x1802058c5  mov     rcx, r14
0x1802058c8  cmp     [rax], r15b
0x1802058cb  jz      short loc_180205940
0x1802058cd  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1802058d2  nop
0x1802058d3  lea     rdx, [rsp+2B8h+Src]
0x1802058db  mov     rcx, rax
0x1802058de  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x1802058e3  mov     rsi, rax
0x1802058e6  cmp     qword ptr [rax+18h], 7
0x1802058eb  jbe     short loc_1802058F0
0x1802058ed  mov     rsi, [rax]
0x1802058f0  lea     rcx, [rsp+2B8h+var_60+4]; this
0x1802058f8  call    ?UtilFileTimeToUlong64@CommonUtil@@YA_KAEBU_FILETIME@@@Z; CommonUtil::UtilFileTimeToUlong64(_FILETIME const &)
0x1802058fd  mov     qword ptr [rsp+2B8h+var_290], rsi
0x180205902  mov     [rsp+2B8h+var_298], rax
0x180205907  mov     r9d, [r13+4]
0x18020590b  lea     r8, aMicrosoftmanag; "MicrosoftManaged"
0x180205912  lea     rdx, aLsDLluLs; "%ls_%d_%llu_%ls"
0x180205919  lea     rcx, [rsp+2B8h+var_98]; this
0x180205921  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x180205926  mov     dword ptr [rsp+2B8h+var_208], eax
0x18020592d  lea     rcx, [rsp+2B8h+Src]; void *
0x180205935  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020593a  nop
0x18020593b  jmp     loc_1802059CD
0x180205940  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x180205945  nop
0x180205946  lea     rdx, [rsp+2B8h+Src]
0x18020594e  mov     rcx, rax
0x180205951  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x180205956  mov     rsi, rax
0x180205959  cmp     qword ptr [rax+18h], 7
0x18020595e  jbe     short loc_180205963
0x180205960  mov     rsi, [rax]
0x180205963  lea     rcx, [rsp+2B8h+var_60+4]; this
0x18020596b  call    ?UtilFileTimeToUlong64@CommonUtil@@YA_KAEBU_FILETIME@@@Z; CommonUtil::UtilFileTimeToUlong64(_FILETIME const &)
0x180205970  mov     ecx, [r13+4]
0x180205974  lea     r9, [r13+0A0h]
0x18020597b  cmp     qword ptr [r9+18h], 7
0x180205980  jbe     short loc_180205985
0x180205982  mov     r9, [r9]
0x180205985  lea     r8, [r13+80h]
0x18020598c  cmp     qword ptr [r8+18h], 7
0x180205991  jbe     short loc_180205996
0x180205993  mov     r8, [r8]; wchar_t *
0x180205996  mov     [rsp+2B8h+var_288], rsi
0x18020599b  mov     qword ptr [rsp+2B8h+var_290], rax
0x1802059a0  mov     dword ptr [rsp+2B8h+var_298], ecx
0x1802059a4  lea     rdx, aLsLsDLluLs; "%ls_%ls_%d_%llu_%ls"
0x1802059ab  lea     rcx, [rsp+2B8h+var_98]; this
0x1802059b3  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1802059b8  mov     dword ptr [rsp+2B8h+var_208], eax
0x1802059bf  lea     rcx, [rsp+2B8h+Src]; void *
0x1802059c7  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802059cc  nop
0x1802059cd  lea     rcx, [rsp+2B8h+var_108]; void *
0x1802059d5  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802059da  mov     rsi, [rsp+2B8h+var_98]
0x1802059e2  mov     rdx, rsi
0x1802059e5  lea     rcx, [rsp+2B8h+lpFileName]
0x1802059ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
  ... truncated ...
```
