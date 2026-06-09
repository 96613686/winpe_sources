# RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged(RealtimeProtection::DlpFileEvidence::DlpFileUploadData &)

- ea: `0x180209ea0`
- end: `0x18020b8d8`
- name: `?UploadFileMicrosoftManaged@DlpFileEvidenceUpload@DlpFileEvidence@RealtimeProtection@@AEAAJAEAUDlpFileUploadData@23@@Z`
- size: `6712`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload *__hidden this, struct RealtimeProtection::DlpFileEvidence::DlpFileUploadData *)`
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b05b0`

## callees

- `0x180005c28`
- `0x18000a010`
- `0x18000b864`
- `0x18001e348`
- `0x180028a10`
- `0x180028d80`
- `0x18002c150`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x18004b3bc`
- `0x180079dc0`
- `0x180081724`
- `0x1800afcac`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x1800c940c`
- `0x180104f64`
- `0x180106620`
- `0x180107188`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18014e274`
- `0x1801f73f8`
- `0x1802088f8`
- `0x180208c60`
- `0x180208d38`
- `0x180208d84`
- `0x180208f38`
- `0x180209420`
- `0x180209454`
- `0x180209604`
- `0x180209710`
- `0x180209ea0`
- `0x18020bb08`
- `0x18020bc88`
- `0x18020bd60`
- `0x18022d600`
- `0x18022d814`
- `0x18022de40`
- `0x180236ab4`
- `0x180237110`
- `0x18023792c`
- `0x180238038`
- `0x18023a290`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18020a0e8`
- `KERNEL32!CloseHandle` at `0x18020a19b`
- `KERNEL32!CloseHandle` at `0x18020a263`
- `KERNEL32!CloseHandle` at `0x18020a2ba`
- `KERNEL32!CloseHandle` at `0x18020a35c`
- `KERNEL32!CloseHandle` at `0x18020a4f4`
- `KERNEL32!CloseHandle` at `0x18020ab67`
- `KERNEL32!CloseHandle` at `0x18020ac90`
- `KERNEL32!CloseHandle` at `0x18020b260`
- `KERNEL32!CloseHandle` at `0x18020b2ec`
- `KERNEL32!CloseHandle` at `0x18020b5d8`
- `KERNEL32!CloseHandle` at `0x18020b704`
- `KERNEL32!CloseHandle` at `0x18020a0e8`
- `KERNEL32!CloseHandle` at `0x18020a19b`
- `KERNEL32!CloseHandle` at `0x18020a263`
- `KERNEL32!CloseHandle` at `0x18020a2ba`
- `KERNEL32!CloseHandle` at `0x18020a35c`
- `KERNEL32!CloseHandle` at `0x18020a4f4`
- `KERNEL32!CloseHandle` at `0x18020ab67`
- `KERNEL32!CloseHandle` at `0x18020ac90`
- `KERNEL32!CloseHandle` at `0x18020b260`
- `KERNEL32!CloseHandle` at `0x18020b2ec`
- `KERNEL32!CloseHandle` at `0x18020b5d8`
- `KERNEL32!CloseHandle` at `0x18020b704`
- `KERNEL32!GetTickCount64` at `0x18020a9f2`
- `KERNEL32!GetTickCount64` at `0x18020aa0a`
- `KERNEL32!GetTickCount64` at `0x18020ad0d`
- `KERNEL32!GetTickCount64` at `0x18020adba`
- `KERNEL32!GetTickCount64` at `0x18020a9f2`
- `KERNEL32!GetTickCount64` at `0x18020aa0a`
- `KERNEL32!GetTickCount64` at `0x18020ad0d`
- `KERNEL32!GetTickCount64` at `0x18020adba`

## string_xrefs

