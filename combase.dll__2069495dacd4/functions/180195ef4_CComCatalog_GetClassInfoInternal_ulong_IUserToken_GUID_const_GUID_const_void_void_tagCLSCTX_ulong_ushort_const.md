# CComCatalog::GetClassInfoInternal(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *,tagCLSCTX,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x180195ef4`
- end: `0x180199161`
- name: `?GetClassInfoInternal@CComCatalog@@AEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAXW4tagCLSCTX@@KPEBG5IQEBQEAUHSTRING__@@I6@Z`
- size: `12909`
- prototype: `HRESULT __fastcall(CComCatalog *this, unsigned int flags, IUserToken *pUserToken, const _GUID *guidConfiguredClsid, const _GUID *riid, void **ppv, void *clsctx, tagCLSCTX catalogFlags, unsigned int explicitPackageFullName, const wchar_t *explicitMainPackageFamilyName, const wchar_t *packageGraphPackageCount, unsigned int packageGraphPackages, HSTRING__ *const *comDependencyMainPackageFamilyCount, unsigned int comDependencyMainPackageFamilies, HSTRING__ *const *flags)`
- caller_count: `4`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801454f0`
- `0x180183b70`
- `0x180195da0`
- `0x180195e30`

## callees

- `0x18000712c`
- `0x180020e14`
- `0x180022f94`
- `0x18003a8bc`
- `0x18003eaa0`
- `0x18004fa14`
- `0x180058e20`
- `0x180061d04`
- `0x180063660`
- `0x180064140`
- `0x180069904`
- `0x1800748dc`
- `0x18008490c`
- `0x180085170`
- `0x1800859ec`
- `0x180085c90`
- `0x180086400`
- `0x1800865b8`
- `0x180087830`
- `0x180087b0c`
- `0x18008db2c`
- `0x1800bcd9c`
- `0x1800fc0e4`
- `0x180106a98`
- `0x1801171fc`
- `0x1801316bc`
- `0x1801441cc`
- `0x18015f1c8`
- `0x1801769e8`
- `0x180186d64`
- `0x180186dc0`
- `0x180189814`
- `0x18018a34c`
- `0x18018b7f8`
- `0x180195ef4`
- `0x1801999b0`
- `0x1801da08c`
- `0x1801da520`
- `0x1801dca50`
- `0x1801de2e4`
- `0x1801de49c`
- `0x180255010`

## string_xrefs

- `0x180196021`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1801960c1`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18019621e`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1801962a5`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1801964f3`: `onecore\com\combase\catalog\catalog.cxx`
- `0x180196723`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18019678f`: `CComCatalog::GetClassInfoInternal`
- `0x18019683e`: `CComCatalog::GetClassInfoInternal`
- `0x180196947`: `CComCatalog::GetClassInfoInternal`
- `0x180196afd`: `CComCatalog::GetClassInfoInternal`
- `0x180196ba8`: `CComCatalog::GetClassInfoInternal`
- `0x180196c48`: `CComCatalog::GetClassInfoInternal`
- `0x180196d7e`: `CComCatalog::GetClassInfoInternal`
- `0x180196ebe`: `CComCatalog::GetClassInfoInternal`
- `0x180196f72`: `CComCatalog::GetClassInfoInternal`
- `0x1801970be`: `CComCatalog::GetClassInfoInternal`
- `0x1801971b0`: `CComCatalog::GetClassInfoInternal`
- `0x180197245`: `CComCatalog::GetClassInfoInternal`
- `0x18019751e`: `CComCatalog::GetClassInfoInternal`
- `0x1801975c2`: `CComCatalog::GetClassInfoInternal`
- `0x18019769f`: `CComCatalog::GetClassInfoInternal`
- `0x180197741`: `CComCatalog::GetClassInfoInternal`
- `0x18019783b`: `CComCatalog::GetClassInfoInternal`
- `0x180197b12`: `CComCatalog::GetClassInfoInternal`
- `0x180197e60`: `CComCatalog::GetClassInfoInternal`
- `0x180197f15`: `CComCatalog::GetClassInfoInternal`
- `0x180197ff5`: `CComCatalog::GetClassInfoInternal`
- `0x1801980aa`: `CComCatalog::GetClassInfoInternal`
- `0x180198187`: `CComCatalog::GetClassInfoInternal`
- `0x18019823a`: `CComCatalog::GetClassInfoInternal`
- `0x180198830`: `CComCatalog::GetClassInfoInternal`
- `0x18019894f`: `CComCatalog::GetClassInfoInternal`
- `0x180198c19`: `CComCatalog::GetClassInfoInternal`
- `0x180198cc0`: `CComCatalog::GetClassInfoInternal`
- `0x180198fc2`: `CComCatalog::GetClassInfoInternal`
- `0x180196a79`: `Look for %ls in PackagedCom current package Catalog...`
- `0x180198837`: `Look for %ls in PackagedCom current package Catalog...`
- `0x180196d85`: `Found %ls in PackagedCom current package Catalog`
- `0x180196f79`: `Found %ls in PackagedCom current package Catalog`
- `0x180198956`: `Found %ls in PackagedCom current package Catalog`
- `0x180196845`: `Found %ls in COM SxS Catalog`
- `0x1801968d3`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x180196e2b`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x180197baf`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1801989ed`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x180198b97`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x180198f55`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x180196796`: `Look for %ls in COM SxS Catalog...`
- `0x18019694e`: `Look for %ls in COM SxS Catalog...`
- `0x1801976a6`: `Look for %ls in COM Base CLB...`
- `0x180197748`: `Found %ls in COM Base CLB`
- `0x1801970c5`: `Found %ls in cache`
- `0x18019724c`: `Found %ls in cache`
- `0x1801971b7`: `Look for %ls in cache...`
- `0x18019818e`: `Look for %ls in ARM32 WOW registry...`
- `0x180198241`: `Found %ls in ARM32 WOW registry`
- `0x180197ffc`: `Look for %ls in x86 WOW registry...`
- `0x1801980b1`: `Found %ls in x86 WOW registry`
- `0x180197e67`: `Look for %ls in registry...`
- `0x180197f1c`: `Found %ls in registry`
- `0x1801977d3`: `Look for %ls in PackagedCom all packages Catalog...`
- `0x180198c20`: `Look for %ls in PackagedCom all packages Catalog...`
- `0x180197b19`: `Found %ls in PackagedCom all packages Catalog`
- `0x180198cc7`: `Found %ls in PackagedCom all packages Catalog`
- `0x180198fc9`: `Adding %ls to cache...`

## pseudocode

