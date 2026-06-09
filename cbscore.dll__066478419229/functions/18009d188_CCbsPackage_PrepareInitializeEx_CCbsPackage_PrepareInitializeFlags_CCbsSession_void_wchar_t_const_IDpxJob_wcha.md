# CCbsPackage::PrepareInitializeEx(CCbsPackage::PrepareInitializeFlags,CCbsSession *,void *,wchar_t const *,IDpxJob *,wchar_t const *,wchar_t const *,_CbsPackageType,ulong,PerSessionPackageState *,ParsingSession * *,CCbsPackage::PrepareInitializeDisposition *)

- ea: `0x18009d188`
- end: `0x18009f706`
- name: `?PrepareInitializeEx@CCbsPackage@@QEAAJW4PrepareInitializeFlags@1@PEAVCCbsSession@@PEAXPEB_WPEAUIDpxJob@@33W4_CbsPackageType@@KPEAUPerSessionPackageState@@PEAPEAUParsingSession@@PEAW4PrepareInitializeDisposition@1@@Z`
- size: `9598`
- prototype: `int __high(enum CCbsPackage::PrepareInitializeFlags, struct CCbsSession *, void *, const wchar_t *, struct IDpxJob *, const wchar_t *, const wchar_t *, enum _CbsPackageType, unsigned int, struct PerSessionPackageState *, struct ParsingSession **, enum CCbsPackage::PrepareInitializeDisposition *)`
- caller_count: `2`
- callee_count: `54`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fa74`
- `0x18009c068`

## callees

- `0x18000b46c`
- `0x18000c248`
- `0x18000c58c`
- `0x18000c5b4`
- `0x180010cc0`
- `0x1800115a8`
- `0x180012fe4`
- `0x180013250`
- `0x180015420`
- `0x180016250`
- `0x180016d40`
- `0x18001837c`
- `0x1800261e0`
- `0x180028e24`
- `0x18002a2bc`
- `0x18002e280`
- `0x18002ec34`
- `0x180033f58`
- `0x18003404c`
- `0x180042448`
- `0x1800439a0`
- `0x1800532d4`
- `0x180056e00`
- `0x1800576cc`
- `0x180057c28`
- `0x18005aa38`
- `0x18005eef0`
- `0x180073b74`
- `0x180073d94`
- `0x180093a70`
- `0x18009564c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x18009d188`
- `0x1800a8678`
- `0x1800c003c`
- `0x1800c1958`
- `0x1800c1984`
- `0x1800eb920`
- `0x1800ed210`
- `0x1800f1d54`
- `0x180126f30`
- `0x18012c6d8`
- `0x18012cfcc`
- `0x180143f5c`
- `0x18019e7c8`
- `0x18019eb64`
- `0x18019eba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d5a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2e5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009d837`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009dfbd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e2bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e8e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009d837`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009dfbd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e2bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e8e1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009d2d3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009d2d3`

## string_xrefs

- `0x18009d599`: `update`
- `0x18009f0fa`: `Failed to create private session store.`
- `0x18009dec9`: `Failed to cache package identity in the package property.`
- `0x18009ed95`: `Failed to cache package identity in the package property.`
- `0x18009dae0`: `Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}`
- `0x18009e310`: `Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}`
- `0x18009dba9`: `Failed to create package extract job for location: {}`
- `0x18009e011`: `Failed to create package extract job for location: {}`
- `0x18009ddee`: `Failed to allocate CbsIdentity for onepackage.`
- `0x18009ecda`: `Failed to allocate CbsIdentity for onepackage.`
- `0x18009de5d`: `Failed to get CbsIdentity for this onepackage.`
- `0x18009ed39`: `Failed to get CbsIdentity for this onepackage.`
- `0x18009d5e1`: `Failed to get target servicing directory.`
- `0x18009d2a2`: `Unable to get non-TI token.`
- `0x18009d300`: `Unable to duplicate non-TI token.`
- `0x18009d365`: `A User token is required on non-existing packages.`
- `0x18009f059`: `Failed to parse package manifest: {}`
- `0x18009f209`: `Failed to copy manifest: {} to private store and verify the content.`
- `0x18009f30a`: `Failed cache package identity in the package property.`
- `0x18009e4ed`: `Failed to parse the package manifest {}`
- `0x18009e602`: `Failed to get CbsIdentity for this package.`
- `0x18009f280`: `Failed to get CbsIdentity for this package.`
- `0x18009e11e`: `Failed to extract package manifest from cabinet`
- `0x18009e774`: `Failed to extract package manifest from cabinet`
- `0x18009e19f`: `Opened cabinet package, package directory: {}, sandbox location: {}, cabinet location: {}, manifest location: {}`
- `0x18009ee6b`: `Failed to parse package manifest from given buffer`

## pseudocode

```c
__int64 __fastcall CCbsPackage::PrepareInitializeEx(
        __int64 a1,
        unsigned int a2,
        CCbsSession *a3,
        __int64 a4,
        const WCHAR *a5,
        __int64 a6,
        const WCHAR *lpFileName,
        __int64 a8,
        int a9,
        int a10,
        __int64 a11,
        ParsingSession **a12,
        unsigned int *a13)
{
  CCbsSession *v14; // rbx
  __int64 v15; // rsi
  int v16; // eax
  ParsingSession **v17; // rcx
  char v18; // di
  void **InitPointer; // rax
  int NonTiToken; // ebx
  void **v21; // rax
  signed int LastError; // eax
  signed int v23; // ebx
  unsigned int v24; // ebx
  int v25; // edx
  __int64 v26; // rdx
  int v27; // edx
  unsigned int v28; // edx
  ParsingSession *v29; // rcx
  int ServicingDirectory; // eax
  __int64 v31; // rcx
  struct Windows::Rtl::StopWatch *v32; // r9
  int v33; // edx
  unsigned int v34; // edx
  ParsingSession *v35; // rcx
  ParsingSession *v36; // rsi
  int v37; // edx
  __int64 v38; // rdx
  DWORD FileAttributesW; // eax
  LPCWCH *v40; // rbx
  int v41; // edi
  __int64 v42; // rdx
  unsigned int v43; // edx
  wchar_t *v45; // rdi
  int v46; // r12d
  __int64 v47; // rdx
  unsigned int v48; // edx
  int v49; // eax
  int v50; // edx
  struct IDpxJob **v51; // r12
  __int64 v52; // rcx
  struct IDpxJob **v53; // rax
  int v54; // eax
  int v55; // edx
  int v56; // eax
  int v57; // edx
  int v58; // eax
  unsigned int v59; // edx
  _QWORD *v60; // rdi
  int v61; // eax
  int v62; // edx
  int v63; // eax
  int v64; // edx
  int v65; // eax
  int v66; // edx
  unsigned int v67; // edx
  struct IDpxJob **v68; // rax
  int v69; // eax
  int v70; // edx
  int v71; // eax
  int v72; // edx
  int SingleFileFromCabinet; // eax
  int v74; // edx
  int v75; // edx
  int v76; // r8d
  int v77; // eax
  __int64 v78; // rdx
  wchar_t *v79; // rbx
  int v80; // eax
  int v81; // eax
  int v82; // edx
  unsigned int v83; // r12d
  __int64 v84; // rcx
  CCbsSession *v85; // rdi
  int v86; // eax
  __int64 v87; // rcx
  __int64 v88; // r9
  struct Windows::Rtl::StopWatch *v89; // r9
  struct ParsingSession *v90; // rbx
  int v91; // eax
  int v92; // edi
  __int64 v93; // rcx
  struct CCbsIdentity **v94; // rax
  int v95; // eax
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rdx
  unsigned __int64 v99; // r9
  int v100; // eax
  int v101; // eax
  wchar_t *v102; // rdi
  int v103; // eax
  wchar_t *v104; // rbx
  int v105; // eax
  int v106; // eax
  __int64 v107; // rcx
  __int64 v108; // rcx
  int v109; // eax
  __int64 v110; // rcx
  _QWORD *v111; // rbx
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rdx
  int v115; // edi
  int v116; // edx
  wchar_t *v117; // r12
  int v118; // eax
  unsigned int v119; // edx
  _QWORD *v120; // rdi
  int CbsIdentity; // eax
  __int64 v122; // rcx
  __int64 v123; // rcx
  int v124; // eax
  __int64 v125; // rcx
  __int64 v126; // rcx
  int v127; // eax
  __int64 v128; // rcx
  __int64 v129; // rcx
  __int64 v130; // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  char v133; // di
  __int64 v134; // rcx
  __int64 v135; // rcx
  __int64 v136; // rax
  int SessionSandbox; // eax
  __int64 v138; // rcx
  __int64 v139; // rcx
  CCbsSession *v140; // rdi
  int v141; // eax
  __int64 v142; // rdx
  CCbsSession *v143; // r12
  __int64 v144; // rcx
  __int64 v145; // rcx
  int CbsIdentityFromAssemblyIdentity; // eax
  __int64 v147; // rcx
  __int64 v148; // rcx
  __int64 v149; // rdx
  const wchar_t **v150; // rdi
  int v151; // eax
  __int64 v152; // rcx
  __int64 v153; // rcx
  __int64 v154; // rax
  unsigned __int64 v155; // rcx
  const wchar_t *v156; // rax
  unsigned __int64 v157; // rdx
  unsigned __int64 v158; // rcx
  bool v159; // zf
  __int64 v160; // rcx
  CCbsSession *v161; // rcx
  int OfflineServicingStackVersion; // eax
  __int64 v163; // rcx
  __int64 v164; // rcx
  unsigned __int64 v165; // rcx
  unsigned __int64 v166; // rdx
  const wchar_t *v167; // rax
  unsigned __int64 v168; // rcx
  unsigned __int64 v169; // rdx
  __int64 v170; // rcx
  const wchar_t *v171; // rax
  wchar_t *v172; // [rsp+20h] [rbp-E0h]
  int v173; // [rsp+20h] [rbp-E0h]
  wchar_t *v174; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v175; // [rsp+68h] [rbp-98h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v177; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v178; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v179; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v180; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v181; // [rsp+98h] [rbp-68h] BYREF
  __int64 v182; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v183; // [rsp+A8h] [rbp-58h] BYREF
  struct ParsingSession *v184; // [rsp+B0h] [rbp-50h] BYREF
  ParsingSession *v185; // [rsp+B8h] [rbp-48h] BYREF
  LPCWCH lpWideCharStr; // [rsp+C0h] [rbp-40h] BYREF
  int v187[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v188; // [rsp+D0h] [rbp-30h] BYREF
  char v189; // [rsp+D8h] [rbp-28h]
  int v190[2]; // [rsp+E0h] [rbp-20h] BYREF
  ParsingSession **v191; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v192; // [rsp+F0h] [rbp-10h] BYREF
  ParsingSession **v193; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v194; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v195; // [rsp+108h] [rbp+8h] BYREF
  __int64 v196; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v197[2]; // [rsp+118h] [rbp+18h] BYREF
  char v198; // [rsp+128h] [rbp+28h]
  int v199; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v200; // [rsp+134h] [rbp+34h] BYREF
  __int64 v201; // [rsp+138h] [rbp+38h] BYREF
  __int64 v202; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v203; // [rsp+148h] [rbp+48h] BYREF
  CCbsSession *v204; // [rsp+150h] [rbp+50h] BYREF
  int v205; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v14 = a3;
  v15 = a4;
  lpWideCharStr = a5;
  v197[0] = &a13;
  v197[1] = &v200;
  v203 = a2;
  v195 = vServicingStackVersion;
  v16 = a9;
  v194 = a6;
  v17 = a12;
  v196 = a4;
  v204 = a3;
  v192 = a8;
  v193 = a12;
  v200 = 0;
  v198 = 1;
  v185 = 0;
  v181 = 0;
  v174 = 0;
  v180 = 0;
  v183 = 0;
  v182 = 0;
  v175 = 0;
  v179 = 0;
  v184 = 0;
  v178 = 0;
  v177 = 0;
  v201 = 0;
  if ( a9 == 1 || a9 <= -2 || (v18 = 1, a9 >= 4) )
    v18 = 0;
  ExistingTokenHandle = 0;
  v202 = 0;
  if ( !v18 && !a4 )
  {
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                             &ExistingTokenHandle,
                             0);
    NonTiToken = GetNonTiToken(InitPointer);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)NonTiToken, "Unable to get non-TI token.");
    if ( NonTiToken >= 0 )
    {
      v21 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                       &v202,
                       0);
      if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, v21) )
        goto LABEL_12;
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)v23, "Unable to duplicate non-TI token.");
      if ( v23 >= 0 )
      {
LABEL_12:
        v15 = v202;
        v196 = v202;
      }
    }
    v14 = v204;
    v16 = a9;
    v17 = v193;
  }
  v188 = v15;
  v189 = 0;
  if ( !v18 && !v15 )
  {
    v24 = -2146498560;
    v199 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "A User token is required on non-existing packages.");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v26 = 367;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    if ( a13 )
      *a13 = v200;
    return v24;
  }
  if ( !v17 )
  {
    v24 = -2147467261;
    v199 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No parsing session result specified");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v27) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v27,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v26 = 369;
    goto LABEL_19;
  }
  *(_DWORD *)(a1 + 864) = v16;
  *(_DWORD *)(a1 + 104) = a10;
  *(_BYTE *)(a1 + 1058) = 0;
  if ( !Windows::AutoNewPtr<ParsingSession>::Allocate<>(&v185) )
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)0x8007000ELL,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    v29 = v185;
    if ( !v185 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v199 = _o__wcsicmp(L"update", a8);
  ServicingDirectory = CCbsSession::GetServicingDirectory(v14, L"Packages", &v179);
  v24 = ServicingDirectory;
  if ( ServicingDirectory < 0 )
  {
    v199 = ServicingDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get target servicing directory.");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v33,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    v35 = v185;
    if ( !v185 )
      goto LABEL_35;
    goto LABEL_34;
  }
  v36 = v185;
  v205 = v203 & 1;
  if ( a9 )
  {
    v115 = v203 & 2;
    v203 = v115;
    if ( a9 == 2 )
    {
      if ( !a11 )
      {
        v24 = -2147024809;
        v203 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<>(v31, 3, "No per-session package state specified for package");
          *(_QWORD *)v187 = &v203;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v132, 3, ": {}", v187);
        }
        v88 = 2147942487LL;
        v78 = 629;
        goto LABEL_215;
      }
    }
    else
    {
      if ( a9 == 3 )
      {
        v24 = ParseCbsPackageFromBuffer(lpWideCharStr, v185);
        if ( (v24 & 0x80000000) != 0 )
        {
          if ( v115 )
            v200 |= 4u;
          else
            CCbsSession::MarkPackageStoreCorrupt(v204);
          v199 = v24;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v130, 3, "Failed to parse package manifest from given buffer");
            *(_QWORD *)v187 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v131, 3, ": {}", v187);
          }
          v88 = v24;
          v78 = 625;
          goto LABEL_215;
        }
        goto LABEL_289;
      }
      if ( !a11 )
      {
        v24 = -2147024809;
        v203 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No state specified for package");
          *(_QWORD *)v187 = &v203;
          LOBYTE(v116) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v116,
            3,
            (unsigned int)": {}",
            (__int64)v187);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x240,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)0x80070057LL,
          (int)v172);
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
        if ( !v36 )
          goto LABEL_28;
        v29 = v36;