- `0x18020b35f`: `DLP::%hs file %ls already exists on storage hash value %ls`
- `0x18020a47c`: `GetAzureStorageTokenWithObjectID failed Error %#lxReason %ls`
- `0x18020a73b`: `/dlpffe/createsasurl`
- `0x18020a8bf`: `/dlpffe/createsasurl`
- `0x18020a2fa`: `DLP::%hs failed to fetch impersonation token hr=%#lx`
- `0x18020a333`: `Failed to get impersonation token error_`
- `0x18020a0c4`: `DLP::%hs file %ls already uploaded and does not exist on disk`
- `0x18020b1f6`: `Commit SasUrl failed for hr:%#lx, httpError:%d, response %ls`
- `0x18020b04b`: `/dlpffe/commit`
- `0x18020b0ad`: `/dlpffe/commit`
- `0x18020aa19`: `DLP::%hs - Setting status to storage exhausted. Current time: %llu, Next attempt time: %llu  `
- `0x18020ab0b`: `CreateSasUrl failed hr:%#lx, HttpErrorCode:%d, response %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged(
        RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload *this,
        struct RealtimeProtection::DlpFileEvidence::DlpFileUploadData *a2)
{
  RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload *v3; // rbx
  CommonUtil *v5; // rsi
  char *v6; // r8
  int v7; // eax
  __m128i si128; // xmm6
  const wchar_t *v9; // rdx
  RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken *Instance; // r15
  __int64 v11; // rax
  CommonUtil *v12; // rcx
  RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload *v13; // rcx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  unsigned int *v17; // r9
  const struct std::nothrow_t *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  int LatestActiveLogonSession; // eax
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // ebx
  unsigned int v23; // esi
  const struct std::nothrow_t *v24; // rdx
  __int64 AuthToken; // rax
  __int64 ObjectId; // rax
  char *v27; // r12
  const struct std::nothrow_t *v28; // rdx
  unsigned int v29; // ebx
  const wchar_t *v30; // rsi
  wchar_t *v31; // r15
  _QWORD *v32; // r14
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  const struct std::nothrow_t *v37; // rdx
  const wchar_t *v38; // r15
  wchar_t *v39; // rax
  int SasUrl; // eax
  char v41; // r10
  __int64 *v42; // r12
  const wchar_t *v43; // r8
  const wchar_t *v44; // rdx
  const wchar_t *v45; // rcx
  const wchar_t *v46; // rax
  const struct std::nothrow_t *v47; // rdx
  __int64 v48; // rcx
  __int64 *v49; // r9
  RealtimeProtection::DlpUtils *v50; // rcx
  unsigned __int64 CurrentUTCtoNextDayUTCDiffInMilliSeconds; // rbx
  unsigned int Value; // eax
  ULONGLONG v53; // rbx
  ULONGLONG TickCount64; // rax
  unsigned int v55; // ebx
  __int64 *v56; // rax
  unsigned int v57; // esi
  bool v58; // dl
  unsigned int v59; // ebx
  const struct std::nothrow_t *v60; // rdx
  int SasUrlResponse; // eax
  const struct std::nothrow_t *v62; // rdx
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  const struct std::nothrow_t *v65; // rdx
  const struct std::nothrow_t *v66; // rdx
  int v67; // ebx
  __int64 *v68; // rax
  __int64 v69; // r8
  __int64 v70; // rbx
  int v71; // r9d
  char *v72; // rax
  _QWORD *v73; // rax
  const struct std::nothrow_t *v74; // rdx
  int v75; // ebx
  __int64 v76; // rbx
  __int64 *v77; // rax
  unsigned int v78; // esi
  bool v79; // dl
  unsigned int v80; // ebx
  const struct std::nothrow_t *v81; // rdx
  const struct std::nothrow_t *v82; // rdx
  char *v83; // r9
  int v84; // r9d
  _QWORD *v85; // rax
  const struct std::nothrow_t *v86; // rdx
  __int64 *v87; // rax
  bool v88; // dl
  unsigned int v89; // ebx
  const struct std::nothrow_t *v90; // rdx
  const struct std::nothrow_t *v91; // rdx
  unsigned int v92; // ebx
  unsigned int v93; // esi
  const struct std::nothrow_t *v94; // rdx
  __int64 v95; // [rsp+C0h] [rbp-338h] BYREF
  __int64 v96; // [rsp+C8h] [rbp-330h] BYREF
  int v97; // [rsp+D0h] [rbp-328h] BYREF
  int v98; // [rsp+D4h] [rbp-324h] BYREF
  int v99; // [rsp+D8h] [rbp-320h] BYREF
  int v100; // [rsp+DCh] [rbp-31Ch] BYREF
  int v101; // [rsp+E0h] [rbp-318h] BYREF
  int v102; // [rsp+E4h] [rbp-314h]
  void *Src; // [rsp+E8h] [rbp-310h]
  RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken *v104; // [rsp+F0h] [rbp-308h]
  int v105[8]; // [rsp+F8h] [rbp-300h] BYREF
  void *v106; // [rsp+118h] [rbp-2E0h]
  __int64 v107; // [rsp+120h] [rbp-2D8h] BYREF
  __int64 v108; // [rsp+128h] [rbp-2D0h] BYREF
  __int64 v109; // [rsp+130h] [rbp-2C8h] BYREF
  __int64 v110; // [rsp+138h] [rbp-2C0h] BYREF
  __int64 v111; // [rsp+140h] [rbp-2B8h] BYREF
  __int64 v112; // [rsp+148h] [rbp-2B0h] BYREF
  __int64 v113; // [rsp+150h] [rbp-2A8h] BYREF
  __int64 v114[2]; // [rsp+158h] [rbp-2A0h] BYREF
  _QWORD v115[6]; // [rsp+168h] [rbp-290h] BYREF
  _QWORD *v116; // [rsp+198h] [rbp-260h]
  __int64 v117; // [rsp+1A0h] [rbp-258h] BYREF
  std::_Ref_count_base *v118; // [rsp+1A8h] [rbp-250h]
  __int64 v119; // [rsp+1B0h] [rbp-248h] BYREF
  __int64 v120; // [rsp+1B8h] [rbp-240h] BYREF
  wchar_t *v121; // [rsp+1C8h] [rbp-230h] BYREF
  void *v122; // [rsp+1D0h] [rbp-228h] BYREF
  char v123; // [rsp+1D8h] [rbp-220h] BYREF
  char v124[4]; // [rsp+1DCh] [rbp-21Ch] BYREF
  HANDLE hObject; // [rsp+1E0h] [rbp-218h] BYREF
  int v126; // [rsp+1E8h] [rbp-210h] BYREF
  wchar_t *v127; // [rsp+1F0h] [rbp-208h] BYREF
  __int64 v128[2]; // [rsp+1F8h] [rbp-200h] BYREF
  __int64 v129; // [rsp+208h] [rbp-1F0h]
  unsigned __int64 v130; // [rsp+210h] [rbp-1E8h]
  __int64 v131[2]; // [rsp+218h] [rbp-1E0h] BYREF
  __m128i v132; // [rsp+228h] [rbp-1D0h]
  struct _LUID v133; // [rsp+238h] [rbp-1C0h] BYREF
  __int128 v134; // [rsp+240h] [rbp-1B8h] BYREF
  __int64 v135; // [rsp+250h] [rbp-1A8h]
  unsigned __int64 v136; // [rsp+258h] [rbp-1A0h]
  __int128 v137; // [rsp+260h] [rbp-198h] BYREF
  __int64 v138; // [rsp+270h] [rbp-188h]
  unsigned __int64 v139; // [rsp+278h] [rbp-180h]
  __int128 v140; // [rsp+280h] [rbp-178h] BYREF
  __int64 v141; // [rsp+290h] [rbp-168h]
  unsigned __int64 v142; // [rsp+298h] [rbp-160h]
  __int128 v143; // [rsp+2A0h] [rbp-158h] BYREF
  __int64 v144; // [rsp+2B0h] [rbp-148h]
  unsigned __int64 v145; // [rsp+2B8h] [rbp-140h]
  void *v146; // [rsp+2C0h] [rbp-138h] BYREF
  _OWORD v147[2]; // [rsp+2C8h] [rbp-130h] BYREF
  __int64 v148; // [rsp+2E8h] [rbp-110h]
  _OWORD v149[2]; // [rsp+2F0h] [rbp-108h] BYREF
  _OWORD v150[2]; // [rsp+310h] [rbp-E8h] BYREF
  _OWORD v151[2]; // [rsp+330h] [rbp-C8h] BYREF
  _OWORD v152[2]; // [rsp+350h] [rbp-A8h] BYREF
  _OWORD v153[2]; // [rsp+370h] [rbp-88h] BYREF
  _OWORD v154[2]; // [rsp+390h] [rbp-68h] BYREF

  v3 = this;
  v96 = (__int64)this;
  if ( *((_DWORD *)a2 + 96) )
    return 0;
  v5 = (struct RealtimeProtection::DlpFileEvidence::DlpFileUploadData *)((char *)a2 + 96);
  v6 = (char *)a2 + 96;
  if ( *((_QWORD *)a2 + 15) > 7u )
    v6 = *(char **)v5;
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::%hs trying upload file %s",
    "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
    v6);
  LODWORD(v121) = 0;
  v123 = 0;
  v122 = 0;
  v126 = 0;
  v114[1] = 0;
  v115[0] = &v123;
  v115[1] = &v121;
  v115[2] = &v122;
  v115[3] = &v126;
  v115[4] = a2;
  v115[5] = v3;
  v7 = g_pfnRoInitialize(1);
  LODWORD(v121) = v7;
  if ( v7 < 0 )
  {
    v123 = 0;
    if ( v7 != -2147417850 )
    {
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"DLP::%hs g_pfnRoInitialize failed with hr=%#lx",
        "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
        (unsigned int)v7);
      v92 = (unsigned int)v121;
      v93 = (unsigned int)v121;
      if ( v122 )
      {
        operator delete(v122, v91);
        v122 = 0;
        v92 = (unsigned int)v121;
      }
      CommonUtil::NewSprintfW((CommonUtil *)&v122, (wchar_t **)L"%ls%#lx", L"RoInitialize Failed with error_", v93);
      lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
      if ( v122 )
        operator delete(v122, v94);
      return v92;
    }
    LODWORD(v121) = 0;
  }
  else
  {
    v123 = 1;
  }
  *(_OWORD *)v131 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v132 = si128;
  LOWORD(v131[0]) = 0;
  *(_OWORD *)v128 = 0;
  v129 = 0;
  v130 = 7;
  LOWORD(v128[0]) = 0;
  *(_DWORD *)v124 = 0;
  Instance = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetInstance();
  v104 = Instance;
  hObject = 0;
  v133.LowPart = 0;
  v146 = 0;
  v116 = (_QWORD *)((char *)v3 + 8);
  if ( !*((_QWORD *)v3 + 1) )
  {
    v11 = std::make_shared<RealtimeProtection::CSenseCloudCncProxy,>(&v117);
    std::shared_ptr<RealtimeProtection::CSenseCloudCncProxy>::operator=((char *)v3 + 8, v11);
    if ( v118 )
      std::_Ref_count_base::_Decref(v118);
  }
  v12 = v5;
  if ( *((_QWORD *)v5 + 3) > 7u )
    v12 = *(CommonUtil **)v5;
  if ( (unsigned int)CommonUtil::UtilIsFileExists(v12, v9) == -2147024894 )
  {
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(CommonUtil **)v5;
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs file %ls already uploaded and does not exist on disk",
      "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
      v5);
    *((_DWORD *)a2 + 96) = 2;
    if ( hObject )
      CloseHandle(hObject);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
    lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
    if ( v122 )
      operator delete(v122, v14);
    return 0;
  }
  if ( *((_BYTE *)v3 + 260) )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs Shutdown pending , exiting . \n",
      "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged");
    if ( v122 )
    {
      operator delete(v122, v15);
      v122 = 0;
    }
    CommonUtil::NewSprintfW((CommonUtil *)&v122, (wchar_t **)L"%ls", L"Upload aborted due to shutdown");
    *((_DWORD *)a2 + 96) = 1;
    if ( hObject )
      CloseHandle(hObject);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
    lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
    if ( v122 )
      operator delete(v122, v16);
    return 0;
  }
  if ( RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::IsRetentionPeriodExpired(
         v13,
         *((_QWORD *)a2 + 3),
         *((_DWORD *)a2 + 1)) )
  {
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(CommonUtil **)v5;
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs Retention period expired for %s",
      "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
      v5);
    if ( v122 )
    {
      operator delete(v122, v18);
      v122 = 0;
    }
    CommonUtil::NewSprintfW((CommonUtil *)&v122, (wchar_t **)L"%ls", L"Retention Period expired");
    *((_DWORD *)a2 + 96) = 1;
    if ( hObject )
      CloseHandle(hObject);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
    lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
    if ( v122 )
      operator delete(v122, v19);
    return 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  LatestActiveLogonSession = CommonUtil::UtilGetLatestActiveLogonSession(&hObject, &v146, &v133, v17);
  LODWORD(v121) = LatestActiveLogonSession;
  if ( LatestActiveLogonSession < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs failed to fetch impersonation token hr=%#lx",
      "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
      (unsigned int)LatestActiveLogonSession);
    v22 = (unsigned int)v121;
    v23 = (unsigned int)v121;
    if ( v122 )
    {
      operator delete(v122, v21);
      v122 = 0;
      v22 = (unsigned int)v121;
    }
    CommonUtil::NewSprintfW(
      (CommonUtil *)&v122,
      (wchar_t **)L"%ls%#lx",
      L"Failed to get impersonation token error_",
      v23);
    if ( hObject )
      CloseHandle(hObject);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
    lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
    if ( v122 )
      operator delete(v122, v24);
    return v22;
  }
  if ( RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::IsAuthComputed(Instance) )
  {
    AuthToken = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetAuthToken(Instance, v105);
    Src = (char *)a2 + 64;
    std::wstring::operator=((char *)a2 + 64, AuthToken);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
    ObjectId = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetObjectId(Instance, v105);
    v27 = (char *)a2 + 256;
    v106 = (char *)a2 + 256;
    std::wstring::operator=((char *)a2 + 256, ObjectId);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
LABEL_71:
    v102 = *((_DWORD *)v3 + 74) & 0x10;
    v149[0] = 0;
    v149[1] = si128;
    LOWORD(v149[0]) = 0;
    v150[0] = 0;
    v150[1] = si128;
    LOWORD(v150[0]) = 0;
    v151[0] = 0;
    v151[1] = si128;
    LOWORD(v151[0]) = 0;
    v152[0] = 0;
    v152[1] = si128;
    LOWORD(v152[0]) = 0;
    v153[0] = 0;
    v153[1] = si128;
    LOWORD(v153[0]) = 0;
    v154[0] = 0;
    v154[1] = si128;
    LOWORD(v154[0]) = 0;
    v134 = 0;
    v135 = 0;
    v136 = 7;
    LOWORD(v134) = 0;
    v137 = 0;
    v138 = 0;
    v139 = 7;
    LOWORD(v137) = 0;
    v140 = 0;
    v141 = 0;
    v142 = 7;
    LOWORD(v140) = 0;
    v143 = 0;
    v144 = 0;
    v145 = 7;
    LOWORD(v143) = 0;
    std::wstring::operator=(v149, Src);
    v38 = (const wchar_t *)((char *)a2 + 32);
    std::wstring::operator=(v150, (char *)a2 + 32);
    std::wstring::operator=(v151, v27);
    std::wstring::assign(v152, L"/dlpffe/createsasurl");
    std::wstring::operator=(v154, (char *)a2 + 320);
    v39 = (wchar_t *)*((_QWORD *)v3 + 1);
    v127 = v39;
    if ( v102 )
    {
      SasUrl = RealtimeProtection::CSenseCloudCncProxy::CreateSasUrl(
                 (int)v39,
                 (int)hObject,
                 (__int64)v128,
                 (__int64)v124);
      v41 = SasUrl;
      LODWORD(v121) = SasUrl;
      v42 = (__int64 *)&qword_18025C818;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( v144 )
        {
          v43 = (const wchar_t *)&v143;
          if ( v145 > 7 )
            v43 = (const wchar_t *)v143;
        }
        else
        {
          v43 = &qword_18025C818;
        }
        if ( v141 )
        {
          v44 = (const wchar_t *)&v140;
          if ( v142 > 7 )
            v44 = (const wchar_t *)v140;
        }
        else
        {
          v44 = &qword_18025C818;
        }
        if ( v138 )
        {
          v45 = (const wchar_t *)&v137;
          if ( v139 > 7 )
            v45 = (const wchar_t *)v137;
        }
        else
        {
          v45 = &qword_18025C818;
        }
        if ( v135 )
        {
          v46 = (const wchar_t *)&v134;
          if ( v136 > 7 )
            v46 = (const wchar_t *)v134;
        }
        else
        {
          v46 = &qword_18025C818;
        }
        WPP_SF_sLdSSSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v41,
          v124[0],
          (__int64)v46,
          (__int64)v45,
          (__int64)v44,
          (__int64)v43);
      }
    }
    else
    {
      std::wstring::wstring(v105, L"/dlpffe/createsasurl");
      LODWORD(v121) = RealtimeProtection::CSenseCloudCncProxy::CreateSasUrl(
                        (int)v127,
                        (int)hObject,
                        v27,
                        (int)v105,
                        (__int64)a2 + 320,
                        v128,
                        (__int64)v124);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
      v42 = (__int64 *)&qword_18025C818;
    }
    LODWORD(v95) = Dlp::FeatureControl::GetValue(189);
    v48 = (unsigned int)(v95 - 1);
    if ( (unsigned int)v48 <= 1 )
    {
      if ( *(_DWORD *)v124 == 403 )
      {
        if ( v129 )
        {
          v49 = v128;
          if ( v130 > 7 )
            v49 = (__int64 *)v128[0];
        }
        else
        {
          v49 = (__int64 *)&qword_18025C818;
        }
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs - HttpErrorCode 403 (storage full) received while creating SAS URL. hr =%#lx, h"
                                 "ttp response %ls ",
          "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
          (unsigned int)v121,
          v49);
        if ( (_DWORD)v95 == 1 )
        {
          CurrentUTCtoNextDayUTCDiffInMilliSeconds = RealtimeProtection::DlpUtils::GetCurrentUTCtoNextDayUTCDiffInMilliSeconds(v50);
        }
        else
        {
          Value = Dlp::FeatureControl::GetValue(190);
          CurrentUTCtoNextDayUTCDiffInMilliSeconds = Value;
          if ( !Value )
            CurrentUTCtoNextDayUTCDiffInMilliSeconds = 7200000;
        }
        *(_DWORD *)(v96 + 300) = 2;
        v53 = GetTickCount64() + CurrentUTCtoNextDayUTCDiffInMilliSeconds;
        *(_QWORD *)(v96 + 304) = v53;
        TickCount64 = GetTickCount64();
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs - Setting status to storage exhausted. Current time: %llu, Next attempt time: %llu  ",
          "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
          TickCount64,
          v53);
      }
      else if ( *((_DWORD *)v3 + 75) == 2 )
      {
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs - Storage status was exhausted but now it is available again. Resetting the MS storage status.",
          "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged");
        *((_DWORD *)v3 + 75) = 1;
        *((_QWORD *)v3 + 38) = 0;
      }
    }
    v55 = (unsigned int)v121;
    if ( (int)v121 >= 0 )
    {
      SasUrlResponse = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::ParseCreateSasUrlResponse(
                         v48,
                         v128,
                         v131);
      LODWORD(v121) = SasUrlResponse;
      if ( SasUrlResponse >= 0 )
      {
        memset(v147, 0, sizeof(v147));
        v148 = 0;
        CommonUtil::CAzureStorageClient::CAzureStorageClient(v147, v131);
        v127 = (wchar_t *)GetTickCount64();
        v67 = CommonUtil::CAzureStorageClient::UploadFileUsingSasUrl(v147, v5);
        LODWORD(v121) = v67;
        if ( v67 < 0 )
        {
          if ( v67 == -2147024713 )
          {
            v83 = (char *)a2 + 32;
            if ( *((_QWORD *)a2 + 7) > 7u )
              v83 = *(char **)v38;
            if ( *((_QWORD *)v5 + 3) > 7u )
              v5 = *(CommonUtil **)v5;
            RealtimeProtection::MpLogMessageImpl(
              (RealtimeProtection *)L"DLP::%hs file %ls already exists on storage hash value %ls",
              "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
              v5,
              v83);
            if ( g_pcsAsimovLock )
            {
              CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v105);
              if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
                && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
              {
                if ( *((_QWORD *)a2 + 7) > 7u )
                  v38 = *(const wchar_t **)v38;
                v117 = (__int64)v38;
                v85 = (_QWORD *)((char *)a2 + 288);
                if ( *((_QWORD *)a2 + 39) > 7u )
                  v85 = (_QWORD *)*v85;
                v114[0] = (__int64)v85;
                LODWORD(v127) = *((_DWORD *)g_aAsimov + 18);
                LODWORD(v96) = *((_DWORD *)g_aAsimov + 17);
                v101 = *((_DWORD *)g_aAsimov + 16);
                v100 = *((unsigned __int8 *)g_aAsimov + 60);
                v99 = *((unsigned __int8 *)g_aAsimov + 59);
                v98 = *((unsigned __int8 *)g_aAsimov + 58);
                v97 = *((unsigned __int8 *)g_aAsimov + 57);
                LODWORD(v95) = *((unsigned __int8 *)g_aAsimov + 56);
                v113 = *((_QWORD *)g_aAsimov + 6);
                v112 = *((_QWORD *)g_aAsimov + 5);
                v111 = *((_QWORD *)g_aAsimov + 4);
                v110 = *((_QWORD *)g_aAsimov + 3);
                v109 = *((_QWORD *)g_aAsimov + 2);
                v107 = *((_QWORD *)g_aAsimov + 1);
                v108 = 0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
                  v84,
                  (int)&byte_1802C78D5,
                  (__int64)&v108,
                  (__int64)&v107,
                  (__int64)&v109,
                  (__int64)&v110,
                  (__int64)&v111,
                  (__int64)&v112,
                  (__int64)&v113,
                  (__int64)&v95,
                  (__int64)&v97,
                  (__int64)&v98,
                  (__int64)&v99,
                  (__int64)&v100,
                  (__int64)&v101,
                  (__int64)&v96,
                  (__int64)&v127,
                  (__int64)v114,
                  (__int64)&v117);
              }
              CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v105);
            }
            *((_DWORD *)a2 + 96) = 2;
            CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)v147);
            RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
            web::details::uri_components::~uri_components((web::details::uri_components *)v149);
            if ( hObject )
              CloseHandle(hObject);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
            lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
            if ( v122 )
              operator delete(v122, v86);
            return 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v87 = v131;
              if ( v132.m128i_i64[1] > 7uLL )
                v87 = (__int64 *)v131[0];
              if ( *((_QWORD *)v5 + 3) > 7u )
                v5 = *(CommonUtil **)v5;
              WPP_SF_sSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5, (__int64)v87, v67);
              v67 = (int)v121;
            }
            if ( v122 )
            {
              operator delete(v122, v66);
              v122 = 0;
            }
            CommonUtil::NewSprintfW(
              (CommonUtil *)&v122,
              (wchar_t **)L"file upload failed hr:%#lx",
              (const wchar_t *)(unsigned int)v67);
            v126 = 5;
            RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::SetAuthTokenStatus(v104, v88);
            v89 = (unsigned int)v121;
            CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)v147);
            RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
            web::details::uri_components::~uri_components((web::details::uri_components *)v149);
            if ( hObject )
              CloseHandle(hObject);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
            lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
            if ( v122 )
              operator delete(v122, v90);
            return v89;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v68 = v131;
            if ( v132.m128i_i64[1] > 7uLL )
              v68 = (__int64 *)v131[0];
            v69 = (__int64)v5;
            if ( *((_QWORD *)v5 + 3) > 7u )
              v69 = *(_QWORD *)v5;
            WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v69, (__int64)v68);
          }
          if ( *((_QWORD *)v5 + 3) > 7u )
            v5 = *(CommonUtil **)v5;
          RealtimeProtection::MpLogMessageImpl(
            (RealtimeProtection *)L"DLP::%hs evidence file %s successfully uploaded",
            "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
            v5);
          v70 = GetTickCount64() - (_QWORD)v127;
          if ( g_pcsAsimovLock )
          {
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v105);
            if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
              && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
            {
              v120 = *((_QWORD *)a2 + 1);
              v119 = v70;
              v72 = (char *)a2 + 32;
              if ( *((_QWORD *)a2 + 7) > 7u )
                v72 = *(char **)v38;
              v108 = (__int64)v72;
              v73 = (_QWORD *)((char *)a2 + 288);
              if ( *((_QWORD *)a2 + 39) > 7u )
                v73 = (_QWORD *)*v73;
              v107 = (__int64)v73;
              LODWORD(v95) = *((_DWORD *)g_aAsimov + 18);
              v97 = *((_DWORD *)g_aAsimov + 17);
              v98 = *((_DWORD *)g_aAsimov + 16);
              v99 = *((unsigned __int8 *)g_aAsimov + 60);
              v100 = *((unsigned __int8 *)g_aAsimov + 59);
              v101 = *((unsigned __int8 *)g_aAsimov + 58);
              LODWORD(v96) = *((unsigned __int8 *)g_aAsimov + 57);
              LODWORD(v127) = *((unsigned __int8 *)g_aAsimov + 56);
              v109 = *((_QWORD *)g_aAsimov + 6);
              v110 = *((_QWORD *)g_aAsimov + 5);
              v111 = *((_QWORD *)g_aAsimov + 4);
              v112 = *((_QWORD *)g_aAsimov + 3);
              v113 = *((_QWORD *)g_aAsimov + 2);
              v114[0] = *((_QWORD *)g_aAsimov + 1);
              v117 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                v71,
                (int)&byte_1802C79DF,
                (__int64)&v117,
                (__int64)v114,
                (__int64)&v113,
                (__int64)&v112,
                (__int64)&v111,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v127,
                (__int64)&v96,
                (__int64)&v101,
                (__int64)&v100,
                (__int64)&v99,
                (__int64)&v98,
                (__int64)&v97,
                (__int64)&v95,
                (__int64)&v107,
                (__int64)&v108,
                (__int64)&v119,
                (__int64)&v120);
            }
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v105);
          }
          if ( v102 )
          {
            std::wstring::operator=(v153, v131);
            std::wstring::assign(v152, L"/dlpffe/commit");
            v75 = RealtimeProtection::CSenseCloudCncProxy::CommitSasUrl(*v116, v149, &v134, v128, v124);
            LODWORD(v121) = v75;
          }
          else
          {
            v76 = *v116;
            std::wstring::wstring(v105, L"/dlpffe/commit");
            LODWORD(v121) = RealtimeProtection::CSenseCloudCncProxy::CommitSasUrl(
                              v76,
                              (int)hObject,
                              (__int64)a2 + 32,
                              v106,
                              (int)v105,
                              (__int64)a2 + 320,
                              v128,
                              (__int64)v124);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
            v75 = (int)v121;
          }
          if ( v75 >= 0 )
          {
            *((_DWORD *)a2 + 96) = 2;
            CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)v147);
            RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
            web::details::uri_components::~uri_components((web::details::uri_components *)v149);
            if ( hObject )
              CloseHandle(hObject);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
            lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
            if ( v122 )
              operator delete(v122, v82);
            return 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v77 = v128;
              if ( v130 > 7 )
                v77 = (__int64 *)v128[0];
              WPP_SF_sddS(*((_QWORD *)WPP_GLOBAL_Control + 2), v75, v124[0], (__int64)v77);
              v75 = (int)v121;
            }
            if ( v129 )
            {
              v42 = v128;
              if ( v130 > 7 )
                v42 = (__int64 *)v128[0];
            }
            v78 = *(_DWORD *)v124;
            if ( v122 )
            {
              operator delete(v122, v74);
              v122 = 0;
            }
            CommonUtil::NewSprintfW(
              (CommonUtil *)&v122,
              (wchar_t **)L"Commit SasUrl failed for hr:%#lx, httpError:%d, response %ls",
              (const wchar_t *)(unsigned int)v75,
              v78,
              v42);
            v126 = 4;
            RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::SetAuthTokenStatus(v104, v79);
            v80 = (unsigned int)v121;
            CommonUtil::CAzureStorageClient::~CAzureStorageClient((CommonUtil::CAzureStorageClient *)v147);
            RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
            web::details::uri_components::~uri_components((web::details::uri_components *)v149);
            if ( hObject )
              CloseHandle(hObject);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
            lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
            if ( v122 )
              operator delete(v122, v81);
            return v80;
          }
        }
      }
      else
      {
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"DLP::%hs failed to parse sas url hr = %#lx",
          "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
          (unsigned int)SasUrlResponse);
        if ( v129 )
        {
          v42 = v128;
          if ( v130 > 7 )
            v42 = (__int64 *)v128[0];
        }
        v63 = (unsigned int)v121;
        if ( *((_QWORD *)a2 + 7) > 7u )
          v38 = *(const wchar_t **)v38;
        if ( v122 )
        {
          operator delete(v122, v62);
          v122 = 0;
        }
        CommonUtil::NewSprintfW(
          (CommonUtil *)&v122,
          (wchar_t **)L"Failed to parse sasurl for file:%ls hr:%#lx, response %ls",
          v38,
          v63,
          v42);
        v126 = 3;
        v64 = (unsigned int)v121;
        RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
        web::details::uri_components::~uri_components((web::details::uri_components *)v149);
        if ( hObject )
          CloseHandle(hObject);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
        lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
        if ( v122 )
          operator delete(v122, v65);
        return v64;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v56 = v128;
        if ( v130 > 7 )
          v56 = (__int64 *)v128[0];
        WPP_SF_sddS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v121, v124[0], (__int64)v56);
        v55 = (unsigned int)v121;
      }
      if ( v129 )
      {
        v42 = v128;
        if ( v130 > 7 )
          v42 = (__int64 *)v128[0];
      }
      v57 = *(_DWORD *)v124;
      if ( v122 )
      {
        operator delete(v122, v47);
        v122 = 0;
      }
      CommonUtil::NewSprintfW(
        (CommonUtil *)&v122,
        (wchar_t **)L"CreateSasUrl failed hr:%#lx, HttpErrorCode:%d, response %ls",
        (const wchar_t *)v55,
        v57,
        v42);
      v126 = 2;
      RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::SetAuthTokenStatus(v104, v58);
      v59 = (unsigned int)v121;
      RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS::~MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS((RealtimeProtection::MP_DLP_HTTP_REQUEST_ADDITIONAL_PARAMS *)&v134);
      web::details::uri_components::~uri_components((web::details::uri_components *)v149);
      if ( hObject )
        CloseHandle(hObject);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
      lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
      if ( v122 )
        operator delete(v122, v60);
      return v59;
    }
  }
  v127 = 0;
  v29 = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::ComputeAuthTokenWithObjectId(Instance, &v127);
  if ( (v29 & 0x80000000) == 0 )
  {
    v35 = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetAuthToken(Instance, v105);
    Src = (char *)a2 + 64;
    std::wstring::operator=((char *)a2 + 64, v35);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
    v36 = RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetObjectId(Instance, v105);
    v27 = (char *)a2 + 256;
    v106 = (char *)a2 + 256;
    std::wstring::operator=((char *)a2 + 256, v36);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v105);
    if ( v127 )
    {
      operator delete(v127, v37);
      Src = (char *)a2 + 64;
      v106 = (char *)a2 + 256;
    }
    v3 = (RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload *)v96;
    goto LABEL_71;
  }
  v30 = L"NULL";
  v31 = L"NULL";
  if ( v127 )
    v31 = v127;
  if ( v122 )
  {
    operator delete(v122, v28);
    v122 = 0;
  }
  CommonUtil::NewSprintfW(
    (CommonUtil *)&v122,
    (wchar_t **)L"GetAzureStorageTokenWithObjectID failed Error %#lxReason %ls",
    (const wchar_t *)v29,
    v31);
  v32 = (_QWORD *)((char *)a2 + 32);
  if ( v32[3] > 7u )
    v32 = (_QWORD *)*v32;
  if ( v122 )
    v30 = (const wchar_t *)v122;
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::%hs - Auth failure hr %#lx errorReason: %ls FileHash %ls",
    "RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::UploadFileMicrosoftManaged",
    v29,
    v30,
    v32);
  v126 = 1;
  if ( v127 )
    operator delete(v127, v33);
  if ( hObject )
    CloseHandle(hObject);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v128);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v131);
  lambda_ba9d7de3997961afeba486bb2f85a6b6_::operator()(v115);
  if ( v122 )
    operator delete(v122, v34);
  return v29;
}

```

