# ProvOperations::AddPackage(ushort const * const *,ulong,ushort const * const *,ulong,int,ulong,int)

- ea: `0x18000f8d0`
- end: `0x180010b2c`
- name: `?AddPackage@ProvOperations@@UEAAJPEBQEBGK0KHKH@Z`
- size: `4700`
- prototype: `__int64 __fastcall(TraceLoggingCorrelationVector **this, const unsigned __int16 *const *, unsigned int, const unsigned __int16 *const *, unsigned int, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `57`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009180`

## callees

- `0x180001678`
- `0x1800017ec`
- `0x180006f50`
- `0x180007674`
- `0x18000a61c`
- `0x18000a8d8`
- `0x18000a954`
- `0x18000ab14`
- `0x18000ad74`
- `0x18000ae0c`
- `0x18000cdc8`
- `0x18000d0fc`
- `0x18000de00`
- `0x18000de84`
- `0x18000e454`
- `0x18000e850`
- `0x18000f8d0`
- `0x180011884`
- `0x1800120bc`
- `0x180013198`
- `0x180013e9c`
- `0x18001434c`
- `0x1800143b8`
- `0x180017914`
- `0x18001833c`
- `0x180018e80`
- `0x18001b388`
- `0x18001b3c8`
- `0x18001b50c`
- `0x18001f8ac`
- `0x180020fe0`
- `0x1800210f0`
- `0x180021edc`
- `0x1800225e8`
- `0x180022784`
- `0x180024064`
- `0x180024880`
- `0x1800255d0`
- `0x180025660`
- `0x180028df4`
- `0x180028e74`
- `0x180028f28`
- `0x180029480`
- `0x1800296a0`
- `0x18002a170`
- `0x18002a414`
- `0x18002a5e4`
- `0x18002a858`
- `0x18002ac38`
- `0x18002ad64`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010011`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010041`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010071`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001078a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800107d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800107f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001084a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001087a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800108d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fbfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010011`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010041`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010071`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001078a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800107d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800107f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001084a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001087a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800108d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001037f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001037f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800107fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800107fd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001032a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001032a`
- `OLEAUT32!__imp_VariantInit` at `0x1800105ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800105ca`
- `OLEAUT32!__imp_VariantClear` at `0x18001065a`
- `OLEAUT32!__imp_VariantClear` at `0x18001065a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001025e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001025e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010296`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001020f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001020f`

## pseudocode