LABEL_27:
        ParsingSession::`scalar deleting destructor'(v29, v28);
LABEL_28:
        if ( a13 )
          *a13 = v200;
        return v24;
      }
      v117 = (wchar_t *)lpWideCharStr;
      v24 = DirectoryFromPath((wchar_t *)lpWideCharStr);
      if ( (v24 & 0x80000000) != 0 )
      {
        v38 = 578;
        goto LABEL_44;
      }
      v24 = PathPrefix(a11 + 16);
      if ( (v24 & 0x80000000) != 0 )
      {
        v38 = 579;
        goto LABEL_44;
      }
      v24 = SczAllocFromSz(a11 + 32, v117);
      if ( (v24 & 0x80000000) != 0 )
      {
        v38 = 580;
        goto LABEL_44;
      }
      v118 = PathPrefix(a11 + 32);
      v24 = v118;
      if ( v118 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v118,
          (int)v172);
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
        if ( v36 )
          ParsingSession::`scalar deleting destructor'(v36, v119);
        goto LABEL_330;
      }
      v77 = DirectoryFromPath(v117);
      v24 = v77;
      if ( v77 < 0 )
      {
        v78 = 582;
        goto LABEL_214;
      }
      v77 = PathPrefix(a11 + 24);
      v24 = v77;
      if ( v77 < 0 )
      {
        v78 = 583;
        goto LABEL_214;
      }
      v77 = SczAllocConcat2Sz(&v175, *(_QWORD *)(a11 + 24), L"desktopdeployment.cab");
      v24 = v77;
      if ( v77 < 0 )
      {
        v78 = 584;
        goto LABEL_214;
      }
      if ( !v199 && (unsigned int)DoesFileExist(v175, 0) )
      {
        v120 = (_QWORD *)(a1 + 112);
        *(_BYTE *)(a1 + 1058) = 1;
        *(_DWORD *)(a1 + 92) = 1;
        CbsIdentity = CreateCbsIdentity((struct CCbsIdentity **)(a1 + 112));
        v24 = CbsIdentity;
        if ( CbsIdentity < 0 )
        {
          v199 = CbsIdentity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v122, 3, "Failed to allocate CbsIdentity for onepackage.");
            *(_QWORD *)v187 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v123, 3, ": {}", v187);
          }
          v88 = v24;
          v78 = 594;
          goto LABEL_215;
        }
        v124 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v120 + 56LL))(
                 *v120,
                 L"OnePackage~~~~0.0.0.0");
        v24 = v124;
        if ( v124 < 0 )
        {
          v199 = v124;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v125, 3, "Failed to get CbsIdentity for this onepackage.");
            *(_QWORD *)v187 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v126, 3, ": {}", v187);
          }
          v88 = v24;
          v78 = 597;
          goto LABEL_215;
        }
        v127 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v120 + 72LL))(*v120, a1 + 120);
        v24 = v127;
        if ( v127 < 0 )
        {
          v199 = v127;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v128, 3, "Failed to cache package identity in the package property.");
            *(_QWORD *)v187 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v129, 3, ": {}", v187);
          }
          v88 = v24;
          v78 = 600;
          goto LABEL_215;
        }
        CCbsPackage::SetCurrentState(a1, 0, 1);
      }
      if ( a9 == -1 || a9 == 4 )
      {
        v77 = FileReplaceExtension(*(wchar_t **)(a11 + 32));
        v24 = v77;
        if ( v77 < 0 )
        {
          v78 = 637;
          goto LABEL_214;
        }
        v77 = SczAllocFromSz(a11 + 48, v174);
        v24 = v77;
        if ( v77 < 0 )
        {
          v78 = 638;
          goto LABEL_214;
        }
        goto LABEL_259;
      }
    }
    if ( !*(_BYTE *)(a1 + 1058) )
    {
      v77 = SczAllocFormatted(&v174, L"%ws.cat", v192);
      v24 = v77;
      if ( v77 < 0 )
      {
        v78 = 744;
        goto LABEL_214;
      }
      v77 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v174);
      v24 = v77;
      if ( v77 < 0 )
      {
        v78 = 745;
        goto LABEL_214;
      }
      goto LABEL_190;
    }
