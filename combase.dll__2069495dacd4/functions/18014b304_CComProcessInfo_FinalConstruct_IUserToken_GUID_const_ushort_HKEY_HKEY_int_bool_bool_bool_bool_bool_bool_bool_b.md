# CComProcessInfo::FinalConstruct(IUserToken *,_GUID const &,ushort *,HKEY__ *,HKEY__ *,int,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool)

- ea: `0x18014b304`
- end: `0x18014ce69`
- name: `?FinalConstruct@CComProcessInfo@@QEAAJPEAUIUserToken@@AEBU_GUID@@PEAGPEAUHKEY__@@3H_N44444444444@Z`
- size: `7013`
- prototype: `__int64 __fastcall(CComProcessInfo *this, IUserToken *pUserToken, const _GUID *rclsid, wchar_t *pwszAppidString, HKEY__ *hKey, HKEY hklmSoftwareClassesOrEquivalent, int fMachineHive, bool ignoreRunAsInteractiveUser, bool supportsApplicationId, bool supportsActivateAtStorage, bool supportsAppIDFlags, bool supportsROTAndMGOTFlags, bool supportsProcessMitigationPolicy, bool supportsRemoteServerName, bool supportsSRPTrustLevel, bool supportsPreferredServerBitness, bool supportsLoadUserSettings, bool supportsProtectionLevel, bool isPackaged)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010f600`

## callees

- `0x180020484`
- `0x180020e14`
- `0x180041e50`
- `0x18004768c`
- `0x180051e70`
- `0x180058e20`
- `0x18005c640`
- `0x180062050`
- `0x1800840f8`
- `0x1800859ec`
- `0x1800865b8`
- `0x1800865f4`
- `0x18008db2c`
- `0x1800a6f50`
- `0x1800e7048`
- `0x180105a24`
- `0x180107964`
- `0x180133b14`
- `0x1801457c0`
- `0x18014894c`
- `0x18014b304`
- `0x18014d5f4`
- `0x18015ddc0`
- `0x180162038`
- `0x1801845f4`
- `0x18018c680`
- `0x18018c7a0`
- `0x1801999b0`
- `0x18019a654`
- `0x1801adba0`
- `0x1801dd7d0`
- `0x180255010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18014b966`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18014b966`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014bab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014bb1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014c1c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014bab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014bb1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014c1c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014b6dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014c227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014b6dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014c227`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014bcea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014bff8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c0bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c20b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c551`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c66a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c838`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c90d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014cc73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014bcea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014bff8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c0bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c20b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c551`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c66a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c838`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014c90d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014cc73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c2a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c62b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c2a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c62b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014bc99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014c40f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014bc99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014c40f`

## string_xrefs

- `0x18014b3b8`: `CComProcessInfo::FinalConstruct`
- `0x18014b43d`: `CComProcessInfo::FinalConstruct`
- `0x18014b5d1`: `CComProcessInfo::FinalConstruct`
- `0x18014b741`: `CComProcessInfo::FinalConstruct`
- `0x18014b78e`: `CComProcessInfo::FinalConstruct`
- `0x18014b902`: `CComProcessInfo::FinalConstruct`
- `0x18014b9b1`: `CComProcessInfo::FinalConstruct`
- `0x18014b9f7`: `CComProcessInfo::FinalConstruct`
- `0x18014ba3b`: `CComProcessInfo::FinalConstruct`
- `0x18014bbb8`: `CComProcessInfo::FinalConstruct`
- `0x18014c25f`: `CComProcessInfo::FinalConstruct`
- `0x18014c36d`: `CComProcessInfo::FinalConstruct`
- `0x18014c7d3`: `CComProcessInfo::FinalConstruct`
- `0x18014c89b`: `CComProcessInfo::FinalConstruct`
- `0x18014b3c9`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b449`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b5d8`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b753`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b7a0`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b914`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b9b8`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b9fe`: `onecore\com\combase\catalog\process.cxx`
- `0x18014ba4f`: `onecore\com\combase\catalog\process.cxx`
- `0x18014bbbf`: `onecore\com\combase\catalog\process.cxx`
- `0x18014c26a`: `onecore\com\combase\catalog\process.cxx`
- `0x18014c379`: `onecore\com\combase\catalog\process.cxx`
- `0x18014c7b8`: `onecore\com\combase\catalog\process.cxx`
- `0x18014c8ad`: `onecore\com\combase\catalog\process.cxx`
- `0x18014cce6`: `onecore\com\combase\catalog\process.cxx`
- `0x18014b737`: `Found surrogate: dllhost`
- `0x18014b5bc`: `Found local service! (%ws)`
- `0x18014bc48`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18014ce29`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18014b458`: `CLSID:%ws APPID:%ws %!HRESULT!`
- `0x18014be4a`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18014bdd0`: `Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18014b8f8`: `No surrogate, No service.`
- `0x18014cd08`: `CLSID:%ws APPID:%ws Value:%ws hr:%#x`
- `0x18014bf31`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18014bebd`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`

## pseudocode