```c
__int64 __fastcall CComCatalog::GetClassInfoInternal(
        CComCatalog *this,
        unsigned int flags,
        IUserToken *pUserToken,
        _GUID *guidConfiguredClsid,
        _GUID *riid,
        void **ppv,
        void *clsctx,
        unsigned int catalogFlags,
        unsigned int explicitPackageFullName,
        wchar_t *explicitMainPackageFamilyName,
        wchar_t *packageGraphPackageCount,
        unsigned int packageGraphPackages,
        HSTRING__ **comDependencyMainPackageFamilyCount,
        unsigned int comDependencyMainPackageFamilies,
        HSTRING__ *const *flags_0)
{
  int v17; // r13d
  int v18; // r12d
  int ProxyStubClassInfoFromPackageScopedCatalog; // edi
  unsigned int v20; // edx
  HRESULT v21; // r9d
  const char *v22; // rdx
  const char *v23; // rcx
  int v24; // r8d
  TraceLevel v25; // r9d
  __int64 v26; // rcx
  int v27; // eax
  IComCatalogInternal *m_ptr; // rbx
  HRESULT v29; // eax
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> *PackagedComCurrentPackageProvider; // rax
  IUserToken *v31; // r14
  int IsPackageInCurrentPackageGraph; // eax
  unsigned int v33; // edx
  HRESULT v34; // r9d
  IUserTokenInternal *v35; // rdx
  IUserToken_vtbl *v36; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  __int64 v38; // rcx
  unsigned int v39; // eax
  char v40; // r14
  unsigned int v41; // edi
  unsigned int v42; // ecx
  bool IsEnabled; // al
  wchar_t *v44; // rdi
  bool v45; // al
  __int64 v46; // rcx
  wchar_t *v47; // r15
  char v48; // di
  char v49; // si
  HRESULT PackageFamilyName; // eax
  unsigned int v51; // edx
  bool v52; // di
  char v53; // r15
  bool v54; // r15
  CComCatalog *v55; // rcx
  IRestrictedErrorRpcMarshal *v56; // rbx
  void **v57; // r15
  _GUID *v58; // r14
  _GUID *v59; // rsi
  CComCatalog *v60; // rcx
  IRestrictedErrorRpcMarshal *v61; // rdi
  TraceLevel v62; // r8d
  IRestrictedErrorRpcMarshal_vtbl *v63; // rsi
  __int64 (__fastcall *v64)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  TraceLevel v65; // edx
  int v66; // r8d
  int v67; // r13d
  unsigned int v68; // edx
  TraceLevel v69; // r8d
  IRestrictedErrorRpcMarshal_vtbl *v70; // rsi
  __int64 (__fastcall *v71)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  int v72; // edx
  int v73; // r15d
  TraceLevel v74; // edx
  IRestrictedErrorRpcMarshal *v75; // r13
  IRestrictedErrorRpcMarshal_vtbl *v76; // rsi
  __int64 (__fastcall *v77)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  _GUID *v78; // r12
  wchar_t *v79; // r8
  tagCLSCTX v80; // r15d
  HRESULT v81; // eax
  wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *p_catalogPackageAwarePackagedComCurrentPackage; // rcx
  IComCatalogPackageAware *v83; // rsi
  HRESULT (__fastcall *GetClassInfoW)(IComCatalogPackageAware *, tagCLSCTX, unsigned int, IUserTokenInternal *, const _GUID *, const wchar_t *, const wchar_t *, unsigned int, HSTRING__ *const *, unsigned int, HSTRING__ *const *, const _GUID *, void **); // rdi
  HRESULT v85; // eax
  int v86; // edx
  unsigned int v87; // r15d
  wchar_t *v88; // r8
  IRestrictedErrorRpcMarshal_vtbl *v89; // rsi
  __int64 (__fastcall *v90)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  HRESULT NoClassInfo; // eax
  unsigned int v92; // edx
  int v93; // edi
  unsigned int v94; // esi
  IRestrictedErrorRpcMarshal_vtbl *v95; // rsi
  HRESULT (__fastcall *v96)(IUnknown *, const _GUID *const, void **); // rax
  __int64 (__fastcall *v97)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  bool v98; // zf
  IRestrictedErrorRpcMarshal *v99; // rdi
  IRestrictedErrorRpcMarshal_vtbl *v100; // rsi
  int v101; // r13d
  HRESULT (__fastcall *v102)(IUnknown *, const _GUID *const, void **); // rax
  __int64 (__fastcall *v103)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  unsigned int v104; // edi
  int v105; // esi
  TraceLevel v106; // edx
  IRestrictedErrorRpcMarshal_vtbl *v107; // rsi
  __int64 (__fastcall *v108)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  TraceLevel v109; // r8d
  IRestrictedErrorRpcMarshal_vtbl *v110; // rsi
  __int64 (__fastcall *v111)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  bool v112; // al
  IComCatalogPackageAware *v113; // rdx
  TraceLevel v114; // r8d
  wchar_t *v115; // r9
  IComCatalogPackageAware *v116; // rcx
  HRESULT v117; // eax
  IComCatalogPackageAware *v118; // rsi
  HRESULT (__fastcall *v119)(IComCatalogPackageAware *, tagCLSCTX, unsigned int, IUserTokenInternal *, const _GUID *, const wchar_t *, const wchar_t *, unsigned int, HSTRING__ *const *, unsigned int, HSTRING__ *const *, const _GUID *, void **); // rdi
  _GUID *v120; // r15
  HRESULT v121; // eax
  IRestrictedErrorRpcMarshal_vtbl *v122; // rsi
  __int64 (__fastcall *v123)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  IComCatalogPackageAware *v124; // rsi
  HRESULT (__fastcall *v125)(IComCatalogPackageAware *, tagCLSCTX, unsigned int, IUserTokenInternal *, const _GUID *, const wchar_t *, const wchar_t *, unsigned int, HSTRING__ *const *, unsigned int, HSTRING__ *const *, const _GUID *, void **); // rdi
  HRESULT v126; // eax
  IRestrictedErrorRpcMarshal_vtbl *v127; // rsi
  __int64 (__fastcall *v128)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *); // rdi
  __int64 v129; // rdx
  unsigned int v130; // edi
  IRestrictedErrorRpcMarshal *v131; // r15
  int v132; // esi
  IRestrictedErrorRpcMarshal *v133; // rdi
  int v134; // r12d
  IRestrictedErrorRpcMarshal *v135; // rdi
  HRESULT ClassInfoW; // eax
  bool v137; // r13
  unsigned __int16 NativeArchitecture; // ax
  bool v139; // cl
  unsigned __int16 v140; // ax
  unsigned __int16 v141; // ax
  TraceLevel v142; // edx
  IRestrictedErrorRpcMarshal_vtbl *v143; // rdi
  __int64 (__fastcall *v144)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *); // r15
  __int64 v145; // rdx
  TraceLevel v146; // edx
  int v147; // ecx
  int v148; // r13d
  TraceLevel v149; // edx
  IRestrictedErrorRpcMarshal_vtbl *v150; // rdi
  __int64 (__fastcall *v151)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *); // r15
  __int64 v152; // rdx
  TraceLevel v153; // edx
  IRestrictedErrorRpcMarshal_vtbl *v154; // rdi
  __int64 (__fastcall *v155)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *); // r15
  __int64 v156; // rdx
  ClassInfoCandidate *p_x86WowClassInfoCandidate; // rdx
  unsigned int v158; // edi
  ClassInfoCandidate *p_nativeClassInfoCandidate; // rdx
  __int64 v160; // rcx
  ClassInfoCandidate *v161; // rdx
  unsigned __int16 v162; // ax
  ClassInfoCandidate *p_arm32WowClassInfoCandidate; // rdx
  ClassInfoCandidate *v164; // rax
  ClassInfoCandidate *v165; // rax
  __int64 v166; // rcx
  ClassInfoCandidate *v167; // rdx
  __int64 v168; // rcx
  bool v169; // al
  IRestrictedErrorRpcMarshal *v170; // rsi
  IRestrictedErrorRpcMarshal_vtbl *v171; // r15
  int v172; // r13d
  HRESULT (__fastcall *v173)(IUnknown *, const _GUID *const, void **); // rax
  __int64 (__fastcall *v174)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  IRestrictedErrorRpcMarshal_vtbl *v175; // r15
  HRESULT (__fastcall *v176)(IUnknown *, const _GUID *const, void **); // rax
  __int64 (__fastcall *v177)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rdi
  HRESULT v178; // eax
  TraceLevel v179; // edx
  HRESULT v180; // eax
  IRestrictedErrorRpcMarshal *v181; // rdi
  HRESULT (__fastcall *RpcGetUnmarshalClass)(IRestrictedErrorRpcMarshal *, const _GUID *, unsigned int, unsigned int, _GUID *); // rbx
  _GUID *v183; // r15
  HRESULT v184; // eax
  TraceLevel v185; // edx
  IRestrictedErrorRpcMarshal_vtbl *v186; // rcx
  HRESULT v187; // eax
  IRestrictedErrorRpcMarshal *v188; // rdi
  HRESULT (__fastcall *v189)(IRestrictedErrorRpcMarshal *, const _GUID *, unsigned int, unsigned int, _GUID *); // rbx
  HRESULT v190; // eax
  IUserToken *v191; // rsi
  IRestrictedErrorRpcMarshal_vtbl *v192; // rdi
  __int64 (__fastcall *v193)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *); // rbx
  _GUID *v194; // rbx
  const char *v195; // rdx
  const char *v196; // rcx
  int v197; // r8d
  TraceLevel v198; // r9d
  bool v199; // di
  int v200; // eax
  unsigned int v201; // edx
  char v202; // cl
  int v203; // eax
  IUnknown *v204; // rax
  _GUID *pCache; // [rsp+20h] [rbp-E0h]
  ClassInfoCandidate *line; // [rsp+28h] [rbp-D8h]
  unsigned int dwFlags; // [rsp+70h] [rbp-90h] BYREF
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy> classInfo; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 fValueFlags[2]; // [rsp+80h] [rbp-80h] BYREF
  bool inCurrentPackageGraph; // [rsp+84h] [rbp-7Ch] BYREF
  char v212; // [rsp+85h] [rbp-7Bh]
  bool resultFromRegistryViewIsTentativelyAcceptable; // [rsp+86h] [rbp-7Ah] BYREF
  int v214; // [rsp+88h] [rbp-78h]
  bool v215; // [rsp+8Ch] [rbp-74h]
  char v216; // [rsp+8Dh] [rbp-73h]
  int v217; // [rsp+90h] [rbp-70h]
  _GUID *rclsid; // [rsp+98h] [rbp-68h]
  _GUID *v219; // [rsp+A0h] [rbp-60h]
  wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> v220; // [rsp+A8h] [rbp-58h] BYREF
  wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> userTokenInternal; // [rsp+B0h] [rbp-50h] BYREF
  HRESULT hrProvider; // [rsp+B8h] [rbp-48h] BYREF
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> catalogPackagedComCurrentPackage; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v224; // [rsp+C8h] [rbp-38h]
  ComCatalogDiagnosticData catalogDiagnosticData; // [rsp+D0h] [rbp-30h] BYREF
  int currentCatalog; // [rsp+E8h] [rbp-18h] BYREF
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy> hrCache; // [rsp+F0h] [rbp-10h] BYREF
  IUserToken *userToken; // [rsp+F8h] [rbp-8h]
  wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> v229; // [rsp+100h] [rbp+0h] BYREF
  wil::com_ptr_t<IClassClassicInfo3,wil::err_returncode_policy> pICCI3; // [rsp+108h] [rbp+8h] BYREF
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy> previousClassInfo; // [rsp+110h] [rbp+10h] BYREF
  ClassInfoCandidate nativeClassInfoCandidate; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 cbSid[2]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 cbIntegritySID; // [rsp+12Ch] [rbp+2Ch] BYREF
  unsigned int dwPreferredServerBitness; // [rsp+130h] [rbp+30h] BYREF
  wil::com_ptr_t<IComCatalogPackageAware,wil::err_returncode_policy> catalogPackageAwarePackagedComAllPackages; // [rsp+138h] [rbp+38h] BYREF
  ClassInfoCandidate arm32WowClassInfoCandidate; // [rsp+140h] [rbp+40h] BYREF
  ClassInfoCandidate x86WowClassInfoCandidate; // [rsp+150h] [rbp+50h] BYREF
  wchar_t *first; // [rsp+160h] [rbp+60h]
  wchar_t *packageFullName; // [rsp+168h] [rbp+68h]
  unsigned __int16 acbKey[4]; // [rsp+170h] [rbp+70h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&PrivMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > currentPackageFamilyName; // [rsp+178h] [rbp+78h] BYREF
  wil::com_ptr_t<IComCatalogPackageAware,wil::err_returncode_policy> catalogPackageAwarePackagedComCurrentPackage; // [rsp+180h] [rbp+80h] BYREF
  HSTRING__ *const *v244; // [rsp+188h] [rbp+88h]
  void **ptrResult; // [rsp+190h] [rbp+90h]
  ClassInfoCandidate *registryClassInfoCandidates[3]; // [rsp+198h] [rbp+98h] BYREF
  unsigned int flagsForCache; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 *pIntegritySID; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned __int8 *pSid; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int8 *apKey[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  wil::details::lambda_call<<lambda_009d5060e5934af28c563eb57404125c> > traceCatalogLookupFailure; // [rsp+1E8h] [rbp+E8h] BYREF
  GuidString clsidString; // [rsp+210h] [rbp+110h] BYREF
  GuidString requestedIidString; // [rsp+260h] [rbp+160h] BYREF
  void *retaddr; // [rsp+308h] [rbp+208h]

  ptrResult = ppv;
  v17 = 0;
  v18 = 0;
  packageFullName = explicitMainPackageFamilyName;
  previousClassInfo.m_ptr = (IUnknown *)comDependencyMainPackageFamilyCount;
  v244 = flags_0;
  traceCatalogLookupFailure.m_lambda.hrProvider = &hrProvider;
  traceCatalogLookupFailure.m_lambda.currentCatalog = (ComCatalogDiagnosticData::Catalogs *)&currentCatalog;
  traceCatalogLookupFailure.m_lambda.flags = &dwFlags;
  rclsid = guidConfiguredClsid;
  userToken = pUserToken;
  v220.m_ptr = (IRestrictedErrorRpcMarshal *)this;
  dwFlags = flags;
  v219 = riid;
  first = packageGraphPackageCount;
  hrProvider = 0;
  currentCatalog = 0;
  traceCatalogLookupFailure.m_lambda.guidConfiguredClsid = guidConfiguredClsid;
  traceCatalogLookupFailure.m_call = 1;
  v217 = 0;
  fValueFlags[0] = 0;
  pSid = 0;
  cbSid[0] = 0;
  pIntegritySID = 0;
  cbIntegritySID = 0;
  nativeClassInfoCandidate.ClassInfo.m_ptr = 0;
  nativeClassInfoCandidate.IsTentativelyAcceptable = 0;
  *(_DWORD *)nativeClassInfoCandidate.WhichCatalog = 128;
  x86WowClassInfoCandidate.ClassInfo.m_ptr = 0;
  x86WowClassInfoCandidate.IsTentativelyAcceptable = 0;
  *(_DWORD *)x86WowClassInfoCandidate.WhichCatalog = 256;
  arm32WowClassInfoCandidate.ClassInfo.m_ptr = 0;
  arm32WowClassInfoCandidate.IsTentativelyAcceptable = 0;
  *(_DWORD *)arm32WowClassInfoCandidate.WhichCatalog = 512;
  *(_QWORD *)catalogDiagnosticData.TriedCatalogs = 0;
  *(_QWORD *)catalogDiagnosticData.AcceptedCatalogs = 0;
  catalogDiagnosticData.Flags = flags;
  if ( (flags & 0xCE8) == 0 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( packageGraphPackages && !previousClassInfo.m_ptr )
      {
        ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
        v20 = 3355;
LABEL_10:
        v21 = ProxyStubClassInfoFromPackageScopedCatalog;
LABEL_11:
        wil::details::in1diag3::Return_Hr(retaddr, v20, "onecore\\com\\combase\\catalog\\catalog.cxx", v21);
LABEL_612:
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&arm32WowClassInfoCandidate);
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&x86WowClassInfoCandidate);
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&nativeClassInfoCandidate);
        traceCatalogLookupFailure.m_call = 0;
        goto LABEL_613;
      }
      if ( (catalogFlags & 0xFFFFFFE8) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
        v20 = 3358;
LABEL_9:
        ProxyStubClassInfoFromPackageScopedCatalog = -2147418113;
        goto LABEL_10;
      }
      if ( (explicitPackageFullName & 0xCFF) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
        v20 = 3359;
        goto LABEL_9;
      }
      if ( (dwFlags & 0x17) != 0 )
      {
        if ( catalogFlags != (dwFlags & 0x17) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
          v20 = 3377;
          goto LABEL_9;
        }
      }
      else if ( catalogFlags != 23 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
        v20 = 3373;
        goto LABEL_9;
      }
      if ( explicitPackageFullName != (dwFlags & 0xFFFFF300) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
        v20 = 3381;
        goto LABEL_9;
      }
      if ( packageFullName && packageGraphPackageCount )
      {
        ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
        v20 = 3384;
        goto LABEL_10;
      }
    }
    v224 = dwFlags & 0x200000;
    LODWORD(v229.m_ptr) = dwFlags & 0x8000000;
    GuidString::GuidString(&clsidString, guidConfiguredClsid);
    GuidString::GuidString(&requestedIidString, riid);
    if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
      ComTraceMessageT<unsigned short const *,unsigned long,unsigned short const *>(
        v23,
        v22,
        v24,
        v25,
        (const wchar_t *)pCache,
        clsidString.m_string,
        dwFlags,
        requestedIidString.m_string);
    *ptrResult = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && !CComCatalog::ms_fInitialized._Storage._Value )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v26);
    }
    v27 = CComCatalog::InitializeCatalogIfNecessary(this);
    ProxyStubClassInfoFromPackageScopedCatalog = v27;
    if ( v27 < 0 )
    {
      v21 = v27;
      v20 = 3411;
      goto LABEL_11;
    }
    m_ptr = 0;
    catalogPackagedComCurrentPackage.m_ptr = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v29 = CComCatalog::InitializePackagedComCurrentPackageProviderIfNecessary(this, 0);
      ProxyStubClassInfoFromPackageScopedCatalog = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0xD58u, "onecore\\com\\combase\\catalog\\catalog.cxx", v29);
LABEL_35:
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackagedComCurrentPackage);
        goto LABEL_612;
      }
      PackagedComCurrentPackageProvider = CComCatalog::GetPackagedComCurrentPackageProvider(
                                            this,
                                            (wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> *)&currentPackageFamilyName);
      wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(
        &catalogPackagedComCurrentPackage,
        PackagedComCurrentPackageProvider);
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&currentPackageFamilyName);
      m_ptr = catalogPackagedComCurrentPackage.m_ptr;
    }
    v31 = userToken;
    userTokenInternal.m_ptr = 0;
    if ( userToken )
    {
      IsPackageInCurrentPackageGraph = userToken->GetUserSid(userToken, &pSid, cbSid);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3428;
LABEL_40:
        v34 = IsPackageInCurrentPackageGraph;
LABEL_41:
        wil::details::in1diag3::Return_Hr(retaddr, v33, "onecore\\com\\combase\\catalog\\catalog.cxx", v34);
LABEL_42:
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&userTokenInternal);
        goto LABEL_35;
      }
      IsPackageInCurrentPackageGraph = v31->GetIntegritySID(v31, &pIntegritySID, &cbIntegritySID);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3429;
        goto LABEL_40;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      {
        v35 = userTokenInternal.m_ptr;
        v36 = v31->__vftable;
        userTokenInternal.m_ptr = 0;
        QueryInterface = v36->QueryInterface;
        if ( v35 )
          v35->Release(v35);
        ProxyStubClassInfoFromPackageScopedCatalog = QueryInterface(
                                                       v31,
                                                       &GUID_000001fc_0000_0000_cfff_123045660046,
                                                       (void **)&userTokenInternal.m_ptr);
        if ( ProxyStubClassInfoFromPackageScopedCatalog < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v38);
          v34 = ProxyStubClassInfoFromPackageScopedCatalog;
          v33 = 3435;
          goto LABEL_41;
        }
      }
    }
    v39 = CComCatalog::FlagsForCacheKey(dwFlags);
    apKey[0] = (unsigned __int8 *)guidConfiguredClsid;
    flagsForCache = v39 & 0xF7FFFFFF;
    catalogDiagnosticData.FlagsForCache = v39 & 0xF7FFFFFF;
    apKey[1] = pSid;
    apKey[2] = pIntegritySID;
    apKey[3] = (unsigned __int8 *)&flagsForCache;
    acbKey[0] = 16;
    acbKey[1] = cbSid[0];
    acbKey[2] = cbIntegritySID;
    acbKey[3] = 4;
    v40 = 1;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v41 = explicitPackageFullName >> 9;
      v42 = dwFlags & 0xFFFFFDFF;
      LOBYTE(v41) = (explicitPackageFullName & 0x200) != 0;
      dwPreferredServerBitness = v41;
    }
    else
    {
      v42 = dwFlags & 0xFFFFFDFF;
      LOBYTE(dwPreferredServerBitness) = (dwFlags & 0x200) != 0;
    }
    dwFlags = v42;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v44 = packageFullName;
    if ( IsEnabled )
    {
      if ( !packageFullName && !first && !packageGraphPackages && !comDependencyMainPackageFamilies )
        v40 = 0;
      LOBYTE(v214) = v40;
    }
    else
    {
      v40 = 0;
      LOBYTE(v214) = 0;
    }
    v45 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v46 = 0;
    if ( !v45 )
    {
      v48 = 0;
      v212 = 0;
      goto LABEL_91;
    }
    v47 = first;
    if ( !v44 && !first )
    {
      v212 = 0;
LABEL_65:
      v48 = v212;
LABEL_91:
      v49 = 0;
      resultFromRegistryViewIsTentativelyAcceptable = 0;
      v215 = 0;
LABEL_92:
      v216 = 0;
      goto LABEL_93;
    }
    v212 = 1;
    if ( v44 )
    {
      if ( (explicitPackageFullName & 0x4000) != 0 )
      {
        inCurrentPackageGraph = 0;
        IsPackageInCurrentPackageGraph = GetIsPackageInCurrentPackageGraph(
                                           v44,
                                           userTokenInternal.m_ptr,
                                           packageGraphPackages,
                                           (HSTRING__ *const *)previousClassInfo.m_ptr,
                                           &inCurrentPackageGraph);
        v46 = 0;
        ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
        if ( IsPackageInCurrentPackageGraph < 0 )
        {
          v33 = 3562;
          goto LABEL_40;
        }
        v215 = !inCurrentPackageGraph;
      }
      else
      {
        v215 = 1;
      }
      v48 = v212;
      v49 = 1;
      resultFromRegistryViewIsTentativelyAcceptable = 1;
      goto LABEL_92;
    }
    if ( !first )
      goto LABEL_65;
    currentPackageFamilyName.m_ptr = 0;
    PackageFamilyName = TryGetPackageFamilyName(userTokenInternal.m_ptr, &currentPackageFamilyName);
    ProxyStubClassInfoFromPackageScopedCatalog = PackageFamilyName;
    if ( PackageFamilyName < 0 )
    {
      v51 = 3589;
LABEL_76:
      wil::details::in1diag3::Return_Hr(retaddr, v51, "onecore\\com\\combase\\catalog\\catalog.cxx", PackageFamilyName);
      Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&currentPackageFamilyName);
      goto LABEL_42;
    }
    if ( currentPackageFamilyName.m_ptr && PackageNamesMatch(v47, currentPackageFamilyName.m_ptr) )
    {
      if ( g_bInSCM )
      {
        v52 = 1;
      }
      else
      {
        LODWORD(hrCache.m_ptr) = 0;
        PackageFamilyName = AppModelPolicy_GetPolicy(
                              (void *)0xFFFFFFFFFFFFFFFCLL,
                              AppModelPolicy_Type_PackageMayContainPrivateComRegistrations,
                              (AppModelPolicy_PolicyValue *)&hrCache);
        ProxyStubClassInfoFromPackageScopedCatalog = PackageFamilyName;
        if ( PackageFamilyName < 0 )
        {
          v51 = 3619;
          goto LABEL_76;
        }
        v52 = LODWORD(hrCache.m_ptr) != 1048577;
      }
      v53 = 0;
      resultFromRegistryViewIsTentativelyAcceptable = v52;
      v215 = 0;
      v216 = 1;
    }
    else
    {
      v216 = 0;
      v53 = 1;
      v215 = 1;
      v52 = 1;
      resultFromRegistryViewIsTentativelyAcceptable = 1;
    }
    v49 = v53;
    Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&currentPackageFamilyName);
    v212 = 1;
    if ( v53 )
    {
      dwFlags &= ~0x1000u;
    }
    else
    {
      v215 = 0;
      resultFromRegistryViewIsTentativelyAcceptable = v52;
    }
    v48 = v212;
LABEL_93:
    v54 = 1;
    inCurrentPackageGraph = 1;
    if ( (dwFlags & 0x80000) == 0 )
      goto LABEL_102;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( v48 )
      {
        v54 = 0;
        goto LABEL_102;
      }
      IsPackageInCurrentPackageGraph = IsAllowListedCLSID(rclsid, &inCurrentPackageGraph);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3700;
        goto LABEL_40;
      }
    }
    else
    {
      IsPackageInCurrentPackageGraph = IsAllowListedCLSID(rclsid, &inCurrentPackageGraph);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3705;
        goto LABEL_40;
      }
    }
    v54 = inCurrentPackageGraph;
LABEL_102:
    if ( ((dwFlags ^ (dwFlags >> 4)) & 0x40000) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v46);
    if ( (dwFlags & 0x440000) == 0x440000 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
        && v40 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v55);
        ProxyStubClassInfoFromPackageScopedCatalog = -2147418113;
        v33 = 3728;
        v34 = -2147418113;
        goto LABEL_41;
      }
      v56 = v220.m_ptr;
      v57 = ptrResult;
      v58 = v219;
      v59 = rclsid;
      ProxyStubClassInfoFromPackageScopedCatalog = CComCatalog::GetProxyStubClassInfoFromPackageScopedCatalog(
                                                     v55,
                                                     dwFlags,
                                                     rclsid,
                                                     (IComCatalogInternal *)v220.m_ptr[21].__vftable,
                                                     s_pCacheInboxAppProxyStubClassInfo,
                                                     v219,
                                                     ptrResult);
      if ( ProxyStubClassInfoFromPackageScopedCatalog == -2147221164 )
        ProxyStubClassInfoFromPackageScopedCatalog = CComCatalog::GetProxyStubClassInfoFromPackageScopedCatalog(
                                                       v60,
                                                       dwFlags,
                                                       v59,
                                                       (IComCatalogInternal *)v56[20].__vftable,
                                                       s_pCachePerUserProxyStubClassInfo,
                                                       v58,
                                                       v57);
      if ( ProxyStubClassInfoFromPackageScopedCatalog < 0 )
      {
        v34 = ProxyStubClassInfoFromPackageScopedCatalog;
        v33 = 3739;
        goto LABEL_41;
      }
LABEL_611:
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&userTokenInternal);
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackagedComCurrentPackage);
      ProxyStubClassInfoFromPackageScopedCatalog = 0;
      goto LABEL_612;
    }
    classInfo.m_ptr = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( !LODWORD(v229.m_ptr) || v224 )
      {
        v61 = v220.m_ptr;
        if ( !v220.m_ptr[18].__vftable || v49 )
        {
LABEL_147:
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
          if ( !v54 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              0xEF2u,
              "onecore\\com\\combase\\catalog\\catalog.cxx",
              -2147221164);
            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&classInfo);
            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&userTokenInternal);
            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackagedComCurrentPackage);
            ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
            goto LABEL_612;
          }
          LODWORD(hrCache.m_ptr) = dwFlags & 0x80000;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
          {
            if ( v215 )
              goto LABEL_153;
            v72 = g_bInSCM;
            if ( g_bInSCM )
            {
              if ( (dwFlags & 0x2000) == 0 )
                goto LABEL_153;
            }
            else if ( !m_ptr || (dwFlags & 1) == 0 )
            {
              goto LABEL_153;
            }
            currentCatalog = 2;
            *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v17 | 2;
            if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
            {
              ComTraceMessageT<void *>(
                "onecore\\com\\combase\\catalog\\catalog.cxx",
                "CComCatalog::GetClassInfoInternal",
                3880,
                CHATTY,
                v79,
                (ServerCall *)&clsidString);
              v72 = g_bInSCM;
            }
            v80 = catalogFlags;
            if ( !v72 )
              v80 = catalogFlags & 1;
            catalogPackageAwarePackagedComCurrentPackage.m_ptr = 0;
            v81 = wil::com_query_to_nothrow<IComCatalogPackageAware,wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &>(
                    &catalogPackagedComCurrentPackage,
                    &catalogPackageAwarePackagedComCurrentPackage.m_ptr);
            ProxyStubClassInfoFromPackageScopedCatalog = v81;
            if ( v81 < 0 )
            {
              wil::details::in1diag3::Return_Hr(retaddr, 0xF37u, "onecore\\com\\combase\\catalog\\catalog.cxx", v81);
LABEL_173:
              p_catalogPackageAwarePackagedComCurrentPackage = (wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComCurrentPackage;
LABEL_463:
              wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(p_catalogPackageAwarePackagedComCurrentPackage);
              goto LABEL_131;
            }
            v83 = catalogPackageAwarePackagedComCurrentPackage.m_ptr;
            GetClassInfoW = catalogPackageAwarePackagedComCurrentPackage.m_ptr->GetClassInfoW;
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
            LODWORD(line) = (_DWORD)packageFullName;
            pCache = rclsid;
            v85 = ((__int64 (__fastcall *)(IComCatalogPackageAware *, _QWORD, _QWORD, IUserTokenInternal *))GetClassInfoW)(
                    v83,
                    (unsigned int)v80,
                    0,
                    userTokenInternal.m_ptr);
            hrProvider = v85;
            ProxyStubClassInfoFromPackageScopedCatalog = v85;
            if ( v85 )
            {
              if ( v85 != -2147221164 )
              {
                if ( v85 < 0 )
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    0xF4Eu,
                    "onecore\\com\\combase\\catalog\\catalog.cxx",
                    v85,
                    "CLSID:%ls Flags:%#x IID:%ls",
                    clsidString.m_string,
                    dwFlags,
                    requestedIidString.m_string);
                goto LABEL_173;
              }
            }
            else
            {
              v18 |= 2u;
              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                  "CComCatalog::GetClassInfoInternal",
                  3905,
                  CHATTY,
                  (wchar_t *)L"Found %ls in PackagedCom current package Catalog",
                  (ServerCall *)&clsidString);
              LOWORD(v67) = 256;
              v217 = 256;
              fValueFlags[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
              {
                *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 2;
                *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 2;
                wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComCurrentPackage);
LABEL_180:
                v78 = rclsid;
                goto LABEL_581;
              }
            }
            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComCurrentPackage);
          }
          else
          {
            v86 = g_bInSCM;
            if ( g_bInSCM )
            {
              v87 = dwFlags;
              if ( (dwFlags & 0x2000) == 0 )
                goto LABEL_153;
            }
            else
            {
              if ( !v61[25].__vftable )
                goto LABEL_153;
              v87 = dwFlags;
              if ( (dwFlags & 1) == 0 )
                goto LABEL_153;
            }
            currentCatalog = 2;
            *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v17 | 2;
            if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
            {
              ComTraceMessageT<void *>(
                "onecore\\com\\combase\\catalog\\catalog.cxx",
                "CComCatalog::GetClassInfoInternal",
                3931,
                CHATTY,
                v88,
                (ServerCall *)&clsidString);
              v86 = g_bInSCM;
              v87 = dwFlags;
            }
            if ( !v86 )
              v87 &= 0xFFFFF301;
            v89 = v61[25].__vftable;
            v90 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v89->QueryInterface + 3);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
            line = (ClassInfoCandidate *)&classInfo;
            pCache = v219;
            hrProvider = v90(v89, v87, userToken, rclsid);
            ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
            if ( hrProvider )
            {
              if ( hrProvider != -2147221164 )
              {
                if ( hrProvider >= 0 )
                  goto LABEL_131;
                v68 = 3961;
                goto LABEL_130;
              }
            }
            else
            {
              v18 |= 2u;
              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                  "CComCatalog::GetClassInfoInternal",
                  3950,
                  CHATTY,
                  (wchar_t *)L"Found %ls in PackagedCom current package Catalog",
                  (ServerCall *)&clsidString);
              LOWORD(v67) = 256;
              v217 = 256;
              fValueFlags[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
              {
                *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 2;
                *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 2;
                goto LABEL_180;
              }
            }
          }
LABEL_153:
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
          v73 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
          if ( (dwFlags & 0x1000) != 0 )
          {
            v73 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 4;
            currentCatalog = 4;
            *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 4u;
            if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
              ComTraceMessageT<void *>(
                "onecore\\com\\combase\\catalog\\catalog.cxx",
                "CComCatalog::GetClassInfoInternal",
                3978,
                v74,
                (wchar_t *)L"Look for %ls in private hive Catalog...",
                (ServerCall *)&clsidString);
            v75 = v220.m_ptr;
            v76 = v220.m_ptr[22].__vftable;
            v77 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v76->QueryInterface + 3);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
            line = (ClassInfoCandidate *)&classInfo;
            pCache = v219;
            hrProvider = v77(v76, dwFlags, userToken, rclsid);
            ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
            if ( hrProvider )
            {
              if ( hrProvider != -2147221164 )
              {
                if ( hrProvider >= 0 )
                  goto LABEL_131;
                v68 = 4002;
                goto LABEL_130;
              }
            }
            else
            {
              v18 |= 4u;
              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                  "CComCatalog::GetClassInfoInternal",
                  3988,
                  CHATTY,
                  (wchar_t *)L"Found %ls in private hive Catalog",
                  (ServerCall *)&clsidString);
              LOWORD(v67) = 256;
              v217 = 256;
              fValueFlags[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
              {
                *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 4;
                *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 4;
LABEL_163:
                v78 = rclsid;
LABEL_581:
                v194 = v219;
                goto LABEL_582;
              }
              v75 = v220.m_ptr;
            }
          }
          else
          {
            v75 = v220.m_ptr;
          }
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
          {
            if ( (_BYTE)v214 || !s_pCacheClassInfo )
            {
LABEL_240:
              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
              if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
              {
                v93 = (int)hrCache.m_ptr;
                v94 = v224;
                if ( !v212 && !LODWORD(hrCache.m_ptr) && !LODWORD(v229.m_ptr) && !v224 )
                {
                  v95 = v75[17].__vftable;
                  if ( v95 )
                  {
                    currentCatalog = 16;
                    v96 = v95->QueryInterface;
                    *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v73 | 0x10;
                    v97 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v96 + 3);
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                    line = (ClassInfoCandidate *)&classInfo;
                    pCache = v219;
                    hrProvider = v97(v95, dwFlags, userToken, rclsid);
                    ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                    if ( hrProvider )
                    {
                      if ( hrProvider != -2147221164 )
                      {
                        if ( hrProvider >= 0 )
                          goto LABEL_131;
                        v68 = 4174;
                        goto LABEL_130;
                      }
                    }
                    else
                    {
                      LOWORD(v67) = 2;
                      v18 |= 0x10u;
                      v217 = 2;
                      *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                      fValueFlags[0] = 2;
                      if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                      {
                        *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 16;
                        *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 16;
                        goto LABEL_180;
                      }
                    }
                    v93 = (int)hrCache.m_ptr;
                  }
                  v94 = v224;
                }
                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                if ( v212 )
                  goto LABEL_299;
                v98 = v93 == 0;
                v99 = v220.m_ptr;
                if ( v98 && !LODWORD(v229.m_ptr) && !v94 )
                {
                  v100 = v220.m_ptr[14].__vftable;
                  v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
                  if ( !v100 )
                    goto LABEL_301;
                  currentCatalog = 32;
                  v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 0x20;
                  v102 = v100->QueryInterface;
                  *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x20u;
                  v103 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v102 + 3);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                  line = (ClassInfoCandidate *)&classInfo;
                  pCache = v219;
                  hrProvider = v103(v100, dwFlags, userToken, rclsid);
                  ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                  if ( hrProvider )
                  {
                    if ( hrProvider != -2147221164 )
                    {
                      if ( hrProvider >= 0 )
                        goto LABEL_131;
                      v68 = 4201;
                      goto LABEL_130;
                    }
                    goto LABEL_300;
                  }
                  LOWORD(v67) = 2;
                  v18 |= 0x20u;
                  *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                  v217 = 2;
                  fValueFlags[0] = 2;
                  if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                  {
                    *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 32;
                    *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 32;
                    goto LABEL_180;
                  }
LABEL_299:
                  v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
LABEL_300:
                  v99 = v220.m_ptr;
LABEL_301:
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                  v112 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
                  v113 = 0;
                  if ( v112 && v216 || !g_bInSCM || (dwFlags & 0x4000) != 0 )
                  {
LABEL_336:
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                    {
                      if ( !v212 && !g_bInSCM )
                      {
                        if ( LODWORD(v229.m_ptr) || (v130 = v224) == 0 )
                        {
                          v131 = v220.m_ptr;
                          v132 = 2048;
                          currentCatalog = 2048;
                          *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v101 | 0x800;
                          v133 = v220.m_ptr + 2;
                          if ( !v220.m_ptr )
                            v133 = 0;
                          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                          hrProvider = DeviceCatalogs::GetClassInfoW(
                                         (DeviceCatalogs *)&v131[28],
                                         dwFlags & 0xFFFFF301,
                                         userToken,
                                         rclsid,
                                         v219,
                                         (void **)&classInfo.m_ptr,
                                         v133);
                          ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                          if ( !hrProvider )
                          {
LABEL_344:
                            v134 = v18 | 0x800;
                            *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 2048;
                            v67 = 1024;
LABEL_345:
                            *(_DWORD *)catalogDiagnosticData.SelectedCatalog = v132;
                            *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v134;
                            v217 = v67;
                            fValueFlags[0] = v67;
                            goto LABEL_180;
                          }
                          if ( hrProvider != -2147221164 )
                          {
                            if ( hrProvider >= 0 )
                              goto LABEL_131;
                            v68 = 4432;
                            goto LABEL_130;
                          }
                          goto LABEL_360;
                        }
LABEL_358:
                        v131 = v220.m_ptr;
LABEL_361:
                        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
                          && resultFromRegistryViewIsTentativelyAcceptable )
                        {
                          goto $noComClassInfoInClassicRegistryProviders;
                        }
                        v137 = 0;
                        inCurrentPackageGraph = 0;
                        if ( !g_bInSCM || (dwFlags & 0x10000000) != 0 )
                        {
                          v139 = 1;
                        }
                        else if ( (dwFlags & 0x20000000) != 0 )
                        {
                          NativeArchitecture = GetNativeArchitecture();
                          v139 = NativeArchitecture == 332;
                          v137 = NativeArchitecture != 332;
                        }
                        else if ( (dwFlags & 0x40000000) != 0 )
                        {
                          v140 = GetNativeArchitecture();
                          v139 = GetArchitecturePointerSizeInBytes(v140) == 8;
                        }
                        else if ( (dwFlags & 0x80000000) == 0 )
                        {
                          v139 = 1;
                          inCurrentPackageGraph = 1;
                          v137 = 1;
                        }
                        else
                        {
                          v141 = GetNativeArchitecture();
                          v139 = v141 == 452;
                          inCurrentPackageGraph = v141 != 452;
                        }
                        if ( LODWORD(v229.m_ptr) || !v130 )
                        {
                          if ( v131[13].__vftable && v139 )
                          {
                            *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x80u;
                            currentCatalog = 128;
                            if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                              ComTraceMessageT<void *>(
                                "onecore\\com\\combase\\catalog\\catalog.cxx",
                                "CComCatalog::GetClassInfoInternal",
                                4555,
                                v142,
                                (wchar_t *)L"Look for %ls in registry...",
                                (ServerCall *)&clsidString);
                            v143 = v131[13].__vftable;
                            v144 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *))*((_QWORD *)v143->QueryInterface + 3);
                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&nativeClassInfoCandidate);
                            v145 = dwFlags;
                            if ( LODWORD(hrCache.m_ptr) )
                              v145 = dwFlags | 0x30000;
                            line = &nativeClassInfoCandidate;
                            pCache = v219;
                            hrProvider = v144(v143, v145, userToken, rclsid);
                            ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                            if ( hrProvider )
                            {
                              if ( hrProvider != -2147221164 )
                              {
                                if ( hrProvider >= 0 )
                                  goto LABEL_131;
                                v68 = 4584;
                                goto LABEL_130;
                              }
                              v131 = v220.m_ptr;
                            }
                            else
                            {
                              v18 |= 0x80u;
                              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                ComTraceMessageT<void *>(
                                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                                  "CComCatalog::GetClassInfoInternal",
                                  4566,
                                  v146,
                                  (wchar_t *)L"Found %ls in registry",
                                  (ServerCall *)&clsidString);
                              v217 = 1;
                              fValueFlags[0] = 1;
                              if ( !ClassRegistrationMatchesRequestedClsctx(
                                      nativeClassInfoCandidate.ClassInfo.m_ptr,
                                      dwFlags,
                                      &nativeClassInfoCandidate.IsTentativelyAcceptable)
                                && !g_bInSCM )
                              {
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&nativeClassInfoCandidate);
                              }
                              v131 = v220.m_ptr;
                              if ( nativeClassInfoCandidate.IsTentativelyAcceptable )
                                *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 128;
                            }
                          }
                          v147 = (int)v229.m_ptr;
                          if ( LODWORD(v229.m_ptr) || !v224 )
                          {
                            if ( v131[15].__vftable )
                            {
                              v98 = !v137;
                              v148 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
                              if ( !v98 )
                              {
                                v148 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 0x100;
                                currentCatalog = 256;
                                *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x100u;
                                if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                  ComTraceMessageT<void *>(
                                    "onecore\\com\\combase\\catalog\\catalog.cxx",
                                    "CComCatalog::GetClassInfoInternal",
                                    4595,
                                    v149,
                                    (wchar_t *)L"Look for %ls in x86 WOW registry...",
                                    (ServerCall *)&clsidString);
                                v150 = v131[15].__vftable;
                                v151 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *))*((_QWORD *)v150->QueryInterface + 3);
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&x86WowClassInfoCandidate);
                                v152 = dwFlags;
                                if ( LODWORD(hrCache.m_ptr) )
                                  v152 = dwFlags | 0x30000;
                                line = &x86WowClassInfoCandidate;
                                pCache = v219;
                                hrProvider = v151(v150, v152, userToken, rclsid);
                                ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                                if ( hrProvider )
                                {
                                  if ( hrProvider != -2147221164 )
                                  {
                                    if ( hrProvider >= 0 )
                                      goto LABEL_131;
                                    v68 = 4617;
                                    goto LABEL_130;
                                  }
                                  v131 = v220.m_ptr;
                                  v147 = (int)v229.m_ptr;
                                }
                                else
                                {
                                  v18 |= 0x100u;
                                  *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                                  if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                    ComTraceMessageT<void *>(
                                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                                      "CComCatalog::GetClassInfoInternal",
                                      4607,
                                      v153,
                                      (wchar_t *)L"Found %ls in x86 WOW registry",
                                      (ServerCall *)&clsidString);
                                  resultFromRegistryViewIsTentativelyAcceptable = 0;
                                  v217 = 8;
                                  fValueFlags[0] = 8;
                                  ClassRegistrationMatchesRequestedClsctx(
                                    x86WowClassInfoCandidate.ClassInfo.m_ptr,
                                    dwFlags,
                                    &resultFromRegistryViewIsTentativelyAcceptable);
                                  v131 = v220.m_ptr;
                                  v147 = (int)v229.m_ptr;
                                  x86WowClassInfoCandidate.IsTentativelyAcceptable = resultFromRegistryViewIsTentativelyAcceptable;
                                  if ( resultFromRegistryViewIsTentativelyAcceptable )
                                    *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 0x100u;
                                }
                              }
                            }
                            else
                            {
                              v148 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
                            }
                            if ( (v147 || !v224) && v131[16].__vftable && inCurrentPackageGraph )
                            {
                              currentCatalog = 512;
                              *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v148 | 0x200;
                              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                ComTraceMessageT<void *>(
                                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                                  "CComCatalog::GetClassInfoInternal",
                                  4628,
                                  CHATTY,
                                  (wchar_t *)L"Look for %ls in ARM32 WOW registry...",
                                  (ServerCall *)&clsidString);
                              v154 = v131[16].__vftable;
                              v155 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *))*((_QWORD *)v154->QueryInterface + 3);
                              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&arm32WowClassInfoCandidate);
                              v156 = dwFlags;
                              if ( LODWORD(hrCache.m_ptr) )
                                v156 = dwFlags | 0x30000;
                              line = &arm32WowClassInfoCandidate;
                              pCache = v219;
                              hrProvider = v155(v154, v156, userToken, rclsid);
                              ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                              if ( !hrProvider )
                              {
                                v18 |= 0x200u;
                                *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                                if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                  ComTraceMessageT<void *>(
                                    "onecore\\com\\combase\\catalog\\catalog.cxx",
                                    "CComCatalog::GetClassInfoInternal",
                                    4640,
                                    CHATTY,
                                    (wchar_t *)L"Found %ls in ARM32 WOW registry",
                                    (ServerCall *)&clsidString);
                                LOWORD(v67) = 8;
                                fValueFlags[0] = 8;
                                v217 = 8;
                                inCurrentPackageGraph = 0;
                                ClassRegistrationMatchesRequestedClsctx(
                                  arm32WowClassInfoCandidate.ClassInfo.m_ptr,
                                  dwFlags,
                                  &inCurrentPackageGraph);
                                arm32WowClassInfoCandidate.IsTentativelyAcceptable = inCurrentPackageGraph;
                                if ( inCurrentPackageGraph )
                                  *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 0x200u;
LABEL_434:
                                if ( nativeClassInfoCandidate.ClassInfo.m_ptr
                                  || x86WowClassInfoCandidate.ClassInfo.m_ptr
                                  || arm32WowClassInfoCandidate.ClassInfo.m_ptr != nativeClassInfoCandidate.ClassInfo.m_ptr )
                                {
                                  if ( !g_bInSCM || (dwFlags & 0x10000000) != 0 )
                                    goto LABEL_438;
                                  if ( (dwFlags & 0x20000000) != 0 )
                                  {
                                    if ( GetNativeArchitecture() != 332 )
                                    {
                                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 256;
                                      p_x86WowClassInfoCandidate = &x86WowClassInfoCandidate;
                                      goto LABEL_439;
                                    }
LABEL_438:
                                    p_x86WowClassInfoCandidate = &nativeClassInfoCandidate;
                                    *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 128;
LABEL_439:
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                      &classInfo,
                                      &p_x86WowClassInfoCandidate->ClassInfo);
                                    goto LABEL_180;
                                  }
                                  if ( (dwFlags & 0x40000000) != 0 )
                                    goto LABEL_438;
                                  if ( (dwFlags & 0x80000000) != 0 )
                                  {
                                    if ( GetNativeArchitecture() != 452 )
                                    {
                                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 512;
                                      p_x86WowClassInfoCandidate = &arm32WowClassInfoCandidate;
                                      goto LABEL_439;
                                    }
                                    goto LABEL_438;
                                  }
                                  v158 = dwFlags | 0x1000000;
                                  hrCache.m_ptr = 0;
                                  if ( (dwFlags & 0x7000100) != 0 )
                                    v158 = dwFlags;
                                  if ( nativeClassInfoCandidate.ClassInfo.m_ptr )
                                  {
                                    p_nativeClassInfoCandidate = &nativeClassInfoCandidate;
                                  }
                                  else
                                  {
                                    p_nativeClassInfoCandidate = &x86WowClassInfoCandidate;
                                    if ( !x86WowClassInfoCandidate.ClassInfo.m_ptr )
                                      p_nativeClassInfoCandidate = &arm32WowClassInfoCandidate;
                                  }
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                    &hrCache,
                                    &p_nativeClassInfoCandidate->ClassInfo);
                                  pICCI3.m_ptr = 0;
                                  if ( hrCache.m_ptr->QueryInterface(
                                         hrCache.m_ptr,
                                         &GUID_0318b242_d086_4de9_b10c_2824a6ca1019,
                                         (void **)&pICCI3) >= 0 )
                                  {
                                    dwPreferredServerBitness = 0;
                                    pICCI3.m_ptr->GetPreferredServerBitness(pICCI3.m_ptr, &dwPreferredServerBitness);
                                    if ( dwPreferredServerBitness )
                                    {
                                      switch ( dwPreferredServerBitness )
                                      {
                                        case 1u:
                                          if ( (v158 & 0x1000100) == 0 )
                                          {
                                            if ( (v158 & 0x2000000) == 0 )
                                            {
                                              if ( (v158 & 0x4000000) == 0 )
                                              {
                                                MicrosoftTelemetryAssertTriggeredNoArgs(v160);
                                                goto LABEL_500;
                                              }
                                              if ( !arm32WowClassInfoCandidate.ClassInfo.m_ptr )
                                              {
LABEL_500:
                                                wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pICCI3);
                                                wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&hrCache);
                                                goto $noComClassInfoInClassicRegistryProviders;
                                              }
                                              *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 512;
                                              p_arm32WowClassInfoCandidate = &arm32WowClassInfoCandidate;
LABEL_475:
                                              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                                &classInfo,
                                                &p_arm32WowClassInfoCandidate->ClassInfo);
                                              wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pICCI3);
                                              wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&hrCache);
                                              goto LABEL_180;
                                            }
                                            goto LABEL_477;
                                          }
                                          break;
                                        case 2u:
                                          if ( GetNativeArchitecture() != 332 )
                                          {
LABEL_477:
                                            if ( !x86WowClassInfoCandidate.ClassInfo.m_ptr )
                                              goto LABEL_500;
                                            *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 256;
                                            p_arm32WowClassInfoCandidate = &x86WowClassInfoCandidate;
                                            goto LABEL_475;
                                          }
                                          break;
                                        case 3u:
                                          v162 = GetNativeArchitecture();
                                          if ( GetArchitecturePointerSizeInBytes(v162) != 8 )
                                            goto LABEL_500;
                                          break;
                                        case 4u:
                                          if ( GetNativeArchitecture() != 452 )
                                          {
                                            if ( arm32WowClassInfoCandidate.ClassInfo.m_ptr )
                                            {
                                              *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 512;
                                              v161 = &arm32WowClassInfoCandidate;
                                              goto LABEL_466;
                                            }
                                            goto LABEL_500;
                                          }
                                          goto LABEL_464;
                                        case 5u:
                                          if ( GetNativeArchitecture() == 0xAA64 )
                                            goto LABEL_464;
                                          goto LABEL_500;
                                        case 0x80000000:
LABEL_464:
                                          if ( nativeClassInfoCandidate.ClassInfo.m_ptr )
                                          {
                                            *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 128;
                                            v161 = &nativeClassInfoCandidate;
LABEL_466:
                                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                              &classInfo,
                                              &v161->ClassInfo);
                                            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pICCI3);
                                            wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&hrCache);
                                            goto LABEL_163;
                                          }
                                          goto LABEL_500;
                                        default:
                                          ProxyStubClassInfoFromPackageScopedCatalog = -2147221165;
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            0x1326u,
                                            "onecore\\com\\combase\\catalog\\catalog.cxx",
                                            -2147221165);
                                          wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pICCI3);
                                          p_catalogPackageAwarePackagedComCurrentPackage = (wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&hrCache;
                                          goto LABEL_463;
                                      }
                                      if ( !nativeClassInfoCandidate.ClassInfo.m_ptr )
                                        goto LABEL_500;
                                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 128;
                                      p_arm32WowClassInfoCandidate = &nativeClassInfoCandidate;
                                      goto LABEL_475;
                                    }
                                  }
                                  memset(registryClassInfoCandidates, 0, sizeof(registryClassInfoCandidates));
                                  if ( (v158 & 0x1000100) != 0 )
                                  {
                                    registryClassInfoCandidates[0] = &nativeClassInfoCandidate;
                                    v164 = &x86WowClassInfoCandidate;
                                  }
                                  else
                                  {
                                    if ( (v158 & 0x2000000) == 0 )
                                    {
                                      if ( (v158 & 0x4000000) == 0 )
                                        goto LABEL_493;
                                      registryClassInfoCandidates[0] = &arm32WowClassInfoCandidate;
                                      registryClassInfoCandidates[1] = &nativeClassInfoCandidate;
                                      v165 = &x86WowClassInfoCandidate;
LABEL_492:
                                      registryClassInfoCandidates[2] = v165;
LABEL_493:
                                      v166 = 0;
                                      while ( 1 )
                                      {
                                        v167 = registryClassInfoCandidates[v166];
                                        if ( v167->ClassInfo.m_ptr )
                                        {
                                          if ( v167->IsTentativelyAcceptable )
                                            break;
                                        }
                                        v166 = (unsigned int)(v166 + 1);
                                        if ( (unsigned int)v166 >= 3 )
                                        {
                                          v168 = 0;
                                          while ( 1 )
                                          {
                                            v167 = registryClassInfoCandidates[v168];
                                            if ( v167->ClassInfo.m_ptr )
                                              goto LABEL_579;
                                            v168 = (unsigned int)(v168 + 1);
                                            if ( (unsigned int)v168 >= 3 )
                                              goto LABEL_500;
                                          }
                                        }
                                      }
LABEL_579:
                                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = *(_DWORD *)v167->WhichCatalog;
                                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                        &classInfo,
                                        &v167->ClassInfo);
                                      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pICCI3);
                                      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&hrCache);
                                      goto LABEL_580;
                                    }
                                    registryClassInfoCandidates[0] = &x86WowClassInfoCandidate;
                                    v164 = &nativeClassInfoCandidate;
                                  }
                                  registryClassInfoCandidates[1] = v164;
                                  v165 = &arm32WowClassInfoCandidate;
                                  goto LABEL_492;
                                }
$noComClassInfoInClassicRegistryProviders:
                                v169 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
                                v170 = v220.m_ptr;
                                if ( v169 )
                                {
                                  if ( !v212 )
                                  {
                                    v171 = v220.m_ptr[27].__vftable;
                                    if ( v171 )
                                    {
                                      if ( LODWORD(v229.m_ptr) || !v224 )
                                      {
                                        v132 = 1024;
                                        currentCatalog = 1024;
                                        v172 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 0x400;
                                        v173 = v171->QueryInterface;
                                        *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x400u;
                                        v174 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v173 + 3);
                                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                        line = (ClassInfoCandidate *)&classInfo;
                                        pCache = v219;
                                        hrProvider = v174(v171, dwFlags, userToken, rclsid);
                                        ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                                        if ( !hrProvider )
                                        {
LABEL_507:
                                          v134 = v18 | 0x400;
                                          v67 = 512;
                                          *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 0x400u;
                                          goto LABEL_345;
                                        }
                                        if ( hrProvider != -2147221164 )
                                        {
                                          if ( hrProvider >= 0 )
                                            goto LABEL_131;
                                          v68 = 4998;
                                          goto LABEL_130;
                                        }
LABEL_519:
                                        v170 = v220.m_ptr;
                                        goto LABEL_520;
                                      }
                                    }
                                  }
                                }
                                else
                                {
                                  v175 = v220.m_ptr[27].__vftable;
                                  if ( v175 && (LODWORD(v229.m_ptr) || !v224) )
                                  {
                                    v132 = 1024;
                                    currentCatalog = 1024;
                                    v172 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 0x400;
                                    v176 = v175->QueryInterface;
                                    *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x400u;
                                    v177 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v176 + 3);
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                    line = (ClassInfoCandidate *)&classInfo;
                                    pCache = v219;
                                    v178 = v177(v175, dwFlags, userToken, rclsid);
                                    hrProvider = v178;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v178;
                                    if ( !v178 )
                                      goto LABEL_507;
                                    if ( v178 != -2147221164 )
                                    {
                                      if ( v178 >= 0 )
                                        goto LABEL_131;
                                      v68 = 5021;
                                      goto LABEL_130;
                                    }
                                    goto LABEL_519;
                                  }
                                }
                                v172 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
LABEL_520:
                                if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                {
                                  if ( v215 || g_bInSCM || !m_ptr || (dwFlags & 0x17) == 1 )
                                  {
                                    v183 = rclsid;
                                  }
                                  else
                                  {
                                    v172 |= 2u;
                                    currentCatalog = 2;
                                    *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v172;
                                    if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                      ComTraceMessageT<void *>(
                                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                                        "CComCatalog::GetClassInfoInternal",
                                        5046,
                                        v179,
                                        (wchar_t *)L"Look for %ls in PackagedCom current package Catalog...",
                                        (ServerCall *)&clsidString);
                                    v220.m_ptr = 0;
                                    v180 = wil::com_query_to_nothrow<IComCatalogPackageAware,wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &>(
                                             &catalogPackagedComCurrentPackage,
                                             (IComCatalogPackageAware **)&v220);
                                    ProxyStubClassInfoFromPackageScopedCatalog = v180;
                                    if ( v180 < 0 )
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        0x13BFu,
                                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                                        v180);
LABEL_530:
                                      p_catalogPackageAwarePackagedComCurrentPackage = &v220;
                                      goto LABEL_463;
                                    }
                                    v181 = v220.m_ptr;
                                    RpcGetUnmarshalClass = v220.m_ptr->RpcGetUnmarshalClass;
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                    v183 = rclsid;
                                    LODWORD(line) = (_DWORD)packageFullName;
                                    pCache = rclsid;
                                    v184 = ((__int64 (__fastcall *)(IRestrictedErrorRpcMarshal *, _QWORD, _QWORD, IUserTokenInternal *))RpcGetUnmarshalClass)(
                                             v181,
                                             catalogFlags & 0xFFFFFFFE,
                                             0,
                                             userTokenInternal.m_ptr);
                                    hrProvider = v184;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v184;
                                    if ( v184 )
                                    {
                                      if ( v184 != -2147221164 )
                                      {
                                        if ( v184 < 0 )
                                          wil::details::in1diag3::Return_HrMsg(
                                            retaddr,
                                            0x13D4u,
                                            "onecore\\com\\combase\\catalog\\catalog.cxx",
                                            v184,
                                            "CLSID:%ls Flags:%#x IID:%ls",
                                            clsidString.m_string,
                                            dwFlags,
                                            requestedIidString.m_string);
                                        goto LABEL_530;
                                      }
                                    }
                                    else
                                    {
                                      v18 |= 2u;
                                      *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                                      if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                        ComTraceMessageT<void *>(
                                          "onecore\\com\\combase\\catalog\\catalog.cxx",
                                          "CComCatalog::GetClassInfoInternal",
                                          5065,
                                          v185,
                                          (wchar_t *)L"Found %ls in PackagedCom current package Catalog",
                                          (ServerCall *)&clsidString);
                                      LOWORD(v67) = 256;
                                      v217 = 256;
                                      fValueFlags[0] = 256;
                                      if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                                      {
                                        *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 2u;
                                        *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 2;
                                        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(&v220);
                                        v78 = v183;
                                        goto LABEL_581;
                                      }
                                      v172 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
                                    }
                                    wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(&v220);
                                  }
                                  if ( !v216 && !g_bInSCM )
                                  {
                                    v186 = v170[23].__vftable;
                                    currentCatalog = 64;
                                    v229.m_ptr = 0;
                                    v187 = (*(__int64 (__fastcall **)(IRestrictedErrorRpcMarshal_vtbl *, GUID *, wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *))v186->QueryInterface)(
                                             v186,
                                             &GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf,
                                             &v229);
                                    ProxyStubClassInfoFromPackageScopedCatalog = v187;
                                    if ( v187 < 0 )
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        0x13E2u,
                                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                                        v187);
LABEL_547:
                                      p_catalogPackageAwarePackagedComCurrentPackage = &v229;
                                      goto LABEL_463;
                                    }
                                    v188 = v229.m_ptr;
                                    *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v172 | 0x40;
                                    v189 = v229.m_ptr->RpcGetUnmarshalClass;
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                    LODWORD(line) = (_DWORD)packageFullName;
                                    pCache = v183;
                                    v190 = ((__int64 (__fastcall *)(IRestrictedErrorRpcMarshal *, _QWORD, _QWORD, IUserTokenInternal *))v189)(
                                             v188,
                                             catalogFlags,
                                             0,
                                             userTokenInternal.m_ptr);
                                    hrProvider = v190;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v190;
                                    if ( v190 )
                                    {
                                      if ( v190 != -2147221164 )
                                      {
                                        if ( v190 < 0 )
                                          wil::details::in1diag3::Return_HrMsg(
                                            retaddr,
                                            0x13F8u,
                                            "onecore\\com\\combase\\catalog\\catalog.cxx",
                                            v190,
                                            "CLSID:%ls Flags:%#x IID:%ls",
                                            clsidString.m_string,
                                            dwFlags,
                                            requestedIidString.m_string);
                                        goto LABEL_547;
                                      }
                                    }
                                    else
                                    {
                                      LOWORD(v67) = 1;
                                      v217 = 1;
                                      *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18 | 0x40;
                                      fValueFlags[0] = 1;
                                      if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                                      {
                                        *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 0x40u;
                                        *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 64;
                                        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(&v229);
                                        goto LABEL_580;
                                      }
                                    }
                                    wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(&v229);
                                    v191 = userToken;
                                    goto LABEL_570;
                                  }
LABEL_569:
                                  v191 = userToken;
                                  goto LABEL_570;
                                }
                                if ( g_bInSCM || !v170[23].__vftable )
                                  goto LABEL_569;
                                currentCatalog = 64;
                                *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v172 | 0x40;
                                if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                  ComTraceMessageT<void *>(
                                    "onecore\\com\\combase\\catalog\\catalog.cxx",
                                    "CComCatalog::GetClassInfoInternal",
                                    5124,
                                    CHATTY,
                                    (wchar_t *)L"Look for %ls in PackagedCom all packages Catalog...",
                                    (ServerCall *)&clsidString);
                                v192 = v170[23].__vftable;
                                v193 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v192->QueryInterface + 3);
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                v191 = userToken;
                                line = (ClassInfoCandidate *)&classInfo;
                                pCache = v219;
                                hrProvider = v193(v192, dwFlags, userToken, rclsid);
                                ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                                if ( !hrProvider )
                                {
                                  *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18 | 0x40;
                                  if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                    ComTraceMessageT<void *>(
                                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                                      "CComCatalog::GetClassInfoInternal",
                                      5131,
                                      CHATTY,
                                      (wchar_t *)L"Found %ls in PackagedCom all packages Catalog",
                                      (ServerCall *)&clsidString);
                                  LOWORD(v67) = 1;
                                  v217 = 1;
                                  fValueFlags[0] = 1;
                                  if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                                  {
                                    *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs |= 0x40u;
                                    *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 64;
                                    goto LABEL_580;
                                  }
                                  goto LABEL_570;
                                }
                                if ( hrProvider == -2147221164 )
                                {
LABEL_570:
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                  v194 = v219;
                                  v78 = rclsid;
                                  LODWORD(hrCache.m_ptr) = -2147221164;
                                  ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                    (HRESULT *)&hrCache,
                                    rclsid,
                                    v219,
                                    &catalogDiagnosticData);
                                  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                    || gfEnableTracing && IsWppLevelEnabled(WARNING) )
                                  {
                                    ComTraceMessageT<long,unsigned short const *,unsigned long,unsigned short const *>(
                                      v196,
                                      v195,
                                      v197,
                                      v198,
                                      (const wchar_t *)pCache,
                                      (HRESULT)line,
                                      clsidString.m_string,
                                      dwFlags,
                                      requestedIidString.m_string);
                                  }
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                  NoClassInfo = CComCatalog::CreateNoClassInfo(
                                                  v191,
                                                  v78,
                                                  v194,
                                                  (void **)&classInfo.m_ptr);
                                  ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                                  if ( NoClassInfo >= 0 )
                                  {
                                    LOWORD(v67) = 4;
                                    fValueFlags[0] = 4;
                                    v217 = 4;
                                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                    {
                                      v199 = v214;
                                      if ( !(_BYTE)v214 )
                                        v199 = HasAnyComDependenciesOnPackages();
$addToCache_3:
                                      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                      {
                                        if ( !v199
                                          && s_pCacheClassInfo
                                          && ((unsigned __int16)v67 & (unsigned __int16)gdwCacheableFlags) != 0 )
                                        {
                                          previousClassInfo.m_ptr = 0;
                                          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&previousClassInfo);
                                          if ( CCache::AddElement(
                                                 s_pCacheClassInfo,
                                                 v78->Data1,
                                                 4u,
                                                 apKey,
                                                 acbKey,
                                                 fValueFlags,
                                                 classInfo.m_ptr,
                                                 &previousClassInfo.m_ptr) == 1 )
                                          {
                                            if ( !previousClassInfo.m_ptr )
                                            {
                                              LODWORD(hrCache.m_ptr) = -2147221164;
                                              ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                                (HRESULT *)&hrCache,
                                                v78,
                                                v219,
                                                &catalogDiagnosticData);
                                              ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
LABEL_592:
                                              v201 = 5202;
LABEL_593:
                                              wil::details::in1diag3::Return_HrMsg(
                                                retaddr,
                                                v201,
                                                "onecore\\com\\combase\\catalog\\catalog.cxx",
                                                ProxyStubClassInfoFromPackageScopedCatalog,
                                                "CLSID:%ls Flags:%#x IID:%ls",
                                                clsidString.m_string,
                                                dwFlags,
                                                requestedIidString.m_string);
                                              goto LABEL_594;
                                            }
                                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                            v200 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(
                                                     &previousClassInfo,
                                                     v194,
                                                     (void **)&classInfo.m_ptr);
                                            ProxyStubClassInfoFromPackageScopedCatalog = v200;
                                            if ( v200 )
                                            {
                                              if ( v200 >= 0 )
                                              {
LABEL_594:
                                                p_catalogPackageAwarePackagedComCurrentPackage = (wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&previousClassInfo;
                                                goto LABEL_463;
                                              }
                                              goto LABEL_592;
                                            }
                                          }
                                          goto LABEL_595;
                                        }
LABEL_607:
                                        v202 = v217;
                                        goto LABEL_608;
                                      }
                                      if ( !s_pCacheClassInfo
                                        || ((unsigned __int16)v67 & (unsigned __int16)gdwCacheableFlags) == 0 )
                                      {
                                        goto LABEL_607;
                                      }
                                      if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                                        ComTraceMessageT<void *>(
                                          "onecore\\com\\combase\\catalog\\catalog.cxx",
                                          "CComCatalog::GetClassInfoInternal",
                                          5211,
                                          CHATTY,
                                          (wchar_t *)L"Adding %ls to cache...",
                                          (ServerCall *)&clsidString);
                                      previousClassInfo.m_ptr = 0;
                                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&previousClassInfo);
                                      if ( CCache::AddElement(
                                             s_pCacheClassInfo,
                                             v78->Data1,
                                             4u,
                                             apKey,
                                             acbKey,
                                             fValueFlags,
                                             classInfo.m_ptr,
                                             &previousClassInfo.m_ptr) == 1 )
                                      {
                                        if ( !previousClassInfo.m_ptr )
                                        {
                                          LODWORD(hrCache.m_ptr) = -2147221164;
                                          ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                            (HRESULT *)&hrCache,
                                            v78,
                                            v219,
                                            &catalogDiagnosticData);
                                          ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
LABEL_606:
                                          v201 = 5238;
                                          goto LABEL_593;
                                        }
                                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                                        v203 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(
                                                 &previousClassInfo,
                                                 v194,
                                                 (void **)&classInfo.m_ptr);
                                        ProxyStubClassInfoFromPackageScopedCatalog = v203;
                                        if ( v203 )
                                        {
                                          if ( v203 >= 0 )
                                            goto LABEL_594;
                                          goto LABEL_606;
                                        }
                                      }
LABEL_595:
                                      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&previousClassInfo);
                                      v202 = fValueFlags[0];
LABEL_608:
                                      v204 = classInfo.m_ptr;
                                      classInfo.m_ptr = 0;
                                      *ptrResult = v204;
                                      if ( (v202 & 4) != 0 )
                                      {
                                        LODWORD(hrCache.m_ptr) = 1;
                                        ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                          (HRESULT *)&hrCache,
                                          v78,
                                          v194,
                                          &catalogDiagnosticData);
                                        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&classInfo);
                                        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&userTokenInternal);
                                        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackagedComCurrentPackage);
                                        ProxyStubClassInfoFromPackageScopedCatalog = 1;
                                        goto LABEL_612;
                                      }
                                      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&classInfo);
                                      goto LABEL_611;
                                    }
LABEL_582:
                                    v199 = v214;
                                    goto $addToCache_3;
                                  }
                                  v92 = 5154;
                                  goto LABEL_225;
                                }
                                if ( hrProvider >= 0 )
                                  goto LABEL_131;
                                v68 = 5142;
LABEL_130:
                                wil::details::in1diag3::Return_HrMsg(
                                  retaddr,
                                  v68,
                                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                                  ProxyStubClassInfoFromPackageScopedCatalog,
                                  "CLSID:%ls Flags:%#x IID:%ls",
                                  clsidString.m_string,
                                  dwFlags,
                                  requestedIidString.m_string);
                                goto LABEL_131;
                              }
                              if ( hrProvider != -2147221164 )
                              {
                                if ( hrProvider >= 0 )
                                  goto LABEL_131;
                                v68 = 4650;
                                goto LABEL_130;
                              }
                            }
                          }
                        }
                        LOWORD(v67) = v217;
                        goto LABEL_434;
                      }
                    }
                    else if ( !g_bInSCM )
                    {
                      if ( LODWORD(v229.m_ptr) || (v130 = v224) == 0 )
                      {
                        v131 = v220.m_ptr;
                        v132 = 2048;
                        currentCatalog = 2048;
                        *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v101 | 0x800;
                        v135 = v220.m_ptr + 2;
                        if ( !v220.m_ptr )
                          v135 = 0;
                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                        ClassInfoW = DeviceCatalogs::GetClassInfoW(
                                       (DeviceCatalogs *)&v131[28],
                                       dwFlags & 0xFFFFF301,
                                       userToken,
                                       rclsid,
                                       v219,
                                       (void **)&classInfo.m_ptr,
                                       v135);
                        hrProvider = ClassInfoW;
                        ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                        if ( !ClassInfoW )
                          goto LABEL_344;
                        if ( ClassInfoW != -2147221164 )
                        {
                          if ( ClassInfoW >= 0 )
                            goto LABEL_131;
                          v68 = 4455;
                          goto LABEL_130;
                        }
                        goto LABEL_360;
                      }
                      goto LABEL_358;
                    }
                    v131 = v220.m_ptr;
LABEL_360:
                    v130 = v224;
                    goto LABEL_361;
                  }
                  v101 |= 0x40u;
                  currentCatalog = 64;
                  *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v101;
                  if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                  {
                    ComTraceMessageT<void *>(
                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                      "CComCatalog::GetClassInfoInternal",
                      4303,
                      v114,
                      v115,
                      (ServerCall *)&clsidString);
                    v113 = 0;
                  }
                  catalogPackageAwarePackagedComAllPackages.m_ptr = v113;
                  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                  {
                    v116 = catalogPackageAwarePackagedComAllPackages.m_ptr;
                    catalogPackageAwarePackagedComAllPackages.m_ptr = 0;
                    if ( v116 )
                      v116->Release(v116);
                    v117 = (*(__int64 (__fastcall **)(IRestrictedErrorRpcMarshal_vtbl *, GUID *, wil::com_ptr_t<IComCatalogPackageAware,wil::err_returncode_policy> *))v99[23].QueryInterface)(
                             v99[23].__vftable,
                             &GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf,
                             &catalogPackageAwarePackagedComAllPackages);
                    ProxyStubClassInfoFromPackageScopedCatalog = v117;
                    if ( v117 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        0x10D6u,
                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                        v117);
LABEL_313:
                      p_catalogPackageAwarePackagedComCurrentPackage = (wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComAllPackages;
                      goto LABEL_463;
                    }
                    v118 = catalogPackageAwarePackagedComAllPackages.m_ptr;
                    v119 = catalogPackageAwarePackagedComAllPackages.m_ptr->GetClassInfoW;
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                    v120 = rclsid;
                    LODWORD(line) = (_DWORD)packageFullName;
                    pCache = rclsid;
                    v121 = ((__int64 (__fastcall *)(IComCatalogPackageAware *, _QWORD, _QWORD, IUserTokenInternal *))v119)(
                             v118,
                             catalogFlags,
                             0,
                             userTokenInternal.m_ptr);
                  }
                  else
                  {
                    v122 = v99[23].__vftable;
                    v123 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v122->QueryInterface + 3);
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                    v120 = rclsid;
                    line = (ClassInfoCandidate *)&classInfo;
                    pCache = v219;
                    v121 = v123(v122, dwFlags, userToken, rclsid);
                  }
                  hrProvider = v121;
                  ProxyStubClassInfoFromPackageScopedCatalog = v121;
                  if ( v121 == -2147221164 && (_BYTE)dwPreferredServerBitness )
                  {
                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                    {
                      v124 = catalogPackageAwarePackagedComAllPackages.m_ptr;
                      v125 = catalogPackageAwarePackagedComAllPackages.m_ptr->GetClassInfoW;
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                      LODWORD(line) = (_DWORD)packageFullName;
                      pCache = v120;
                      v126 = ((__int64 (__fastcall *)(IComCatalogPackageAware *, _QWORD, __int64, IUserTokenInternal *))v125)(
                               v124,
                               catalogFlags,
                               512,
                               userTokenInternal.m_ptr);
                    }
                    else
                    {
                      v127 = v220.m_ptr[23].__vftable;
                      v128 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, __int64, IUserToken *, _GUID *))*((_QWORD *)v127->QueryInterface + 3);
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                      v129 = dwFlags;
                      LODWORD(v129) = dwFlags | 0x200;
                      line = (ClassInfoCandidate *)&classInfo;
                      pCache = v219;
                      v126 = v128(v127, v129, userToken, v120);
                    }
                    hrProvider = v126;
                    ProxyStubClassInfoFromPackageScopedCatalog = v126;
                    if ( v126 )
                      goto LABEL_331;
                    pICCI3.m_ptr = (IClassClassicInfo3 *)&classInfo;
                    if ( lambda_c56a88c6bd0f565e516d65786a230941_::operator()() < 0 )
                    {
                      hrProvider = -2147221164;
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                    }
                    ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                  }
                  if ( !ProxyStubClassInfoFromPackageScopedCatalog )
                  {
                    v18 |= 0x40u;
                    *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                    if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                      ComTraceMessageT<void *>(
                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                        "CComCatalog::GetClassInfoInternal",
                        4385,
                        CHATTY,
                        (wchar_t *)L"Found %ls in PackagedCom all packages Catalog",
                        (ServerCall *)&clsidString);
                    LOWORD(v67) = 1;
                    v217 = 1;
                    fValueFlags[0] = 1;
                    if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                    {
                      *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 64;
                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 64;
                      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComAllPackages);
                      goto LABEL_163;
                    }
                    v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
LABEL_335:
                    wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&catalogPackageAwarePackagedComAllPackages);
                    goto LABEL_336;
                  }
LABEL_331:
                  if ( ProxyStubClassInfoFromPackageScopedCatalog != -2147221164 )
                  {
                    if ( ProxyStubClassInfoFromPackageScopedCatalog < 0 )
                      wil::details::in1diag3::Return_HrMsg(
                        retaddr,
                        0x112Du,
                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                        ProxyStubClassInfoFromPackageScopedCatalog,
                        "CLSID:%ls Flags:%#x IID:%ls",
                        clsidString.m_string,
                        dwFlags,
                        requestedIidString.m_string);
                    goto LABEL_313;
                  }
                  goto LABEL_335;
                }
              }
              else
              {
                v104 = v224;
                v105 = (int)v229.m_ptr;
                if ( !LODWORD(hrCache.m_ptr) && !LODWORD(v229.m_ptr) && !v224 && v75[17].__vftable )
                {
                  currentCatalog = 16;
                  *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v73 | 0x10;
                  if ( gfEnableTracing && IsWppLevelEnabled((TraceLevel)(LODWORD(v229.m_ptr) + 4)) )
                    ComTraceMessageT<void *>(
                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                      "CComCatalog::GetClassInfoInternal",
                      4213,
                      v106,
                      (wchar_t *)L"Look for %ls in REGDB...",
                      (ServerCall *)&clsidString);
                  v107 = v75[17].__vftable;
                  v108 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v107->QueryInterface + 3);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                  line = (ClassInfoCandidate *)&classInfo;
                  pCache = v219;
                  hrProvider = v108(v107, dwFlags, userToken, rclsid);
                  ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                  if ( hrProvider )
                  {
                    if ( hrProvider != -2147221164 )
                    {
                      if ( hrProvider >= 0 )
                        goto LABEL_131;
                      v68 = 4231;
                      goto LABEL_130;
                    }
                  }
                  else
                  {
                    v18 |= 0x10u;
                    *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                    if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                      ComTraceMessageT<void *>(
                        "onecore\\com\\combase\\catalog\\catalog.cxx",
                        "CComCatalog::GetClassInfoInternal",
                        4220,
                        CHATTY,
                        (wchar_t *)L"Found %ls in REGDB",
                        (ServerCall *)&clsidString);
                    LOWORD(v67) = 2;
                    v217 = 2;
                    fValueFlags[0] = 2;
                    if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                    {
                      *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 16;
                      *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 16;
                      goto LABEL_163;
                    }
                  }
                  v105 = (int)v229.m_ptr;
                  v104 = v224;
                }
                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                if ( LODWORD(hrCache.m_ptr) || v105 )
                  goto LABEL_299;
                v98 = v104 == 0;
                v99 = v220.m_ptr;
                if ( v98 )
                {
                  v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
                  if ( !v220.m_ptr[14].__vftable )
                    goto LABEL_301;
                  v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs | 0x20;
                  currentCatalog = 32;
                  *(_DWORD *)catalogDiagnosticData.TriedCatalogs |= 0x20u;
                  if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                    ComTraceMessageT<void *>(
                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                      "CComCatalog::GetClassInfoInternal",
                      4243,
                      v109,
                      (wchar_t *)L"Look for %ls in COM Base CLB...",
                      (ServerCall *)&clsidString);
                  v110 = v99[14].__vftable;
                  v111 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v110->QueryInterface + 3);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
                  line = (ClassInfoCandidate *)&classInfo;
                  pCache = v219;
                  hrProvider = v111(v110, dwFlags, userToken, rclsid);
                  ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
                  if ( hrProvider )
                  {
                    if ( hrProvider != -2147221164 )
                    {
                      if ( hrProvider >= 0 )
                        goto LABEL_131;
                      v68 = 4260;
                      goto LABEL_130;
                    }
                    goto LABEL_300;
                  }
                  v18 |= 0x20u;
                  *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
                  if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                    ComTraceMessageT<void *>(
                      "onecore\\com\\combase\\catalog\\catalog.cxx",
                      "CComCatalog::GetClassInfoInternal",
                      4249,
                      CHATTY,
                      (wchar_t *)L"Found %ls in COM Base CLB",
                      (ServerCall *)&clsidString);
                  LOWORD(v67) = 2;
                  v217 = 2;
                  fValueFlags[0] = 2;
                  if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
                  {
                    *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 32;
                    *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 32;
                    goto LABEL_163;
                  }
                  goto LABEL_299;
                }
              }
              v101 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
              goto LABEL_301;
            }
            v73 |= 8u;
            *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v73;
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
            if ( !CCache::GetElement(s_pCacheClassInfo, rclsid->Data1, 4u, apKey, acbKey, fValueFlags, &classInfo.m_ptr) )
            {
              v18 |= 8u;
              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                  "CComCatalog::GetClassInfoInternal",
                  4028,
                  CHATTY,
                  (wchar_t *)L"Found %ls in cache",
                  (ServerCall *)&clsidString);
              if ( classInfo.m_ptr
                && (!IsCComNoClassInfo(classInfo.m_ptr) || !HasAnyComDependenciesOnPackages())
                && CComCatalog::CheckForRefresh(userToken, classInfo.m_ptr, s_pCacheClassInfo) >= 0 )
              {
                NoClassInfo = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(&classInfo, v219, ptrResult);
                ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                if ( !NoClassInfo )
                  goto LABEL_220;
                if ( NoClassInfo < 0 )
                {
                  v92 = 4086;
LABEL_225:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    v92,
                    "onecore\\com\\combase\\catalog\\catalog.cxx",
                    NoClassInfo);
                  goto LABEL_131;
                }
                goto LABEL_131;
              }
            }
          }
          else
          {
            if ( !s_pCacheClassInfo )
              goto LABEL_240;
            v73 |= 8u;
            *(_DWORD *)catalogDiagnosticData.TriedCatalogs = v73;
            if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
              ComTraceMessageT<void *>(
                "onecore\\com\\combase\\catalog\\catalog.cxx",
                "CComCatalog::GetClassInfoInternal",
                4109,
                CHATTY,
                (wchar_t *)L"Look for %ls in cache...",
                (ServerCall *)&clsidString);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
            if ( !CCache::GetElement(s_pCacheClassInfo, rclsid->Data1, 4u, apKey, acbKey, fValueFlags, &classInfo.m_ptr) )
            {
              v18 |= 8u;
              *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = v18;
              if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\catalog\\catalog.cxx",
                  "CComCatalog::GetClassInfoInternal",
                  4124,
                  CHATTY,
                  (wchar_t *)L"Found %ls in cache",
                  (ServerCall *)&clsidString);
              if ( classInfo.m_ptr && CComCatalog::CheckForRefresh(userToken, classInfo.m_ptr, s_pCacheClassInfo) >= 0 )
              {
                NoClassInfo = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(&classInfo, v219, ptrResult);
                ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                if ( !NoClassInfo )
                {
LABEL_220:
                  if ( (fValueFlags[0] & 4) != 0 )
                    ProxyStubClassInfoFromPackageScopedCatalog = 1;
                  goto LABEL_131;
                }
                if ( NoClassInfo < 0 )
                {
                  v92 = 4137;
                  goto LABEL_225;
                }
LABEL_131:
                wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&classInfo);
                goto LABEL_42;
              }
            }
          }
          v217 = fValueFlags[0];
          goto LABEL_240;
        }
        currentCatalog = 1;
        v17 = 1;
        *(_DWORD *)catalogDiagnosticData.TriedCatalogs = 1;
        if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
          ComTraceMessageT<void *>(
            "onecore\\com\\combase\\catalog\\catalog.cxx",
            "CComCatalog::GetClassInfoInternal",
            3762,
            v62,
            (wchar_t *)L"Look for %ls in COM SxS Catalog...",
            (ServerCall *)&clsidString);
        v63 = v61[18].__vftable;
        v64 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v63->QueryInterface + 3);
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
        line = (ClassInfoCandidate *)&classInfo;
        pCache = v219;
        hrProvider = v64(v63, dwFlags, userToken, rclsid);
        ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
        if ( hrProvider )
        {
          if ( hrProvider != -2147221164 )
          {
            if ( hrProvider >= 0 )
              goto LABEL_131;
            v68 = 3781;
            goto LABEL_130;
          }
          goto LABEL_146;
        }
        v18 = 1;
        *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = 1;
        if ( !gfEnableTracing || !IsWppLevelEnabled(CHATTY) )
          goto LABEL_125;
        v66 = 3768;
LABEL_124:
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\catalog\\catalog.cxx",
          "CComCatalog::GetClassInfoInternal",
          v66,
          v65,
          (wchar_t *)L"Found %ls in COM SxS Catalog",
          (ServerCall *)&clsidString);
LABEL_125:
        LOWORD(v67) = 16;
        fValueFlags[0] = 16;
        v217 = 16;
        if ( ClassRegistrationMatchesRequestedClsctx(classInfo.m_ptr, dwFlags, 0) )
        {
          *(_DWORD *)catalogDiagnosticData.AcceptedCatalogs = 1;
          *(_DWORD *)catalogDiagnosticData.SelectedCatalog = 1;
LABEL_580:
          v78 = rclsid;
          goto LABEL_581;
        }
        v17 = *(_DWORD *)catalogDiagnosticData.TriedCatalogs;
      }
    }
    else if ( !LODWORD(v229.m_ptr) || v224 )
    {
      v61 = v220.m_ptr;
      if ( !v220.m_ptr[18].__vftable )
        goto LABEL_147;
      currentCatalog = 1;
      v17 = 1;
      *(_DWORD *)catalogDiagnosticData.TriedCatalogs = 1;
      if ( gfEnableTracing && IsWppLevelEnabled(CHATTY) )
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\catalog\\catalog.cxx",
          "CComCatalog::GetClassInfoInternal",
          3795,
          v69,
          (wchar_t *)L"Look for %ls in COM SxS Catalog...",
          (ServerCall *)&clsidString);
      v70 = v61[18].__vftable;
      v71 = (__int64 (__fastcall *)(IRestrictedErrorRpcMarshal_vtbl *, _QWORD, IUserToken *, _GUID *))*((_QWORD *)v70->QueryInterface + 3);
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((wil::com_ptr_t<IRegistration,wil::err_returncode_policy> *)&classInfo);
      line = (ClassInfoCandidate *)&classInfo;
      pCache = v219;
      hrProvider = v71(v70, dwFlags, userToken, rclsid);
      ProxyStubClassInfoFromPackageScopedCatalog = hrProvider;
      if ( hrProvider )
      {
        if ( hrProvider != -2147221164 )
        {
          if ( hrProvider >= 0 )
            goto LABEL_131;
          v68 = 3814;
          goto LABEL_130;
        }
        goto LABEL_146;
      }
      v18 = 1;
      *(_DWORD *)catalogDiagnosticData.FoundInCatalogs = 1;
      if ( !gfEnableTracing || !IsWppLevelEnabled(CHATTY) )
        goto LABEL_125;
      v66 = 3801;
      goto LABEL_124;
    }
LABEL_146:
    v61 = v220.m_ptr;
    goto LABEL_147;
  }
  ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
  wil::details::in1diag3::Return_Hr(retaddr, 0xD17u, "onecore\\com\\combase\\catalog\\catalog.cxx", -2147024809);
  wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&arm32WowClassInfoCandidate);
  wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&x86WowClassInfoCandidate);
  wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&nativeClassInfoCandidate);
  traceCatalogLookupFailure.m_call = 0;
LABEL_613:
  lambda_009d5060e5934af28c563eb57404125c_::operator()(&traceCatalogLookupFailure);
  return (unsigned int)ProxyStubClassInfoFromPackageScopedCatalog;
}

```