LABEL_259:
    v133 = v205;
    if ( a9 == -1 )
    {
      v24 = ParseCbsPackage(0, *(const wchar_t *const *)(a11 + 32), v36, v32);
      if ( (v24 & 0x80000000) != 0 )
      {
        if ( v203 )
        {
          v134 = v200 | 4;
          v200 |= 4u;
        }
        else
        {
          CCbsSession::MarkPackageStoreCorrupt(v204);
          v134 = v200;
        }
        if ( v24 != -2147024894 || !v133 )
        {
          v199 = v24;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v187 = *(_QWORD *)(a11 + 32);
            LogAdapter::Logger::LogPartial<wchar_t *>(v134, 3, "Failed to parse package manifest: {}", v187);
            *(_QWORD *)v190 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v135, 3, ": {}", v190);
          }
          v88 = v24;
          v78 = 770;
          goto LABEL_215;
        }
        v200 = v134 | 2;
LABEL_267:
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
        v24 = 1;
        goto LABEL_330;
      }
      goto LABEL_289;
    }
    goto LABEL_190;
  }
  if ( !a11 )
  {
    v24 = -2147024809;
    v203 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No state specified for cabinet package");
      lpWideCharStr = (LPCWCH)&v203;
      LOBYTE(v37) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v37,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v38 = 404;
    goto LABEL_44;
  }
  v24 = DirectoryFromPath((wchar_t *)lpWideCharStr);
  if ( (v24 & 0x80000000) != 0 )
  {
    v38 = 405;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    if ( !v36 )
    {
LABEL_35:
      if ( a13 )
        *a13 = v200;
      return v24;
    }
    v35 = v36;
LABEL_34:
    ParsingSession::`scalar deleting destructor'(v35, v34);
    goto LABEL_35;
  }
  v24 = PathPrefix(a11 + 16);
  if ( (v24 & 0x80000000) != 0 )
  {
    v38 = 406;
    goto LABEL_44;
  }
  if ( lpFileName
    && ((FileAttributesW = GetFileAttributesW(lpFileName), FileAttributesW != -1) && (FileAttributesW & 0x10) != 0
     || (int)RecursivelyCreateDirectory(lpFileName, 0) >= 0) )
  {
    v40 = (LPCWCH *)(a11 + 24);
    v41 = SczAllocFromSz(a11 + 24, lpFileName);
    if ( v41 < 0 )
    {
      v42 = 430;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v41,
        (int)v172);
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
      if ( v36 )
        ParsingSession::`scalar deleting destructor'(v36, v43);
      if ( a13 )
        *a13 = v200;
      return (unsigned int)v41;
    }
  }
  else
  {
    v40 = (LPCWCH *)(a11 + 24);
    v41 = SczAllocFromSz(a11 + 24, *(_QWORD *)(a11 + 16));
    if ( v41 < 0 )
    {
      v42 = 440;
      goto LABEL_54;
    }
  }
  v41 = PathPrefix(v40);
  if ( v41 < 0 )
  {
    v42 = 443;
    goto LABEL_54;
  }
  v41 = SczEnsureBackslashTerminated(v40);
  if ( v41 < 0 )
  {
    v42 = 445;
    goto LABEL_54;
  }
  v41 = SczAllocFormatted(&v181, L"%s.mum", v192);
  if ( v41 < 0 )
  {
    v42 = 447;
    goto LABEL_54;
  }
  v45 = v181;
  v46 = SczAllocConcat2Sz(a11 + 32, *v40, v181);
  if ( v46 < 0 )
  {
    v47 = 449;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)(unsigned int)v46,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    if ( v36 )
      ParsingSession::`scalar deleting destructor'(v36, v48);
    if ( a13 )
      *a13 = v200;
    return (unsigned int)v46;
  }
  v191 = (ParsingSession **)(a11 + 40);
  v46 = SczAllocFromSz(a11 + 40, lpWideCharStr);
  if ( v46 < 0 )
  {
    v47 = 451;
    goto LABEL_69;
  }
  v46 = PathPrefix(a11 + 40);
  if ( v46 < 0 )
  {
    v47 = 453;
    goto LABEL_69;
  }
  v49 = NestableImpersonator::Impersonate((NestableImpersonator *)&v188);
  v46 = v49;
  if ( v49 < 0 )
  {
    v199 = v49;
    if ( LogAdapter::g_Logger )
    {
      lpWideCharStr = *v40;
      v184 = (struct ParsingSession *)v45;
      v185 = *v191;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}",
        (__int64)&v185,
        (__int64)&v184,
        (__int64)&lpWideCharStr);
      v204 = (CCbsSession *)&v199;
      LOBYTE(v50) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v50,
        3,
        (unsigned int)": {}",
        (__int64)&v204);
    }
    v47 = 460;
    goto LABEL_69;
  }
  v51 = (struct IDpxJob **)(a11 + 192);
  if ( !*(_QWORD *)(a11 + 192) )
  {
    v52 = a11 + 192;
    if ( v194 )
    {
      Windows::AutoComPtr<CCbsPublicSession>::TakeReference(v52, v194);
    }
    else
    {
      v53 = (struct IDpxJob **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v52);
      v54 = Dpx_DpxNewJob(*v40, v53);
      v46 = v54;
      if ( v54 < 0 )
      {
        v199 = v54;
        if ( LogAdapter::g_Logger )
        {
          lpWideCharStr = *v40;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to create package extract job for location: {}",
            (__int64)&lpWideCharStr);
          v184 = (struct ParsingSession *)&v199;
          LOBYTE(v55) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v55,
            3,
            (unsigned int)": {}",
            (__int64)&v184);
        }
        v47 = 475;
        goto LABEL_69;
      }
      v56 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**(_QWORD **)(a11 + 192) + 120LL))(
              *(_QWORD *)(a11 + 192),
              L"ignore_filenotfound_warnings",
              L"1");
      v46 = v56;
      if ( v56 < 0 )
      {
        v199 = v56;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to set DPX_OPTION_IGNORE_FNF_WARNINGS");
          lpWideCharStr = (LPCWCH)&v199;
          LOBYTE(v57) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v57,
            3,
            (unsigned int)": {}",
            (__int64)&lpWideCharStr);
        }
        v47 = 479;
        goto LABEL_69;
      }
      v51 = (struct IDpxJob **)(a11 + 192);
    }
  }
  v58 = SczAllocConcat2Sz(&v175, *v40, L"desktopdeployment.cab");
  v203 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)(unsigned int)v58,
      (int)v172);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    if ( v36 )
      ParsingSession::`scalar deleting destructor'(v36, v59);
    if ( a13 )
      *a13 = v200;
    return v203;
  }
  if ( !v199 )
  {
    if ( (unsigned int)DoesFileExist(v175, 0)
      || DpxExtractSingleFileFromCabinet(
           *v51,
           (struct CCbsPackage *)a1,
           *((_DWORD *)v204 + 368) != 0,
           *v40,
           *(const wchar_t **)(a11 + 40),
           L"desktopdeployment.cab") >= 0 )
    {
      *(_BYTE *)(a1 + 1058) = 1;
      *(_DWORD *)(a1 + 92) = 1;
    }
    else
    {
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(v51);
    }
  }
  if ( !*(_BYTE *)(a1 + 1058) )
  {
    if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 32)) == -1 )
    {
      if ( !*v51 )
      {
        v68 = (struct IDpxJob **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v51);
        v69 = Dpx_DpxNewJob(*v40, v68);
        v46 = v69;
        if ( v69 < 0 )
        {
          v199 = v69;
          if ( LogAdapter::g_Logger )
          {
            lpWideCharStr = *v40;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to create package extract job for location: {}",
              (__int64)&lpWideCharStr);
            v184 = (struct ParsingSession *)&v199;
            LOBYTE(v70) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v70,
              3,
              (unsigned int)": {}",
              (__int64)&v184);
          }
          v47 = 540;
          goto LABEL_69;
        }
        v71 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**(_QWORD **)(a11 + 192) + 120LL))(
                *(_QWORD *)(a11 + 192),
                L"ignore_filenotfound_warnings",
                L"1");
        v46 = v71;
        if ( v71 < 0 )
        {
          v199 = v71;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to set DPX_OPTION_IGNORE_FNF_WARNINGS");
            lpWideCharStr = (LPCWCH)&v199;
            LOBYTE(v72) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v72,
              3,
              (unsigned int)": {}",
              (__int64)&lpWideCharStr);
          }
          v47 = 544;
          goto LABEL_69;
        }
        v51 = (struct IDpxJob **)(a11 + 192);
      }
      SingleFileFromCabinet = DpxExtractSingleFileFromCabinet(
                                *v51,
                                (struct CCbsPackage *)a1,
                                *((_DWORD *)v204 + 368) != 0,
                                *v40,
                                *(const wchar_t **)(a11 + 40),
                                v45);
      v46 = SingleFileFromCabinet;
      if ( SingleFileFromCabinet < 0 )
      {
        v199 = SingleFileFromCabinet;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to extract package manifest from cabinet");
          lpWideCharStr = (LPCWCH)&v199;
          LOBYTE(v74) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v74,
            3,
            (unsigned int)": {}",
            (__int64)&lpWideCharStr);
        }
        v47 = 558;
        goto LABEL_69;
      }
    }
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    v191 = *(ParsingSession ***)(a11 + 32);
    v194 = *(_QWORD *)(a11 + 40);
    *(_QWORD *)v190 = *v40;
    *(_QWORD *)v187 = *(_QWORD *)(a11 + 16);
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v75,
        v76,
        (unsigned int)"Opened cabinet package, package directory: {}, sandbox location: {}, cabinet location: {}, manifest location: {}",
        (__int64)v187,
        (__int64)v190,
        (__int64)&v194,
        (__int64)&v191);
    v77 = SczAllocFormatted(&v174, L"%ws.cat", v192);
    v24 = v77;
    if ( v77 < 0 )
    {
      v78 = 644;
LABEL_214:
      v88 = (unsigned int)v77;
      goto LABEL_215;
    }
    v79 = v174;
    v80 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v174);
    v199 = v80;
    if ( v80 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v80,
        (int)v172);