```c
__int64 __fastcall CComProcessInfo::FinalConstruct(
        CComProcessInfo *this,
        IUserToken *pUserToken,
        const _GUID *rclsid,
        wchar_t *pwszAppidString,
        HKEY__ *hKey,
        HKEY hklmSoftwareClassesOrEquivalent,
        int fMachineHive,
        bool ignoreRunAsInteractiveUser,
        bool supportsApplicationId,
        bool supportsActivateAtStorage,
        bool supportsAppIDFlags,
        bool supportsROTAndMGOTFlags,
        bool supportsProcessMitigationPolicy,
        bool supportsRemoteServerName,
        bool supportsSRPTrustLevel,
        bool supportsPreferredServerBitness,
        bool supportsLoadUserSettings,
        bool supportsProtectionLevel,
        bool isPackaged)
{
  wchar_t *line; // r12
  bool v22; // zf
  _GUID v23; // xmm0
  TraceLevel v24; // edx
  HRESULT RegistryStringValue; // ebx
  wchar_t *v26; // rax
  wchar_t **p_m_pwszServiceName; // r14
  wchar_t *v28; // rax
  const char *v29; // rdx
  TraceLevel v30; // r9d
  const wchar_t *v31; // rcx
  int v32; // r8d
  HRESULT (__fastcall *GetPackageName)(IUserToken *, wchar_t **); // rbx
  __int64 v34; // rdx
  wchar_t *v35; // r8
  TraceLevel v36; // edx
  wchar_t *v37; // r8
  wchar_t *v38; // rax
  const char *v39; // rdx
  const char *v40; // rcx
  int v41; // r8d
  TraceLevel v42; // r9d
  const wchar_t *v43; // rdx
  wchar_t **p_m_pwszSurrogatePath; // rsi
  wchar_t *v45; // rdx
  wchar_t *v46; // rax
  const char *v47; // rdx
  const char *v48; // rcx
  TraceLevel v49; // r9d
  wchar_t *v50; // rax
  const char *v51; // rdx
  const char *v52; // rcx
  TraceLevel v53; // r9d
  wchar_t *v54; // rdx
  __int64 v55; // rdx
  wchar_t v56; // ax
  wchar_t *v57; // rcx
  unsigned int v58; // esi
  SIZE_T v59; // rax
  wchar_t *v60; // rax
  HRESULT v61; // eax
  unsigned int v62; // ebx
  SIZE_T v63; // rax
  wchar_t *v64; // rax
  wchar_t **p_m_pwszApplicationId; // rsi
  int v66; // eax
  TraceLevel v67; // r8d
  LSTATUS v68; // eax
  unsigned __int8 *v69; // r15
  LSTATUS v70; // eax
  wchar_t *v71; // rax
  const char *v72; // rdx
  const char *v73; // rcx
  TraceLevel v74; // r9d
  unsigned int m_dwAppIDFlags; // ecx
  wchar_t *v76; // rax
  const char *v77; // rdx
  TraceLevel v78; // r9d
  wchar_t *v79; // rax
  const char *v80; // rdx
  TraceLevel v81; // r9d
  wchar_t *v82; // rax
  const char *v83; // rdx
  TraceLevel v84; // r9d
  wchar_t *v85; // rax
  const char *v86; // rdx
  TraceLevel v87; // r9d
  wchar_t *v88; // rax
  const char *v89; // rdx
  TraceLevel v90; // r9d
  LSTATUS v91; // eax
  wchar_t *v92; // rax
  const char *v93; // rdx
  TraceLevel v94; // r9d
  LSTATUS v95; // eax
  wchar_t *v96; // rax
  const char *v97; // rdx
  TraceLevel v98; // r9d
  LSTATUS v99; // eax
  HRESULT v100; // r12d
  TraceLevel v101; // r9d
  wchar_t *v102; // rax
  const char *v103; // rdx
  TraceLevel v104; // r9d
  wchar_t *v105; // rax
  TraceLevel v106; // r9d
  int RegistrySecurityDescriptor; // eax
  _GUID *v108; // rcx
  tagEventLogSD v109; // r8d
  LSTATUS v110; // eax
  wchar_t *v111; // rax
  const char *v112; // rdx
  TraceLevel v113; // r9d
  wchar_t *v114; // rax
  const char *v115; // rdx
  TraceLevel v116; // r9d
  LSTATUS v117; // eax
  wchar_t *v118; // rax
  const char *v119; // rdx
  TraceLevel v120; // r9d
  wchar_t *v121; // rax
  const char *v122; // rdx
  TraceLevel v123; // r9d
  LSTATUS v124; // eax
  int v125; // r8d
  wchar_t *v126; // rax
  const char *v127; // rdx
  TraceLevel v128; // r9d
  HKEY v129; // r15
  int v130; // eax
  LSTATUS v131; // eax
  TraceLevel v132; // edx
  unsigned int m_ptr; // eax
  LSTATUS v134; // eax
  unsigned int v135; // edx
  TraceLevel v136; // r9d
  LSTATUS v137; // eax
  wchar_t *v138; // rax
  const char *v139; // rdx
  TraceLevel v140; // r9d
  wchar_t *v141; // rax
  const char *v142; // rdx
  TraceLevel v143; // r9d
  wchar_t *v144; // rax
  const char *v145; // rdx
  TraceLevel v146; // r9d
  wchar_t *v147; // rax
  const char *v148; // rdx
  TraceLevel v149; // r9d
  wchar_t *v150; // rax
  const char *v151; // rdx
  TraceLevel v152; // r9d
  wchar_t *v153; // rax
  const char *v154; // rdx
  TraceLevel v155; // r9d
  wchar_t *v156; // rax
  const char *v157; // rdx
  TraceLevel v158; // r9d
  bool v159; // al
  int PerUserCacheInformation; // eax
  LSTATUS v161; // eax
  __int64 v162; // rax
  wchar_t *v163; // rax
  const char *v164; // rdx
  TraceLevel v165; // r9d
  wchar_t *v166; // rax
  const char *v167; // rdx
  TraceLevel v168; // r9d
  const wchar_t *level; // [rsp+20h] [rbp-E0h]
  const wchar_t *v171; // [rsp+38h] [rbp-C8h]
  __int64 file; // [rsp+40h] [rbp-C0h]
  HRESULT v173; // [rsp+50h] [rbp-B0h]
  unsigned int cbValue; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int dwValueType; // [rsp+64h] [rbp-9Ch] BYREF
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&PrivMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > protectionLevel; // [rsp+68h] [rbp-98h] BYREF
  unsigned int dwValue; // [rsp+70h] [rbp-90h] BYREF
  HKEY__ *hKeyAppID; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v179; // [rsp+80h] [rbp-80h]
  HKEY__ *hKeyOle; // [rsp+88h] [rbp-78h] BYREF
  HKEY v181; // [rsp+90h] [rbp-70h]
  IUserToken *userToken; // [rsp+98h] [rbp-68h]
  HKEY v183; // [rsp+A0h] [rbp-60h]
  CGuidStr v184; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t wszValue[256]; // [rsp+100h] [rbp+0h] BYREF
  void *retaddr; // [rsp+358h] [rbp+258h]

  userToken = pUserToken;
  v181 = hKey;
  v183 = hklmSoftwareClassesOrEquivalent;
  cbValue = 0;
  dwValueType = 0;
  line = pwszAppidString;
  v179 = pwszAppidString;
  memset_0(wszValue, 0, sizeof(wszValue));
  v22 = gfEnableTracing == 0;
  v23 = *rclsid;
  hKeyOle = 0;
  this->m_guidProcessId = v23;
  dwValue = 0;
  this->m_fIsMachineHive = fMachineHive;
  if ( !v22 && IsWppLevelEnabled(VERBOSE) )
    ComTraceMessage(
      -1,
      "onecore\\com\\combase\\catalog\\process.cxx",
      "CComProcessInfo::FinalConstruct",
      136,
      v24,
      L"AppID %!GUID!",
      rclsid);
  RegistryStringValue = GetRegistryStringValue(hKey, 0, 0, 2u, &this->m_pwszProcessName);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      CGuidStr::CGuidStr(&v184, rclsid);
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        "onecore\\com\\combase\\catalog\\process.cxx",
        "CComProcessInfo::FinalConstruct",
        146,
        ERRORS,
        L"CLSID:%ws APPID:%ws %!HRESULT!",
        v26,
        line,
        RegistryStringValue);
    }
    return (unsigned int)RegistryStringValue;
  }
  p_m_pwszServiceName = &this->m_pwszServiceName;
  RegistryStringValue = GetRegistryStringValue(
                          hKey,
                          0,
                          Com::Catalog::Constants::LocalService,
                          2u,
                          &this->m_pwszServiceName);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      return (unsigned int)RegistryStringValue;
    CGuidStr::CGuidStr(&v184, rclsid);
    v31 = Com::Catalog::Constants::LocalService;
    v32 = 162;
    goto LABEL_389;
  }
  if ( isPackaged )
  {
    protectionLevel.m_ptr = 0;
    GetPackageName = userToken->GetPackageName;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &protectionLevel,
      0);
    RegistryStringValue = GetPackageName(userToken, &protectionLevel.m_ptr);
    if ( RegistryStringValue < 0 )
      goto LABEL_18;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &this->m_packageName,
      0);
    v34 = -1;
    do
      ++v34;
    while ( protectionLevel.m_ptr[v34] );
    RegistryStringValue = WindowsCreateString(protectionLevel.m_ptr, v34, &this->m_packageName.m_ptr);
    if ( RegistryStringValue < 0 )
    {
LABEL_18:
      Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&protectionLevel);
      return (unsigned int)RegistryStringValue;
    }
    Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&protectionLevel);
  }
  v35 = *p_m_pwszServiceName;
  if ( *p_m_pwszServiceName )
  {
    if ( *v35 )
    {
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\catalog\\process.cxx",
          "CComProcessInfo::FinalConstruct",
          185,
          v36,
          L"Found local service! (%ws)",
          v37);
      this->m_eProcessType = ProcessTypeService;
      RegistryStringValue = GetRegistryStringValue(
                              hKey,
                              0,
                              Com::Catalog::Constants::ServiceParameters,
                              2u,
                              &this->m_pwszServiceParameters);
      if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
      {
        if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
          return (unsigned int)RegistryStringValue;
        CGuidStr::CGuidStr(&v184, rclsid);
        v31 = Com::Catalog::Constants::ServiceParameters;
        v32 = 193;
        goto LABEL_389;
      }
      if ( isPackaged )
      {
        RegistryStringValue = -2147221161;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,bool,bool,long>(
            v40,
            v39,
            v41,
            v42,
            level,
            v38,
            line,
            v171,
            0,
            isPackaged,
            v173);
        }
        return (unsigned int)RegistryStringValue;
      }
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
      goto LABEL_70;
    }
    if ( v35 != g_wszEmptyString )
      HeapFree(g_hHeap, 0, v35);
  }
  p_m_pwszSurrogatePath = &this->m_pwszSurrogatePath;
  *p_m_pwszServiceName = 0;
  RegistryStringValue = GetRegistryStringValue(
                          hKey,
                          0,
                          Com::Catalog::Constants::DllSurrogate,
                          0,
                          &this->m_pwszSurrogatePath);
  if ( RegistryStringValue < 0 )
  {
    if ( RegistryStringValue != -2147024894 )
    {
      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
        return (unsigned int)RegistryStringValue;
      CGuidStr::CGuidStr(&v184, rclsid);
      v31 = Com::Catalog::Constants::DllSurrogate;
      v32 = 391;
LABEL_389:
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (const char *)v31,
        v29,
        v32,
        v30,
        L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v28,
        line,
        v31,
        RegistryStringValue);
      return (unsigned int)RegistryStringValue;
    }
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\catalog\\process.cxx",
        "CComProcessInfo::FinalConstruct",
        385,
        (TraceLevel)v43,
        L"No surrogate, No service.");
    this->m_eProcessType = ProcessTypeNormal;
  }
  else
  {
    v43 = *p_m_pwszSurrogatePath;
    if ( *p_m_pwszSurrogatePath == g_wszEmptyString )
    {
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<>(
          "onecore\\com\\combase\\catalog\\process.cxx",
          "CComProcessInfo::FinalConstruct",
          338,
          (TraceLevel)v43,
          L"Found surrogate: dllhost");
      this->m_eProcessType = ProcessTypeComPlus;
    }
    else
    {
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\catalog\\process.cxx",
          "CComProcessInfo::FinalConstruct",
          344,
          VERBOSE,
          L"Found surrogate: %ws",
          v45);
      this->m_eProcessType = ProcessTypeLegacySurrogate;
      RegistryStringValue = GetRegistryStringValue(hKey, 0, g_wszDebugSurrogate, 0, &this->m_pwszSurrogateCommandDebug);
      if ( RegistryStringValue < 0 )
      {
        if ( RegistryStringValue != -2147024894 )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              v52,
              v51,
              356,
              v53,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v50,
              line,
              g_wszDebugSurrogate,
              RegistryStringValue);
          }
          return (unsigned int)RegistryStringValue;
        }
      }
      else
      {
        this->m_fDebugSurrogate = 1;
      }
      if ( !this->m_fDebugSurrogate )
      {
        RegistryStringValue = GetRegistryStringValue(
                                hKey,
                                0,
                                g_wszDllSurrogateExecutable,
                                0,
                                &this->m_pwszServerExecutable);
        if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              v48,
              v47,
              375,
              v49,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v46,
              line,
              g_wszDllSurrogateExecutable,
              RegistryStringValue);
          }
          return (unsigned int)RegistryStringValue;
        }
      }
    }
  }
LABEL_70:
  this->m_eRunAsType = RunAsLaunchingUser;
  RegistryStringValue = ReadRegistryStringValue(hKey, v43, Com::Catalog::Constants::RunAs, wszValue, 0x100u);
  if ( RegistryStringValue < 0 || !wszValue[0] )
    goto LABEL_103;
  if ( (unsigned int)_o__wcsicmp(wszValue, Com::Catalog::Constants::Interactive_User) )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<void *>(
        "onecore\\com\\combase\\catalog\\process.cxx",
        "CComProcessInfo::FinalConstruct",
        418,
        VERBOSE,
        L"Found RunAs: %ws",
        wszValue);
    this->m_eRunAsType = RunAsSpecifiedUser;
    v55 = -1;
    do
      ++v55;
    while ( wszValue[v55] );
    v56 = wszValue[0];
    v57 = wszValue;
    while ( v56 && v56 != 92 )
      v56 = *++v57;
    if ( *v57 )
    {
      v62 = v55 + 1;
      v63 = 2LL * (unsigned int)(v55 + 1);
      if ( !is_mul_ok((unsigned int)(v55 + 1), 2u) )
        v63 = -1;
      v64 = (wchar_t *)HeapAlloc(g_hHeap, 0, v63);
      this->m_pwszRunAsUser = v64;
      if ( v64 )
      {
        v61 = StringCchCopyW(v64, v62, wszValue);
        goto LABEL_102;
      }
    }
    else
    {
      v58 = v55 + 4;
      v59 = 2LL * (unsigned int)(v55 + 4);
      if ( !is_mul_ok((unsigned int)(v55 + 4), 2u) )
        v59 = -1;
      v60 = (wchar_t *)HeapAlloc(g_hHeap, 0, v59);
      this->m_pwszRunAsUser = v60;
      if ( v60 )
      {
        RegistryStringValue = StringCchCopyW(v60, v58, gpwszLocalMachineDomain);
        if ( RegistryStringValue < 0 )
          goto LABEL_103;
        RegistryStringValue = StringCchCatW(this->m_pwszRunAsUser, v58, L"\\");
        if ( RegistryStringValue < 0 )
          goto LABEL_103;
        v61 = StringCchCatW(this->m_pwszRunAsUser, v58, wszValue);
LABEL_102:
        RegistryStringValue = v61;
        goto LABEL_103;
      }
    }
    return (unsigned int)-2147024882;
  }
  if ( ignoreRunAsInteractiveUser )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\catalog\\process.cxx",
        "CComProcessInfo::FinalConstruct",
        407,
        VERBOSE,
        L"Ignoring RunAs: Interactive User");
  }
  else
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\catalog\\process.cxx",
        "CComProcessInfo::FinalConstruct",
        412,
        VERBOSE,
        L"Found RunAs: Interactive User");
    this->m_eRunAsType = RunAsInteractiveUser;
  }
LABEL_103:
  if ( supportsApplicationId )
  {
    p_m_pwszApplicationId = &this->m_pwszApplicationId;
    v66 = GetRegistryStringValue(hKey, 0, g_wszApplicationId, 0, &this->m_pwszApplicationId);
    RegistryStringValue = v66;
    if ( v66 < 0 )
    {
      if ( v66 != -2147024894 )
        return (unsigned int)RegistryStringValue;
      RegistryStringValue = 0;
    }
    else
    {
      v54 = *p_m_pwszApplicationId;
      if ( !**p_m_pwszApplicationId )
        return (unsigned int)-2147221165;
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\catalog\\process.cxx",
          "CComProcessInfo::FinalConstruct",
          489,
          v67,
          L"Found ApplicationId: %ws",
          v54);
      this->m_eRunAsType = RunAsPackage;
    }
  }
  this->m_fActivateAtStorage = 0;
  if ( supportsActivateAtStorage )
  {
    RegistryStringValue = ReadRegistryStringValue(hKey, v54, g_wszActivateAtStorage, wszValue, 0x100u);
    if ( RegistryStringValue < 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v73,
            v72,
            526,
            v74,
            L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v71,
            line,
            g_wszActivateAtStorage,
            RegistryStringValue);
        }
        return (unsigned int)RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else if ( ((wszValue[0] - 89) & 0xFFDF) == 0 )
    {
      this->m_fActivateAtStorage = 1;
    }
  }
  this->m_dwAppIDFlags = 0;
  hKeyAppID = 0;
  *(_QWORD *)&this->m_dwROTFlags = 0;
  this->m_processMitigationPolicy = 0;
  if ( supportsAppIDFlags || supportsROTAndMGOTFlags || supportsProcessMitigationPolicy )
  {
    v68 = RegOpenKeyExW(v183, line, 0, 0x20019u, &hKeyAppID);
    if ( !v68 )
    {
      if ( supportsAppIDFlags )
      {
        cbValue = 4;
        LODWORD(v69) = 0;
        LODWORD(protectionLevel.m_ptr) = 0;
        v70 = RegQueryValueExW(hKeyAppID, L"AppIDFlags", 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
        if ( v70 )
        {
          if ( v70 == 2 )
          {
            RegistryStringValue = 0;
          }
          else
          {
            if ( v70 > 0 )
              RegistryStringValue = (unsigned __int16)v70 | 0x80070000;
            else
              RegistryStringValue = v70;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)L"AppIDFlags",
                v89,
                573,
                v90,
                L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v88,
                line,
                L"AppIDFlags",
                RegistryStringValue);
            }
          }
        }
        else
        {
          if ( dwValueType == 4 && cbValue == 4 )
            this->m_dwAppIDFlags = (unsigned int)protectionLevel.m_ptr;
          else
            RegistryStringValue = -2147221165;
          m_dwAppIDFlags = this->m_dwAppIDFlags;
          if ( (m_dwAppIDFlags & 0x100) != 0 )
          {
            if ( this->m_eRunAsType != RunAsLaunchingUser )
            {
              RegistryStringValue = -2147221165;
              if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
              {
                CGuidStr::CGuidStr(&v184, rclsid);
                ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                  (const char *)L"AppIDFlags",
                  v77,
                  625,
                  v78,
                  L"Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                  v76,
                  line,
                  L"AppIDFlags",
                  -2147221165);
              }
              return (unsigned int)RegistryStringValue;
            }
            this->m_eRunAsType = RunAsSessionVirtual;
          }
          if ( (m_dwAppIDFlags & 0x208) == 0x200 )
          {
            RegistryStringValue = -2147221165;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)L"AppIDFlags",
                v80,
                642,
                v81,
                L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIE"
                 "D_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v79,
                line,
                L"AppIDFlags",
                -2147221165);
            }
            return (unsigned int)RegistryStringValue;
          }
          if ( (m_dwAppIDFlags & 0x408) == 0x400 )
          {
            RegistryStringValue = -2147221165;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)L"AppIDFlags",
                v83,
                655,
                v84,
                L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFI"
                 "ED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v82,
                line,
                L"AppIDFlags",
                -2147221165);
            }
            return (unsigned int)RegistryStringValue;
          }
          if ( (m_dwAppIDFlags & 0x600) == 0x600 )
          {
            RegistryStringValue = -2147221165;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)L"AppIDFlags",
                v86,
                668,
                v87,
                L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_L"
                 "OGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v85,
                line,
                L"AppIDFlags",
                -2147221165);
            }
            return (unsigned int)RegistryStringValue;
          }
        }
      }
      else
      {
        LODWORD(v69) = 0;
      }
      if ( supportsROTAndMGOTFlags )
      {
        LODWORD(protectionLevel.m_ptr) = 0;
        cbValue = 4;
        v91 = RegQueryValueExW(hKeyAppID, g_wszROTFlags, 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
        if ( v91 )
        {
          if ( v91 == 2 )
          {
            RegistryStringValue = 0;
          }
          else
          {
            if ( v91 > 0 )
              RegistryStringValue = (unsigned __int16)v91 | 0x80070000;
            else
              RegistryStringValue = v91;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)g_wszROTFlags,
                v93,
                694,
                v94,
                L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v92,
                line,
                g_wszROTFlags,
                RegistryStringValue);
            }
          }
        }
        else if ( dwValueType == 4 && cbValue == 4 )
        {
          this->m_dwROTFlags = (unsigned int)protectionLevel.m_ptr;
        }
        else
        {
          RegistryStringValue = -2147221165;
        }
        cbValue = 4;
        v95 = RegQueryValueExW(hKeyAppID, g_wszMGOTFlags, 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
        if ( v95 )
        {
          if ( v95 == 2 )
          {
            RegistryStringValue = 0;
          }
          else
          {
            if ( v95 > 0 )
              RegistryStringValue = (unsigned __int16)v95 | 0x80070000;
            else
              RegistryStringValue = v95;
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            {
              CGuidStr::CGuidStr(&v184, rclsid);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (const char *)g_wszMGOTFlags,
                v97,
                714,
                v98,
                L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v96,
                line,
                g_wszMGOTFlags,
                RegistryStringValue);
            }
          }
        }
        else if ( dwValueType == 4 && cbValue == 4 )
        {
          this->m_dwMGOTFlags = (unsigned int)protectionLevel.m_ptr;
        }
        else
        {
          RegistryStringValue = -2147221165;
        }
      }
      if ( !supportsProcessMitigationPolicy )
        goto LABEL_211;
      v99 = RegQueryValueExW(hKeyAppID, g_wszProcessMitigationPolicy, 0, &dwValueType, 0, &cbValue);
      if ( v99 == 2 )
      {
        RegistryStringValue = 0;
LABEL_211:
        RegCloseKey(hKeyAppID);
        goto LABEL_226;
      }
      if ( v99 || dwValueType != 3 || cbValue <= 1 )
      {
        RegistryStringValue = -2147221165;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (const char *)g_wszProcessMitigationPolicy,
            v103,
            752,
            v104,
            L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v102,
            line,
            g_wszProcessMitigationPolicy,
            -2147221165);
        }
        goto LABEL_211;
      }
      v69 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, cbValue);
      if ( !v69 )
      {
        RegistryStringValue = -2147024882;
        goto LABEL_211;
      }
      v100 = RegistryStringValue;
      if ( RegistryStringValue >= 0 )
      {
        RegistryStringValue = RegQueryValueExW(hKeyAppID, g_wszProcessMitigationPolicy, 0, &dwValueType, v69, &cbValue);
        if ( RegistryStringValue )
        {
          HeapFree(g_hHeap, 0, v69);
          LODWORD(v69) = 0;
          if ( RegistryStringValue > 0 )
            RegistryStringValue = (unsigned __int16)RegistryStringValue | 0x80070000;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<unsigned short const *,unsigned long,unsigned long,long>(
              "onecore\\com\\combase\\catalog\\process.cxx",
              "CComProcessInfo::FinalConstruct",
              739,
              v101,
              L"Value:%ws Type:%d Size:%d %!HRESULT!",
              g_wszProcessMitigationPolicy,
              dwValueType,
              cbValue,
              RegistryStringValue);
          goto LABEL_210;
        }
        RegistryStringValue = v100;
        this->m_processMitigationPolicy.cbSize = cbValue;
        this->m_processMitigationPolicy.pBlobData = v69;
      }
      LODWORD(v69) = 0;
LABEL_210:
      line = v179;
      goto LABEL_211;
    }
    LODWORD(v69) = 0;
    if ( v68 != 2 )
    {
      if ( v68 > 0 )
        RegistryStringValue = (unsigned __int16)v68 | 0x80070000;
      else
        RegistryStringValue = v68;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        CGuidStr::CGuidStr(&v184, rclsid);
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\process.cxx",
          "CComProcessInfo::FinalConstruct",
          764,
          v106,
          L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v105,
          line,
          line,
          RegistryStringValue);
      }
LABEL_226:
      if ( RegistryStringValue < 0 )
        return (unsigned int)RegistryStringValue;
    }
  }
  else
  {
    LODWORD(v69) = 0;
  }
  RegistrySecurityDescriptor = GetRegistrySecurityDescriptor(
                                 v181,
                                 v54,
                                 &this->m_pLaunchPermission,
                                 &this->m_cbLaunchPermission);
  RegistryStringValue = RegistrySecurityDescriptor;
  if ( RegistrySecurityDescriptor < 0 )
  {
    if ( RegistrySecurityDescriptor != -2147221166 )
    {
      if ( RegistrySecurityDescriptor == -2147221165 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
          || gfEnableTracing != (_DWORD)v69 && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (const char *)Com::Catalog::Constants::LaunchPermission,
            v167,
            785,
            v168,
            L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v166,
            line,
            Com::Catalog::Constants::LaunchPermission,
            -2147221165);
        }
        if ( g_bInSCM != (_DWORD)v69 )
          LogInvalidSecurityDescriptor(v108, 0x4725u, v109);
      }
      return (unsigned int)RegistryStringValue;
    }
    this->m_dwFlags |= 2u;
    RegistryStringValue = (int)v69;
  }
  else
  {
    this->m_dwFlags |= 1u;
  }
  if ( CComProcessInfo::m_fGotLegacyLevels != (_DWORD)v69
    || RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszHKLMOle, 0, 0x20019u, &hKeyOle) )
  {
    goto LABEL_270;
  }
  cbValue = 4;
  v110 = RegQueryValueExW(hKeyOle, g_wszLegacyAuthenticationLevel, 0, &dwValueType, (LPBYTE)&dwValue, &cbValue);
  if ( v110 )
  {
    if ( v110 == 2 )
    {
      RegistryStringValue = (int)v69;
    }
    else
    {
      if ( v110 > 0 )
        RegistryStringValue = (unsigned __int16)v110 | 0x80070000;
      else
        RegistryStringValue = v110;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
        || gfEnableTracing != (_DWORD)v69 && IsWppLevelEnabled(ERRORS) )
      {
        CGuidStr::CGuidStr(&v184, rclsid);
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (const char *)g_wszLegacyAuthenticationLevel,
          v115,
          821,
          v116,
          L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v114,
          line,
          g_wszLegacyAuthenticationLevel,
          RegistryStringValue);
      }
    }
  }
  else if ( dwValueType == 4 && cbValue == 4 )
  {
    CComProcessInfo::m_dwLegacyAuthenticationLevel = dwValue;
  }
  else
  {
    RegistryStringValue = -2147221165;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing != (_DWORD)v69 && IsWppLevelEnabled(ERRORS) )
    {
      CGuidStr::CGuidStr(&v184, rclsid);
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (const char *)g_wszLegacyAuthenticationLevel,
        v112,
        811,
        v113,
        L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v111,
        line,
        g_wszLegacyAuthenticationLevel,
        -2147221165);
    }
  }
  cbValue = 4;
  v117 = RegQueryValueExW(hKeyOle, g_wszLegacyImpersonationLevel, 0, &dwValueType, (LPBYTE)&dwValue, &cbValue);
  if ( v117 )
  {
    if ( v117 == 2 )
    {
      RegistryStringValue = (int)v69;
    }
    else
    {
      if ( v117 > 0 )
        RegistryStringValue = (unsigned __int16)v117 | 0x80070000;
      else
        RegistryStringValue = v117;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
        || gfEnableTracing != (_DWORD)v69 && IsWppLevelEnabled(ERRORS) )
      {
        CGuidStr::CGuidStr(&v184, rclsid);
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (const char *)g_wszLegacyImpersonationLevel,
          v122,
          846,
          v123,
          L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v121,
          line,
          g_wszLegacyImpersonationLevel,
          RegistryStringValue);
      }
    }
  }
  else if ( dwValueType == 4 && cbValue == 4 )
  {
    CComProcessInfo::m_dwLegacyImpersonationLevel = dwValue;
  }
  else
  {
    RegistryStringValue = -2147221165;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing != (_DWORD)v69 && IsWppLevelEnabled(ERRORS) )
    {
      CGuidStr::CGuidStr(&v184, rclsid);
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (const char *)g_wszLegacyImpersonationLevel,
        v119,
        836,
        v120,
        L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v118,
        line,
        g_wszLegacyImpersonationLevel,
        -2147221165);
    }
  }
  RegCloseKey(hKeyOle);
  if ( RegistryStringValue >= 0 )
  {
LABEL_270:
    cbValue = 4;
    v124 = RegQueryValueExW(
             v181,
             g_wszAuthenticationLevel,
             0,
             &dwValueType,
             (LPBYTE)&this->m_dwAuthenticationLevel,
             &cbValue);
    v125 = 0;
    RegistryStringValue = v124;
    if ( (v124 || dwValueType != 4) && cbValue != 4 )
    {
      if ( !v124 )
      {
        RegistryStringValue = -2147221165;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (const char *)g_wszAuthenticationLevel,
            v127,
            865,
            v128,
            L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v126,
            line,
            g_wszAuthenticationLevel,
            -2147221165);
        }
        return (unsigned int)RegistryStringValue;
      }
      if ( v124 != 2 )
      {
        if ( v124 > 0 )
          RegistryStringValue = (unsigned __int16)v124 | 0x80070000;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          CGuidStr::CGuidStr(&v184, rclsid);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (const char *)g_wszAuthenticationLevel,
            v164,
            877,
            v165,
            L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v163,
            line,
            g_wszAuthenticationLevel,
            RegistryStringValue);
        }
        return (unsigned int)RegistryStringValue;
      }
      this->m_dwAuthenticationLevel = CComProcessInfo::m_dwLegacyAuthenticationLevel;
    }
    RegistryStringValue = 0;
    v129 = v181;
    if ( supportsRemoteServerName )
    {
      v130 = GetRegistryStringValue(v181, 0, g_wszRemoteServerName, 3u, &this->m_pwszRemoteServerName);
      v125 = 0;
      RegistryStringValue = v130;
      if ( v130 < 0 )
      {
        if ( v130 != -2147024894 )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (const char *)g_wszRemoteServerName,
              v139,
              891,
              v140,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v138,
              line,
              g_wszRemoteServerName,
              RegistryStringValue);
          }
          return (unsigned int)RegistryStringValue;
        }
        RegistryStringValue = 0;
      }
    }
    if ( supportsSRPTrustLevel )
    {
      LODWORD(protectionLevel.m_ptr) = 0;
      cbValue = 4;
      v131 = RegQueryValueExW(v129, g_wszSRPTrustLevel, 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
      v125 = 0;
      if ( v131 )
      {
        if ( v131 != 2 )
        {
          if ( v131 > 0 )
            RegistryStringValue = (unsigned __int16)v131 | 0x80070000;
          else
            RegistryStringValue = v131;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (const char *)g_wszSRPTrustLevel,
              v145,
              925,
              v146,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v144,
              line,
              g_wszSRPTrustLevel,
              RegistryStringValue);
          }
          return (unsigned int)RegistryStringValue;
        }
        RegistryStringValue = 0;
      }
      else
      {
        if ( dwValueType != 4 || cbValue != 4 )
        {
          RegistryStringValue = -2147221165;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (const char *)g_wszSRPTrustLevel,
              v142,
              913,
              v143,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v141,
              line,
              g_wszSRPTrustLevel,
              -2147221165);
          }
          return (unsigned int)RegistryStringValue;
        }
        if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        {
          ComTraceMessageT<unsigned int>(
            "onecore\\com\\combase\\catalog\\process.cxx",
            "CComProcessInfo::FinalConstruct",
            905,
            v132,
            L"Found SAFER Level: %#x",
            (unsigned int)protectionLevel.m_ptr);
          v125 = 0;
        }
        m_ptr = (unsigned int)protectionLevel.m_ptr;
        this->m_dwFlags |= 0x10u;
        this->m_dwSaferTrustLevel = m_ptr;
      }
    }
    if ( supportsPreferredServerBitness != (_BYTE)v125 )
    {
      LODWORD(protectionLevel.m_ptr) = v125;
      cbValue = 4;
      v134 = RegQueryValueExW(
               v129,
               Com::Catalog::Constants::PreferredServerBitness,
               0,
               &dwValueType,
               (LPBYTE)&protectionLevel,
               &cbValue);
      v125 = 0;
      if ( v134 )
      {
        if ( v134 != 2 )
        {
          if ( v134 > 0 )
            RegistryStringValue = (unsigned __int16)v134 | 0x80070000;
          else
            RegistryStringValue = v134;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (const char *)Com::Catalog::Constants::PreferredServerBitness,
              v151,
              962,
              v152,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v150,
              line,
              Com::Catalog::Constants::PreferredServerBitness,
              RegistryStringValue);
          }
          return (unsigned int)RegistryStringValue;
        }
        RegistryStringValue = 0;
      }
      else
      {
        if ( dwValueType != 4
          || cbValue != 4
          || (v135 = (unsigned int)protectionLevel.m_ptr, LODWORD(protectionLevel.m_ptr) > 5)
          && LODWORD(protectionLevel.m_ptr) != 0x80000000 )
        {
          RegistryStringValue = -2147221165;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            CGuidStr::CGuidStr(&v184, rclsid);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (const char *)Com::Catalog::Constants::PreferredServerBitness,
              v148,
              950,
              v149,
              L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v147,
              line,
              Com::Catalog::Constants::PreferredServerBitness,
              -2147221165);
          }
          return (unsigned int)RegistryStringValue;
        }
        if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        {
          ComTraceMessageT<unsigned int>(
            "onecore\\com\\combase\\catalog\\process.cxx",
            "CComProcessInfo::FinalConstruct",
            942,
            v136,
            L"Found PreferredServerBitness: %#x",
            v135);
          v135 = (unsigned int)protectionLevel.m_ptr;
          v125 = 0;
        }
        this->m_dwFlags |= 0x20u;
        this->m_dwPreferredServerBitness = v135;
      }
    }
    if ( supportsLoadUserSettings == (_BYTE)v125 )
      goto LABEL_357;
    LODWORD(protectionLevel.m_ptr) = v125;
    cbValue = 4;
    v137 = RegQueryValueExW(v129, g_wszLoadUserSettings, 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
    LOBYTE(v125) = 0;
    if ( v137 )
    {
      if ( v137 == 2 )
      {
        RegistryStringValue = 0;
        goto LABEL_351;
      }
      if ( v137 > 0 )
        RegistryStringValue = (unsigned __int16)v137 | 0x80070000;
      else
        RegistryStringValue = v137;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        CGuidStr::CGuidStr(&v184, rclsid);
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (const char *)g_wszLoadUserSettings,
          v157,
          992,
          v158,
          L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v156,
          line,
          g_wszLoadUserSettings,
          RegistryStringValue);
        LOBYTE(v125) = 0;
      }
LABEL_350:
      if ( RegistryStringValue < 0 )
        goto LABEL_357;
LABEL_351:
      v159 = UseNewCatalogCacheBehavior();
      LOBYTE(v125) = 0;
      if ( v159 )
      {
        if ( !g_bInSCM )
        {
          this->m_changeDetectionSequence = RegistrationChangeDetection::GetSequence();
          goto LABEL_356;
        }
        ObjectLibrary::ReferencedPtr<CObjectContext>::InternalRelease(&this->m_perUserCacheInformation);
        PerUserCacheInformation = RegistrationChangeDetection::GetPerUserCacheInformation(
                                    userToken,
                                    &this->m_changeDetectionSequence,
                                    &this->m_perUserCacheInformation.ptr_);
        LOBYTE(v125) = 0;
        RegistryStringValue = PerUserCacheInformation;
        if ( PerUserCacheInformation < 0 )
          goto LABEL_357;
      }
      if ( fMachineHive )
        goto LABEL_357;
      RegistryStringValue = GetKeyRefreshInfo(v129, &this->m_keyRefreshInfo);
LABEL_356:
      LOBYTE(v125) = 0;
LABEL_357:
      if ( supportsProtectionLevel == (_BYTE)v125 )
        return (unsigned int)RegistryStringValue;
      LODWORD(protectionLevel.m_ptr) = -1;
      cbValue = 4;
      v161 = RegQueryValueExW(v129, L"ProtectionLevel", 0, &dwValueType, (LPBYTE)&protectionLevel, &cbValue);
      if ( v161 )
      {
        if ( v161 == 2 )
          return 0;
        if ( v161 > 0 )
          RegistryStringValue = (unsigned __int16)v161 | 0x80070000;
        else
          RegistryStringValue = v161;
      }
      else
      {
        if ( dwValueType != 4 || cbValue != 4 || LODWORD(protectionLevel.m_ptr) != 2 )
        {
          RegistryStringValue = -2147221165;
          goto LABEL_371;
        }
        this->m_protectionLevel = SuppressImplicit;
      }
      if ( RegistryStringValue >= 0 )
        return (unsigned int)RegistryStringValue;
LABEL_371:
      CGuidStr::CGuidStr(&v184, rclsid);
      LODWORD(file) = RegistryStringValue;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x418u,
        "onecore\\com\\combase\\catalog\\process.cxx",
        RegistryStringValue,
        "CLSID:%ws APPID:%ws Value:%ws hr:%#x",
        v162,
        line,
        L"ProtectionLevel",
        file);
      return (unsigned int)RegistryStringValue;
    }
    if ( dwValueType == 4 && cbValue == 4 )
    {
      this->m_bLoadUserSettings = (int)protectionLevel.m_ptr;
      goto LABEL_350;
    }
    RegistryStringValue = -2147221165;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      CGuidStr::CGuidStr(&v184, rclsid);
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (const char *)g_wszLoadUserSettings,
        v154,
        981,
        v155,
        L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v153,
        line,
        g_wszLoadUserSettings,
        -2147221165);
    }
  }
  return (unsigned int)RegistryStringValue;
}

```