## disassembly

```asm
0x180209ea0  mov     rax, rsp
0x180209ea3  mov     [rax+18h], rbx
0x180209ea7  mov     [rax+20h], rsi
0x180209eab  push    rdi
0x180209eac  push    r12
0x180209eae  push    r13
0x180209eb0  push    r14
0x180209eb2  push    r15
0x180209eb4  sub     rsp, 3D0h
0x180209ebb  movaps  xmmword ptr [rax-38h], xmm6
0x180209ebf  mov     rax, cs:__security_cookie
0x180209ec6  xor     rax, rsp
0x180209ec9  mov     [rsp+3F8h+var_48], rax
0x180209ed1  mov     r14, rdx
0x180209ed4  mov     rbx, rcx
0x180209ed7  mov     [rsp+3F8h+var_330], rcx
0x180209edf  xor     edi, edi
0x180209ee1  cmp     [rdx+180h], edi
0x180209ee7  jz      short loc_180209EF0
0x180209ee9  xor     eax, eax
0x180209eeb  jmp     loc_18020B8A6
0x180209ef0  lea     rsi, [rdx+60h]
0x180209ef4  mov     r8, rsi
0x180209ef7  cmp     qword ptr [rsi+18h], 7
0x180209efc  jbe     short loc_180209F01
0x180209efe  mov     r8, [rsi]
0x180209f01  lea     r13, aRealtimeprotec_43; "RealtimeProtection::DlpFileEvidence::Dl"...
0x180209f08  mov     rdx, r13; wchar_t *
0x180209f0b  lea     rcx, aDlpHsTryingUpl; "DLP::%hs trying upload file %s"
0x180209f12  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x180209f17  mov     dword ptr [rsp+3F8h+var_230], edi
0x180209f1e  mov     [rsp+3F8h+var_220], dil
0x180209f26  mov     [rsp+3F8h+var_228], rdi
0x180209f2e  mov     [rsp+3F8h+var_210], edi
0x180209f35  xorps   xmm0, xmm0
0x180209f38  movups  [rsp+3F8h+var_298], xmm0
0x180209f40  movups  [rsp+3F8h+var_288], xmm0
0x180209f48  movups  [rsp+3F8h+var_278], xmm0
0x180209f50  mov     byte ptr [rsp+3F8h+var_298], dil
0x180209f58  lea     rax, [rsp+3F8h+var_220]
0x180209f60  mov     qword ptr [rsp+3F8h+var_298+8], rax
0x180209f68  lea     rax, [rsp+3F8h+var_230]
0x180209f70  mov     qword ptr [rsp+3F8h+var_288], rax
0x180209f78  lea     rax, [rsp+3F8h+var_228]
0x180209f80  mov     qword ptr [rsp+3F8h+var_288+8], rax
0x180209f88  lea     rax, [rsp+3F8h+var_210]
0x180209f90  mov     qword ptr [rsp+3F8h+var_278], rax
0x180209f98  mov     qword ptr [rsp+3F8h+var_278+8], r14
0x180209fa0  mov     [rsp+3F8h+var_268], rbx
0x180209fa8  mov     ecx, 1
0x180209fad  mov     rax, cs:?g_pfnRoInitialize@@3P6AJW4RO_INIT_TYPE@@@ZEA; long (*g_pfnRoInitialize)(RO_INIT_TYPE)
0x180209fb4  call    cs:__guard_dispatch_icall_fptr
0x180209fba  mov     dword ptr [rsp+3F8h+var_230], eax
0x180209fc1  test    eax, eax
0x180209fc3  js      short loc_180209FCF
0x180209fc5  mov     [rsp+3F8h+var_220], 1
0x180209fcd  jmp     short loc_180209FE9
0x180209fcf  mov     [rsp+3F8h+var_220], dil
0x180209fd7  cmp     eax, 80010106h
0x180209fdc  jnz     loc_18020B829
0x180209fe2  mov     dword ptr [rsp+3F8h+var_230], edi
0x180209fe9  xorps   xmm0, xmm0
0x180209fec  movups  xmmword ptr [rsp+3F8h+var_1E0], xmm0
0x180209ff4  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180209ffc  movdqu  [rsp+3F8h+var_1D0], xmm6
0x18020a005  mov     word ptr [rsp+3F8h+var_1E0], di
0x18020a00d  movups  xmmword ptr [rsp+3F8h+var_200], xmm0
0x18020a015  mov     [rsp+3F8h+var_1F0], rdi
0x18020a01d  mov     [rsp+3F8h+var_1E8], 7
0x18020a029  mov     word ptr [rsp+3F8h+var_200], di
0x18020a031  mov     dword ptr [rsp+3F8h+var_21C], edi
0x18020a038  call    ?GetInstance@DlpFileEvidenceToken@DlpFileEvidence@RealtimeProtection@@SAAEAV123@XZ; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetInstance(void)
0x18020a03d  mov     r15, rax
0x18020a040  mov     [rsp+3F8h+var_308], rax
0x18020a048  mov     [rsp+3F8h+hObject], rdi
0x18020a050  mov     [rsp+3F8h+var_1C0.LowPart], edi
0x18020a057  mov     [rsp+3F8h+var_138], rdi
0x18020a05f  lea     r12, [rbx+8]
0x18020a063  mov     [rsp+3F8h+var_260], r12
0x18020a06b  cmp     [r12], rdi
0x18020a06f  jnz     short loc_18020A09B
0x18020a071  lea     rcx, [rsp+3F8h+var_258]
0x18020a079  call    ??$make_shared@VCSenseCloudCncProxy@RealtimeProtection@@$$V@std@@YA?AV?$shared_ptr@VCSenseCloudCncProxy@RealtimeProtection@@@0@XZ; std::make_shared<RealtimeProtection::CSenseCloudCncProxy,>(void)
0x18020a07e  mov     rdx, rax
0x18020a081  mov     rcx, r12
0x18020a084  call    ??4?$shared_ptr@VCSenseCloudCncProxy@RealtimeProtection@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<RealtimeProtection::CSenseCloudCncProxy>::operator=(std::shared_ptr<RealtimeProtection::CSenseCloudCncProxy> &&)
0x18020a089  mov     rcx, [rsp+3F8h+var_250]; this
0x18020a091  test    rcx, rcx
0x18020a094  jz      short loc_18020A09B
0x18020a096  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18020a09b  mov     rcx, rsi
0x18020a09e  cmp     qword ptr [rsi+18h], 7
0x18020a0a3  jbe     short loc_18020A0A8
0x18020a0a5  mov     rcx, [rsi]; this
0x18020a0a8  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x18020a0ad  cmp     eax, 80070002h
0x18020a0b2  jnz     short loc_18020A132
0x18020a0b4  cmp     qword ptr [rsi+18h], 7
0x18020a0b9  jbe     short loc_18020A0BE
0x18020a0bb  mov     rsi, [rsi]
0x18020a0be  mov     r8, rsi
0x18020a0c1  mov     rdx, r13; wchar_t *
0x18020a0c4  lea     rcx, aDlpHsFileLsAlr; "DLP::%hs file %ls already uploaded and "...
0x18020a0cb  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18020a0d0  mov     dword ptr [r14+180h], 2
0x18020a0db  mov     rcx, [rsp+3F8h+hObject]; hObject
0x18020a0e3  test    rcx, rcx
0x18020a0e6  jz      short loc_18020A0EF
0x18020a0e8  call    cs:__imp_CloseHandle
0x18020a0ee  nop
0x18020a0ef  lea     rcx, [rsp+3F8h+var_200]; void *
0x18020a0f7  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a0fc  nop
0x18020a0fd  lea     rcx, [rsp+3F8h+var_1E0]; void *
0x18020a105  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a10a  nop
0x18020a10b  lea     rcx, [rsp+3F8h+var_298+8]
0x18020a113  call    _lambda_ba9d7de3997961afeba486bb2f85a6b6___operator__
0x18020a118  nop
0x18020a119  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a121  test    rcx, rcx
0x18020a124  jz      short loc_18020A12B
0x18020a126  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a12b  xor     eax, eax
0x18020a12d  jmp     loc_18020B8A6
0x18020a132  cmp     [rbx+104h], dil
0x18020a139  jz      loc_18020A1E5
0x18020a13f  mov     rdx, r13; wchar_t *
0x18020a142  lea     rcx, aDlpHsShutdownP; "DLP::%hs Shutdown pending , exiting . "...
0x18020a149  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18020a14e  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a156  test    rcx, rcx
0x18020a159  jz      short loc_18020A168
0x18020a15b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a160  mov     [rsp+3F8h+var_228], rdi
0x18020a168  lea     r8, aUploadAbortedD; "Upload aborted due to shutdown"
0x18020a16f  lea     rdx, aLs_0; "%ls"
0x18020a176  lea     rcx, [rsp+3F8h+var_228]; this
0x18020a17e  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18020a183  mov     dword ptr [r14+180h], 1
0x18020a18e  mov     rcx, [rsp+3F8h+hObject]; hObject
0x18020a196  test    rcx, rcx
0x18020a199  jz      short loc_18020A1A2
0x18020a19b  call    cs:__imp_CloseHandle
0x18020a1a1  nop
0x18020a1a2  lea     rcx, [rsp+3F8h+var_200]; void *
0x18020a1aa  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a1af  nop
0x18020a1b0  lea     rcx, [rsp+3F8h+var_1E0]; void *
0x18020a1b8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a1bd  nop
0x18020a1be  lea     rcx, [rsp+3F8h+var_298+8]
0x18020a1c6  call    _lambda_ba9d7de3997961afeba486bb2f85a6b6___operator__
0x18020a1cb  nop
0x18020a1cc  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a1d4  test    rcx, rcx
0x18020a1d7  jz      short loc_18020A1DE
0x18020a1d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a1de  xor     eax, eax
0x18020a1e0  jmp     loc_18020B8A6
0x18020a1e5  mov     r8d, [r14+4]; unsigned int
0x18020a1e9  mov     rdx, [r14+18h]; unsigned __int64
0x18020a1ed  call    ?IsRetentionPeriodExpired@DlpFileEvidenceUpload@DlpFileEvidence@RealtimeProtection@@AEAA_N_KK@Z; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceUpload::IsRetentionPeriodExpired(unsigned __int64,ulong)
0x18020a1f2  test    al, al
0x18020a1f4  jz      loc_18020A2AD
0x18020a1fa  cmp     qword ptr [rsi+18h], 7
0x18020a1ff  jbe     short loc_18020A204
0x18020a201  mov     rsi, [rsi]
0x18020a204  mov     r8, rsi
0x18020a207  mov     rdx, r13; wchar_t *
0x18020a20a  lea     rcx, aDlpHsRetention; "DLP::%hs Retention period expired for %"...
0x18020a211  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18020a216  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a21e  test    rcx, rcx
0x18020a221  jz      short loc_18020A230
0x18020a223  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a228  mov     [rsp+3F8h+var_228], rdi
0x18020a230  lea     r8, aRetentionPerio; "Retention Period expired"
0x18020a237  lea     rdx, aLs_0; "%ls"
0x18020a23e  lea     rcx, [rsp+3F8h+var_228]; this
0x18020a246  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18020a24b  mov     dword ptr [r14+180h], 1
0x18020a256  mov     rcx, [rsp+3F8h+hObject]; hObject
0x18020a25e  test    rcx, rcx
0x18020a261  jz      short loc_18020A26A
0x18020a263  call    cs:__imp_CloseHandle
0x18020a269  nop
0x18020a26a  lea     rcx, [rsp+3F8h+var_200]; void *
0x18020a272  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a277  nop
0x18020a278  lea     rcx, [rsp+3F8h+var_1E0]; void *
0x18020a280  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a285  nop
0x18020a286  lea     rcx, [rsp+3F8h+var_298+8]
0x18020a28e  call    _lambda_ba9d7de3997961afeba486bb2f85a6b6___operator__
0x18020a293  nop
0x18020a294  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a29c  test    rcx, rcx
0x18020a29f  jz      short loc_18020A2A6
0x18020a2a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a2a6  xor     eax, eax
0x18020a2a8  jmp     loc_18020B8A6
0x18020a2ad  mov     rcx, [rsp+3F8h+hObject]; hObject
0x18020a2b5  test    rcx, rcx
0x18020a2b8  jz      short loc_18020A2C8
0x18020a2ba  call    cs:__imp_CloseHandle
0x18020a2c0  mov     [rsp+3F8h+hObject], rdi
0x18020a2c8  lea     r8, [rsp+3F8h+var_1C0]; struct _LUID *
0x18020a2d0  lea     rdx, [rsp+3F8h+var_138]; void **
0x18020a2d8  lea     rcx, [rsp+3F8h+hObject]; phToken
0x18020a2e0  call    ?UtilGetLatestActiveLogonSession@CommonUtil@@YAJPEAPEAXPEAU_LUID@@PEAK@Z; CommonUtil::UtilGetLatestActiveLogonSession(void * *,_LUID *,ulong *)
0x18020a2e5  mov     dword ptr [rsp+3F8h+var_230], eax
0x18020a2ec  test    eax, eax
0x18020a2ee  jns     loc_18020A3A6
0x18020a2f4  mov     r8d, eax
0x18020a2f7  mov     rdx, r13; wchar_t *
0x18020a2fa  lea     rcx, aDlpHsFailedToF; "DLP::%hs failed to fetch impersonation "...
0x18020a301  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18020a306  mov     ebx, dword ptr [rsp+3F8h+var_230]
0x18020a30d  mov     esi, ebx
0x18020a30f  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a317  test    rcx, rcx
0x18020a31a  jz      short loc_18020A330
0x18020a31c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a321  mov     [rsp+3F8h+var_228], rdi
0x18020a329  mov     ebx, dword ptr [rsp+3F8h+var_230]
0x18020a330  mov     r9d, esi
0x18020a333  lea     r8, aFailedToGetImp; "Failed to get impersonation token error"...
0x18020a33a  lea     rdx, aLsLx; "%ls%#lx"
0x18020a341  lea     rcx, [rsp+3F8h+var_228]; this
0x18020a349  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18020a34e  nop
0x18020a34f  mov     rcx, [rsp+3F8h+hObject]; hObject
0x18020a357  test    rcx, rcx
0x18020a35a  jz      short loc_18020A363
0x18020a35c  call    cs:__imp_CloseHandle
0x18020a362  nop
0x18020a363  lea     rcx, [rsp+3F8h+var_200]; void *
0x18020a36b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a370  nop
0x18020a371  lea     rcx, [rsp+3F8h+var_1E0]; void *
0x18020a379  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a37e  nop
0x18020a37f  lea     rcx, [rsp+3F8h+var_298+8]
0x18020a387  call    _lambda_ba9d7de3997961afeba486bb2f85a6b6___operator__
0x18020a38c  nop
0x18020a38d  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a395  test    rcx, rcx
0x18020a398  jz      short loc_18020A39F
0x18020a39a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a39f  mov     eax, ebx
0x18020a3a1  jmp     loc_18020B8A6
0x18020a3a6  mov     rcx, r15; this
0x18020a3a9  call    ?IsAuthComputed@DlpFileEvidenceToken@DlpFileEvidence@RealtimeProtection@@QEBA_NXZ; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::IsAuthComputed(void)
0x18020a3ae  test    al, al
0x18020a3b0  jz      short loc_18020A41F
0x18020a3b2  lea     rdx, [rsp+3F8h+var_300]
0x18020a3ba  mov     rcx, r15
0x18020a3bd  call    ?GetAuthToken@DlpFileEvidenceToken@DlpFileEvidence@RealtimeProtection@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetAuthToken(void)
0x18020a3c2  lea     rcx, [r14+40h]
0x18020a3c6  mov     [rsp+3F8h+Src], rcx
0x18020a3ce  mov     rdx, rax
0x18020a3d1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18020a3d6  lea     rcx, [rsp+3F8h+var_300]; void *
0x18020a3de  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a3e3  lea     rdx, [rsp+3F8h+var_300]
0x18020a3eb  mov     rcx, r15
0x18020a3ee  call    ?GetObjectId@DlpFileEvidenceToken@DlpFileEvidence@RealtimeProtection@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::GetObjectId(void)
0x18020a3f3  lea     r12, [r14+100h]
0x18020a3fa  mov     [rsp+3F8h+var_2E0], r12
0x18020a402  mov     rdx, rax
0x18020a405  mov     rcx, r12
0x18020a408  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18020a40d  lea     rcx, [rsp+3F8h+var_300]; void *
0x18020a415  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18020a41a  jmp     loc_18020A5D4
0x18020a41f  mov     [rsp+3F8h+var_208], rdi
0x18020a427  lea     rdx, [rsp+3F8h+var_208]; wchar_t **
0x18020a42f  mov     rcx, r15; this
0x18020a432  call    ?ComputeAuthTokenWithObjectId@DlpFileEvidenceToken@DlpFileEvidence@RealtimeProtection@@QEAAJPEAPEA_W@Z; RealtimeProtection::DlpFileEvidence::DlpFileEvidenceToken::ComputeAuthTokenWithObjectId(wchar_t * *)
0x18020a437  mov     ebx, eax
0x18020a439  test    eax, eax
0x18020a43b  jns     loc_18020A53E
0x18020a441  lea     rsi, aNull_3; "NULL"
0x18020a448  mov     r15, rsi
0x18020a44b  cmp     [rsp+3F8h+var_208], rdi
0x18020a453  cmovnz  r15, [rsp+3F8h+var_208]
0x18020a45c  mov     rcx, [rsp+3F8h+var_228]; void *
0x18020a464  test    rcx, rcx
0x18020a467  jz      short loc_18020A476
0x18020a469  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18020a46e  mov     [rsp+3F8h+var_228], rdi
0x18020a476  mov     r9, r15
0x18020a479  mov     r8d, ebx; wchar_t *
0x18020a47c  lea     rdx, aGetazurestorag; "GetAzureStorageTokenWithObjectID failed"...
0x18020a483  lea     rcx, [rsp+3F8h+var_228]; this
0x18020a48b  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18020a490  add     r14, 20h ; ' '
0x18020a494  cmp     qword ptr [r14+18h], 7
0x18020a499  jbe     short loc_18020A49E
  ... truncated ...
```