LABEL_144:
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
      v24 = v199;
LABEL_330:
      wil::details::lambda_call__CCbsPackage::PrepareInitializeEx_::_2_::_lambda_1___::_lambda_call__CCbsPackage::PrepareInitializeEx_::_2_::_lambda_1___(v197);
      return v24;
    }
    if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 48)) != -1 )
    {
LABEL_190:
      if ( !*(_BYTE *)(a1 + 1058) )
      {
        v111 = (_QWORD *)(a11 + 32);
        if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 32)) == -1 )
        {
          *(_QWORD *)v187 = *v111;
          *(_QWORD *)v190 = v179;
          if ( (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<wchar_t const *,wchar_t const *>(
                                  v190,
                                  v187) )
          {
            v112 = *v111;
            v191 = 0;
            v113 = FileFromPath(v112);
            v92 = SczAllocFromSz(&v191, v113);
            if ( v92 < 0 )
            {
              v114 = 792;
LABEL_195:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v114,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
                (const char *)(unsigned int)v92,
                (int)v172);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v191);
LABEL_161:
              ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
              Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
              Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
              Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
              Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
              v24 = v92;
              goto LABEL_330;
            }
            v136 = FileFromPath(*(_QWORD *)(a11 + 48));
            v92 = SczAllocFromSz(&v174, v136);
            if ( v92 < 0 )
            {
              v114 = 795;
              goto LABEL_195;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 32);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 48);
            SessionSandbox = CCbsSession::CreateSessionSandbox(v204, *((void **)v204 + 141), 0, 0);
            v92 = SessionSandbox;
            if ( SessionSandbox < 0 )
            {
              v199 = SessionSandbox;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogPartial<>(v138, 3, "Failed to create private session store.");
                *(_QWORD *)v187 = &v199;
                LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v139, 3, ": {}", v187);
              }
              v114 = 801;
              goto LABEL_195;
            }
            v140 = v204;
            v141 = SczAllocConcat2Sz(a11 + 32, *((_QWORD *)v204 + 138), v191);
            v24 = v141;
            if ( v141 < 0 )
            {
              v142 = 804;
LABEL_279:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v142,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
                (const char *)(unsigned int)v141,
                (int)v172);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v191);
              goto LABEL_216;
            }
            v141 = SczAllocConcat2Sz(a11 + 48, *((_QWORD *)v140 + 138), v174);
            v24 = v141;
            if ( v141 < 0 )
            {
              v142 = 807;
              goto LABEL_279;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v191);
          }
        }
        v199 = 0;
        v143 = v204;
        v172 = *(wchar_t **)(a11 + 32);
        v24 = CopyManifestFilesAndVerifyContent(4 * (unsigned int)(unsigned __int8)v205, v204, a1, v192);
        if ( (v199 & 1) != 0 )
        {
          v200 |= 2u;
          goto LABEL_267;
        }
        if ( (v24 & 0x80000000) != 0 )
        {
          v199 = v24;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v187 = *(_QWORD *)(a11 + 32);
            LogAdapter::Logger::LogPartial<wchar_t *>(
              v144,
              3,
              "Failed to copy manifest: {} to private store and verify the content.",
              v187);
            *(_QWORD *)v190 = &v199;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v145, 3, ": {}", v190);
          }
          v88 = v24;
          v78 = 828;
          goto LABEL_215;
        }