## disassembly

```asm
0x18014b304  push    rbp
0x18014b306  push    rbx
0x18014b307  push    rsi
0x18014b308  push    rdi
0x18014b309  push    r12
0x18014b30b  push    r13
0x18014b30d  push    r14
0x18014b30f  push    r15
0x18014b311  lea     rbp, [rsp-218h]
0x18014b319  sub     rsp, 318h
0x18014b320  mov     rax, cs:__security_cookie
0x18014b327  xor     rax, rsp
0x18014b32a  mov     [rbp+250h+var_50], rax
0x18014b331  mov     rax, [rbp+250h+arg_28]
0x18014b338  mov     r13, rclsid
0x18014b33b  mov     r15, [rbp+250h+hParent]
0x18014b342  mov     rdi, this
0x18014b345  mov     [rbp+250h+userToken], pUserToken
0x18014b349  lea     this, [rbp+250h+wszValue]; void *
0x18014b34d  xor     esi, esi
0x18014b34f  mov     [rbp+250h+var_2C0], r15
0x18014b353  xor     edx, edx; Val
0x18014b355  mov     [rbp+250h+var_2B0], rax
0x18014b359  mov     r8d, 200h; Size
0x18014b35f  mov     [rsp+350h+cbValue], esi
0x18014b363  mov     [rsp+350h+dwValueType], esi
0x18014b367  mov     r12, pwszAppidString
0x18014b36a  mov     [rbp+250h+var_2D0], pwszAppidString
0x18014b36e  call    memset_0
0x18014b373  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18014b379  lea     edx, [rsi+3]
0x18014b37c  movups  xmm0, xmmword ptr [r13+0]
0x18014b381  mov     eax, [rbp+250h+arg_30]
0x18014b387  mov     [rbp+250h+hKeyOle], rsi
0x18014b38b  movdqu  xmmword ptr [rdi+30h], xmm0
0x18014b390  mov     [rsp+350h+dwValue], esi
0x18014b394  mov     [rdi+0D8h], eax
0x18014b39a  jz      short loc_18014B3D8
0x18014b39c  mov     ecx, edx; level
0x18014b39e  call    IsWppLevelEnabled
0x18014b3a3  test    al, al
0x18014b3a5  jz      short loc_18014B3D8
0x18014b3a7  lea     rax, aAppidGuid; "AppID %!GUID!"
0x18014b3ae  mov     [rsp+350h+line], r13
0x18014b3b3  mov     [rsp+350h+format], rax; format
0x18014b3b8  lea     rclsid, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18014b3bf  mov     [rsp+350h+level], edx; level
0x18014b3c3  mov     r9d, 88h; line
0x18014b3c9  lea     pUserToken, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\process"...
0x18014b3d0  or      ecx, 0FFFFFFFFh; hr
0x18014b3d3  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18014b3d8  lea     rax, [rdi+40h]
0x18014b3dc  mov     r9d, 2; dwQueryFlags
0x18014b3e2  xor     r8d, r8d; pwszValueName
0x18014b3e5  mov     qword ptr [rsp+350h+level], rax; ppwszValue
0x18014b3ea  xor     edx, edx; pwszSubKeyName
0x18014b3ec  mov     this, r15; hParent
0x18014b3ef  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18014b3f4  mov     ebx, eax
0x18014b3f6  mov     eax, 80000000h
0x18014b3fb  lea     ecx, [rbx+rax]
0x18014b3fe  test    eax, ecx
0x18014b400  jnz     short loc_18014B474
0x18014b402  cmp     ebx, 80070002h
0x18014b408  jz      short loc_18014B474
0x18014b40a  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x18014b410  test    ecx, ecx
0x18014b412  jnz     short loc_18014B42D
0x18014b414  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18014b41a  jz      $Cleanup_11
0x18014b420  call    IsWppLevelEnabled
0x18014b425  test    al, al
0x18014b427  jz      $Cleanup_11
0x18014b42d  mov     pUserToken, r13; rguid
0x18014b430  lea     this, [rbp+250h+var_2A0]; this
0x18014b434  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18014b439  mov     [rsp+350h+var_318], ebx; <args_2>
0x18014b43d  lea     pUserToken, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18014b444  mov     [rsp+350h+line], r12; <args_1>
0x18014b449  lea     this, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\process"...
0x18014b450  mov     [rsp+350h+format], rax; <args_0>
0x18014b455  xor     r9d, r9d; level
0x18014b458  lea     rax, aClsidWsAppidWs_1; "CLSID:%ws APPID:%ws %!HRESULT!"
0x18014b45f  mov     r8d, 92h; line
0x18014b465  mov     qword ptr [rsp+350h+level], rax; format
0x18014b46a  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x18014b46f  jmp     $Cleanup_11
0x18014b474  lea     r14, [rdi+50h]
0x18014b478  mov     r9d, 2; dwQueryFlags
0x18014b47e  lea     rclsid, ?LocalService@Constants@Catalog@Com@@3QBGB; pwszValueName
0x18014b485  mov     qword ptr [rsp+350h+level], r14; ppwszValue
0x18014b48a  xor     edx, edx; pwszSubKeyName
0x18014b48c  mov     this, r15; hParent
0x18014b48f  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18014b494  mov     ecx, 80000000h
0x18014b499  mov     ebx, eax
0x18014b49b  add     eax, ecx
0x18014b49d  test    ecx, eax
0x18014b49f  jnz     short loc_18014B4EC
0x18014b4a1  cmp     ebx, 80070002h
0x18014b4a7  jz      short loc_18014B4EC
0x18014b4a9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18014b4af  test    eax, eax
0x18014b4b1  jnz     short loc_18014B4CE
0x18014b4b3  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18014b4b9  jz      $Cleanup_11
0x18014b4bf  xor     ecx, ecx; level
0x18014b4c1  call    IsWppLevelEnabled
0x18014b4c6  test    al, al
0x18014b4c8  jz      $Cleanup_11
0x18014b4ce  mov     pUserToken, r13; rguid
0x18014b4d1  lea     this, [rbp+250h+var_2A0]; this
0x18014b4d5  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18014b4da  lea     this, ?LocalService@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::LocalService
0x18014b4e1  mov     r8d, 0A2h
0x18014b4e7  jmp     loc_18014CE20
0x18014b4ec  mov     sil, [rbp+250h+arg_90]
0x18014b4f3  xor     ebx, ebx
0x18014b4f5  test    sil, sil
0x18014b4f8  jz      loc_18014B57F
0x18014b4fe  mov     rax, [rbp+250h+userToken]
0x18014b502  lea     this, [rsp+350h+protectionLevel]; this
0x18014b507  mov     [rsp+350h+protectionLevel], rbx
0x18014b50c  xor     edx, edx; ptr
0x18014b50e  mov     rax, [rax]
0x18014b511  mov     rbx, [rax+50h]
0x18014b515  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18014b51a  mov     this, [rbp+250h+userToken]
0x18014b51e  lea     pUserToken, [rsp+350h+protectionLevel]
0x18014b523  mov     rax, rbx
0x18014b526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b52b  mov     ebx, eax
0x18014b52d  test    eax, eax
0x18014b52f  jns     short loc_18014B540
0x18014b531  lea     this, [rsp+350h+protectionLevel]; this
0x18014b536  call    ??1?$MakeAllocator@VView@?$HashMap@IPEAUHSTRING__@@U?$DefaultHash@I@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@I@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$HashMapOptions@IPEAUHSTRING__@@U?$DefaultLifetimeTraits@I@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>(void)
0x18014b53b  jmp     $Cleanup_11
0x18014b540  lea     rbx, [rdi+100h]
0x18014b547  xor     edx, edx; ptr
0x18014b549  mov     this, rbx; this
0x18014b54c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18014b551  mov     this, [rsp+350h+protectionLevel]; sourceString
0x18014b556  or      pUserToken, 0FFFFFFFFFFFFFFFFh
0x18014b55a  xor     eax, eax
0x18014b55c  inc     pUserToken; length
0x18014b55f  cmp     [this+pUserToken*2], ax
0x18014b563  jnz     short loc_18014B55C
0x18014b565  mov     rclsid, rbx; string
0x18014b568  call    WindowsCreateString
0x18014b56d  lea     this, [rsp+350h+protectionLevel]; this
0x18014b572  mov     ebx, eax
0x18014b574  test    eax, eax
0x18014b576  js      short loc_18014B536
0x18014b578  call    ??1?$MakeAllocator@VView@?$HashMap@IPEAUHSTRING__@@U?$DefaultHash@I@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@I@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$HashMapOptions@IPEAUHSTRING__@@U?$DefaultLifetimeTraits@I@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>(void)
0x18014b57d  xor     ebx, ebx
0x18014b57f  mov     rclsid, [r14]; lpMem
0x18014b582  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18014b589  test    rclsid, rclsid
0x18014b58c  jz      loc_18014B6E3
0x18014b592  cmp     [rclsid], bx
0x18014b596  jz      loc_18014B6CF
0x18014b59c  xor     r14d, r14d
0x18014b59f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18014b5a6  jz      short loc_18014B5E4
0x18014b5a8  lea     edx, [r14+3]
0x18014b5ac  mov     ecx, edx; level
0x18014b5ae  call    IsWppLevelEnabled
0x18014b5b3  test    al, al
0x18014b5b5  jz      short loc_18014B5E4
0x18014b5b7  mov     [rsp+350h+format], rclsid; <args_0>
0x18014b5bc  lea     rax, aFoundLocalServ; "Found local service! (%ws)"
0x18014b5c3  mov     r9d, edx; level
0x18014b5c6  mov     qword ptr [rsp+350h+level], rax; format
0x18014b5cb  mov     r8d, 0B9h; line
0x18014b5d1  lea     pUserToken, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18014b5d8  lea     this, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\process"...
0x18014b5df  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x18014b5e4  lea     rax, [rdi+58h]
0x18014b5e8  mov     dword ptr [rdi+48h], 1
0x18014b5ef  mov     r9d, 2; dwQueryFlags
0x18014b5f5  mov     qword ptr [rsp+350h+level], rax; file
0x18014b5fa  lea     rclsid, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; pwszValueName
0x18014b601  xor     edx, edx; pwszSubKeyName
0x18014b603  mov     this, r15; hParent
0x18014b606  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18014b60b  mov     ecx, 80000000h
0x18014b610  mov     ebx, eax
0x18014b612  add     eax, ecx
0x18014b614  test    ecx, eax
0x18014b616  jnz     short loc_18014B664
0x18014b618  cmp     ebx, 80070002h
0x18014b61e  jz      short loc_18014B664
0x18014b620  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18014b626  test    eax, eax
0x18014b628  jnz     short loc_18014B646
0x18014b62a  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18014b631  jz      $Cleanup_11
0x18014b637  xor     ecx, ecx; level
0x18014b639  call    IsWppLevelEnabled
0x18014b63e  test    al, al
0x18014b640  jz      $Cleanup_11
0x18014b646  mov     pUserToken, r13; rguid
0x18014b649  lea     this, [rbp+250h+var_2A0]; this
0x18014b64d  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18014b652  lea     this, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::ServiceParameters
0x18014b659  mov     r8d, 0C1h
0x18014b65f  jmp     loc_18014CE20
0x18014b664  test    sil, sil
0x18014b667  jz      short loc_18014B6BE
0x18014b669  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18014b66f  mov     ebx, 80040157h
0x18014b674  test    eax, eax
0x18014b676  jnz     short loc_18014B694
0x18014b678  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18014b67f  jz      $Cleanup_11
0x18014b685  xor     ecx, ecx; level
0x18014b687  call    IsWppLevelEnabled
0x18014b68c  test    al, al
0x18014b68e  jz      $Cleanup_11
0x18014b694  mov     pUserToken, r13; rguid
0x18014b697  lea     this, [rbp+250h+var_2A0]; this
0x18014b69b  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18014b6a0  mov     [rsp+350h+var_308], sil; <args_0>
0x18014b6a5  mov     byte ptr [rsp+350h+file], r14b; format
0x18014b6aa  mov     [rsp+350h+line], r12; line
0x18014b6af  mov     [rsp+350h+format], rax; function
0x18014b6b4  call    ??$ComTraceMessageT@PEAGPEAGPEBG_N_NJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG32_N4J@Z; ComTraceMessageT<ushort *,ushort *,ushort const *,bool,bool,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,ushort const *,bool,bool,long)
0x18014b6b9  jmp     $Cleanup_11
0x18014b6be  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x18014b6c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18014b6ca  jmp     loc_18014B924
0x18014b6cf  cmp     rclsid, rax
0x18014b6d2  jz      short loc_18014B6E3
0x18014b6d4  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18014b6db  xor     edx, edx; dwFlags
0x18014b6dd  call    cs:__imp_HeapFree
0x18014b6e3  lea     rsi, [rdi+78h]
0x18014b6e7  mov     [r14], rbx
0x18014b6ea  xor     r9d, r9d; dwQueryFlags
0x18014b6ed  mov     qword ptr [rsp+350h+level], rsi; ppwszValue
0x18014b6f2  lea     rclsid, ?DllSurrogate@Constants@Catalog@Com@@3QBGB; pwszValueName
0x18014b6f9  xor     edx, edx; pwszSubKeyName
0x18014b6fb  mov     this, r15; hParent
0x18014b6fe  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18014b703  xor     r14d, r14d
0x18014b706  mov     ebx, eax
0x18014b708  test    eax, eax
0x18014b70a  js      loc_18014B8D3
0x18014b710  mov     pUserToken, [rsi]
0x18014b713  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18014b71a  cmp     pUserToken, rax
0x18014b71d  jnz     short loc_18014B76B
0x18014b71f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18014b726  jz      short loc_18014B75F
0x18014b728  lea     edx, [r14+3]
0x18014b72c  mov     ecx, edx; level
0x18014b72e  call    IsWppLevelEnabled
0x18014b733  test    al, al
0x18014b735  jz      short loc_18014B75F
0x18014b737  lea     rax, aFoundSurrogate_0; "Found surrogate: dllhost"
0x18014b73e  mov     r9d, edx; level
0x18014b741  lea     pUserToken, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18014b748  mov     qword ptr [rsp+350h+level], rax; format
0x18014b74d  mov     r8d, 152h; line
0x18014b753  lea     this, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\process"...
0x18014b75a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18014b75f  mov     dword ptr [rdi+48h], 2
0x18014b766  jmp     loc_18014B924
0x18014b76b  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18014b772  jz      short loc_18014B7B2
0x18014b774  mov     ecx, 3; level
0x18014b779  call    IsWppLevelEnabled
0x18014b77e  test    al, al
0x18014b780  jz      short loc_18014B7B2
0x18014b782  mov     [rsp+350h+format], pUserToken; <args_0>
0x18014b787  lea     rax, aFoundSurrogate; "Found surrogate: %ws"
0x18014b78e  lea     pUserToken, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18014b795  mov     qword ptr [rsp+350h+level], rax; format
0x18014b79a  mov     r9d, 3; level
0x18014b7a0  lea     this, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\process"...
0x18014b7a7  mov     r8d, 158h; line
0x18014b7ad  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x18014b7b2  lea     rax, [rdi+0E0h]
0x18014b7b9  mov     dword ptr [rdi+48h], 3
0x18014b7c0  lea     rsi, g_wszDebugSurrogate
0x18014b7c7  mov     qword ptr [rsp+350h+level], rax; ppwszValue
0x18014b7cc  mov     rclsid, rsi; pwszValueName
0x18014b7cf  xor     r9d, r9d; dwQueryFlags
0x18014b7d2  xor     edx, edx; pwszSubKeyName
0x18014b7d4  mov     this, r15; hParent
0x18014b7d7  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18014b7dc  mov     ebx, eax
0x18014b7de  test    eax, eax
0x18014b7e0  js      short loc_18014B7EE
0x18014b7e2  mov     dword ptr [rdi+0F4h], 1
0x18014b7ec  jmp     short loc_18014B7FA
0x18014b7ee  cmp     ebx, 80070002h
0x18014b7f4  jnz     loc_18014B88D
0x18014b7fa  cmp     [rdi+0F4h], r14d
0x18014b801  jnz     loc_18014B924
  ... truncated ...
```