```c
__int64 __fastcall ProvOperations::AddPackage(
        TraceLoggingCorrelationVector **this,
        const unsigned __int16 *const *a2,
        unsigned int a3,
        const unsigned __int16 *const *a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        int a8)
{
  int v8; // r12d
  __int64 v12; // rcx
  __int64 v13; // r8
  ProvOperations *v14; // r13
  const struct _tlgProvider_t *v15; // rax
  int v16; // r9d
  HKEY v18; // rax
  unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  unsigned int i; // ebx
  __int64 v22; // rdi
  _QWORD *v23; // rbx
  _QWORD *v24; // r15
  _WORD *v25; // rdx
  __int64 v26; // r8
  int v27; // ecx
  HKEY v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r15
  _QWORD *v31; // rbx
  _QWORD *v32; // rdi
  HKEY v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  void *v37; // rax
  const struct _tlgProvider_t *v38; // rax
  const BYTE *v39; // rbx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v41; // rdx
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  unsigned __int64 v45; // rcx
  int v46; // eax
  int v47; // ebx
  __int64 v48; // rdx
  BYTE **v49; // rax
  HRESULT v50; // eax
  LPVOID v51; // rcx
  HRESULT v52; // eax
  char *v53; // rdx
  int v54; // eax
  unsigned int v55; // r8d
  const unsigned __int16 *v56; // rcx
  int Configuration; // eax
  __int64 v58; // r8
  unsigned __int64 v59; // rdx
  const char *v60; // r9
  unsigned __int64 v61; // rbx
  _QWORD *v62; // r12
  _QWORD *v63; // rax
  void *v64; // rcx
  _DWORD *j; // rbx
  _DWORD *v66; // rdi
  ProvOperations *v67; // rax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  unsigned __int64 v71; // rax
  unsigned int v72; // r15d
  const struct _tlgProvider_t *v73; // rax
  int v74; // eax
  const struct _tlgProvider_t *v75; // rax
  void **v76; // r8
  wil *v77; // rcx
  LPVOID v78; // rcx
  LPVOID v79; // rcx
  unsigned int v80; // eax
  unsigned int v81; // r8d
  unsigned int v82; // ebx
  __int64 v84; // rcx
  __int64 v85; // r8
  int dwOptions; // [rsp+20h] [rbp-678h]
  int dwOptionsa; // [rsp+20h] [rbp-678h]
  int dwOptionsb; // [rsp+20h] [rbp-678h]
  int dwOptionsc; // [rsp+20h] [rbp-678h]
  int dwOptionsd; // [rsp+20h] [rbp-678h]
  HKEY hKey; // [rsp+50h] [rbp-648h] BYREF
  unsigned int v92; // [rsp+58h] [rbp-640h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-638h] BYREF
  int v94; // [rsp+68h] [rbp-630h] BYREF
  unsigned int v95[2]; // [rsp+70h] [rbp-628h] BYREF
  ProvOperations *v96; // [rsp+78h] [rbp-620h] BYREF
  __int128 v97; // [rsp+80h] [rbp-618h] BYREF
  __int64 v98; // [rsp+90h] [rbp-608h]
  int v99[2]; // [rsp+98h] [rbp-600h] BYREF
  _QWORD *v100; // [rsp+A0h] [rbp-5F8h] BYREF
  int v101[2]; // [rsp+A8h] [rbp-5F0h] BYREF
  __int64 v102; // [rsp+B0h] [rbp-5E8h]
  int v103[4]; // [rsp+C0h] [rbp-5D8h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-5C8h]
  char *v105; // [rsp+E0h] [rbp-5B8h]
  __int128 v106; // [rsp+E8h] [rbp-5B0h] BYREF
  __int64 v107; // [rsp+F8h] [rbp-5A0h]
  int v108[2]; // [rsp+100h] [rbp-598h] BYREF
  __int128 v109; // [rsp+108h] [rbp-590h]
  __int64 v110; // [rsp+118h] [rbp-580h]
  HANDLE v111[3]; // [rsp+120h] [rbp-578h] BYREF
  BYTE *lpData[2]; // [rsp+138h] [rbp-560h] BYREF
  __int64 v113; // [rsp+148h] [rbp-550h]
  unsigned __int64 v114; // [rsp+150h] [rbp-548h]
  __int128 v115; // [rsp+158h] [rbp-540h] BYREF
  __int64 v116; // [rsp+168h] [rbp-530h]
  unsigned __int64 v117; // [rsp+170h] [rbp-528h]
  void *v118[2]; // [rsp+178h] [rbp-520h] BYREF
  __int64 v119; // [rsp+188h] [rbp-510h]
  unsigned __int64 v120; // [rsp+190h] [rbp-508h]
  __int128 v121; // [rsp+198h] [rbp-500h] BYREF
  __int64 v122; // [rsp+1A8h] [rbp-4F0h]
  unsigned __int64 v123; // [rsp+1B0h] [rbp-4E8h]
  LPVOID *v124; // [rsp+1B8h] [rbp-4E0h] BYREF
  char v125; // [rsp+1C0h] [rbp-4D8h]
  unsigned __int64 v126; // [rsp+1D0h] [rbp-4C8h]
  void **v127; // [rsp+1E0h] [rbp-4B8h] BYREF
  int v128; // [rsp+1E8h] [rbp-4B0h] BYREF
  char v129; // [rsp+1ECh] [rbp-4ACh]
  int v130; // [rsp+210h] [rbp-488h] BYREF
  const char *v131; // [rsp+218h] [rbp-480h]
  __int64 v132; // [rsp+220h] [rbp-478h]
  char v133; // [rsp+228h] [rbp-470h]
  int v134; // [rsp+230h] [rbp-468h]
  _BYTE v135[152]; // [rsp+238h] [rbp-460h] BYREF
  __int128 v136; // [rsp+2D0h] [rbp-3C8h]
  int v137; // [rsp+2E0h] [rbp-3B8h]
  __int64 v138; // [rsp+2E8h] [rbp-3B0h]
  int *v139; // [rsp+2F0h] [rbp-3A8h]
  __int64 v140; // [rsp+2F8h] [rbp-3A0h]
  __int64 v141; // [rsp+300h] [rbp-398h]
  void ***v142; // [rsp+308h] [rbp-390h]
  __int64 v143; // [rsp+310h] [rbp-388h]
  int v144; // [rsp+318h] [rbp-380h]
  int *v145; // [rsp+320h] [rbp-378h]
  char v146; // [rsp+328h] [rbp-370h]
  WCHAR pszPathIn[8]; // [rsp+330h] [rbp-368h] BYREF
  __int64 v148; // [rsp+340h] [rbp-358h]
  unsigned __int64 v149; // [rsp+348h] [rbp-350h]
  VARIANTARG pvarg; // [rsp+350h] [rbp-348h] BYREF
  struct IMVEngine **p_ppv; // [rsp+370h] [rbp-328h]
  unsigned int *v152; // [rsp+378h] [rbp-320h]
  unsigned int *v153; // [rsp+380h] [rbp-318h]
  __int64 v154; // [rsp+388h] [rbp-310h]
  _BYTE v155[16]; // [rsp+390h] [rbp-308h] BYREF
  HKEY *p_hKey; // [rsp+3A0h] [rbp-2F8h]
  __int64 v157; // [rsp+3A8h] [rbp-2F0h]
  char Destination[144]; // [rsp+3B0h] [rbp-2E8h] BYREF
  unsigned __int8 v159[528]; // [rsp+440h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+698h] [rbp+0h]

  v8 = (int)a4;
  v96 = (ProvOperations *)this;
  v92 = a7;
  v128 = 0;
  v129 = 0;
  v133 = 0;
  v130 = 0;
  v131 = "ProvOpsAddPkg";
  v132 = 0;
  v134 = 0;
  v136 = 0;
  memset_0(v135, 0, sizeof(v135));
  v137 = 1;
  v138 = 0;
  v139 = &v128;
  v140 = 0;
  v141 = 0;
  v142 = &v127;
  v143 = 0;
  v144 = 0;
  v145 = &v130;
  v146 = 0;
  v127 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *)&v127);
  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    v95[0] = a3;
    v153 = v95;
    v154 = 4;
    McGenEventWrite_EventWriteTransfer(v12, ProvOpsAddPackageInitiated, v13, 2);
  }
  v14 = (ProvOperations *)(this + 2);
  if ( (unsigned __int8)IsGeneralized(v12) )
  {
    if ( (unsigned __int64)this[5] >= 8 )
      v14 = *(ProvOperations **)v14;
    v15 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v15 > 5u )
    {
      v96 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v15,
        (unsigned int)byte_18003ED61,
        (_DWORD)v139 + 8,
        v16,
        (__int64)&v96);
    }
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v127);
    v127 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v127);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v127);
    return 1;
  }
  v105 = Destination;
  TraceLoggingCorrelationVector::ToString(this[7], Destination);
  if ( (unsigned __int64)this[5] < 8 )
    v18 = (HKEY)(this + 2);
  else
    v18 = *(HKEY *)v14;
  hKey = v18;
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgStarted<unsigned short const *>(
    &v127,
    &hKey,
    Destination);
  try
  {
    ppv = 0;
    p_ppv = (struct IMVEngine **)&ppv;
    v152 = &v92;
    v153 = (unsigned int *)&v127;
    LOBYTE(v154) = 1;
    ProvAgent::ProvAgent((ProvAgent *)v111);
    ProvAgent::LockForProvisioning(v111);
    PackageCollector::PackageCollector((PackageCollector *)v155);
    for ( i = 0; i < a3 && a2; ++i )
    {
      v19 = (unsigned __int16 *)a2[i];
      v149 = 7;
      v148 = 0;
      pszPathIn[0] = 0;
      if ( *v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
      }
      std::wstring::assign(pszPathIn, v19);
      PackageCollector::AddSearchPath(v155, pszPathIn);
      if ( v149 >= 8 )
        operator delete(*(void **)pszPathIn);
    }
    PackageCollector::Search(v155, v101);
    v106 = 0;
    v107 = 0;
    LOBYTE(v94) = 0;
    std::vector<bool>::vector<bool>(v108, (v102 - *(_QWORD *)v101) >> 3, &v94);
    PackageDecryptor::DecryptCollection((unsigned int)&v106, (unsigned int)v101, v8, a5, (__int64)v108);
    v97 = 0;
    v98 = 0;
    PackageCollector::PackageCollector((PackageCollector *)v103);
    PackageCollector::AddDefaultSearchPaths((PackageCollector *)v103);
    v22 = PackageCollector::Search(v103, pszPathIn);
    if ( &v97 != (__int128 *)v22 )
    {
      v23 = (_QWORD *)v97;
      if ( (_QWORD)v97 )
      {
        v24 = (_QWORD *)*((_QWORD *)&v97 + 1);
        if ( (_QWORD)v97 != *((_QWORD *)&v97 + 1) )
        {
          do
          {
            if ( *v23 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v23 + 64LL))(*v23, 1);
            ++v23;
          }
          while ( v23 != v24 );
          v23 = (_QWORD *)v97;
        }
        operator delete(v23);
        v97 = 0;
        v98 = 0;
      }
      v97 = *(_OWORD *)v22;
      v98 = *(_QWORD *)(v22 + 16);
      *(_QWORD *)v22 = 0;
      *(_QWORD *)(v22 + 8) = 0;
      *(_QWORD *)(v22 + 16) = 0;
    }
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(pszPathIn);
    PackageCollector::~PackageCollector((PackageCollector *)v103);
    hKey = (HKEY)((v102 - *(_QWORD *)v101) >> 3);
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsPrunePkgsStarted<unsigned __int64>(
      &v127,
      &hKey);
    ProvPackageValidator::RemoveInapplicablePackages(
      (ProvPackageValidator *)&v97,
      (const struct ProvPackage ***)v101,
      v92,
      a8);
    hKey = (HKEY)((v102 - *(_QWORD *)v101) >> 3);
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsPrunePkgsEnded<unsigned __int64>(
      &v127,
      &hKey);
    *(_OWORD *)v103 = 0;
    v104 = 0;
    PackageCopier::PackageCopier((PackageCopier *)&v94);
    v25 = *(_WORD **)ProvisioningPaths::GetProgramDataProvisioningFolderPath();
    v120 = 7;
    v119 = 0;
    LOWORD(v118[0]) = 0;
    if ( *v25 )
    {
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
    }
    std::wstring::assign(v118, v25);
    v149 = 7;
    v148 = 0;
    pszPathIn[0] = 0;
    std::wstring::assign(pszPathIn);
    PackageCopier::CopyPackages(v27, (int)v101, (int)v108, (int)v103, pszPathIn);
    PackageDecryptor::CleanTempFiles((PackageDecryptor *)&v106);
    v114 = 7;
    v29 = 0;
    v113 = 0;
    LOWORD(lpData[0]) = 0;
    v30 = *(_QWORD *)v103;
    v31 = *(_QWORD **)v103;
    v32 = *(_QWORD **)&v103[2];
    while ( v31 != v32 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 72LL))(*v31) )
      {
        v33 = (HKEY)(*(__int64 (__fastcall **)(_QWORD, LPVOID **))(*(_QWORD *)*v31 + 32LL))(*v31, &v124);
        if ( *((_QWORD *)v33 + 3) >= 8u )
          v33 = *(HKEY *)v33;
        hKey = v33;
        v34 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v31 + 24LL))(*v31, &v115);
        if ( v34[3] >= 8u )
          v34 = (_QWORD *)*v34;
        v100 = v34;
        v35 = (_QWORD *)(**(__int64 (__fastcall ***)(_QWORD, __int128 *))*v31)(*v31, &v121);
        if ( v35[3] >= 8u )
          v35 = (_QWORD *)*v35;
        *(_QWORD *)v99 = v35;
        v36 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v31 + 16LL))(*v31, pszPathIn);
        if ( v36[3] >= 8u )
          v36 = (_QWORD *)*v36;
        *(_QWORD *)v95 = v36;
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgContext<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
          (unsigned int)&v127,
          (unsigned int)v95,
          (unsigned int)v99,
          (unsigned int)&v100,
          (__int64)&hKey,
          (__int64)Destination);
        if ( v149 >= 8 )
          operator delete(*(void **)pszPathIn);
        v149 = 7;
        v148 = 0;
        pszPathIn[0] = 0;
        if ( v123 >= 8 )
          operator delete((void *)v121);
        v123 = 7;
        v122 = 0;
        LOWORD(v121) = 0;
        if ( v117 >= 8 )
          operator delete((void *)v115);
        v117 = 7;
        v116 = 0;
        LOWORD(v115) = 0;
        if ( v126 >= 8 )
          operator delete(v124);
        v37 = (void *)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v31 + 16LL))(*v31, pszPathIn);
        std::wstring::operator=(lpData, v37);
        if ( v149 >= 8 )
          operator delete(*(void **)pszPathIn);
      }
      else
      {
        v38 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
        v28 = (HKEY)*(unsigned int *)v38;
        if ( (unsigned int)v28 > 5 )
        {
          dwOptionsa = 2;
          tlgWriteTransfer_EventWriteTransfer(v38, byte_18003EE89, v139 + 2, 0);
        }
      }
      ++v31;
      v29 = v113;
    }
    if ( !v29 )
      goto LABEL_85;
    v39 = (const BYTE *)lpData;
    if ( v114 >= 8 )
      v39 = lpData[0];
    if ( v92 != 2 )
      goto LABEL_85;
    hKey = 0;
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v41 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\OOBEPackage";
    if ( !IsStateSeparationEnabled )
      v41 = L"SOFTWARE\\Microsoft\\Provisioning\\OOBEPackage";
    v42 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v41, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( v42 )
    {
      v43 = 76;
      goto LABEL_71;
    }
    v44 = -1;
    do
      ++v44;
    while ( *(_WORD *)&v39[2 * v44] );
    *(_QWORD *)&pvarg.vt = 0;
    v45 = v44 + 1;
    if ( is_mul_ok(v45, 2u) )
    {
      if ( 2 * v45 <= 0xFFFFFFFF )
      {
        v42 = RegSetValueExW(hKey, L"PackageId", 0, ((v45 * (unsigned __int128)2uLL) >> 64) + 1, v39, 2 * v45);
        if ( !v42 )
        {
          v28 = hKey;
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_85;
        }
        v43 = 84;
LABEL_71:
        v46 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v43,
                (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
                (const char *)v42,
                dwOptionsa);
        v28 = hKey;
        v47 = v46;
        if ( hKey )
          RegCloseKey(hKey);
        v94 = v47;
        if ( v47 >= 0 )
          goto LABEL_85;
        goto LABEL_82;
      }
      v48 = 82;
    }
    else
    {
      v48 = 81;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v48,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)0x80070216LL,
      dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    v94 = -2147024362;
LABEL_82:
    v49 = lpData;
    if ( v114 >= 8 )
      v49 = (BYTE **)lpData[0];
    hKey = (HKEY)v49;
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgRegisterLastPackageInOOBEFailed<unsigned short const *,long &>(
      &v127,
      &hKey,
      &v94);
LABEL_85:
    if ( a6 )
    {
      if ( !v92 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)0x80070057LL,
          dwOptionsa);
      if ( v92 >= 9 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)0x80070057LL,
          dwOptionsa);
      ProvAgent::SetCurrentTurn((__int64)v111, v92);
      v50 = CoInitializeEx(0, 0);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)v50,
          dwOptionsa);
      BYTE1(v94) = 1;
      v51 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v51 + 16LL))(v51);
      }
      v52 = CoCreateInstance(
              &GUID_fb647f50_2192_49e0_a68f_5775434058c7,
              0,
              1u,
              &GUID_7b967ffd_bc01_4a23_aedd_055f4002710f,
              &ppv);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)v52,
          dwOptionsb);
      if ( (unsigned __int64)this[5] < 8 )
        v53 = (char *)(this + 2);
      else
        v53 = *(char **)v14;
      (*(void (__fastcall **)(LPVOID, char *))(*(_QWORD *)ppv + 32LL))(ppv, v53);
      if ( v92 == 1 && ProvAgent::InUpgrade() )
        UpgradeClearSettingsGroups();
      v54 = ProvOperations::CheckFirstRun(v96);
      if ( v54 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x166, v55, (const char *)(unsigned int)v54, dwOptionsb);
      memset_0(v159, 0, 0x20Au);
      v95[0] = 522;
      Configuration = MvGetConfiguration(v56, v159, v95);
      if ( Configuration < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)Configuration,
          dwOptionsb);
      v59 = ((__int64)v32 - v30) >> 3;
      v95[0] = v59;
      if ( v59 > 0x7FFFFFFF )
        v95[0] = -1;
      v60 = v59 > 0x7FFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v59 > 0x7FFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16E,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          v60,
          dwOptionsb);
      *(_OWORD *)pszPathIn = 0;
      v148 = 0;
      std::vector<unsigned short const *>::resize(pszPathIn, v59, v58, v60);
      v61 = 0;
      v62 = *(_QWORD **)pszPathIn;
      while ( v61 < ((__int64)v32 - v30) >> 3 )
      {
        v63 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v30 + 8 * v61) + 56LL))(*(_QWORD *)(v30 + 8 * v61));
        if ( v63[3] >= 8u )
          v63 = (_QWORD *)*v63;
        v62[v61++] = v63;
      }
      ProvAgent::GetContexts(&v121, v92);
      __SET_PAIR__((unsigned __int64)v66, (unsigned __int64)v64, v121);
      for ( j = (_DWORD *)v121; j != v66; j += 4 )
      {
        if ( *((_QWORD *)v96 + 5) < 8u )
          v67 = (ProvOperations *)(this + 2);
        else
          v67 = *(ProvOperations **)v14;
        *(_QWORD *)&pvarg.vt = v67;
        v99[0] = j[3];
        LODWORD(v100) = j[1];
        LODWORD(hKey) = *j;
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsContext<unsigned int,unsigned int,unsigned long const &,unsigned int,unsigned short const *>(
          (unsigned int)&v127,
          (unsigned int)&hKey,
          (unsigned int)&v100,
          (_DWORD)j + 8,
          (__int64)v99,
          (__int64)&pvarg,
          (__int64)Destination);
        v68 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int8 *, const unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(
                ppv,
                v159,
                L"Software\\Microsoft\\Multivariant\\Handlers");
        if ( v68 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v68,
            dwOptionsc);
        v124 = &ppv;
        v125 = 1;
        if ( (unsigned int)(*j - 2) <= 1 )
        {
          VariantInit(&pvarg);
          pvarg.lVal = j[2];
          pvarg.vt = 19;
          v69 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)ppv + 64LL))(
                  ppv,
                  L"slot",
                  &pvarg);
          if ( v69 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x183,
              (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
              (const char *)(unsigned int)v69,
              dwOptionsc);
          pvarg.lVal = j[3];
          v70 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)ppv + 64LL))(
                  ppv,
                  L"slotstatus",
                  &pvarg);
          if ( v70 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x186,
              (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
              (const char *)(unsigned int)v70,
              dwOptionsc);
          VariantClear(&pvarg);
        }
        *(_OWORD *)&pvarg.vt = *(_OWORD *)j;
        ProvAgent::GetRelevantStates(&v115, (__int64)&pvarg);
        v71 = (__int64)(*((_QWORD *)&v115 + 1) - v115) >> 2;
        if ( v71 > 0x7FFFFFFF )
          v72 = -1;
        else
          v72 = (__int64)(*((_QWORD *)&v115 + 1) - v115) >> 2;
        if ( v71 > 0x7FFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x18C,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            v71 > 0x7FFFFFFF ? (const char *)0x80070216LL : 0,
            dwOptionsc);
        v73 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
        if ( *(_DWORD *)v73 > 5u )
          tlgWriteTransfer_EventWriteTransfer(v73, byte_18003EFA3, v139 + 2, 0);
        dwOptionsd = v95[0];
        v74 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)ppv + 48LL))(ppv, v115, v72, v62);
        if ( v74 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x192,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v74,
            dwOptionsd);
        v75 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
        if ( *(_DWORD *)v75 > 5u )
          tlgWriteTransfer_EventWriteTransfer(v75, &dword_180040E74, v139 + 2, 0);
        if ( (_QWORD)v115 )
        {
          operator delete((void *)v115);
          v115 = 0;
          v116 = 0;
        }
        v125 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 104LL))(ppv);
        v64 = (void *)v121;
      }
      if ( v64 )
      {
        operator delete(v64);
        v121 = 0;
        v122 = 0;
      }
      if ( v62 )
        operator delete(v62);
      CoUninitialize();
    }
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      v76 = v118;
      if ( v120 >= 8 )
        v76 = (void **)v118[0];
      McTemplateU0z_EventWriteTransfer(v28, ProvOpsAddPackageSucceeded, v76);
    }
    if ( v114 >= 8 )
      operator delete(lpData[0]);
    v114 = 7;
    v113 = 0;
    LOWORD(lpData[0]) = 0;
    if ( v120 >= 8 )
      operator delete(v118[0]);
    v120 = 7;
    v119 = 0;
    LOWORD(v118[0]) = 0;
    PackageCopier::~PackageCopier((PackageCopier *)&v94);
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v103);
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(&v97);
    v110 = 0;
    if ( *(_QWORD *)v108 )
    {
      operator delete(*(void **)v108);
      *(_QWORD *)v108 = 0;
      v109 = 0;
    }
    PackageDecryptor::CleanTempFiles((PackageDecryptor *)&v106);
    std::vector<std::wstring>::_Tidy(&v106);
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v101);
    PackageCollector::~PackageCollector((PackageCollector *)v155);
    ProvAgent::~ProvAgent((ProvAgent *)v111);
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgSucceeded(
      (Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *)&v127,
      Destination);
  }
  catch ( ... )
  {
    v80 = wil::ResultFromCaughtException(v77);
    v82 = v80;
    LODWORD(hKey) = v80;
    if ( v80 != -2147024885 && v80 != -2147467260 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x19E, v81, (const char *)v82, dwOptions);
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgFailed<long &>(
      &v127,
      &hKey,
      v105);
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      LODWORD(hKey) = v82;
      p_hKey = &hKey;
      v157 = 4;
      McGenEventWrite_EventWriteTransfer(v84, ">", v85, 2);
    }
    if ( (unsigned __int8)IsCheckUserConsentPresent(v84) && !a8 )
      ReportInstallationError(v82);
    LODWORD(hKey) = v82;
    PostProvisioningActivities(*p_ppv, *v152);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v153);
    v79 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v127 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v127);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v127);
    return (unsigned int)hKey;
  }
  PostProvisioningActivities((struct IMVEngine *)ppv, v92);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v127);
  v78 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v127 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v127);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v127);
  return 0;
}

```