LABEL_290:
        if ( !*(_BYTE *)(a1 + 1058) )
        {
          CbsIdentityFromAssemblyIdentity = GetCbsIdentityFromAssemblyIdentity(
                                              (const struct IDENTITY_TYPE *)(*((_QWORD *)v36 + 7) + 304LL),
                                              (struct CCbsIdentity **)(a1 + 112),
                                              0);
          v24 = CbsIdentityFromAssemblyIdentity;
          if ( CbsIdentityFromAssemblyIdentity < 0 )
          {
            v199 = CbsIdentityFromAssemblyIdentity;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<>(v147, 3, "Failed to get CbsIdentity for this package.");
              *(_QWORD *)v187 = &v199;
              LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v148, 3, ": {}", v187);
            }
            v88 = v24;
            v78 = 840;
            goto LABEL_215;
          }
          v149 = *(_QWORD *)(*((_QWORD *)v36 + 7) + 80LL);
          if ( v149 )
          {
            v77 = SczAllocFromSz(a1 + 1032, v149);
            v24 = v77;
            if ( v77 < 0 )
            {
              v78 = 844;
              goto LABEL_214;
            }
          }
          v150 = (const wchar_t **)(a1 + 120);
          v151 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 72LL))(
                   *(_QWORD *)(a1 + 112),
                   a1 + 120);
          v24 = v151;
          if ( v151 < 0 )
          {
            v199 = v151;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<>(v152, 3, "Failed cache package identity in the package property.");
              *(_QWORD *)v187 = &v199;
              LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v153, 3, ": {}", v187);
            }
            v88 = v24;
            v78 = 848;
            goto LABEL_215;
          }
          *(_DWORD *)(a1 + 632) = *(_DWORD *)(*((_QWORD *)v36 + 7) + 24LL);
          v154 = *(_QWORD *)(*((_QWORD *)v36 + 7) + 272LL);
          if ( v154 )
            *(_QWORD *)(a1 + 600) = *(_QWORD *)(v154 + 8);
          if ( *(_BYTE *)(a1 + 1060) )
          {
            v171 = &qword_1802EB518;
            if ( *v150 )
              v171 = *v150;
            *(_QWORD *)v187 = v171;
            LogAdapter::TraceInfo<wchar_t const *>(
              "Skipping minimum servicing stack required check for Package: {}",
              v187);
          }
          else
          {
            v155 = *(_QWORD *)(a1 + 600);
            if ( v155 > v195 )
            {
              v24 = -2146498525;
              LODWORD(v204) = -2146498525;
              if ( LogAdapter::g_Logger )
              {
                v203 = (unsigned __int16)v195;
                v205 = WORD1(v195);
                LODWORD(v194) = WORD2(v195);
                LODWORD(v196) = (unsigned __int16)v155;
                LODWORD(v193) = WORD1(v155);
                LODWORD(v192) = WORD2(v155);
                v156 = &qword_1802EB518;
                v157 = HIWORD(v195);
                v158 = HIWORD(v155);
                v159 = *v150 == 0;
                LODWORD(v195) = HIWORD(v195);
                if ( !v159 )
                  v156 = *v150;
                *(_QWORD *)v190 = v156;
                LODWORD(v191) = v158;
                LogAdapter::Logger::LogPartial<wchar_t const *,int,int,int,int,int,int,int,int>(
                  v158,
                  v157,
                  (unsigned int)"Package \"{}\" requires Servicing Stack v{}.{}.{}.{} but current Servicing Stack is v{}.{}.{}.{}.",
                  (unsigned int)v190,
                  (__int64)&v191,
                  (__int64)&v192,
                  (__int64)&v193,
                  (__int64)&v196,
                  (__int64)&v195,
                  (__int64)&v194,
                  (__int64)&v205,
                  (__int64)&v203);
                *(_QWORD *)v187 = &v204;
                LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v160, 3, ": {}", v187);
              }
              v88 = 2148468771LL;
              v78 = 881;
              goto LABEL_215;
            }
            if ( (unsigned int)CCbsSession::IsOffline(v143) )
            {
              v204 = 0;
              OfflineServicingStackVersion = CCbsSession::GetOfflineServicingStackVersion(
                                               v161,
                                               (unsigned __int64 *)&v204);
              v24 = OfflineServicingStackVersion;
              if ( OfflineServicingStackVersion < 0 )
              {
                LODWORD(v204) = OfflineServicingStackVersion;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogPartial<>(v163, 3, "Failed to get offline servicing stack version.");
                  *(_QWORD *)v187 = &v204;
                  LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v164, 3, ": {}", v187);
                }
                v88 = v24;
                v78 = 887;
                goto LABEL_215;
              }
              v165 = (unsigned __int64)v204;
              v166 = *(_QWORD *)(a1 + 600);
              if ( !v204 )
                v165 = v195;
              if ( v166 > v165 )
              {
                v24 = -2146498525;
                v205 = -2146498525;
                if ( LogAdapter::g_Logger )
                {
                  LODWORD(v191) = (unsigned __int16)v165;
                  LODWORD(v192) = WORD1(v165);
                  LODWORD(v193) = WORD2(v165);
                  LODWORD(v195) = (unsigned __int16)v166;
                  LODWORD(v194) = WORD1(v166);
                  v199 = WORD2(v166);
                  v167 = &qword_1802EB518;
                  v168 = HIWORD(v165);
                  v169 = HIWORD(v166);
                  v159 = *v150 == 0;
                  LODWORD(v196) = v168;
                  if ( !v159 )
                    v167 = *v150;
                  *(_QWORD *)v190 = v167;
                  v203 = v169;
                  LogAdapter::Logger::LogPartial<wchar_t const *,int,int,int,int,int,int,int,int>(
                    v168,
                    v169,
                    (unsigned int)"Package \"{}\" requires Servicing Stack v{}.{}.{}.{} but offline Servicing Stack is v{}.{}.{}.{}.",
                    (unsigned int)v190,
                    (__int64)&v203,
                    (__int64)&v199,
                    (__int64)&v194,
                    (__int64)&v195,
                    (__int64)&v196,
                    (__int64)&v193,
                    (__int64)&v192,
                    (__int64)&v191);
                  *(_QWORD *)v187 = &v205;
                  LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v170, 3, ": {}", v187);
                }
                v88 = 2148468771LL;
                v78 = 906;
                goto LABEL_215;
              }
            }
          }
        }
        if ( a11 )
          *(_DWORD *)(a11 + 8) = a9;
        v200 |= 1u;
        v185 = 0;
        *v193 = v36;
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
        v24 = 0;
        goto LABEL_330;
      }