## disassembly

```asm
0x180195ef4  push    rbp
0x180195ef6  push    rbx
0x180195ef7  push    rsi
0x180195ef8  push    rdi
0x180195ef9  push    r12
0x180195efb  push    r13
0x180195efd  push    r14
0x180195eff  push    r15
0x180195f01  lea     rbp, [rsp-1C8h]
0x180195f09  sub     rsp, 2C8h
0x180195f10  mov     rax, cs:__security_cookie
0x180195f17  xor     rax, rsp
0x180195f1a  mov     [rbp+200h+var_50], rax
0x180195f21  mov     rax, [rbp+200h+arg_28]
0x180195f28  xor     esi, esi
0x180195f2a  mov     rbx, [rbp+200h+guid]
0x180195f31  mov     r15, guidConfiguredClsid
0x180195f34  mov     rdi, [rbp+200h+arg_50]
0x180195f3b  mov     r14, this
0x180195f3e  mov     [rbp+200h+ptrResult], rax
0x180195f45  mov     r13d, esi
0x180195f48  mov     rax, [rbp+200h+arg_48]
0x180195f4f  mov     r12d, esi
0x180195f52  mov     [rbp+200h+packageFullName], rax
0x180195f56  mov     rax, [rbp+200h+arg_60]
0x180195f5d  mov     [rbp+200h+previousClassInfo.m_ptr], rax
0x180195f61  mov     rax, [rbp+200h+flags_0]
0x180195f68  mov     [rbp+200h+var_178], rax
0x180195f6f  lea     rax, [rbp+200h+hrProvider]
0x180195f73  mov     [rbp+200h+traceCatalogLookupFailure.m_lambda.hrProvider], rax
0x180195f7a  lea     rax, [rbp+200h+currentCatalog]
0x180195f7e  mov     [rbp+200h+traceCatalogLookupFailure.m_lambda.currentCatalog], rax
0x180195f85  lea     rax, [rsp+300h+dwFlags]
0x180195f8a  mov     [rbp+200h+traceCatalogLookupFailure.m_lambda.flags], rax
0x180195f91  mov     [rbp+200h+rclsid], guidConfiguredClsid
0x180195f95  mov     [rbp+200h+userToken], pUserToken
0x180195f99  mov     [rbp+200h+var_258.m_ptr], this
0x180195f9d  mov     [rsp+300h+dwFlags], flags
0x180195fa1  mov     [rbp+200h+var_260], rbx
0x180195fa5  mov     [rbp+200h+first], rdi
0x180195fa9  mov     [rbp+200h+hrProvider], esi
0x180195fac  mov     [rbp+200h+currentCatalog], esi
0x180195faf  mov     [rbp+200h+traceCatalogLookupFailure.m_lambda.guidConfiguredClsid], guidConfiguredClsid
0x180195fb6  mov     [rbp+200h+traceCatalogLookupFailure.m_call], 1
0x180195fbd  mov     [rbp+200h+var_270], esi
0x180195fc0  mov     [rbp+200h+fValueFlags], si
0x180195fc4  mov     [rbp+200h+pSid], rsi
0x180195fcb  mov     [rbp+200h+cbSid], si
0x180195fcf  mov     [rbp+200h+pIntegritySID], rsi
0x180195fd6  mov     [rbp+200h+cbIntegritySID], si
0x180195fda  mov     [rbp+200h+nativeClassInfoCandidate.ClassInfo.m_ptr], rsi
0x180195fde  mov     [rbp+200h+nativeClassInfoCandidate.IsTentativelyAcceptable], sil
0x180195fe2  mov     dword ptr [rbp+200h+nativeClassInfoCandidate.WhichCatalog], 80h
0x180195fe9  mov     [rbp+200h+x86WowClassInfoCandidate.ClassInfo.m_ptr], rsi
0x180195fed  mov     [rbp+200h+x86WowClassInfoCandidate.IsTentativelyAcceptable], sil
0x180195ff1  mov     dword ptr [rbp+200h+x86WowClassInfoCandidate.WhichCatalog], 100h
0x180195ff8  mov     [rbp+200h+arm32WowClassInfoCandidate.ClassInfo.m_ptr], rsi
0x180195ffc  mov     [rbp+200h+arm32WowClassInfoCandidate.IsTentativelyAcceptable], sil
0x180196000  mov     dword ptr [rbp+200h+arm32WowClassInfoCandidate.WhichCatalog], 200h
0x180196007  mov     qword ptr [rbp+200h+catalogDiagnosticData.TriedCatalogs], rsi
0x18019600b  mov     qword ptr [rbp+200h+catalogDiagnosticData.AcceptedCatalogs], rsi
0x18019600f  mov     [rbp+200h+catalogDiagnosticData.Flags], flags
0x180196012  test    flags, 0CE8h
0x180196018  jz      short loc_180196061
0x18019601a  mov     this, [rbp+208h]; callerReturnAddress
0x180196021  lea     pUserToken, aOnecoreComComb_111; "onecore\\com\\combase\\catalog\\catalog"...
0x180196028  mov     edi, 80070057h
0x18019602d  mov     flags, 0D17h; lineNumber
0x180196032  mov     r9d, edi; hr
0x180196035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019603a  lea     this, [rbp+200h+arm32WowClassInfoCandidate]; this
0x18019603e  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x180196043  lea     this, [rbp+200h+x86WowClassInfoCandidate]; this
0x180196047  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x18019604c  lea     this, [rbp+200h+nativeClassInfoCandidate]; this
0x180196050  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x180196055  mov     [rbp+200h+traceCatalogLookupFailure.m_call], sil
0x18019605c  jmp     loc_180199130
0x180196061  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x180196068  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18019606d  mov     esi, [rbp+200h+arg_40]
0x180196073  mov     flags, [rbp+200h+arg_38]
0x180196079  mov     ecx, [rsp+300h+dwFlags]
0x18019607d  test    al, al
0x18019607f  jz      loc_18019613F
0x180196085  cmp     [rbp+200h+currentPackageGraphPackageCount], r12d
0x18019608c  jbe     short loc_1801960A0
0x18019608e  cmp     [rbp+200h+previousClassInfo.m_ptr], r12
0x180196092  jnz     short loc_1801960A0
0x180196094  mov     edi, 80070057h
0x180196099  mov     flags, 0D1Bh
0x18019609e  jmp     short loc_1801960B7
0x1801960a0  test    flags, 0FFFFFFE8h
0x1801960a6  jz      short loc_1801960D2
0x1801960a8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(clsctx & ~CAT_VALID_CLSCTX_MASK) == 0")
0x1801960ad  mov     flags, 0D1Eh; lineNumber
0x1801960b2  mov     edi, 8000FFFFh
0x1801960b7  mov     r9d, edi; hr
0x1801960ba  mov     this, [rbp+208h]; callerReturnAddress
0x1801960c1  lea     pUserToken, aOnecoreComComb_111; "onecore\\com\\combase\\catalog\\catalog"...
0x1801960c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801960cd  jmp     loc_18019910E
0x1801960d2  test    esi, 0CFFh
0x1801960d8  jz      short loc_1801960E6
0x1801960da  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(catalogFlags & ~CAT_REG_MASK) == 0")
0x1801960df  mov     flags, 0D1Fh
0x1801960e4  jmp     short loc_1801960B2
0x1801960e6  mov     eax, ecx
0x1801960e8  and     eax, 17h
0x1801960eb  jnz     short loc_1801960FE
0x1801960ed  cmp     flags, 17h
0x1801960f0  jz      short loc_18019610E
0x1801960f2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "clsctx == CLSCTX_ALL")
0x1801960f7  mov     flags, 0D2Dh
0x1801960fc  jmp     short loc_1801960B2
0x1801960fe  cmp     flags, eax
0x180196100  jz      short loc_18019610E
0x180196102  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "clsctx == static_cast<CLSCTX>(flags & CAT_VALID_CLSCTX_MASK)")
0x180196107  mov     flags, 0D31h
0x18019610c  jmp     short loc_1801960B2
0x18019610e  mov     eax, ecx
0x180196110  and     eax, 0FFFFF300h
0x180196115  cmp     esi, eax
0x180196117  jz      short loc_180196125
0x180196119  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "catalogFlags == (flags & CAT_REG_MASK)")
0x18019611e  mov     flags, 0D35h
0x180196123  jmp     short loc_1801960B2
0x180196125  cmp     [rbp+200h+packageFullName], r12
0x180196129  jz      short loc_18019613F
0x18019612b  test    rdi, rdi
0x18019612e  jz      short loc_18019613F
0x180196130  mov     edi, 80070057h
0x180196135  mov     flags, 0D38h
0x18019613a  jmp     loc_1801960B7
0x18019613f  mov     eax, ecx
0x180196141  mov     rdx, r15; guid
0x180196144  and     ecx, 200000h
0x18019614a  and     eax, 8000000h
0x18019614f  mov     [rbp+200h+var_238], ecx
0x180196152  lea     this, [rbp+200h+clsidString]; this
0x180196159  mov     dword ptr [rbp+200h+var_200.m_ptr], eax
0x18019615c  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180196161  mov     rdx, rbx; guid
0x180196164  lea     this, [rbp+200h+requestedIidString]; this
0x18019616b  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180196170  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180196177  jz      short loc_1801961AC
0x180196179  mov     ecx, 4; level
0x18019617e  call    IsWppLevelEnabled
0x180196183  test    al, al
0x180196185  jz      short loc_1801961AC
0x180196187  lea     rax, [rbp+200h+requestedIidString]
0x18019618e  mov     [rsp+300h+format], rax; format
0x180196193  mov     eax, [rsp+300h+dwFlags]
0x180196197  mov     [rsp+300h+level], eax; level
0x18019619b  lea     rax, [rbp+200h+clsidString]
0x1801961a2  mov     [rsp+300h+line], rax; line
0x1801961a7  call    ??$ComTraceMessageT@PEBGKPEBG@@YAXPEBD0HW4TraceLevel@@PEBG2K2@Z; ComTraceMessageT<ushort const *,ulong,ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ushort const *)
0x1801961ac  mov     rax, [rbp+200h+ptrResult]
0x1801961b3  mov     [rax], r12
0x1801961b6  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x1801961bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801961c2  test    al, al
0x1801961c4  jz      short loc_1801961D6
0x1801961c6  mov     al, cs:?ms_fInitialized@CComCatalog@@0U?$atomic@_N@std@@A._Storage._Value; std::atomic<bool> CComCatalog::ms_fInitialized ...
0x1801961cc  nop
0x1801961cd  test    al, al
0x1801961cf  jnz     short loc_1801961D6
0x1801961d1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ms_fInitialized")
0x1801961d6  mov     this, r14; this
0x1801961d9  call    ?InitializeCatalogIfNecessary@CComCatalog@@QEAAJXZ; CComCatalog::InitializeCatalogIfNecessary(void)
0x1801961de  mov     edi, eax
0x1801961e0  test    eax, eax
0x1801961e2  jns     short loc_1801961F1
0x1801961e4  mov     r9d, eax
0x1801961e7  mov     flags, 0D53h
0x1801961ec  jmp     loc_1801960BA
0x1801961f1  xor     ebx, ebx
0x1801961f3  mov     [rbp+200h+catalogPackagedComCurrentPackage.m_ptr], rbx
0x1801961f7  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x1801961fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180196203  test    al, al
0x180196205  jz      short loc_180196265
0x180196207  xor     flags, flags; initializingCatalog
0x180196209  mov     this, r14; this
0x18019620c  call    ?InitializePackagedComCurrentPackageProviderIfNecessary@CComCatalog@@AEAAJ_N@Z; CComCatalog::InitializePackagedComCurrentPackageProviderIfNecessary(bool)
0x180196211  mov     edi, eax
0x180196213  test    eax, eax
0x180196215  jns     short loc_180196240
0x180196217  mov     this, [rbp+208h]; callerReturnAddress
0x18019621e  lea     pUserToken, aOnecoreComComb_111; "onecore\\com\\combase\\catalog\\catalog"...
0x180196225  mov     r9d, eax; hr
0x180196228  mov     flags, 0D58h; lineNumber
0x18019622d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196232  lea     this, [rbp+200h+catalogPackagedComCurrentPackage]; this
0x180196236  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x18019623b  jmp     loc_18019910E
0x180196240  lea     rdx, [rbp+200h+currentPackageFamilyName]; result
0x180196244  mov     this, r14; this
0x180196247  call    ?GetPackagedComCurrentPackageProvider@CComCatalog@@AEAA?AV?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@XZ; CComCatalog::GetPackagedComCurrentPackageProvider(void)
0x18019624c  mov     rdx, rax; other
0x18019624f  lea     this, [rbp+200h+catalogPackagedComCurrentPackage]; this
0x180196253  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &&)
0x180196258  lea     this, [rbp+200h+currentPackageFamilyName]; this
0x18019625c  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x180196261  mov     rbx, [rbp+200h+catalogPackagedComCurrentPackage.m_ptr]
0x180196265  mov     r14, [rbp+200h+userToken]
0x180196269  mov     [rbp+200h+userTokenInternal.m_ptr], r12
0x18019626d  test    r14, r14
0x180196270  jz      loc_180196346
0x180196276  mov     rax, [r14]
0x180196279  lea     pUserToken, [rbp+200h+cbSid]
0x18019627d  lea     rdx, [rbp+200h+pSid]
0x180196284  mov     this, r14
0x180196287  mov     rax, [rax+28h]
0x18019628b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196290  mov     edi, eax
0x180196292  test    eax, eax
0x180196294  jns     short loc_1801962BF
0x180196296  mov     flags, 0D64h; lineNumber
0x18019629b  mov     r9d, eax; hr
0x18019629e  mov     this, [rbp+208h]; callerReturnAddress
0x1801962a5  lea     pUserToken, aOnecoreComComb_111; "onecore\\com\\combase\\catalog\\catalog"...
0x1801962ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801962b1  lea     this, [rbp+200h+userTokenInternal]; this
0x1801962b5  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x1801962ba  jmp     loc_180196232
0x1801962bf  mov     rax, [r14]
0x1801962c2  lea     pUserToken, [rbp+200h+cbIntegritySID]
0x1801962c6  lea     rdx, [rbp+200h+pIntegritySID]
0x1801962cd  mov     this, r14
0x1801962d0  mov     rax, [rax+38h]
0x1801962d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801962d9  mov     edi, eax
0x1801962db  test    eax, eax
0x1801962dd  jns     short loc_1801962E6
0x1801962df  mov     flags, 0D65h
0x1801962e4  jmp     short loc_18019629B
0x1801962e6  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x1801962ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801962f2  test    al, al
0x1801962f4  jz      short loc_180196346
0x1801962f6  mov     rdx, [rbp+200h+userTokenInternal.m_ptr]
0x1801962fa  mov     rax, [r14]
0x1801962fd  mov     [rbp+200h+userTokenInternal.m_ptr], r12
0x180196301  mov     rdi, [rax]
0x180196304  test    rdx, rdx
0x180196307  jz      short loc_180196318
0x180196309  mov     this, [rdx]
0x18019630c  mov     rax, [this+10h]
0x180196310  mov     this, rdx
0x180196313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196318  lea     pUserToken, [rbp+200h+userTokenInternal]
0x18019631c  mov     this, r14
0x18019631f  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x180196326  mov     rax, rdi
0x180196329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019632e  mov     edi, eax
0x180196330  test    eax, eax
0x180196332  jns     short loc_180196346
0x180196334  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "IUserToken object does not implement IUserTokenInternal")
0x180196339  mov     r9d, edi
0x18019633c  mov     flags, 0D6Bh
0x180196341  jmp     loc_18019629E
0x180196346  mov     ecx, [rsp+300h+dwFlags]; dwFlags
0x18019634a  call    ?FlagsForCacheKey@CComCatalog@@CAKK@Z; CComCatalog::FlagsForCacheKey(ulong)
0x18019634f  btr     eax, 1Bh
0x180196353  mov     [rbp+200h+apKey], r15
0x18019635a  mov     [rbp+200h+flagsForCache], eax
0x180196360  mov     [rbp+200h+catalogDiagnosticData.FlagsForCache], eax
0x180196363  mov     rax, [rbp+200h+pSid]
0x18019636a  mov     [rbp+200h+apKey+8], rax
0x180196371  mov     rax, [rbp+200h+pIntegritySID]
0x180196378  mov     [rbp+200h+apKey+10h], rax
0x18019637f  lea     rax, [rbp+200h+flagsForCache]
0x180196386  mov     [rbp+200h+apKey+18h], rax
0x18019638d  mov     eax, 10h
0x180196392  mov     [rbp+200h+acbKey], ax
0x180196396  movzx   eax, [rbp+200h+cbSid]
0x18019639a  mov     [rbp+200h+acbKey+2], ax
0x18019639e  movzx   eax, [rbp+200h+cbIntegritySID]
0x1801963a2  mov     [rbp+200h+acbKey+4], ax
0x1801963a6  mov     eax, 4
0x1801963ab  mov     [rbp+200h+acbKey+6], ax
0x1801963af  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x1801963b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801963bb  xor     r15d, r15d
0x1801963be  lea     r14d, [r15+1]
0x1801963c2  test    al, al
0x1801963c4  jz      short loc_1801963DB
0x1801963c6  mov     ecx, [rsp+300h+dwFlags]
0x1801963ca  mov     edi, esi
0x1801963cc  shr     edi, 9
0x1801963cf  btr     ecx, 9
0x1801963d3  and     dil, r14b
0x1801963d6  mov     [rbp+200h+dwPreferredServerBitness], edi
0x1801963d9  jmp     short loc_1801963EE
0x1801963db  mov     eax, [rsp+300h+dwFlags]
0x1801963df  mov     ecx, eax
0x1801963e1  btr     ecx, 9
  ... truncated ...
```