## disassembly

```asm
0x18000f8d0  push    rbx
0x18000f8d2  push    rsi
0x18000f8d3  push    rdi
0x18000f8d4  push    r12
0x18000f8d6  push    r13
0x18000f8d8  push    r14
0x18000f8da  push    r15
0x18000f8dc  sub     rsp, 660h
0x18000f8e3  mov     rax, cs:__security_cookie
0x18000f8ea  xor     rax, rsp
0x18000f8ed  mov     [rsp+698h+var_48], rax
0x18000f8f5  mov     r12, r9
0x18000f8f8  mov     edi, r8d
0x18000f8fb  mov     r15, rdx
0x18000f8fe  mov     r14, rcx
0x18000f901  mov     [rsp+698h+var_620], rcx
0x18000f906  mov     eax, [rsp+698h+arg_30]
0x18000f90d  mov     [rsp+698h+var_640], eax
0x18000f911  xor     esi, esi
0x18000f913  mov     [rsp+698h+var_4B0], esi
0x18000f91a  mov     [rsp+698h+var_4AC], sil
0x18000f922  mov     [rsp+698h+var_470], sil
0x18000f92a  mov     [rsp+698h+var_488], esi
0x18000f931  lea     rax, aProvopsaddpkg; "ProvOpsAddPkg"
0x18000f938  mov     [rsp+698h+var_480], rax
0x18000f940  mov     [rsp+698h+var_478], rsi
0x18000f948  mov     [rsp+698h+var_468], esi
0x18000f94f  xorps   xmm0, xmm0
0x18000f952  movdqa  [rsp+698h+var_3C8], xmm0
0x18000f95b  xor     edx, edx; Val
0x18000f95d  mov     r8d, 98h; Size
0x18000f963  lea     rcx, [rsp+698h+var_460]; void *
0x18000f96b  call    memset_0
0x18000f970  mov     [rsp+698h+var_3B8], 1
0x18000f97b  xor     eax, eax
0x18000f97d  mov     [rsp+698h+var_3B0], rax
0x18000f985  lea     rax, [rsp+698h+var_4B0]
0x18000f98d  mov     [rsp+698h+var_3A8], rax
0x18000f995  mov     [rsp+698h+var_3A0], rsi
0x18000f99d  mov     [rsp+698h+var_398], rsi
0x18000f9a5  lea     rax, [rsp+698h+var_4B8]
0x18000f9ad  mov     [rsp+698h+var_390], rax
0x18000f9b5  mov     [rsp+698h+var_388], rsi
0x18000f9bd  mov     [rsp+698h+var_380], esi
0x18000f9c4  lea     rax, [rsp+698h+var_488]
0x18000f9cc  mov     [rsp+698h+var_378], rax
0x18000f9d4  mov     [rsp+698h+var_370], sil
0x18000f9dc  lea     rbx, ??_7ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::`vftable'
0x18000f9e3  mov     [rsp+698h+var_4B8], rbx
0x18000f9eb  lea     rcx, [rsp+698h+var_4B8]; this
0x18000f9f3  call    ?StartActivity@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StartActivity(void)
0x18000f9f8  nop
0x18000f9f9  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x18000fa00  jz      short loc_18000FA3C
0x18000fa02  mov     [rsp+698h+var_628], edi
0x18000fa06  lea     rax, [rsp+698h+var_628]
0x18000fa0b  mov     [rsp+698h+var_318], rax
0x18000fa13  mov     [rsp+698h+var_310], 4
0x18000fa1f  lea     rax, [rsp+698h+var_328]
0x18000fa27  mov     qword ptr [rsp+698h+dwOptions], rax
0x18000fa2c  lea     r9d, [rsi+2]
0x18000fa30  lea     rdx, ProvOpsAddPackageInitiated
0x18000fa37  call    McGenEventWrite_EventWriteTransfer
0x18000fa3c  lea     r13, [r14+10h]
0x18000fa40  call    IsGeneralized
0x18000fa45  test    al, al
0x18000fa47  jz      short loc_18000FAC8
0x18000fa49  mov     r14d, 8
0x18000fa4f  cmp     [r13+18h], r14
0x18000fa53  jb      short loc_18000FA59
0x18000fa55  mov     r13, [r13+0]
0x18000fa59  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18000fa5e  mov     ecx, [rax]
0x18000fa60  cmp     ecx, 5
0x18000fa63  jbe     short loc_18000FA8E
0x18000fa65  mov     [rsp+698h+var_620], r13
0x18000fa6a  mov     r8, [rsp+698h+var_3A8]
0x18000fa72  add     r8, r14
0x18000fa75  lea     rcx, [rsp+698h+var_620]
0x18000fa7a  mov     qword ptr [rsp+698h+dwOptions], rcx
0x18000fa7f  lea     rdx, byte_18003ED61
0x18000fa86  mov     rcx, rax
0x18000fa89  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000fa8e  lea     rcx, [rsp+698h+var_4B8]
0x18000fa96  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000fa9b  nop
0x18000fa9c  mov     [rsp+698h+var_4B8], rbx
0x18000faa4  lea     rcx, [rsp+698h+var_4B8]
0x18000faac  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000fab1  lea     rcx, [rsp+698h+var_4B8]
0x18000fab9  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000fabe  mov     eax, 1
0x18000fac3  jmp     loc_180010A27
0x18000fac8  lea     rax, [rsp+698h+Destination]
0x18000fad0  mov     [rsp+698h+var_5B8], rax
0x18000fad8  lea     rdx, [rsp+698h+Destination]; Destination
0x18000fae0  mov     rcx, [r14+38h]; this
0x18000fae4  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x18000fae9  mov     r14d, 8
0x18000faef  cmp     [r13+18h], r14
0x18000faf3  jb      short loc_18000FAFB
0x18000faf5  mov     rax, [r13+0]
0x18000faf9  jmp     short loc_18000FAFE
0x18000fafb  mov     rax, r13
0x18000fafe  mov     [rsp+698h+hKey], rax
0x18000fb03  lea     r8, [rsp+698h+Destination]
0x18000fb0b  lea     rdx, [rsp+698h+hKey]
0x18000fb10  lea     rcx, [rsp+698h+var_4B8]
0x18000fb18  call    ??$ProvOpsAddPkgStarted@PEBG@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAX$$QEAPEBGPEBD@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgStarted<ushort const *>(ushort const * &&,char const *)
0x18000fb1d  mov     [rsp+698h+ppv], rsi
0x18000fb22  lea     rax, [rsp+698h+ppv]
0x18000fb27  mov     [rsp+698h+var_328], rax
0x18000fb2f  lea     rax, [rsp+698h+var_640]
0x18000fb34  mov     [rsp+698h+var_320], rax
0x18000fb3c  lea     rax, [rsp+698h+var_4B8]
0x18000fb44  mov     [rsp+698h+var_318], rax
0x18000fb4c  mov     byte ptr [rsp+698h+var_310], 1
0x18000fb54  lea     rcx, [rsp+698h+var_578]; this
0x18000fb5c  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x18000fb61  nop
0x18000fb62  lea     rcx, [rsp+698h+var_578]; this
0x18000fb6a  call    ?LockForProvisioning@ProvAgent@@QEAAXXZ; ProvAgent::LockForProvisioning(void)
0x18000fb6f  lea     rcx, [rsp+698h+var_308]; this
0x18000fb77  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x18000fb7c  nop
0x18000fb7d  mov     ebx, esi
0x18000fb7f  cmp     ebx, edi
0x18000fb81  jnb     loc_18000FC09
0x18000fb87  test    r15, r15
0x18000fb8a  jz      short loc_18000FC09
0x18000fb8c  mov     eax, ebx
0x18000fb8e  mov     rdx, [r15+rax*8]; Src
0x18000fb92  mov     [rsp+698h+var_350], 7
0x18000fb9e  mov     [rsp+698h+var_358], rsi
0x18000fba6  mov     [rsp+698h+pszPathIn], si
0x18000fbae  cmp     [rdx], si
0x18000fbb1  jnz     short loc_18000FBB8
0x18000fbb3  mov     r8, rsi
0x18000fbb6  jmp     short loc_18000FBC6
0x18000fbb8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fbbc  inc     r8
0x18000fbbf  cmp     [rdx+r8*2], si
0x18000fbc4  jnz     short loc_18000FBBC
0x18000fbc6  lea     rcx, [rsp+698h+pszPathIn]; void *
0x18000fbce  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000fbd3  nop
0x18000fbd4  lea     rdx, [rsp+698h+pszPathIn]
0x18000fbdc  lea     rcx, [rsp+698h+var_308]
0x18000fbe4  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x18000fbe9  nop
0x18000fbea  cmp     [rsp+698h+var_350], r14
0x18000fbf2  jb      short loc_18000FC02
0x18000fbf4  mov     rcx, qword ptr [rsp+698h+pszPathIn]
0x18000fbfc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fc02  inc     ebx
0x18000fc04  jmp     loc_18000FB7F
0x18000fc09  lea     rdx, [rsp+698h+var_5F0]
0x18000fc11  lea     rcx, [rsp+698h+var_308]
0x18000fc19  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x18000fc1e  nop
0x18000fc1f  xorps   xmm0, xmm0
0x18000fc22  movdqu  [rsp+698h+var_5B0], xmm0
0x18000fc2b  mov     [rsp+698h+var_5A0], rsi
0x18000fc33  mov     byte ptr [rsp+698h+var_630], sil
0x18000fc38  mov     rdx, [rsp+698h+var_5E8]
0x18000fc40  sub     rdx, qword ptr [rsp+698h+var_5F0]
0x18000fc48  sar     rdx, 3
0x18000fc4c  lea     r8, [rsp+698h+var_630]
0x18000fc51  lea     rcx, [rsp+698h+var_598]
0x18000fc59  call    ??0?$vector@_NV?$allocator@_N@std@@@std@@QEAA@_KAEB_N@Z; std::vector<bool>::vector<bool>(unsigned __int64,bool const &)
0x18000fc5e  nop
0x18000fc5f  mov     r9d, [rsp+698h+arg_20]
0x18000fc67  lea     rax, [rsp+698h+var_598]
0x18000fc6f  mov     qword ptr [rsp+698h+dwOptions], rax
0x18000fc74  mov     r8, r12
0x18000fc77  lea     rdx, [rsp+698h+var_5F0]
0x18000fc7f  lea     rcx, [rsp+698h+var_5B0]
0x18000fc87  call    ?DecryptCollection@PackageDecryptor@@QEAAXPEAV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@PEBQEBG_KPEAV?$vector@_NV?$allocator@_N@std@@@3@@Z; PackageDecryptor::DecryptCollection(std::vector<std::unique_ptr<ProvPackage>> *,ushort const * const *,unsigned __int64,std::vector<bool> *)
0x18000fc8c  xorps   xmm0, xmm0
0x18000fc8f  movdqu  [rsp+698h+var_618], xmm0
0x18000fc98  mov     [rsp+698h+var_608], rsi
0x18000fca0  lea     rcx, [rsp+698h+var_5D8]; this
0x18000fca8  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x18000fcad  nop
0x18000fcae  lea     rcx, [rsp+698h+var_5D8]; this
0x18000fcb6  call    ?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ; PackageCollector::AddDefaultSearchPaths(void)
0x18000fcbb  lea     rdx, [rsp+698h+pszPathIn]
0x18000fcc3  lea     rcx, [rsp+698h+var_5D8]
0x18000fccb  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x18000fcd0  mov     rdi, rax
0x18000fcd3  lea     rax, [rsp+698h+var_618]
0x18000fcdb  cmp     rax, rdi
0x18000fcde  jz      loc_18000FD72
0x18000fce4  mov     rbx, qword ptr [rsp+698h+var_618]
0x18000fcec  test    rbx, rbx
0x18000fcef  jz      short loc_18000FD44
0x18000fcf1  mov     r15, qword ptr [rsp+698h+var_618+8]
0x18000fcf9  cmp     rbx, r15
0x18000fcfc  jz      short loc_18000FD27
0x18000fcfe  mov     rcx, [rbx]
0x18000fd01  test    rcx, rcx
0x18000fd04  jz      short loc_18000FD17
0x18000fd06  mov     rax, [rcx]
0x18000fd09  mov     edx, 1
0x18000fd0e  mov     rax, [rax+40h]
0x18000fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd17  add     rbx, r14
0x18000fd1a  cmp     rbx, r15
0x18000fd1d  jnz     short loc_18000FCFE
0x18000fd1f  mov     rbx, qword ptr [rsp+698h+var_618]
0x18000fd27  mov     rcx, rbx
0x18000fd2a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fd30  xorps   xmm0, xmm0
0x18000fd33  movdqu  [rsp+698h+var_618], xmm0
0x18000fd3c  mov     [rsp+698h+var_608], rsi
0x18000fd44  mov     rax, [rdi]
0x18000fd47  mov     qword ptr [rsp+698h+var_618], rax
0x18000fd4f  mov     rax, [rdi+8]
0x18000fd53  mov     qword ptr [rsp+698h+var_618+8], rax
0x18000fd5b  mov     rax, [rdi+10h]
0x18000fd5f  mov     [rsp+698h+var_608], rax
0x18000fd67  mov     [rdi], rsi
0x18000fd6a  mov     [rdi+8], rsi
0x18000fd6e  mov     [rdi+10h], rsi
0x18000fd72  lea     rcx, [rsp+698h+pszPathIn]
0x18000fd7a  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x18000fd7f  nop
0x18000fd80  lea     rcx, [rsp+698h+var_5D8]; this
0x18000fd88  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x18000fd8d  nop
0x18000fd8e  mov     rax, [rsp+698h+var_5E8]
0x18000fd96  sub     rax, qword ptr [rsp+698h+var_5F0]
0x18000fd9e  sar     rax, 3
0x18000fda2  mov     [rsp+698h+hKey], rax
0x18000fda7  lea     rdx, [rsp+698h+hKey]
0x18000fdac  lea     rcx, [rsp+698h+var_4B8]
0x18000fdb4  call    ??$ProvOpsPrunePkgsStarted@_K@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAX$$QEA_K@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsPrunePkgsStarted<unsigned __int64>(unsigned __int64 &&)
0x18000fdb9  mov     r9d, [rsp+698h+arg_38]
0x18000fdc1  mov     r8d, [rsp+698h+var_640]
0x18000fdc6  lea     rdx, [rsp+698h+var_5F0]
0x18000fdce  lea     rcx, [rsp+698h+var_618]; this
0x18000fdd6  call    ?RemoveInapplicablePackages@ProvPackageValidator@@QEAAXPEAV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@KH@Z; ProvPackageValidator::RemoveInapplicablePackages(std::vector<std::unique_ptr<ProvPackage>> *,ulong,int)
0x18000fddb  mov     rax, [rsp+698h+var_5E8]
0x18000fde3  sub     rax, qword ptr [rsp+698h+var_5F0]
0x18000fdeb  sar     rax, 3
0x18000fdef  mov     [rsp+698h+hKey], rax
0x18000fdf4  lea     rdx, [rsp+698h+hKey]
0x18000fdf9  lea     rcx, [rsp+698h+var_4B8]
0x18000fe01  call    ??$ProvOpsPrunePkgsEnded@_K@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAX$$QEA_K@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsPrunePkgsEnded<unsigned __int64>(unsigned __int64 &&)
0x18000fe06  xorps   xmm0, xmm0
0x18000fe09  movdqu  xmmword ptr [rsp+698h+var_5D8], xmm0
0x18000fe12  mov     [rsp+698h+var_5C8], rsi
0x18000fe1a  lea     rcx, [rsp+698h+var_630]; this
0x18000fe1f  call    ??0PackageCopier@@QEAA@XZ; PackageCopier::PackageCopier(void)
0x18000fe24  nop
0x18000fe25  call    ?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)
0x18000fe2a  mov     rdx, [rax]; Src
0x18000fe2d  mov     r12d, 7
0x18000fe33  mov     [rsp+698h+var_508], r12
0x18000fe3b  mov     [rsp+698h+var_510], rsi
0x18000fe43  mov     word ptr [rsp+698h+var_520], si
0x18000fe4b  cmp     [rdx], si
0x18000fe4e  jnz     short loc_18000FE55
0x18000fe50  mov     r8, rsi
0x18000fe53  jmp     short loc_18000FE63
0x18000fe55  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fe59  inc     r8
0x18000fe5c  cmp     [rdx+r8*2], si
0x18000fe61  jnz     short loc_18000FE59
0x18000fe63  lea     rcx, [rsp+698h+var_520]; void *
0x18000fe6b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000fe70  nop
0x18000fe71  mov     [rsp+698h+var_350], r12
0x18000fe79  mov     [rsp+698h+var_358], rsi
0x18000fe81  mov     [rsp+698h+pszPathIn], si
0x18000fe89  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000fe8d  xor     r8d, r8d
0x18000fe90  lea     rdx, [rsp+698h+var_520]
0x18000fe98  lea     rcx, [rsp+698h+pszPathIn]; void *
0x18000fea0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000fea5  lea     rax, [rsp+698h+pszPathIn]
0x18000fead  mov     qword ptr [rsp+698h+dwOptions], rax; pszPathIn
0x18000feb2  lea     r9, [rsp+698h+var_5D8]; int
0x18000feba  lea     r8, [rsp+698h+var_598]; int
0x18000fec2  lea     rdx, [rsp+698h+var_5F0]; int
0x18000feca  call    ?CopyPackages@PackageCopier@@QEAAXAEBV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@AEBV?$vector@_NV?$allocator@_N@std@@@3@PEAV23@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; PackageCopier::CopyPackages(std::vector<std::unique_ptr<ProvPackage>> const &,std::vector<bool> const &,std::vector<std::unique_ptr<ProvPackage>> *,std::wstring)
0x18000fecf  lea     rcx, [rsp+698h+var_5B0]; this
0x18000fed7  call    ?CleanTempFiles@PackageDecryptor@@QEAAXXZ; PackageDecryptor::CleanTempFiles(void)
0x18000fedc  mov     [rsp+698h+var_548], r12
0x18000fee4  mov     rax, rsi
0x18000fee7  mov     [rsp+698h+var_550], rax
0x18000feef  mov     word ptr [rsp+698h+lpData], si
0x18000fef7  mov     r15, qword ptr [rsp+698h+var_5D8]
0x18000feff  mov     rbx, r15
0x18000ff02  mov     rdi, qword ptr [rsp+698h+var_5D8+8]
0x18000ff0a  cmp     rbx, rdi
0x18000ff0d  jz      loc_180010137
0x18000ff13  mov     rcx, [rbx]
0x18000ff16  mov     rax, [rcx]
0x18000ff19  mov     rax, [rax+48h]
  ... truncated ...
```