LABEL_289:
      v143 = v204;
      goto LABEL_290;
    }
    v81 = NestableImpersonator::Impersonate((NestableImpersonator *)&v188);
    v83 = v81;
    if ( v81 < 0 )
    {
      v199 = v81;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v187 = *(_QWORD *)(a11 + 24);
        lpWideCharStr = *(LPCWCH *)(a11 + 40);
        *(_QWORD *)v190 = v45;
        LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t *>(
          (_DWORD)lpWideCharStr,
          v82,
          (unsigned int)"Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}",
          (unsigned int)&lpWideCharStr,
          (__int64)v190,
          (__int64)v187);
        v204 = (CCbsSession *)&v199;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v84, 3, ": {}", &v204);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)v83,
        (int)v172);
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
      v24 = v83;
      goto LABEL_330;
    }
    v85 = v204;
    v86 = DpxExtractSingleFileFromCabinet(
            *(struct IDpxJob **)(a11 + 192),
            (struct CCbsPackage *)a1,
            *((_DWORD *)v204 + 368) != 0,
            *(const wchar_t **)(a11 + 24),
            *(const wchar_t **)(a11 + 40),
            v79);
    v24 = v86;
    if ( (unsigned int)(v86 + 2147024894) > 1 )
    {
      if ( v86 < 0 )
      {
        v199 = v86;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v187 = *(_QWORD *)(a11 + 40);
          *(_QWORD *)v190 = *(_QWORD *)(a11 + 48);
          LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *>(
            v190[0],
            3,
            (unsigned int)"Failed to extract package catalog {} from cabinet {}",
            (unsigned int)v190,
            (__int64)v187);
          lpWideCharStr = (LPCWCH)&v199;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v87, 3, ": {}", &lpWideCharStr);
        }
        v88 = v24;
        v78 = 719;
        goto LABEL_215;
      }
      goto LABEL_185;
    }
    if ( !Windows::AutoNewPtr<ParsingSession>::Allocate<>(&v184) )
    {
      v24 = -2147024882;
      v78 = 670;
      v88 = 2147942414LL;
LABEL_215:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v78,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)v88,
        (int)v172);
      goto LABEL_216;
    }
    v90 = v184;
    v91 = ParseCbsPackage(0, *(const wchar_t *const *)(a11 + 32), v184, v89);
    v92 = v91;
    if ( v91 < 0 )
    {
      v199 = v91;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v187 = *(_QWORD *)(a11 + 32);
        LogAdapter::Logger::LogPartial<wchar_t *>(*(_QWORD *)v187, 3, "Failed to parse the package manifest {}", v187);
        *(_QWORD *)v190 = &v199;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v93, 3, ": {}", v190);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v92,
        (int)v172);
      goto LABEL_161;
    }
    lpWideCharStr = 0;
    v94 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&lpWideCharStr);
    v95 = GetCbsIdentityFromAssemblyIdentity((const struct IDENTITY_TYPE *)(*((_QWORD *)v90 + 7) + 304LL), v94, 0);
    v24 = v95;
    if ( v95 >= 0 )
    {
      (*(void (__fastcall **)(LPCWCH, __int64 *))(*(_QWORD *)lpWideCharStr + 72LL))(lpWideCharStr, &v201);
      v100 = SczAllocFormatted(&v178, L"%ws.mum", v201);
      v24 = v100;
      if ( v100 < 0 )
      {
        v99 = (unsigned int)v100;
        v98 = 682;
        goto LABEL_167;
      }
      v101 = SczAllocFormatted(&v177, L"%ws.cat", v201);
      v24 = v101;
      if ( v101 < 0 )
      {
        v99 = (unsigned int)v101;
        v98 = 683;
        goto LABEL_167;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 32);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 48);
      v102 = v178;
      v103 = SczAllocConcat2Sz(a11 + 32, *(_QWORD *)(a11 + 24), v178);
      v24 = v103;
      if ( v103 < 0 )
      {
        v99 = (unsigned int)v103;
        v98 = 689;
        goto LABEL_167;
      }
      v104 = v177;
      v105 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v177);
      v199 = v105;
      if ( v105 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B4,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v105,
          (int)v172);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
        goto LABEL_144;
      }
      v106 = DpxExtractSingleFileFromCabinet(
               *(struct IDpxJob **)(a11 + 192),
               (struct CCbsPackage *)a1,
               *((_DWORD *)v204 + 368) != 0,
               *(const wchar_t **)(a11 + 24),
               *(const wchar_t **)(a11 + 40),
               v102);
      v92 = v106;
      if ( v106 < 0 )
      {
        v199 = v106;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<>(v107, 3, "Failed to extract package manifest from cabinet");
          *(_QWORD *)v187 = &v199;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v108, 3, ": {}", v187);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BE,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v92,
          v173);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
        goto LABEL_161;
      }
      v85 = v204;
      v109 = DpxExtractSingleFileFromCabinet(
               *(struct IDpxJob **)(a11 + 192),
               (struct CCbsPackage *)a1,
               *((_DWORD *)v204 + 368) != 0,
               *(const wchar_t **)(a11 + 24),
               *(const wchar_t **)(a11 + 40),
               v104);
      v24 = v109;
      if ( v109 >= 0 )
      {
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
LABEL_185:
        if ( (a10 & 8) == 0 )
        {
          v77 = SczAllocFormatted(&v180, L"%ws.ses", v192);
          v24 = v77;
          if ( v77 < 0 )
          {
            v78 = 728;
            goto LABEL_214;
          }
          DpxExtractSingleFileFromCabinet(
            *(struct IDpxJob **)(a11 + 192),
            (struct CCbsPackage *)a1,
            *((_DWORD *)v85 + 368) != 0,
            *(const wchar_t **)(a11 + 24),
            *(const wchar_t **)(a11 + 40),
            v180);
        }
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
        goto LABEL_190;
      }
      v199 = v109;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v187 = *(_QWORD *)(a11 + 40);
        *(_QWORD *)v190 = *(_QWORD *)(a11 + 48);
        LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *>(
          v190[0],
          3,
          (unsigned int)"Failed to extract package catalog {} from cabinet {}",
          (unsigned int)v190,
          (__int64)v187);
        v204 = (CCbsSession *)&v199;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v110, 3, ": {}", &v204);
      }
      v98 = 714;
    }
    else
    {
      v199 = v95;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<>(v96, 3, "Failed to get CbsIdentity for this package.");
        *(_QWORD *)v187 = &v199;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v97, 3, ": {}", v187);
      }
      v98 = 678;
    }
    v99 = v24;
LABEL_167:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v98,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v99,
      (int)v172);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
LABEL_216:
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
    Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v184);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
    Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v185);
    goto LABEL_330;
  }
  v60 = (_QWORD *)(a1 + 112);
  v61 = CreateCbsIdentity((struct CCbsIdentity **)(a1 + 112));
  v24 = v61;
  if ( v61 < 0 )
  {
    v199 = v61;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate CbsIdentity for onepackage.");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v62) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v62,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v38 = 522;
    goto LABEL_44;
  }
  v63 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v60 + 56LL))(*v60, L"OnePackage~~~~0.0.0.0");
  v24 = v63;
  if ( v63 < 0 )
  {
    v199 = v63;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get CbsIdentity for this onepackage.");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v64) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v64,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v38 = 525;
    goto LABEL_44;
  }
  v65 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v60 + 72LL))(*v60, a1 + 120);
  v24 = v65;
  if ( v65 < 0 )
  {
    v199 = v65;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to cache package identity in the package property.");
      lpWideCharStr = (LPCWCH)&v199;
      LOBYTE(v66) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v66,
        3,
        (unsigned int)": {}",
        (__int64)&lpWideCharStr);
    }
    v38 = 528;
    goto LABEL_44;
  }
  CCbsPackage::SetCurrentState(a1, 0, 1);
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v188);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v202);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v201);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v178);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v179);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v175);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v182);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v183);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v180);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v174);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v181);
  if ( v36 )
    ParsingSession::`scalar deleting destructor'(v36, v67);
  if ( a13 )
    *a13 = v200;
  return 0;
}

```

## disassembly

```asm
0x18009d188  mov     [rsp-8+arg_8], rbx
0x18009d18d  push    rbp
0x18009d18e  push    rsi
0x18009d18f  push    rdi
0x18009d190  push    r12
0x18009d192  push    r13
0x18009d194  push    r14
0x18009d196  push    r15
0x18009d198  lea     rbp, [rsp-70h]
0x18009d19d  sub     rsp, 170h
0x18009d1a4  mov     rax, cs:__security_cookie
0x18009d1ab  xor     rax, rsp
0x18009d1ae  mov     [rbp+0A0h+var_40], rax
0x18009d1b2  mov     rax, [rbp+0A0h+arg_20]
0x18009d1b9  mov     r13, rcx
0x18009d1bc  mov     rcx, [rbp+0A0h+arg_28]
0x18009d1c3  mov     rbx, r8
0x18009d1c6  mov     r14, [rbp+0A0h+arg_38]
0x18009d1cd  mov     rsi, r9
0x18009d1d0  mov     r12, [rbp+0A0h+lpFileName]
0x18009d1d7  mov     r15, [rbp+0A0h+arg_50]
0x18009d1de  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d1e2  lea     rax, [rbp+0A0h+arg_60]
0x18009d1e9  mov     [rbp+0A0h+var_88], rax
0x18009d1ed  lea     rax, [rbp+0A0h+var_6C]
0x18009d1f1  mov     [rbp+0A0h+var_80], rax
0x18009d1f5  mov     rax, cs:?vServicingStackVersion@@3_KA; unsigned __int64 vServicingStackVersion
0x18009d1fc  mov     [rbp+0A0h+var_58], edx
0x18009d1ff  xor     edx, edx
0x18009d201  mov     [rbp+0A0h+var_98], rax
0x18009d205  mov     eax, [rbp+0A0h+arg_40]
0x18009d20b  mov     [rbp+0A0h+var_A0], rcx
0x18009d20f  mov     rcx, [rbp+0A0h+arg_58]
0x18009d216  mov     [rbp+0A0h+var_90], r9
0x18009d21a  mov     [rbp+0A0h+var_50], rbx
0x18009d21e  mov     [rbp+0A0h+var_B0], r14
0x18009d222  mov     [rbp+0A0h+var_A8], rcx
0x18009d226  mov     [rbp+0A0h+var_6C], edx
0x18009d229  mov     [rbp+0A0h+var_78], 1
0x18009d22d  mov     [rbp+0A0h+var_E8], rdx
0x18009d231  mov     [rbp+0A0h+var_108], rdx
0x18009d235  mov     [rsp+1A0h+var_140], rdx
0x18009d23a  mov     [rbp+0A0h+var_110], rdx
0x18009d23e  mov     [rbp+0A0h+var_F8], rdx
0x18009d242  mov     [rbp+0A0h+var_100], rdx
0x18009d246  mov     [rsp+1A0h+var_138], rdx
0x18009d24b  mov     [rbp+0A0h+var_118], rdx
0x18009d24f  mov     [rbp+0A0h+var_F0], rdx
0x18009d253  mov     [rbp+0A0h+var_120], rdx
0x18009d257  mov     [rsp+1A0h+var_128], rdx
0x18009d25c  mov     [rbp+0A0h+var_68], rdx
0x18009d260  cmp     eax, 1
0x18009d263  jz      short loc_18009D272
0x18009d265  cmp     eax, 0FFFFFFFEh
0x18009d268  jle     short loc_18009D272
0x18009d26a  mov     dil, 1
0x18009d26d  cmp     eax, 4
0x18009d270  jl      short loc_18009D275
0x18009d272  mov     dil, dl
0x18009d275  mov     [rsp+1A0h+ExistingTokenHandle], rdx
0x18009d27a  mov     [rbp+0A0h+var_60], rdx
0x18009d27e  test    dil, dil
0x18009d281  jnz     loc_18009D32F
0x18009d287  test    r9, r9
0x18009d28a  jnz     loc_18009D32F
0x18009d290  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d295  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18009d29a  mov     rcx, rax; void **
0x18009d29d  call    ?GetNonTiToken@@YAJPEAPEAX@Z; GetNonTiToken(void * *)
0x18009d2a2  lea     r8, aUnableToGetNon; "Unable to get non-TI token."
0x18009d2a9  mov     edx, eax
0x18009d2ab  mov     ecx, 1
0x18009d2b0  mov     ebx, eax
0x18009d2b2  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18009d2b7  xor     edx, edx
0x18009d2b9  test    ebx, ebx
0x18009d2bb  js      short loc_18009D321
0x18009d2bd  lea     rcx, [rbp+0A0h+var_60]
0x18009d2c1  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18009d2c6  mov     rcx, [rsp+1A0h+ExistingTokenHandle]; ExistingTokenHandle
0x18009d2cb  mov     r8, rax; DuplicateTokenHandle
0x18009d2ce  mov     edx, 2; ImpersonationLevel
0x18009d2d3  call    cs:__imp_DuplicateToken
0x18009d2da  nop     dword ptr [rax+rax+00h]
0x18009d2df  xor     edx, edx
0x18009d2e1  test    eax, eax
0x18009d2e3  jnz     short loc_18009D319
0x18009d2e5  call    cs:__imp_GetLastError
0x18009d2ec  nop     dword ptr [rax+rax+00h]
0x18009d2f1  mov     ebx, eax
0x18009d2f3  test    eax, eax
0x18009d2f5  jle     short loc_18009D300
0x18009d2f7  movzx   ebx, ax
0x18009d2fa  or      ebx, 80070000h
0x18009d300  lea     r8, aUnableToDuplic_1; "Unable to duplicate non-TI token."
0x18009d307  mov     edx, ebx
0x18009d309  mov     ecx, 1
0x18009d30e  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18009d313  xor     edx, edx
0x18009d315  test    ebx, ebx
0x18009d317  js      short loc_18009D321
0x18009d319  mov     rsi, [rbp+0A0h+var_60]
0x18009d31d  mov     [rbp+0A0h+var_90], rsi
0x18009d321  mov     rbx, [rbp+0A0h+var_50]
0x18009d325  mov     eax, [rbp+0A0h+arg_40]
0x18009d32b  mov     rcx, [rbp+0A0h+var_A8]
0x18009d32f  mov     [rbp+0A0h+var_D0], rsi
0x18009d333  mov     [rbp+0A0h+var_C8], dl
0x18009d336  test    dil, dil
0x18009d339  jnz     loc_18009D448
0x18009d33f  test    rsi, rsi
0x18009d342  jnz     loc_18009D448
0x18009d348  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d34f  mov     ebx, 800F0800h
0x18009d354  mov     [rbp+0A0h+var_70], ebx
0x18009d357  test    rcx, rcx
0x18009d35a  jz      short loc_18009D39A
0x18009d35c  lea     r14d, [rsi+3]
0x18009d360  xor     edx, edx
0x18009d362  mov     r8d, r14d
0x18009d365  lea     r9, aAUserTokenIsRe; "A User token is required on non-existin"...
0x18009d36c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d371  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d378  lea     rax, [rbp+0A0h+var_70]
0x18009d37c  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d380  lea     r9, asc_1802EE7AC; ": {}"
0x18009d387  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d38b  mov     r8d, r14d
0x18009d38e  mov     dl, 1
0x18009d390  mov     [rsp+1A0h+var_180], rax; int
0x18009d395  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d39a  mov     edx, 16Fh; void *
0x18009d39f  mov     rcx, [rbp+0A8h]; this
0x18009d3a6  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d3ad  mov     r9d, ebx; char *
0x18009d3b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d3b5  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d3b9  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d3be  lea     rcx, [rbp+0A0h+var_60]
0x18009d3c2  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d3c7  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d3cc  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d3d1  lea     rcx, [rbp+0A0h+var_68]
0x18009d3d5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3da  lea     rcx, [rsp+1A0h+var_128]
0x18009d3df  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3e4  lea     rcx, [rbp+0A0h+var_120]
0x18009d3e8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3ed  lea     rcx, [rbp+0A0h+var_118]
0x18009d3f1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3f6  lea     rcx, [rsp+1A0h+var_138]
0x18009d3fb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d400  lea     rcx, [rbp+0A0h+var_100]
0x18009d404  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d409  lea     rcx, [rbp+0A0h+var_F8]
0x18009d40d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d412  lea     rcx, [rbp+0A0h+var_110]
0x18009d416  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d41b  lea     rcx, [rsp+1A0h+var_140]
0x18009d420  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d425  lea     rcx, [rbp+0A0h+var_108]
0x18009d429  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d42e  mov     rdx, [rbp+0A0h+arg_60]
0x18009d435  test    rdx, rdx
0x18009d438  jz      loc_18009F6DC
0x18009d43e  mov     ecx, [rbp+0A0h+var_6C]
0x18009d441  mov     [rdx], ecx
0x18009d443  jmp     loc_18009F6DC
0x18009d448  test    rcx, rcx
0x18009d44b  jnz     short loc_18009D4AB
0x18009d44d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d454  mov     ebx, 80004003h
0x18009d459  mov     [rbp+0A0h+var_70], ebx
0x18009d45c  test    rcx, rcx
0x18009d45f  jz      short loc_18009D4A1
0x18009d461  mov     r14d, 3
0x18009d467  lea     r9, aNoParsingSessi; "No parsing session result specified"
0x18009d46e  mov     r8d, r14d
0x18009d471  xor     edx, edx
0x18009d473  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d478  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d47f  lea     rax, [rbp+0A0h+var_70]
0x18009d483  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d487  lea     r9, asc_1802EE7AC; ": {}"
0x18009d48e  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d492  mov     r8d, r14d
0x18009d495  mov     dl, 1
0x18009d497  mov     [rsp+1A0h+var_180], rax
0x18009d49c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d4a1  mov     edx, 171h
0x18009d4a6  jmp     loc_18009D39F
0x18009d4ab  mov     [r13+360h], eax
0x18009d4b2  lea     rcx, [rbp+0A0h+var_E8]
0x18009d4b6  mov     eax, [rbp+0A0h+arg_48]
0x18009d4bc  mov     [r13+68h], eax
0x18009d4c0  mov     [r13+422h], dl
0x18009d4c7  call    ??$Allocate@$$V@?$AutoNewPtr@UParsingSession@@@Windows@@QEAAPEAUParsingSession@@XZ; Windows::AutoNewPtr<ParsingSession>::Allocate<>(void)
0x18009d4cc  test    rax, rax
0x18009d4cf  jnz     loc_18009D596
0x18009d4d5  mov     rcx, [rbp+0A8h]; this
0x18009d4dc  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d4e3  mov     ebx, 8007000Eh
0x18009d4e8  mov     edx, 177h; void *
0x18009d4ed  mov     r9d, ebx; char *
0x18009d4f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d4f5  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d4f9  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d4fe  lea     rcx, [rbp+0A0h+var_60]
0x18009d502  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d507  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d50c  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d511  lea     rcx, [rbp+0A0h+var_68]
0x18009d515  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d51a  lea     rcx, [rsp+1A0h+var_128]
0x18009d51f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d524  lea     rcx, [rbp+0A0h+var_120]
0x18009d528  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d52d  lea     rcx, [rbp+0A0h+var_118]
0x18009d531  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d536  lea     rcx, [rsp+1A0h+var_138]
0x18009d53b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d540  lea     rcx, [rbp+0A0h+var_100]
0x18009d544  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d549  lea     rcx, [rbp+0A0h+var_F8]
0x18009d54d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d552  lea     rcx, [rbp+0A0h+var_110]
0x18009d556  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d55b  lea     rcx, [rsp+1A0h+var_140]
0x18009d560  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d565  lea     rcx, [rbp+0A0h+var_108]
0x18009d569  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d56e  mov     rcx, [rbp+0A0h+var_E8]; this
0x18009d572  test    rcx, rcx
0x18009d575  jz      short loc_18009D57C
0x18009d577  call    ??_GParsingSession@@QEAAPEAXI@Z; ParsingSession::`scalar deleting destructor'(uint)
0x18009d57c  mov     rax, [rbp+0A0h+arg_60]
0x18009d583  test    rax, rax
0x18009d586  jz      loc_18009F6DC
0x18009d58c  mov     ecx, [rbp+0A0h+var_6C]
0x18009d58f  mov     [rax], ecx
0x18009d591  jmp     loc_18009F6DC
0x18009d596  mov     rdx, r14
0x18009d599  lea     rcx, aUpdate_2; "update"
0x18009d5a0  call    cs:__imp__o__wcsicmp
0x18009d5a7  nop     dword ptr [rax+rax+00h]
0x18009d5ac  lea     r8, [rbp+0A0h+var_118]; wchar_t **
0x18009d5b0  mov     rcx, rbx; this
0x18009d5b3  lea     rdx, aPackages; "Packages"
0x18009d5ba  mov     [rbp+0A0h+var_70], eax
0x18009d5bd  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x18009d5c2  mov     ebx, eax
0x18009d5c4  test    eax, eax
0x18009d5c6  jns     loc_18009D6D7
0x18009d5cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d5d3  mov     [rbp+0A0h+var_70], eax
0x18009d5d6  test    rcx, rcx
0x18009d5d9  jz      short loc_18009D61B
0x18009d5db  mov     r14d, 3
0x18009d5e1  lea     r9, aFailedToGetTar_0; "Failed to get target servicing director"...
0x18009d5e8  mov     r8d, r14d
0x18009d5eb  xor     edx, edx
0x18009d5ed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d5f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d5f9  lea     rax, [rbp+0A0h+var_70]
0x18009d5fd  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d601  lea     r9, asc_1802EE7AC; ": {}"
0x18009d608  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d60c  mov     r8d, r14d
0x18009d60f  mov     dl, 1
0x18009d611  mov     [rsp+1A0h+var_180], rax; int
0x18009d616  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d61b  mov     rcx, [rbp+0A8h]; this
0x18009d622  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d629  mov     r9d, ebx; char *
0x18009d62c  mov     edx, 186h; void *
0x18009d631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d636  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d63a  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d63f  lea     rcx, [rbp+0A0h+var_60]
0x18009d643  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d648  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d64d  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d652  lea     rcx, [rbp+0A0h+var_68]
0x18009d656  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d65b  lea     rcx, [rsp+1A0h+var_128]
0x18009d660  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d665  lea     rcx, [rbp+0A0h+var_120]
0x18009d669  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d66e  lea     rcx, [rbp+0A0h+var_118]
0x18009d672  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d677  lea     rcx, [rsp+1A0h+var_138]
0x18009d67c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d681  lea     rcx, [rbp+0A0h+var_100]
0x18009d685  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d68a  lea     rcx, [rbp+0A0h+var_F8]
0x18009d68e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d693  lea     rcx, [rbp+0A0h+var_110]
0x18009d697  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d69c  lea     rcx, [rsp+1A0h+var_140]
0x18009d6a1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
  ... truncated ...
```
