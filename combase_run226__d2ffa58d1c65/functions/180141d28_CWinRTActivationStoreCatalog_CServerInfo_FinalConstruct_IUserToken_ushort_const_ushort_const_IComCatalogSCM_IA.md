# CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct(IUserToken *,ushort const *,ushort const *,IComCatalogSCM *,IActivationCatalogContext *,RegistrationStoreContext::ServerHandleDetail *,RegistrationStoreContext::ServerForMachineHandleDetail *)

- ea: `0x180141d28`
- end: `0x1801441c4`
- name: `?FinalConstruct@CServerInfo@CWinRTActivationStoreCatalog@@QEAAJPEAUIUserToken@@PEBG1PEAUIComCatalogSCM@@PEAUIActivationCatalogContext@@PEAUServerHandleDetail@RegistrationStoreContext@@PEAUServerForMachineHandleDetail@7@@Z`
- size: `9372`
- prototype: `HRESULT __fastcall(CWinRTActivationStoreCatalog::CServerInfo *this, IUserToken *pUserToken, const wchar_t *serverName, const wchar_t *packageMoniker, IComCatalogSCM *pComCatalogCallback, IActivationCatalogContext *pRegistrationStore, RegistrationStoreContext::ServerHandleDetail *serverHandle, RegistrationStoreContext::ServerForMachineHandleDetail *serverForMachineHandle)`
- caller_count: `1`
- callee_count: `51`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18010d5a0`

## callees

- `0x18000b408`
- `0x18003a8bc`
- `0x180041a00`
- `0x180041e50`
- `0x1800421e0`
- `0x1800450a0`
- `0x18004768c`
- `0x18004cc90`
- `0x18005314c`
- `0x180053a60`
- `0x1800548bc`
- `0x180055000`
- `0x180056ce0`
- `0x18005b87c`
- `0x18005d12c`
- `0x1800859ec`
- `0x1800865b8`
- `0x180086714`
- `0x18008db2c`
- `0x1800c4250`
- `0x1800d3b5c`
- `0x1800d3bf0`
- `0x1800d4014`
- `0x1800d49d8`
- `0x1800d56a0`
- `0x1800ddc40`
- `0x1800e93f0`
- `0x1801003b8`
- `0x180105a24`
- `0x180117250`
- `0x1801174bc`
- `0x180126260`
- `0x1801271e4`
- `0x18012b924`
- `0x18012d5c4`
- `0x18012eebc`
- `0x180131984`
- `0x18013a770`
- `0x18013c024`
- `0x180141d28`
- `0x1801457c0`
- `0x18014ebe8`
- `0x18015706c`
- `0x180163a04`
- `0x18017e094`
- `0x180189b00`
- `0x18018a1ac`
- `0x180190700`
- `0x1801999b0`
- `0x18019c9fc`

## import_xrefs

- `ext-ms-win-core-winrt-remote-l1-1-0!WinRTPerMachineSingleInstancing` at `0x180143409`
- `ext-ms-win-core-winrt-remote-l1-1-0!WinRTPerMachineSingleInstancing` at `0x180143409`

## string_xrefs

- `0x180141e83`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801421f9`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142464`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142583`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801425d1`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142613`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142682`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801426fd`: `onecore\com\combase\catalog\storecat.cxx`
- `0x18014274f`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142791`: `onecore\com\combase\catalog\storecat.cxx`
- `0x18014292c`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142bab`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180142df0`: `onecore\com\combase\catalog\storecat.cxx`
- `0x18014301a`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801430ae`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801433aa`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801435b3`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143869`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801439d6`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143bb6`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143d5c`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143ec0`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143ef4`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180143f93`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1801420a8`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property AppID (%ws): %!HRESULT!`
- `0x180141f39`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ServerType (%d): %!HRESULT!`
- `0x180142cda`: `Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, only NormalExe can have CommandLine`
- `0x180142e0c`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivatableClasses : %!HRESULT!`
- `0x180142a9d`: `Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, only NormalExe and ExeService can have ExePath`
- `0x180142bc6`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property CommandLine (%ws): %!HRESULT!`
- `0x18014294c`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ExePath (%ws): %!HRESULT!`
- `0x180142213`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ExecutionPackageName (%ws): %!HRESULT!`
- `0x18014247f`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property appUserModelID (%ws): %!HRESULT!`
- `0x1801435d6`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Identity (%ws): %!HRESULT!`
- `0x1801433cc`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Instancing %d: %!HRESULT!`
- `0x180143041`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property IdentityType (%d): %!HRESULT!`
- `0x18014316f`: `Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, services must be RunAs`
- `0x180143f9a`: `entry.GetLastWriteTime result is %!TIME!`
- `0x180143d79`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Permissions: %!HRESULT!`
- `0x180143a92`: `Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, NormalExe but has ServiceName`
- `0x18014388d`: `Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ServiceName (%ws): %!HRESULT!`
- `0x1801439e5`: `Server entry %ws is in per-user store, but has ServiceName property (%ws)`

## pseudocode

```c
HRESULT __fastcall CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct(
        CWinRTActivationStoreCatalog::CServerInfo *this,
        IUserToken *pUserToken,
        wchar_t *serverName,
        const wchar_t *packageMoniker,
        IComCatalogSCM *pComCatalogCallback,
        IActivationCatalogContext *pRegistrationStore,
        RegistrationStoreContext::ServerHandleDetail *serverHandle,
        RegistrationStoreContext::ServerForMachineHandleDetail *serverForMachineHandle)
{
  HRESULT result; // eax
  Windows::Foundation::RegistrationScope v13; // eax
  void *v14; // rcx
  __int64 v15; // rcx
  const wchar_t *v16; // rdx
  HRESULT v17; // ebx
  IComProcessInfo3 *v18; // r9
  HRESULT v19; // ebx
  char v20; // r8
  HRESULT Permissions; // r15d
  unsigned __int16 v22; // cx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v24; // eax
  Windows::Foundation::IdentityType v25; // rax^4
  __int64 v26; // rdx
  int String; // eax
  IComProcessInfo3 *v28; // rdi
  PCWSTR v29; // rax
  bool IsEnabled; // al
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *p_executionPackageName; // rcx
  const wchar_t *v32; // rax
  PackageFamilyErrorDetails *v33; // r9
  HRESULT InstalledPackageFullNameFromMainPackageFamilyName; // eax
  const wchar_t *v35; // rax
  PackageFamilyErrorDetails *v36; // r9
  IComProcessInfo3 *v37; // rbx
  unsigned __int64 registrationScope; // rdx
  PCWSTR v39; // rax
  wchar_t *v40; // rax
  HSTRING__ *v41; // rdx
  HRESULT v42; // eax
  HSTRING__ *hstr; // rcx
  HSTRING__ *v44; // r12
  unsigned int v45; // edx
  IUserToken *v46; // r15
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rsi
  HRESULT v48; // eax
  unsigned int *v49; // rdx
  const wchar_t *RawBuffer; // rax
  IUserTokenInternal *ptr; // r14
  const wchar_t *v52; // rsi
  const wchar_t *v53; // rax
  HRESULT v54; // eax
  IComProcessInfo3 *v55; // rcx
  IComProcessInfo3 *v56; // rsi
  const wchar_t *v57; // rax
  int v58; // eax
  HRESULT v59; // r9d
  unsigned int v60; // edx
  Windows::Foundation::RegistrationScope scope; // ecx
  AppModel::TrustLevel v62; // eax
  bool Value; // r8
  bool Present; // dl
  AppModel::RuntimeBehavior v65; // eax
  AppModel::BnoIsolation v66; // eax
  HRESULT v67; // eax
  unsigned __int64 serverType; // rdx
  int v69; // r8d
  PCWSTR v70; // rax
  wchar_t *v71; // rsi
  const char *v72; // rcx
  bool v73; // dl
  HRESULT CommandLineW; // eax
  const wchar_t *v75; // rdx
  IComProcessInfo3 *v76; // r8
  PCWSTR v77; // rax
  HRESULT AbsoluteExpandedPathAsPWSTR; // eax
  const char *v79; // rcx
  bool v80; // dl
  HRESULT v81; // eax
  const wchar_t *v82; // rdx
  IComProcessInfo3 *v83; // r11
  HRESULT v84; // esi
  int StringResource; // eax
  HRESULT v86; // ecx
  int v87; // eax
  char v88; // r8
  Windows::Foundation::IdentityType IdentityType; // eax
  bool v90; // zf
  unsigned __int16 v91; // cx
  int v92; // eax
  const char *v93; // rcx
  Windows::Foundation::RegistrationScope v94; // eax
  Windows::Foundation::IdentityType v95; // eax
  const char *v96; // rdx
  const char *v97; // rcx
  TraceLevel v98; // r9d
  const char *v99; // rdx
  const char *v100; // rcx
  TraceLevel v101; // r9d
  wchar_t *v102; // r14
  const char *v103; // rdx
  const char *v104; // rcx
  int v105; // r8d
  TraceLevel v106; // r9d
  IComProcessInfo3 *v107; // r14
  unsigned __int64 v108; // rdx
  int v109; // r8d
  PCWSTR v110; // rax
  const char *v111; // rcx
  const wchar_t *v112; // rax
  IComProcessInfo3 *v113; // rsi
  HRESULT v114; // r10d
  unsigned __int64 v115; // rdx
  PCWSTR v116; // rax
  int v117; // eax
  wchar_t *v118; // rax
  const char *v119; // rcx
  const wchar_t *v120; // rax
  int v121; // eax
  wchar_t *v122; // rdx
  int v123; // r11d
  HRESULT v124; // r11d
  unsigned __int16 v125; // cx
  IUnknown *pRegProcessInfo; // rcx
  Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *v127; // r11
  int v128; // eax
  int Attributes; // eax
  Optional<enum _PSM_ACTIVATE_BACKGROUND_TYPE> ExplicitPsmActivationType; // rax
  __int64 v131; // rdx
  HRESULT v132; // eax
  unsigned int v133; // edx
  TraceLevel v134; // edx
  int v135; // edx
  TraceLevel v136; // r8d
  IUnknown *v137; // rdx
  const char *v138; // r10
  const unsigned __int16 *v139; // rax
  const unsigned __int16 *v140; // r15
  Windows::Foundation::RegistrationScope v141; // eax
  wchar_t *identity; // r11
  const wchar_t *v143; // r9
  const wchar_t *v144; // r8
  const char *v145; // rcx
  wchar_t *serviceName; // rax
  wchar_t *format; // [rsp+20h] [rbp-120h]
  Windows::Foundation::RegistrationScope file[2]; // [rsp+30h] [rbp-110h]
  Windows::Foundation::IdentityType function[2]; // [rsp+38h] [rbp-108h]
  Windows::Foundation::IdentityType line[2]; // [rsp+40h] [rbp-100h]
  unsigned __int16 uResourceId[2]; // [rsp+C0h] [rbp-80h] BYREF
  IComProcessInfo3 *pComProcessInfo3; // [rsp+C8h] [rbp-78h] BYREF
  int fIsAppContainer; // [rsp+D0h] [rbp-70h] BYREF
  wchar_t *v154; // [rsp+D8h] [rbp-68h]
  MultiString activatableClasses; // [rsp+E0h] [rbp-60h] BYREF
  EntryPropertyStore propertyStore; // [rsp+E8h] [rbp-58h] BYREF
  Microsoft::WRL::ComPtr<IMetaDataImport2> v157; // [rsp+F8h] [rbp-48h] BYREF
  ExpandableString exePath; // [rsp+100h] [rbp-40h] BYREF
  IUserToken *userToken; // [rsp+110h] [rbp-30h]
  Windows::Foundation::InstancingType v160[2]; // [rsp+118h] [rbp-28h]
  unsigned int dwRotFlagsFromAppID; // [rsp+120h] [rbp-20h] BYREF
  IComCatalogSCM *dwMgotFlagsFromAppID; // [rsp+128h] [rbp-18h] BYREF
  __int64 lLastDebugInformationWriteTime; // [rsp+130h] [rbp-10h]
  Optional<OpaqueString> hostRuntimeId; // [rsp+138h] [rbp-8h] BYREF
  CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper serverHelper; // [rsp+150h] [rbp+10h] BYREF
  CGuidStr v166; // [rsp+2E0h] [rbp+1A0h] BYREF
  void *retaddr; // [rsp+388h] [rbp+248h]

  userToken = pUserToken;
  v154 = serverName;
  dwMgotFlagsFromAppID = pComCatalogCallback;
  lLastDebugInformationWriteTime = (__int64)pRegistrationStore;
  *(_QWORD *)v160 = serverHandle;
  fIsAppContainer = 0;
  result = DuplicatePWSTR(serverName, &this->_serverName);
  if ( result >= 0 )
  {
    v13 = pRegistrationStore->GetRegistrationStoreScope(pRegistrationStore);
    this->_registrationScope = v13;
    if ( v13 != RegistrationScope_PerUser )
      goto LABEL_10;
    if ( pUserToken )
    {
      pComProcessInfo3 = 0;
      result = pUserToken->GetUserToken(pUserToken, (void **)&pComProcessInfo3);
      if ( result < 0 )
        return result;
      v15 = (__int64)pComProcessInfo3;
    }
    else
    {
      result = IsTokenChildAppContainer(v14, &fIsAppContainer);
      if ( result < 0 )
        return result;
      if ( fIsAppContainer )
        goto LABEL_10;
      v15 = -4;
    }
    result = IsTokenBoolPresent((void *)v15, TokenIsAppContainer, &fIsAppContainer);
    if ( result < 0 )
      return result;
LABEL_10:
    CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::CServerInfoPropertiesHelper(
      &serverHelper,
      this->_registrationScope);
    v17 = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::ReadServerRegistrationEntry(
            &serverHelper,
            pRegistrationStore,
            serverHandle,
            serverForMachineHandle);
    fIsAppContainer = -2147024883;
    if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147024883 )
    {
      ServerMachineRegistrationEntryProperties::~ServerMachineRegistrationEntryProperties(&serverHelper._machineProperties);
      ServerRegistrationEntryProperties::~ServerRegistrationEntryProperties(&serverHelper._userProperties);
      return v17;
    }
    v18 = 0;
    v19 = -2147024894;
    if ( this->_registrationScope )
    {
LABEL_28:
      LOBYTE(v16) = serverHelper._machineInvalidProperties[0];
      v20 = serverHelper._machineMissingRequiredProperties[0];
      goto LABEL_29;
    }
    v20 = serverHelper._machineMissingRequiredProperties[0];
    this->_serverType = serverHelper._machineProperties.ServerType;
    if ( (v20 & 0x20) != 0 )
    {
      Permissions = -2147024894;
    }
    else
    {
      LOBYTE(v16) = serverHelper._machineInvalidProperties[0];
      if ( (serverHelper._machineInvalidProperties[0] & 0x20) == 0 )
      {
        if ( !gfEnableTracing || (Permissions = 0, !IsWppLevelEnabled(VERBOSE)) )
        {
LABEL_29:
          if ( this->_registrationScope != (_DWORD)v18 )
            goto LABEL_53;
          if ( (v20 & 0x40) != 0 )
            goto LABEL_38;
          if ( ((unsigned __int8)v16 & 0x40) != 0 )
          {
            Permissions = -2147024883;
LABEL_43:
            if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
              && (gfEnableTracing == (_DWORD)v18 || !IsWppLevelEnabled(ERRORS)) )
            {
LABEL_46:
              if ( Permissions != -2147024894 )
              {
                if ( Permissions != -2147024882 )
                {
                  v22 = 5218;
LABEL_26:
                  uResourceId[0] = (unsigned __int16)v18;
                  pComProcessInfo3 = v18;
                  if ( LoadStringResource(v22, v16, (const wchar_t **)&pComProcessInfo3, uResourceId) < 0 )
                    RoOriginateError(Permissions, 0);
                  else
                    RoOriginateErrorW(Permissions, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                }
LABEL_267:
                CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::~CServerInfoPropertiesHelper(&serverHelper);
                return Permissions;
              }
              goto LABEL_53;
            }
            goto LABEL_51;
          }
          if ( serverHelper._machineProperties.AppId.Present == (_BYTE)v18 )
          {
LABEL_38:
            Permissions = -2147024894;
          }
          else
          {
            StringRawBuffer = WindowsGetStringRawBuffer(serverHelper._machineProperties.AppId.Value.hstr_, 0);
            v24 = IIDFromString(StringRawBuffer, &this->_appId);
            v18 = 0;
            Permissions = v24;
            if ( v24 < 0 )
              Permissions = -2147024883;
            if ( Permissions != -2147024894 )
            {
LABEL_41:
              if ( Permissions < 0 )
              {
                if ( Permissions != -2147024894 )
                  goto LABEL_43;
LABEL_53:
                if ( packageMoniker )
                {
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                    &this->_deployingPackageName,
                    0);
                  v26 = -1;
                  do
                    ++v26;
                  while ( packageMoniker[v26] );
                  String = WindowsCreateString(packageMoniker, v26, &this->_deployingPackageName.m_ptr);
                  v18 = 0;
                  Permissions = String;
                  if ( String < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      0xC49u,
                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                      String);
                    goto LABEL_267;
                  }
                  v19 = -2147024894;
                }
                v28 = v18;
                pComProcessInfo3 = v18;
                if ( serverHelper._scope == (_DWORD)v18 )
                {
                  Permissions = -2147024894;
                  goto LABEL_70;
                }
                if ( (serverHelper._userMissingRequiredProperties[0] & 0x10) != 0 )
                  goto LABEL_66;
                if ( (serverHelper._userInvalidProperties[0] & 0x10) != 0 )
                {
                  Permissions = -2147024883;
                  goto LABEL_67;
                }
                if ( serverHelper._userProperties.ExecutionPackageFamily.Present == (_BYTE)v18 )
                {
LABEL_66:
                  Permissions = -2147024894;
                }
                else
                {
                  Permissions = (int)v18;
                  OpaqueString::operator=(
                    (OpaqueString *)&pComProcessInfo3,
                    &serverHelper._userProperties.ExecutionPackageFamily.Value);
                  v28 = pComProcessInfo3;
                  v18 = 0;
                }
LABEL_67:
                v19 = Permissions;
                if ( Permissions != -2147024894 )
                {
LABEL_72:
                  if ( v19 >= 0 )
                  {
                    if ( gfEnableTracing == (_DWORD)v18 || !IsWppLevelEnabled(VERBOSE) )
                      goto LABEL_79;
                    v29 = WindowsGetStringRawBuffer((HSTRING)v28, 0);
LABEL_78:
                    line[0] = v19;
                    file[0] = this->_registrationScope;
                    ComTraceHr(
                      v19,
                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                      "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                      3156,
                      L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ExecutionPackag"
                       "eName (%ws): %!HRESULT!",
                      serverName,
                      *(_QWORD *)file,
                      v29,
                      *(_QWORD *)line);
                    v18 = 0;
                    if ( v19 >= 0 )
                    {
LABEL_79:
                      propertyStore.MapView.ptr_ = (Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *)v18;
                      if ( !userToken
                        || (Permissions = userToken->QueryInterface(
                                            userToken,
                                            &GUID_000001fc_0000_0000_cfff_123045660046,
                                            (void **)&propertyStore),
                            Permissions >= 0) )
                      {
                        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
                        p_executionPackageName = &this->_executionPackageName;
                        if ( IsEnabled )
                        {
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                            p_executionPackageName,
                            0);
                          v32 = WindowsGetStringRawBuffer((HSTRING)v28, 0);
                          InstalledPackageFullNameFromMainPackageFamilyName = GetInstalledPackageFullNameFromMainPackageFamilyName(
                                                                                (IUserTokenInternal *)propertyStore.MapView.ptr_,
                                                                                v32,
                                                                                &this->_executionPackageName.m_ptr,
                                                                                v33);
                        }
                        else
                        {
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                            p_executionPackageName,
                            0);
                          v35 = WindowsGetStringRawBuffer((HSTRING)v28, 0);
                          InstalledPackageFullNameFromMainPackageFamilyName = GetInstalledPackageFullNameFromMainPackageFamilyNameOld(
                                                                                (IUserTokenInternal *)propertyStore.MapView.ptr_,
                                                                                v35,
                                                                                &this->_executionPackageName.m_ptr,
                                                                                v36);
                        }
                        Permissions = InstalledPackageFullNameFromMainPackageFamilyName;
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&propertyStore);
                      goto LABEL_95;
                    }
                    if ( v19 != -2147024894 )
                    {
LABEL_90:
                      if ( v19 != -2147024882 )
                      {
                        pComProcessInfo3 = v18;
                        uResourceId[0] = (unsigned __int16)v18;
                        if ( LoadStringResource(0x1483u, v16, (const wchar_t **)&pComProcessInfo3, uResourceId) < 0 )
                          RoOriginateError(v19, 0);
                        else
                          RoOriginateErrorW(v19, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                      }
LABEL_95:
                      if ( Permissions < 0 )
                      {
LABEL_96:
                        WindowsDeleteString((HSTRING)v28);
                        goto LABEL_267;
                      }
                      v37 = 0;
                      pComProcessInfo3 = 0;
                      if ( serverHelper._scope == RegistrationScope_PerMachine
                        || (serverHelper._userMissingRequiredProperties[0] & 8) != 0 )
                      {
                        Permissions = -2147024894;
                      }
                      else if ( (serverHelper._userInvalidProperties[0] & 8) != 0 )
                      {
                        Permissions = -2147024883;
                      }
                      else if ( serverHelper._userProperties.AppUserModelId.Present )
                      {
                        Permissions = 0;
                        OpaqueString::operator=(
                          (OpaqueString *)&pComProcessInfo3,
                          &serverHelper._userProperties.AppUserModelId.Value);
                        v37 = pComProcessInfo3;
                      }
                      else
                      {
                        Permissions = -2147024894;
                      }
                      registrationScope = (unsigned int)this->_registrationScope;
                      if ( (_DWORD)registrationScope != 1 && Permissions == -2147024894 )
                      {
                        if ( !gfEnableTracing )
                        {
LABEL_110:
                          registrationScope = (unsigned int)(1 - registrationScope);
                          if ( Permissions == ((_DWORD)registrationScope != 0 ? 0x80070002 : 0)
                            || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                            && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                          {
LABEL_119:
                            if ( Permissions != -2147024894 )
                            {
                              pComProcessInfo3 = 0;
                              uResourceId[0] = 0;
                              if ( LoadStringResource(
                                     0x1475u,
                                     (const wchar_t *)registrationScope,
                                     (const wchar_t **)&pComProcessInfo3,
                                     uResourceId) < 0 )
                                RoOriginateError(Permissions, 0);
                              else
                                RoOriginateErrorW(Permissions, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                              goto LABEL_131;
                            }
LABEL_133:
                            hostRuntimeId.Present = 0;
                            hostRuntimeId.Value.hstr_ = 0;
                            v42 = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetHostRuntimeId(
                                    &serverHelper,
                                    &hostRuntimeId);
                            Permissions = v42;
                            if ( v42 < 0 )
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                0xCACu,
                                "onecore\\com\\combase\\catalog\\storecat.cxx",
                                v42);
                              hstr = hostRuntimeId.Value.hstr_;
LABEL_135:
                              WindowsDeleteString(hstr);
LABEL_131:
                              WindowsDeleteString((HSTRING)v37);
                              goto LABEL_96;
                            }
                            v44 = hostRuntimeId.Value.hstr_;
                            if ( hostRuntimeId.Present )
                            {
                              if ( this->_serverType )
                              {
                                v45 = 3247;
LABEL_139:
                                Permissions = -2147221165;
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  v45,
                                  "onecore\\com\\combase\\catalog\\storecat.cxx",
                                  -2147221165);
LABEL_140:
                                hstr = v44;
                                goto LABEL_135;
                              }
                              if ( !this->_executionPackageName.m_ptr )
                              {
                                v45 = 3248;
                                goto LABEL_139;
                              }
                              v46 = userToken;
                              v157.ptr_ = 0;
                              if ( userToken )
                              {
                                QueryInterface = userToken->QueryInterface;
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v157);
                                v48 = QueryInterface(
                                        v46,
                                        &GUID_000001fc_0000_0000_cfff_123045660046,
                                        (void **)&v157.ptr_);
                                Permissions = v48;
                                if ( v48 < 0 )
                                {
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    0xCB5u,
                                    "onecore\\com\\combase\\catalog\\storecat.cxx",
                                    v48);
LABEL_146:
                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v157);
                                  goto LABEL_140;
                                }
                              }
                              WindowsDeleteString(0);
                              pComProcessInfo3 = 0;
                              RawBuffer = Windows::Internal::StringReference::GetRawBuffer(
                                            (Windows::Internal::StringReference *)&this->_executionPackageName,
                                            v49);
                              ptr = (IUserTokenInternal *)v157.ptr_;
                              v52 = RawBuffer;
                              v53 = WindowsGetStringRawBuffer(v44, 0);
                              v54 = ResolveHostRuntime(
                                      v53,
                                      ptr,
                                      v52,
                                      (HSTRING__ **)&pComProcessInfo3,
                                      &this->_appTrustLevel,
                                      &this->_runtimeBehavior);
                              Permissions = v54;
                              if ( v54 < 0 )
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  0xCBAu,
                                  "onecore\\com\\combase\\catalog\\storecat.cxx",
                                  v54);
                                v55 = pComProcessInfo3;
LABEL_149:
                                WindowsDeleteString((HSTRING)v55);
                                goto LABEL_146;
                              }
                              v56 = pComProcessInfo3;
                              v57 = WindowsGetStringRawBuffer((HSTRING)pComProcessInfo3, 0);
                              v58 = DuplicatePWSTR(v57, &this->_exePath);
                              Permissions = v58;
                              if ( v58 < 0 )
                              {
                                v59 = v58;
                                v60 = 3260;
LABEL_152:
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  v60,
                                  "onecore\\com\\combase\\catalog\\storecat.cxx",
                                  v59);
                                v55 = v56;
                                goto LABEL_149;
                              }
                              Permissions = DuplicateQuotedPWSTR(this->_exePath, &this->_quotedExePath);
                              if ( Permissions < 0 )
                              {
                                v59 = Permissions;
                                v60 = 3273;
                                goto LABEL_152;
                              }
                              if ( this->_runtimeBehavior )
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  0xCD1u,
                                  "onecore\\com\\combase\\catalog\\storecat.cxx",
                                  -2147221164);
                                WindowsDeleteString((HSTRING)v56);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v157);
                                WindowsDeleteString(v44);
                                WindowsDeleteString((HSTRING)v37);
                                WindowsDeleteString((HSTRING)v28);
                                Permissions = -2147221164;
                                goto LABEL_267;
                              }
                              WindowsDeleteString((HSTRING)v56);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v157);
                              goto LABEL_246;
                            }
                            scope = serverHelper._scope;
                            v62 = TrustLevel_PartialTrust;
                            Value = serverHelper._userProperties.RunFullTrust.Value;
                            Present = serverHelper._userProperties.RunFullTrust.Present;
                            if ( serverHelper._scope )
                            {
                              if ( serverHelper._userProperties.RunFullTrust.Present
                                && serverHelper._userProperties.RunFullTrust.Value )
                              {
                                v62 = TrustLevel_FullTrust;
                              }
                              else
                              {
                                v62 = serverHelper._userProperties.TrustLevel.Present
                                    ? serverHelper._userProperties.TrustLevel.Value
                                    : TrustLevel_PartialTrust;
                              }
                            }
                            this->_appTrustLevel = v62;
                            v65 = RuntimeBehavior_Universal;
                            if ( scope )
                            {
                              if ( Present && Value )
                                v65 = RuntimeBehavior_DesktopBridge;
                              else
                                v65 = serverHelper._userProperties.RuntimeBehavior.Present
                                    ? serverHelper._userProperties.RuntimeBehavior.Value
                                    : RuntimeBehavior_Universal;
                            }
                            this->_runtimeBehavior = v65;
                            v66 = BnoIsolation_None;
                            if ( scope )
                              v66 = serverHelper._userProperties.BnoIsolation.Present
                                  ? serverHelper._userProperties.BnoIsolation.Value
                                  : BnoIsolation_None;
                            this->_bnoIsolation = v66;
                            exePath.Unexpanded.hstr_ = 0;
                            v67 = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetExePath(
                                    &serverHelper,
                                    &exePath);
                            serverType = (unsigned int)this->_serverType;
                            Permissions = v67;
                            v69 = gfEnableTracing;
                            if ( (_DWORD)serverType && v67 == -2147024894 )
                            {
                              if ( !gfEnableTracing )
                              {
LABEL_175:
                                serverType = (unsigned int)-(int)serverType;
                                if ( Permissions == ((_DWORD)serverType != 0 ? 0x80070002 : 0)
                                  || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                  && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                                {
                                  v71 = v154;
LABEL_186:
                                  if ( Permissions == -2147024894 )
                                  {
                                    if ( this->_serverType == NormalExe )
                                    {
                                      pComProcessInfo3 = 0;
                                      uResourceId[0] = 0;
                                      if ( LoadStringResource(
                                             0x1466u,
                                             (const wchar_t *)serverType,
                                             (const wchar_t **)&pComProcessInfo3,
                                             uResourceId) < 0 )
                                        RoOriginateError(Permissions, 0);
                                      else
                                        RoOriginateErrorW(
                                          Permissions,
                                          uResourceId[0],
                                          (const wchar_t *)pComProcessInfo3);
                                      goto LABEL_209;
                                    }
                                    goto LABEL_210;
                                  }
                                  if ( Permissions != -2147024882 )
                                  {
                                    pComProcessInfo3 = 0;
                                    uResourceId[0] = 0;
                                    if ( LoadStringResource(
                                           0x1467u,
                                           (const wchar_t *)serverType,
                                           (const wchar_t **)&pComProcessInfo3,
                                           uResourceId) < 0 )
                                      RoOriginateError(Permissions, 0);
                                    else
                                      RoOriginateErrorW(Permissions, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                                  }
LABEL_208:
                                  if ( Permissions < 0 )
                                  {
LABEL_209:
                                    OpaqueString::~OpaqueString(&exePath.Unexpanded);
                                    goto LABEL_140;
                                  }
LABEL_210:
                                  propertyStore.MapView.ptr_ = 0;
                                  CommandLineW = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetCommandLineW(
                                                   &serverHelper,
                                                   (ExpandableString *)&propertyStore);
                                  v75 = (const wchar_t *)(unsigned int)gfEnableTracing;
                                  v76 = 0;
                                  Permissions = CommandLineW;
                                  if ( CommandLineW == -2147024894 )
                                  {
                                    if ( !gfEnableTracing )
                                      goto LABEL_224;
                                    if ( IsWppLevelEnabled(VERBOSE) )
                                    {
LABEL_218:
                                      v77 = (PCWSTR)v76;
                                      goto LABEL_222;
                                    }
                                  }
                                  if ( Permissions >= 0 )
                                  {
                                    if ( !(_DWORD)v75 || !IsWppLevelEnabled(VERBOSE) )
                                      goto LABEL_230;
                                    v77 = WindowsGetStringRawBuffer((HSTRING)propertyStore.MapView.ptr_, 0);
LABEL_222:
                                    line[0] = Permissions;
                                    file[0] = this->_registrationScope;
                                    ComTraceHr(
                                      Permissions,
                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                      "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                      3353,
                                      L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property"
                                       " CommandLine (%ws): %!HRESULT!",
                                      v71,
                                      *(_QWORD *)file,
                                      v77,
                                      *(_QWORD *)line);
                                    v76 = 0;
                                    if ( Permissions < 0 )
                                    {
                                      if ( Permissions == -2147024894 )
                                        goto LABEL_224;
LABEL_226:
                                      if ( Permissions != -2147024882 )
                                      {
                                        pComProcessInfo3 = v76;
                                        uResourceId[0] = (unsigned __int16)v76;
                                        if ( LoadStringResource(
                                               0x1464u,
                                               v75,
                                               (const wchar_t **)&pComProcessInfo3,
                                               uResourceId) < 0 )
                                          RoOriginateError(Permissions, 0);
                                        else
                                          RoOriginateErrorW(
                                            Permissions,
                                            uResourceId[0],
                                            (const wchar_t *)pComProcessInfo3);
                                      }
LABEL_243:
                                      if ( Permissions < 0 )
                                      {
LABEL_244:
                                        OpaqueString::~OpaqueString((OpaqueString *)&propertyStore);
                                        goto LABEL_209;
                                      }
LABEL_245:
                                      OpaqueString::~OpaqueString((OpaqueString *)&propertyStore);
                                      OpaqueString::~OpaqueString(&exePath.Unexpanded);
LABEL_246:
                                      activatableClasses.hstr_ = 0;
                                      v81 = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetActivatableClasses(
                                              &serverHelper,
                                              &activatableClasses);
                                      v83 = 0;
                                      v84 = v81;
                                      Permissions = -2147221165;
                                      if ( v81 != -2147024894 )
                                        goto LABEL_249;
                                      if ( !gfEnableTracing )
                                        goto LABEL_271;
                                      if ( !IsWppLevelEnabled(VERBOSE) )
                                      {
LABEL_249:
                                        if ( v84 >= 0 )
                                        {
                                          if ( gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(VERBOSE) )
                                            goto LABEL_262;
                                        }
                                        else
                                        {
                                          if ( v84 == -2147024894 )
                                            goto LABEL_271;
                                          if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                            && (gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(ERRORS)) )
                                          {
LABEL_259:
                                            if ( v84 == -2147024882 )
                                              goto LABEL_266;
                                            pComProcessInfo3 = v83;
                                            uResourceId[0] = (unsigned __int16)v83;
                                            StringResource = LoadStringResource(
                                                               0x147Eu,
                                                               v82,
                                                               (const wchar_t **)&pComProcessInfo3,
                                                               uResourceId);
                                            v86 = v84;
                                            if ( StringResource >= 0 )
                                            {
                                              RoOriginateErrorW(v84, uResourceId[0], (const wchar_t *)pComProcessInfo3);
LABEL_266:
                                              OpaqueString::~OpaqueString(&activatableClasses);
                                              WindowsDeleteString(v44);
                                              WindowsDeleteString((HSTRING)v37);
                                              WindowsDeleteString((HSTRING)v28);
                                              Permissions = v84;
                                              goto LABEL_267;
                                            }
LABEL_269:
                                            RoOriginateError(v86, 0);
                                            goto LABEL_266;
                                          }
                                        }
                                      }
                                      function[0] = v84;
                                      file[0] = this->_registrationScope;
                                      ComTraceHr(
                                        v84,
                                        "onecore\\com\\combase\\catalog\\storecat.cxx",
                                        "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                        3405,
                                        L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, proper"
                                         "ty ActivatableClasses : %!HRESULT!",
                                        v154,
                                        *(_QWORD *)file,
                                        *(_QWORD *)function);
                                      v83 = 0;
                                      if ( v84 < 0 )
                                      {
                                        if ( v84 != -2147024894 )
                                          goto LABEL_259;
                                        goto LABEL_271;
                                      }
LABEL_262:
                                      *(_DWORD *)uResourceId = (_DWORD)v83;
                                      *(_QWORD *)&exePath.IsExpandable = WindowsGetStringRawBuffer(
                                                                           activatableClasses.hstr_,
                                                                           (UINT32 *)uResourceId);
                                      exePath.Unexpanded.hstr_ = (HSTRING__ *)(unsigned int)(2 * *(_DWORD *)uResourceId
                                                                                           + 2);
                                      v84 = AutoBlob::Initialize(&this->_activatableClasses, (const tagBLOB *)&exePath);
                                      if ( v84 < 0 )
                                        goto LABEL_266;
                                      if ( !IsValidMultiSz(&this->_activatableClasses) )
                                      {
                                        pComProcessInfo3 = v83;
                                        uResourceId[0] = (unsigned __int16)v83;
                                        v84 = -2147221165;
                                        v87 = LoadStringResource(
                                                0x147Eu,
                                                v82,
                                                (const wchar_t **)&pComProcessInfo3,
                                                uResourceId);
                                        v86 = -2147221165;
                                        if ( v87 < 0 )
                                          goto LABEL_269;
LABEL_265:
                                        RoOriginateErrorW(v86, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                                        goto LABEL_266;
                                      }
LABEL_271:
                                      v84 = (int)v83;
                                      v88 = serverHelper._userInvalidProperties[0];
                                      LOBYTE(v82) = serverHelper._userMissingRequiredProperties[0];
                                      if ( serverHelper._scope != (_DWORD)v83 )
                                      {
                                        IdentityType = serverHelper._userProperties.IdentityType;
                                        this->_identityType = serverHelper._userProperties.IdentityType;
                                        if ( ((unsigned __int8)v82 & 0x40) != 0 )
                                        {
                                          v84 = -2147024894;
                                        }
                                        else if ( (v88 & 0x40) != 0 )
                                        {
                                          v84 = -2147024883;
                                        }
LABEL_274:
                                        serverHelper._identityType = IdentityType;
                                        if ( v84 >= 0 )
                                        {
                                          if ( gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(VERBOSE) )
                                            goto LABEL_294;
                                          goto LABEL_289;
                                        }
LABEL_275:
                                        if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                          && (gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(ERRORS)) )
                                        {
                                          goto LABEL_290;
                                        }
LABEL_289:
                                        line[0] = v84;
                                        function[0] = this->_identityType;
                                        file[0] = this->_registrationScope;
                                        ComTraceHr(
                                          v84,
                                          "onecore\\com\\combase\\catalog\\storecat.cxx",
                                          "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                          3437,
                                          L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, prop"
                                           "erty IdentityType (%d): %!HRESULT!",
                                          v154,
                                          *(_QWORD *)file,
                                          *(_QWORD *)function,
                                          *(_QWORD *)line);
                                        v83 = 0;
                                        if ( v84 < 0 )
                                        {
LABEL_290:
                                          v91 = 5224;
                                          goto LABEL_291;
                                        }
                                        v88 = serverHelper._userInvalidProperties[0];
                                        LOBYTE(v82) = serverHelper._userMissingRequiredProperties[0];
LABEL_294:
                                        if ( hostRuntimeId.Present != (_BYTE)v83
                                          && this->_identityType != IdentityType_ActivateAsPackage )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            0xD77u,
                                            "onecore\\com\\combase\\catalog\\storecat.cxx",
                                            -2147221165);
LABEL_297:
                                          OpaqueString::~OpaqueString(&activatableClasses);
                                          goto LABEL_140;
                                        }
                                        if ( (unsigned int)(this->_serverType - 1) <= 1
                                          && this->_identityType != IdentityType_RunAs )
                                        {
                                          pComProcessInfo3 = v83;
                                          uResourceId[0] = (unsigned __int16)v83;
                                          if ( LoadStringResource(
                                                 0x1476u,
                                                 v82,
                                                 (const wchar_t **)&pComProcessInfo3,
                                                 uResourceId) < 0 )
                                            RoOriginateError(-2147221165, 0);
                                          else
                                            RoOriginateErrorW(
                                              -2147221165,
                                              uResourceId[0],
                                              (const wchar_t *)pComProcessInfo3);
                                          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                            || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                          {
                                            ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                              v93,
                                              "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                              3462,
                                              ERRORS,
                                              L"Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, servi"
                                               "ces must be RunAs",
                                              v154,
                                              this->_registrationScope);
                                          }
                                          goto LABEL_297;
                                        }
                                        v94 = this->_registrationScope;
                                        if ( v94 == RegistrationScope_PerUser )
                                        {
                                          v95 = this->_identityType;
                                          if ( v95 == IdentityType_RunAs || (unsigned int)(v95 - 3) <= 2 )
                                          {
                                            pComProcessInfo3 = v83;
                                            uResourceId[0] = (unsigned __int16)v83;
                                            if ( LoadStringResource(
                                                   0x1469u,
                                                   v82,
                                                   (const wchar_t **)&pComProcessInfo3,
                                                   uResourceId) < 0 )
                                              RoOriginateError(-2147221165, 0);
                                            else
                                              RoOriginateErrorW(
                                                -2147221165,
                                                uResourceId[0],
                                                (const wchar_t *)pComProcessInfo3);
                                            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                              || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                            {
                                              ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,enum Windows::Foundation::IdentityType,enum Windows::Foundation::IdentityType>(
                                                v97,
                                                v96,
                                                3485,
                                                v98,
                                                L"Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, Ide"
                                                 "ntityType is %d but scope requires %d",
                                                v154,
                                                this->_registrationScope,
                                                this->_identityType,
                                                IdentityType_ActivateAsActivator);
                                            }
                                            goto LABEL_297;
                                          }
                                        }
                                        else if ( v94 == RegistrationScope_PerMachine
                                               && this->_identityType == IdentityType_ActivateAsPackage )
                                        {
                                          pComProcessInfo3 = v83;
                                          uResourceId[0] = (unsigned __int16)v83;
                                          if ( LoadStringResource(
                                                 0x1479u,
                                                 v82,
                                                 (const wchar_t **)&pComProcessInfo3,
                                                 uResourceId) < 0 )
                                            RoOriginateError(-2147221165, 0);
                                          else
                                            RoOriginateErrorW(
                                              -2147221165,
                                              uResourceId[0],
                                              (const wchar_t *)pComProcessInfo3);
                                          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                            || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                          {
                                            ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,enum Windows::Foundation::IdentityType,enum Windows::Foundation::IdentityType>(
                                              v100,
                                              v99,
                                              3501,
                                              v101,
                                              L"Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, Ident"
                                               "ityType is %d but scope cannot have %d",
                                              v154,
                                              this->_registrationScope,
                                              this->_identityType,
                                              IdentityType_ActivateAsPackage);
                                          }
                                          goto LABEL_297;
                                        }
                                        if ( serverHelper._scope == (_DWORD)v83 )
                                        {
                                          v84 = -2147024894;
                                        }
                                        else
                                        {
                                          this->_instancing = serverHelper._userProperties.Instancing;
                                          if ( ((unsigned __int8)v82 & 0x20) != 0 )
                                          {
                                            v84 = -2147024894;
                                          }
                                          else
                                          {
                                            v84 = (int)v83;
                                            if ( (v88 & 0x20) != 0 )
                                              v84 = -2147024883;
                                          }
                                          if ( v84 != -2147024894 )
                                          {
LABEL_336:
                                            if ( v84 >= 0 )
                                            {
                                              if ( gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(VERBOSE) )
                                              {
                                                v102 = v154;
LABEL_347:
                                                if ( this->_registrationScope == (_DWORD)v83 )
                                                {
                                                  if ( !IsGetEndPointMapperCrossVmPipeNamespacePresent()
                                                    || (unsigned int)WinRTPerMachineSingleInstancing() != 1 )
                                                  {
                                                    pComProcessInfo3 = 0;
                                                    uResourceId[0] = 0;
                                                    if ( LoadStringResource(
                                                           0x147Au,
                                                           v82,
                                                           (const wchar_t **)&pComProcessInfo3,
                                                           uResourceId) < 0 )
                                                      RoOriginateError(-2147221165, 0);
                                                    else
                                                      RoOriginateErrorW(
                                                        -2147221165,
                                                        uResourceId[0],
                                                        (const wchar_t *)pComProcessInfo3);
                                                    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                      || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                                    {
                                                      ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,enum Windows::Foundation::InstancingType>(
                                                        v104,
                                                        v103,
                                                        v105,
                                                        v106,
                                                        format,
                                                        v102,
                                                        this->_registrationScope,
                                                        this->_instancing);
                                                    }
                                                    goto LABEL_297;
                                                  }
                                                  v83 = 0;
                                                }
LABEL_358:
                                                if ( (int)(v84 + 0x80000000) >= 0 && v84 != -2147024894 )
                                                {
LABEL_360:
                                                  v91 = 5227;
LABEL_291:
                                                  uResourceId[0] = (unsigned __int16)v83;
                                                  pComProcessInfo3 = v83;
                                                  v92 = LoadStringResource(
                                                          v91,
                                                          v82,
                                                          (const wchar_t **)&pComProcessInfo3,
                                                          uResourceId);
                                                  v86 = v84;
                                                  if ( v92 < 0 )
                                                  {
                                                    RoOriginateError(v84, 0);
                                                    goto LABEL_266;
                                                  }
                                                  goto LABEL_265;
                                                }
LABEL_361:
                                                v107 = v83;
                                                pComProcessInfo3 = v83;
                                                if ( serverHelper._scope == (_DWORD)v83
                                                  && (char)serverHelper._machineMissingRequiredProperties[0] >= 0 )
                                                {
                                                  if ( (char)serverHelper._machineInvalidProperties[0] < 0 )
                                                  {
                                                    v84 = -2147024883;
LABEL_368:
                                                    v108 = (unsigned int)this->_identityType;
                                                    v109 = -2147024894;
                                                    if ( (_DWORD)v108 != 1 && v84 == -2147024894 )
                                                    {
                                                      if ( gfEnableTracing == (_DWORD)v83 )
                                                      {
LABEL_373:
                                                        v108 = (unsigned int)(1 - v108);
                                                        if ( v84 == ((_DWORD)v108 != 0 ? v109 : 0)
                                                          || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                          && (gfEnableTracing == (_DWORD)v83
                                                           || !IsWppLevelEnabled(ERRORS)) )
                                                        {
                                                          goto LABEL_383;
                                                        }
                                                        goto LABEL_377;
                                                      }
                                                      if ( IsWppLevelEnabled(VERBOSE) )
                                                      {
LABEL_377:
                                                        v110 = (PCWSTR)v83;
                                                        goto LABEL_381;
                                                      }
                                                    }
                                                    if ( v84 >= 0 )
                                                    {
                                                      if ( gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(VERBOSE) )
                                                        goto LABEL_391;
                                                      v110 = WindowsGetStringRawBuffer((HSTRING)v107, 0);
LABEL_381:
                                                      line[0] = v84;
                                                      file[0] = this->_registrationScope;
                                                      ComTraceHr(
                                                        v84,
                                                        "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                        "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                        3552,
                                                        L"Read Server entry %ws in scope %!Windows::Foundation::Registrati"
                                                         "onScope!, property Identity (%ws): %!HRESULT!",
                                                        v154,
                                                        *(_QWORD *)file,
                                                        v110,
                                                        *(_QWORD *)line);
                                                      v83 = 0;
                                                      if ( v84 < 0 )
                                                      {
                                                        v109 = -2147024894;
LABEL_383:
                                                        if ( v84 == v109 )
                                                        {
                                                          if ( this->_identityType == IdentityType_RunAs )
                                                          {
                                                            pComProcessInfo3 = v83;
                                                            uResourceId[0] = (unsigned __int16)v83;
                                                            if ( LoadStringResource(
                                                                   0x146Du,
                                                                   (const wchar_t *)v108,
                                                                   (const wchar_t **)&pComProcessInfo3,
                                                                   uResourceId) < 0 )
                                                              RoOriginateError(v84, 0);
                                                            else
                                                              RoOriginateErrorW(
                                                                v84,
                                                                uResourceId[0],
                                                                (const wchar_t *)pComProcessInfo3);
                                                            goto LABEL_401;
                                                          }
LABEL_403:
                                                          v113 = v83;
                                                          pComProcessInfo3 = v83;
                                                          if ( serverHelper._scope != (_DWORD)v83
                                                            || (*(_WORD *)serverHelper._machineMissingRequiredProperties
                                                              & 0x100) != 0 )
                                                          {
                                                            goto LABEL_409;
                                                          }
                                                          if ( (*(_WORD *)serverHelper._machineInvalidProperties & 0x100) != 0 )
                                                          {
                                                            v114 = -2147024883;
                                                            goto LABEL_410;
                                                          }
                                                          if ( serverHelper._machineProperties.ServiceName.Present == (_BYTE)v83 )
                                                          {
LABEL_409:
                                                            v114 = v109;
                                                            fIsAppContainer = v109;
                                                          }
                                                          else
                                                          {
                                                            fIsAppContainer = (int)v83;
                                                            OpaqueString::operator=(
                                                              (OpaqueString *)&pComProcessInfo3,
                                                              &serverHelper._machineProperties.ServiceName.Value);
                                                            v114 = fIsAppContainer;
                                                            v83 = 0;
                                                            v113 = pComProcessInfo3;
                                                          }
LABEL_410:
                                                          v115 = (unsigned int)this->_serverType;
                                                          if ( (_DWORD)v115 || v114 != -2147024894 )
                                                            goto LABEL_414;
                                                          if ( gfEnableTracing == (_DWORD)v83 )
                                                          {
LABEL_424:
                                                            if ( v114 == -2147024894 )
                                                            {
                                                              if ( (unsigned int)(this->_serverType - 1) <= 1 )
                                                              {
                                                                pComProcessInfo3 = v83;
                                                                uResourceId[0] = (unsigned __int16)v83;
                                                                if ( LoadStringResource(
                                                                       0x1470u,
                                                                       (const wchar_t *)v115,
                                                                       (const wchar_t **)&pComProcessInfo3,
                                                                       uResourceId) < 0 )
                                                                  RoOriginateError(fIsAppContainer, 0);
                                                                else
                                                                  RoOriginateErrorW(
                                                                    fIsAppContainer,
                                                                    uResourceId[0],
                                                                    (const wchar_t *)pComProcessInfo3);
                                                                goto LABEL_451;
                                                              }
                                                              goto LABEL_452;
                                                            }
                                                            pComProcessInfo3 = v83;
                                                            uResourceId[0] = (unsigned __int16)v83;
                                                            if ( LoadStringResource(
                                                                   0x1471u,
                                                                   (const wchar_t *)v115,
                                                                   (const wchar_t **)&pComProcessInfo3,
                                                                   uResourceId) < 0 )
                                                              RoOriginateError(fIsAppContainer, 0);
                                                            else
                                                              RoOriginateErrorW(
                                                                fIsAppContainer,
                                                                uResourceId[0],
                                                                (const wchar_t *)pComProcessInfo3);
                                                            v117 = fIsAppContainer;
LABEL_450:
                                                            v83 = 0;
                                                            if ( v117 < 0 )
                                                              goto LABEL_451;
LABEL_452:
                                                            if ( this->_hasAppId == (_BYTE)v83 )
                                                            {
LABEL_469:
                                                              propertyStore.MapView.ptr_ = (Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *)v83;
                                                              Permissions = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetPermissions(
                                                                              &serverHelper,
                                                                              (SecurityDescriptor **)&propertyStore);
                                                              if ( Permissions != -2147024894 )
                                                                goto LABEL_472;
                                                              if ( gfEnableTracing == (_DWORD)v127 )
                                                                goto LABEL_485;
                                                              if ( !IsWppLevelEnabled(VERBOSE) )
                                                              {
LABEL_472:
                                                                if ( Permissions >= 0 )
                                                                {
                                                                  if ( gfEnableTracing == (_DWORD)v127
                                                                    || !IsWppLevelEnabled(VERBOSE) )
                                                                  {
                                                                    goto LABEL_484;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  if ( Permissions == -2147024894 )
                                                                    goto LABEL_485;
                                                                  if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                                    && (gfEnableTracing == (_DWORD)v127
                                                                     || !IsWppLevelEnabled(ERRORS)) )
                                                                  {
LABEL_482:
                                                                    if ( Permissions != -2147024882 )
                                                                    {
                                                                      propertyStore.MapView.ptr_ = v127;
                                                                      v125 = 5235;
                                                                      uResourceId[0] = (unsigned __int16)v127;
LABEL_463:
                                                                      if ( LoadStringResource(
                                                                             v125,
                                                                             v122,
                                                                             (const wchar_t **)&propertyStore,
                                                                             uResourceId) < 0 )
                                                                        RoOriginateError(Permissions, 0);
                                                                      else
                                                                        RoOriginateErrorW(
                                                                          Permissions,
                                                                          uResourceId[0],
                                                                          (const wchar_t *)propertyStore.MapView.ptr_);
                                                                    }
LABEL_466:
                                                                    WindowsDeleteString((HSTRING)v113);
                                                                    WindowsDeleteString((HSTRING)v107);
                                                                    goto LABEL_297;
                                                                  }
                                                                }
                                                              }
                                                              function[0] = Permissions;
                                                              file[0] = this->_registrationScope;
                                                              ComTraceHr(
                                                                Permissions,
                                                                "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                3719,
                                                                L"Read Server entry %ws in scope %!Windows::Foundation::Re"
                                                                 "gistrationScope!, property Permissions: %!HRESULT!",
                                                                v154,
                                                                *(_QWORD *)file,
                                                                *(_QWORD *)function);
                                                              v127 = 0;
                                                              if ( Permissions < 0 )
                                                              {
                                                                if ( Permissions != -2147024894 )
                                                                  goto LABEL_482;
LABEL_485:
                                                                if ( g_bInSCM == (_DWORD)v127 )
                                                                {
                                                                  propertyStore.MapView.ptr_ = v127;
                                                                  Attributes = CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::GetAttributes(
                                                                                 &serverHelper,
                                                                                 &propertyStore);
                                                                  Permissions = Attributes;
                                                                  if ( Attributes < 0 )
                                                                  {
                                                                    if ( Attributes != -2147024894 )
                                                                    {
LABEL_489:
                                                                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&propertyStore);
                                                                      goto LABEL_466;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    Permissions = EntryPropertyStore::ForceToMemory(&propertyStore);
                                                                    if ( Permissions < 0 )
                                                                      goto LABEL_489;
                                                                    Permissions = propertyStore.MapView.ptr_->QueryInterface(
                                                                                    propertyStore.MapView.ptr_,
                                                                                    &GUID_00000000_0000_0000_c000_000000000046,
                                                                                    (void **)&this->_pAttributes);
                                                                    if ( Permissions < 0 )
                                                                      goto LABEL_489;
                                                                  }
                                                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&propertyStore);
                                                                  LODWORD(v127) = 0;
                                                                }
                                                                ExplicitPsmActivationType = serverHelper._machineProperties.ExplicitPsmActivationType;
                                                                if ( serverHelper._scope != (_DWORD)v127 )
                                                                  ExplicitPsmActivationType = serverHelper._userProperties.ExplicitPsmActivationType;
                                                                v131 = *(_QWORD *)v160;
                                                                this->_explicitPsmActivationType = ExplicitPsmActivationType;
                                                                if ( v131 )
                                                                {
                                                                  v132 = (*(__int64 (__fastcall **)(__int64, __int64, RegistrationRefreshPolicy *))(*(_QWORD *)lLastDebugInformationWriteTime + 176LL))(
                                                                           lLastDebugInformationWriteTime,
                                                                           v131,
                                                                           &this->_registrationServerRefreshPolicy);
                                                                  Permissions = v132;
                                                                  if ( v132 < 0 )
                                                                  {
                                                                    v133 = 3769;
LABEL_497:
                                                                    wil::details::in1diag3::Return_Hr(
                                                                      retaddr,
                                                                      v133,
                                                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                      v132);
                                                                    goto LABEL_466;
                                                                  }
                                                                  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
                                                                    ComTraceMessageT<unsigned int>(
                                                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                      "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                      3770,
                                                                      v134,
                                                                      L"entry.GetRefreshPolicy result is %d",
                                                                      this->_registrationServerRefreshPolicy);
                                                                  v131 = *(_QWORD *)v160;
                                                                }
                                                                if ( this->_registrationScope == RegistrationScope_PerUser )
                                                                {
                                                                  v132 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)lLastDebugInformationWriteTime + 216LL))(
                                                                           lLastDebugInformationWriteTime,
                                                                           v131,
                                                                           &this->_lLastServerWriteTime);
                                                                  Permissions = v132;
                                                                  if ( v132 < 0 )
                                                                  {
                                                                    v133 = 3776;
                                                                    goto LABEL_497;
                                                                  }
                                                                  if ( !gfEnableTracing )
                                                                  {
LABEL_532:
                                                                    WindowsDeleteString((HSTRING)v113);
                                                                    WindowsDeleteString((HSTRING)v107);
                                                                    OpaqueString::~OpaqueString(&activatableClasses);
                                                                    WindowsDeleteString(v44);
                                                                    WindowsDeleteString((HSTRING)v37);
                                                                    WindowsDeleteString((HSTRING)v28);
                                                                    Permissions = 0;
                                                                    goto LABEL_267;
                                                                  }
                                                                  if ( !IsWppLevelEnabled(VERBOSE) )
                                                                  {
LABEL_509:
                                                                    if ( gfEnableTracing != v135
                                                                      && IsWppLevelEnabled(INFO) )
                                                                    {
                                                                      lLastDebugInformationWriteTime = this->_lLastDebugInformationWriteTime;
                                                                      fIsAppContainer = this->_registrationDebugInformationRefreshPolicy;
                                                                      exePath.Unexpanded.hstr_ = (HSTRING__ *)this->_lLastServerWriteTime;
                                                                      *(_DWORD *)uResourceId = this->_registrationServerRefreshPolicy;
                                                                      if ( this->_pAttributes == v137 )
                                                                      {
                                                                        v138 = "do not exist";
                                                                        if ( g_bInSCM != (_DWORD)v137 )
                                                                          v138 = "ignored";
                                                                      }
                                                                      else
                                                                      {
                                                                        v138 = "exist";
                                                                      }
                                                                      if ( this->_registrationScope == (_DWORD)v137 )
                                                                      {
                                                                        CGuidStr::CGuidStr(&v166, &this->_appId);
                                                                        v140 = v139;
                                                                        v137 = 0;
                                                                      }
                                                                      else
                                                                      {
                                                                        v140 = &pszValueToSet;
                                                                      }
                                                                      v141 = this->_registrationScope;
                                                                      if ( v141 )
                                                                        identity = (wchar_t *)v137;
                                                                      else
                                                                        identity = this->_identity;
                                                                      v160[0] = this->_instancing;
                                                                      LODWORD(userToken) = this->_identityType;
                                                                      if ( v141 == RegistrationScope_PerUser )
                                                                        v143 = Windows::Internal::StringReference::GetRawBuffer(
                                                                                 (Windows::Internal::StringReference *)&this->_executionPackageName,
                                                                                 (unsigned int *)v137);
                                                                      else
                                                                        v143 = (const wchar_t *)v137;
                                                                      if ( this->_registrationScope == RegistrationScope_PerUser )
                                                                        v144 = Windows::Internal::StringReference::GetRawBuffer(
                                                                                 (Windows::Internal::StringReference *)&this->_appUserModelID,
                                                                                 (unsigned int *)v137);
                                                                      else
                                                                        v144 = (const wchar_t *)v137;
                                                                      if ( this->_registrationScope == RegistrationScope_PerUser )
                                                                        v137 = (IUnknown *)Windows::Internal::StringReference::GetRawBuffer(
                                                                                             (Windows::Internal::StringReference *)&this->_deployingPackageName,
                                                                                             (unsigned int *)v137);
                                                                      v145 = (const char *)(unsigned int)this->_registrationScope;
                                                                      serviceName = 0;
                                                                      if ( !(_DWORD)v145 )
                                                                        serviceName = this->_serviceName;
                                                                      ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,unsigned int,unsigned short *,unsigned short *,unsigned short *,unsigned short *,unsigned short const *,unsigned short const *,unsigned short const *,enum Windows::Foundation::IdentityType,enum Windows::Foundation::InstancingType,unsigned short *,unsigned short const *,char const *,int,__int64,int,__int64>(
                                                                        v145,
                                                                        (const char *)v137,
                                                                        (int)v144,
                                                                        (TraceLevel)v143,
                                                                        format,
                                                                        v154,
                                                                        (Windows::Foundation::RegistrationScope)v145,
                                                                        this->_serverType,
                                                                        this->_exePath,
                                                                        this->_quotedExePath,
                                                                        this->_commandLine,
                                                                        serviceName,
                                                                        (const wchar_t *)v137,
                                                                        v144,
                                                                        v143,
                                                                        (Windows::Foundation::IdentityType)userToken,
                                                                        v160[0],
                                                                        identity,
                                                                        v140,
                                                                        v138,
                                                                        *(int *)uResourceId,
                                                                        (__int64)exePath.Unexpanded.hstr_,
                                                                        fIsAppContainer,
                                                                        lLastDebugInformationWriteTime);
                                                                      v44 = hostRuntimeId.Value.hstr_;
                                                                    }
                                                                    goto LABEL_532;
                                                                  }
                                                                  ComTraceMessageT<void *>(
                                                                    "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                    "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                    3777,
                                                                    v136,
                                                                    L"entry.GetLastWriteTime result is %!TIME!",
                                                                    (wchar_t *)this->_lLastServerWriteTime);
                                                                }
                                                                v135 = 0;
                                                                goto LABEL_509;
                                                              }
LABEL_484:
                                                              exePath.Unexpanded.hstr_ = (HSTRING__ *)LOWORD(propertyStore.MapView.ptr_[1].__vftable);
                                                              *(_QWORD *)&exePath.IsExpandable = propertyStore.MapView.ptr_->__vftable;
                                                              v128 = AutoBlob::Initialize(
                                                                       &this->_permissions,
                                                                       (const tagBLOB *)&exePath);
                                                              v127 = 0;
                                                              Permissions = v128;
                                                              if ( v128 < 0 )
                                                                goto LABEL_466;
                                                              goto LABEL_485;
                                                            }
                                                            format = (wchar_t *)&GUID_00000000_0000_0000_c000_000000000046;
                                                            v121 = ((__int64 (__fastcall *)(IComCatalogSCM *, __int64, IUserToken *, _GUID *))dwMgotFlagsFromAppID->GetProcessInfo)(
                                                                     dwMgotFlagsFromAppID,
                                                                     134414336,
                                                                     userToken,
                                                                     &this->_appId);
                                                            v122 = 0;
                                                            fIsAppContainer = v121;
                                                            v123 = v121;
                                                            if ( v121 >= 0 )
                                                            {
                                                              if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
                                                              {
LABEL_468:
                                                                pRegProcessInfo = this->_pRegProcessInfo;
                                                                dwRotFlagsFromAppID = (unsigned int)v122;
                                                                LODWORD(dwMgotFlagsFromAppID) = (_DWORD)v122;
                                                                pComProcessInfo3 = (IComProcessInfo3 *)v122;
                                                                pRegProcessInfo->QueryInterface(
                                                                  pRegProcessInfo,
                                                                  &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
                                                                  (void **)&pComProcessInfo3);
                                                                pComProcessInfo3->GetROTFlags(
                                                                  pComProcessInfo3,
                                                                  &dwRotFlagsFromAppID);
                                                                pComProcessInfo3->GetROTFlags(
                                                                  pComProcessInfo3,
                                                                  (unsigned int *)&dwMgotFlagsFromAppID);
                                                                pComProcessInfo3->Release(pComProcessInfo3);
                                                                v83 = 0;
                                                                this->_dwRotFlags = dwRotFlagsFromAppID;
                                                                this->_dwMgotFlags = (unsigned int)dwMgotFlagsFromAppID;
                                                                goto LABEL_469;
                                                              }
                                                            }
                                                            else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                                   && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                                                            {
LABEL_461:
                                                              if ( v123 == -2147221164 )
                                                              {
                                                                propertyStore.MapView.ptr_ = (Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *)v122;
                                                                v125 = 5234;
                                                                uResourceId[0] = (unsigned __int16)v122;
                                                                goto LABEL_463;
                                                              }
                                                              if ( v123 >= 0 )
                                                                goto LABEL_468;
LABEL_451:
                                                              WindowsDeleteString((HSTRING)v113);
                                                              WindowsDeleteString((HSTRING)v107);
                                                              OpaqueString::~OpaqueString(&activatableClasses);
                                                              WindowsDeleteString(v44);
                                                              WindowsDeleteString((HSTRING)v37);
                                                              WindowsDeleteString((HSTRING)v28);
                                                              Permissions = fIsAppContainer;
                                                              goto LABEL_267;
                                                            }
                                                            CGuidStr::CGuidStr(&v166, &this->_appId);
                                                            file[1] = SHIDWORD(v154);
                                                            ComTraceHr(
                                                              v124,
                                                              "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                              "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                              3677,
                                                              L"GetProcessInfo(%ws) for Server entry %ws in scope %!Window"
                                                               "s::Foundation::RegistrationScope!: %!HRESULT!");
                                                            v123 = fIsAppContainer;
                                                            v122 = 0;
                                                            goto LABEL_461;
                                                          }
                                                          if ( !IsWppLevelEnabled(VERBOSE) )
                                                          {
LABEL_414:
                                                            if ( v114 >= 0 )
                                                            {
                                                              if ( gfEnableTracing == (_DWORD)v83
                                                                || !IsWppLevelEnabled(VERBOSE) )
                                                              {
                                                                goto LABEL_433;
                                                              }
                                                              v116 = WindowsGetStringRawBuffer((HSTRING)v113, 0);
                                                              v114 = fIsAppContainer;
LABEL_423:
                                                              line[0] = v114;
                                                              file[0] = this->_registrationScope;
                                                              ComTraceHr(
                                                                v114,
                                                                "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                3604,
                                                                L"Read Server entry %ws in scope %!Windows::Foundation::Re"
                                                                 "gistrationScope!, property ServiceName (%ws): %!HRESULT!",
                                                                v154,
                                                                *(_QWORD *)file,
                                                                v116,
                                                                *(_QWORD *)line);
                                                              v114 = fIsAppContainer;
                                                              v83 = 0;
                                                              if ( fIsAppContainer < 0 )
                                                                goto LABEL_424;
LABEL_433:
                                                              if ( this->_registrationScope == RegistrationScope_PerUser )
                                                              {
                                                                fIsAppContainer = -2147221165;
                                                                pComProcessInfo3 = v83;
                                                                uResourceId[0] = (unsigned __int16)v83;
                                                                if ( LoadStringResource(
                                                                       0x146Au,
                                                                       (const wchar_t *)v115,
                                                                       (const wchar_t **)&pComProcessInfo3,
                                                                       uResourceId) < 0 )
                                                                  RoOriginateError(-2147221165, 0);
                                                                else
                                                                  RoOriginateErrorW(
                                                                    -2147221165,
                                                                    uResourceId[0],
                                                                    (const wchar_t *)pComProcessInfo3);
                                                                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                                  || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                                                {
                                                                  v118 = (wchar_t *)WindowsGetStringRawBuffer(
                                                                                      (HSTRING)v113,
                                                                                      0);
                                                                  ComTraceMessageT<unsigned short const *,unsigned short *>(
                                                                    "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                                    "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                    3618,
                                                                    ERRORS,
                                                                    L"Server entry %ws is in per-user store, but has Servi"
                                                                     "ceName property (%ws)",
                                                                    v154,
                                                                    v118);
                                                                }
                                                                goto LABEL_451;
                                                              }
                                                              if ( (unsigned int)(this->_serverType - 1) > 1 )
                                                              {
                                                                fIsAppContainer = -2147221165;
                                                                pComProcessInfo3 = v83;
                                                                uResourceId[0] = (unsigned __int16)v83;
                                                                if ( LoadStringResource(
                                                                       0x146Fu,
                                                                       (const wchar_t *)v115,
                                                                       (const wchar_t **)&pComProcessInfo3,
                                                                       uResourceId) < 0 )
                                                                  RoOriginateError(-2147221165, 0);
                                                                else
                                                                  RoOriginateErrorW(
                                                                    -2147221165,
                                                                    uResourceId[0],
                                                                    (const wchar_t *)pComProcessInfo3);
                                                                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                                  || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                                                {
                                                                  ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                                                    v119,
                                                                    "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                                    3631,
                                                                    ERRORS,
                                                                    L"Server entry %ws in scope %!Windows::Foundation::Reg"
                                                                     "istrationScope!, NormalExe but has ServiceName",
                                                                    v154,
                                                                    this->_registrationScope);
                                                                }
                                                                goto LABEL_451;
                                                              }
                                                              v120 = WindowsGetStringRawBuffer((HSTRING)v113, 0);
                                                              v117 = DuplicatePWSTR(v120, &this->_serviceName);
                                                              fIsAppContainer = v117;
                                                              goto LABEL_450;
                                                            }
                                                            v115 = (unsigned int)-(int)v115;
                                                            if ( v114 == ((_DWORD)v115 == 0 ? 0x80070002 : 0)
                                                              || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                              && (gfEnableTracing == (_DWORD)v83
                                                               || !IsWppLevelEnabled(ERRORS)) )
                                                            {
                                                              goto LABEL_424;
                                                            }
                                                          }
                                                          v116 = (PCWSTR)v83;
                                                          goto LABEL_423;
                                                        }
                                                        pComProcessInfo3 = v83;
                                                        uResourceId[0] = (unsigned __int16)v83;
                                                        if ( LoadStringResource(
                                                               0x146Eu,
                                                               (const wchar_t *)v108,
                                                               (const wchar_t **)&pComProcessInfo3,
                                                               uResourceId) < 0 )
                                                          RoOriginateError(v84, 0);
                                                        else
                                                          RoOriginateErrorW(
                                                            v84,
                                                            uResourceId[0],
                                                            (const wchar_t *)pComProcessInfo3);
LABEL_400:
                                                        v83 = 0;
                                                        if ( v84 < 0 )
                                                        {
LABEL_401:
                                                          WindowsDeleteString((HSTRING)v107);
                                                          goto LABEL_266;
                                                        }
                                                        v109 = -2147024894;
                                                        goto LABEL_403;
                                                      }
LABEL_391:
                                                      if ( this->_identityType != IdentityType_RunAs )
                                                      {
                                                        pComProcessInfo3 = v83;
                                                        uResourceId[0] = (unsigned __int16)v83;
                                                        v84 = -2147221165;
                                                        if ( LoadStringResource(
                                                               0x146Cu,
                                                               (const wchar_t *)v108,
                                                               (const wchar_t **)&pComProcessInfo3,
                                                               uResourceId) < 0 )
                                                          RoOriginateError(-2147221165, 0);
                                                        else
                                                          RoOriginateErrorW(
                                                            -2147221165,
                                                            uResourceId[0],
                                                            (const wchar_t *)pComProcessInfo3);
                                                        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                          || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                                        {
                                                          ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                                            v111,
                                                            "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                                            3566,
                                                            ERRORS,
                                                            L"Server entry %ws in scope %!Windows::Foundation::Registratio"
                                                             "nScope!, ActivateAsActivator but has Identity",
                                                            v154,
                                                            this->_registrationScope);
                                                        }
                                                        goto LABEL_401;
                                                      }
                                                      v112 = WindowsGetStringRawBuffer((HSTRING)v107, 0);
                                                      v84 = DuplicatePWSTR(v112, &this->_identity);
                                                      goto LABEL_400;
                                                    }
                                                    goto LABEL_373;
                                                  }
                                                  if ( serverHelper._machineProperties.Identity.Present != (_BYTE)v83 )
                                                  {
                                                    v84 = (int)v83;
                                                    OpaqueString::operator=(
                                                      (OpaqueString *)&pComProcessInfo3,
                                                      &serverHelper._machineProperties.Identity.Value);
                                                    v107 = pComProcessInfo3;
                                                    v83 = 0;
                                                    goto LABEL_368;
                                                  }
                                                }
                                                v84 = -2147024894;
                                                goto LABEL_368;
                                              }
                                            }
                                            else
                                            {
                                              if ( v84 == -2147024894 )
                                                goto LABEL_358;
                                              if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                                && (gfEnableTracing == (_DWORD)v83 || !IsWppLevelEnabled(ERRORS)) )
                                              {
                                                goto LABEL_360;
                                              }
                                            }
LABEL_344:
                                            v102 = v154;
                                            line[0] = v84;
                                            function[0] = (Windows::Foundation::IdentityType)this->_instancing;
                                            file[0] = this->_registrationScope;
                                            ComTraceHr(
                                              v84,
                                              "onecore\\com\\combase\\catalog\\storecat.cxx",
                                              "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                              3516,
                                              L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, "
                                               "property Instancing %d: %!HRESULT!",
                                              v154,
                                              *(_QWORD *)file,
                                              *(_QWORD *)function,
                                              *(_QWORD *)line);
                                            v83 = 0;
                                            if ( v84 < 0 )
                                              goto LABEL_358;
                                            goto LABEL_347;
                                          }
                                        }
                                        if ( gfEnableTracing == (_DWORD)v83 )
                                          goto LABEL_361;
                                        if ( IsWppLevelEnabled(VERBOSE) )
                                          goto LABEL_344;
                                        goto LABEL_336;
                                      }
                                      v90 = (serverHelper._machineMissingRequiredProperties[0] & 4) == 0;
                                      IdentityType = serverHelper._machineProperties.IdentityType;
                                      this->_identityType = serverHelper._machineProperties.IdentityType;
                                      if ( v90 )
                                      {
                                        if ( (serverHelper._machineInvalidProperties[0] & 4) == 0 )
                                          goto LABEL_274;
                                        v84 = -2147024883;
                                      }
                                      else
                                      {
                                        v84 = -2147024894;
                                      }
                                      serverHelper._identityType = IdentityType;
                                      goto LABEL_275;
                                    }
LABEL_230:
                                    if ( this->_serverType != (_DWORD)v76 )
                                    {
                                      pComProcessInfo3 = v76;
                                      uResourceId[0] = (unsigned __int16)v76;
                                      Permissions = -2147221165;
                                      if ( LoadStringResource(
                                             0x1463u,
                                             v75,
                                             (const wchar_t **)&pComProcessInfo3,
                                             uResourceId) < 0 )
                                        RoOriginateError(-2147221165, 0);
                                      else
                                        RoOriginateErrorW(
                                          -2147221165,
                                          uResourceId[0],
                                          (const wchar_t *)pComProcessInfo3);
                                      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                        || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                      {
                                        ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                          v79,
                                          "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                          3366,
                                          ERRORS,
                                          L"Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, only Norm"
                                           "alExe can have CommandLine",
                                          v71,
                                          this->_registrationScope);
                                      }
                                      goto LABEL_244;
                                    }
                                    if ( serverHelper._scope == (_DWORD)v76 )
                                      v80 = (char)v76;
                                    else
                                      v80 = serverHelper._userProperties.IsPackageRelativePath.Present
                                         && serverHelper._userProperties.IsPackageRelativePath.Value;
                                    AbsoluteExpandedPathAsPWSTR = GetAbsoluteExpandedPathAsPWSTR(
                                                                    (const ExpandableString *)&propertyStore,
                                                                    v80,
                                                                    packageMoniker,
                                                                    userToken,
                                                                    &this->_commandLine);
LABEL_242:
                                    Permissions = AbsoluteExpandedPathAsPWSTR;
                                    goto LABEL_243;
                                  }
                                  if ( Permissions != -2147024894 )
                                  {
                                    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                      && (gfEnableTracing == (_DWORD)v76 || !IsWppLevelEnabled(ERRORS)) )
                                    {
                                      goto LABEL_226;
                                    }
                                    goto LABEL_218;
                                  }
LABEL_224:
                                  if ( this->_serverType != (_DWORD)v76 )
                                    goto LABEL_245;
                                  AbsoluteExpandedPathAsPWSTR = DuplicateQuotedPWSTR(
                                                                  this->_exePath,
                                                                  &this->_quotedExePath);
                                  goto LABEL_242;
                                }
                                goto LABEL_179;
                              }
                              if ( IsWppLevelEnabled(VERBOSE) )
                              {
LABEL_179:
                                v70 = 0;
                                goto LABEL_183;
                              }
                            }
                            if ( Permissions >= 0 )
                            {
                              if ( !v69 || !IsWppLevelEnabled(VERBOSE) )
                              {
                                v71 = v154;
                                goto LABEL_196;
                              }
                              v70 = WindowsGetStringRawBuffer(exePath.Unexpanded.hstr_, 0);
LABEL_183:
                              v71 = v154;
                              line[0] = Permissions;
                              file[0] = this->_registrationScope;
                              ComTraceHr(
                                Permissions,
                                "onecore\\com\\combase\\catalog\\storecat.cxx",
                                "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                3301,
                                L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ExePa"
                                 "th (%ws): %!HRESULT!",
                                v154,
                                *(_QWORD *)file,
                                v70,
                                *(_QWORD *)line);
                              if ( Permissions < 0 )
                                goto LABEL_186;
LABEL_196:
                              if ( this->_serverType >= (unsigned int)SvchostService )
                              {
                                pComProcessInfo3 = 0;
                                uResourceId[0] = 0;
                                Permissions = -2147221165;
                                if ( LoadStringResource(
                                       0x1465u,
                                       (const wchar_t *)serverType,
                                       (const wchar_t **)&pComProcessInfo3,
                                       uResourceId) < 0 )
                                  RoOriginateError(-2147221165, 0);
                                else
                                  RoOriginateErrorW(-2147221165, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                  || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                {
                                  ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                    v72,
                                    "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                                    3315,
                                    ERRORS,
                                    L"Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, only NormalExe "
                                     "and ExeService can have ExePath",
                                    v71,
                                    this->_registrationScope);
                                }
                                goto LABEL_209;
                              }
                              if ( serverHelper._scope )
                                v73 = serverHelper._userProperties.IsPackageRelativePath.Present
                                   && serverHelper._userProperties.IsPackageRelativePath.Value;
                              else
                                v73 = 0;
                              Permissions = GetAbsoluteExpandedPathAsPWSTR(
                                              &exePath,
                                              v73,
                                              packageMoniker,
                                              userToken,
                                              &this->_exePath);
                              goto LABEL_208;
                            }
                            goto LABEL_175;
                          }
                          goto LABEL_114;
                        }
                        if ( IsWppLevelEnabled(VERBOSE) )
                        {
LABEL_114:
                          v39 = 0;
                          goto LABEL_118;
                        }
                      }
                      if ( Permissions >= 0 )
                      {
                        if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
                          goto LABEL_123;
                        v39 = WindowsGetStringRawBuffer((HSTRING)v37, 0);
LABEL_118:
                        line[0] = Permissions;
                        file[0] = this->_registrationScope;
                        ComTraceHr(
                          Permissions,
                          "onecore\\com\\combase\\catalog\\storecat.cxx",
                          "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                          3205,
                          L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property appUserMode"
                           "lID (%ws): %!HRESULT!",
                          serverName,
                          *(_QWORD *)file,
                          v39,
                          *(_QWORD *)line);
                        if ( Permissions < 0 )
                          goto LABEL_119;
LABEL_123:
                        if ( this->_registrationScope == RegistrationScope_PerMachine )
                        {
                          pComProcessInfo3 = 0;
                          uResourceId[0] = 0;
                          Permissions = -2147221165;
                          if ( LoadStringResource(
                                 0x147Bu,
                                 (const wchar_t *)registrationScope,
                                 (const wchar_t **)&pComProcessInfo3,
                                 uResourceId) < 0 )
                            RoOriginateError(-2147221165, 0);
                          else
                            RoOriginateErrorW(-2147221165, uResourceId[0], (const wchar_t *)pComProcessInfo3);
                          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                            || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                          {
                            v40 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v37, 0);
                            ComTraceMessageT<unsigned short const *,unsigned short *>(
                              "onecore\\com\\combase\\catalog\\storecat.cxx",
                              "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                              3219,
                              ERRORS,
                              L"Server entry %ws is in per-machine store, but has appUserModelID property (%ws)",
                              serverName,
                              v40);
                          }
                          goto LABEL_131;
                        }
                        v41 = (HSTRING__ *)v37;
                        v37 = 0;
                        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                          &this->_appUserModelID,
                          v41);
                        goto LABEL_133;
                      }
                      goto LABEL_110;
                    }
LABEL_94:
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                      &this->_executionPackageName,
                      0);
                    Permissions = WindowsDuplicateString(
                                    this->_deployingPackageName.m_ptr,
                                    &this->_executionPackageName.m_ptr);
                    goto LABEL_95;
                  }
                  if ( v19 == -2147024894 )
                    goto LABEL_94;
                  if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                    && (gfEnableTracing == (_DWORD)v18 || !IsWppLevelEnabled(ERRORS)) )
                  {
                    goto LABEL_90;
                  }
LABEL_77:
                  v29 = (PCWSTR)v18;
                  goto LABEL_78;
                }
LABEL_70:
                if ( gfEnableTracing == (_DWORD)v18 )
                  goto LABEL_94;
                if ( IsWppLevelEnabled(VERBOSE) )
                  goto LABEL_77;
                goto LABEL_72;
              }
              if ( gfEnableTracing == (_DWORD)v18 || !IsWppLevelEnabled(VERBOSE) )
              {
LABEL_52:
                this->_hasAppId = 1;
                goto LABEL_53;
              }
LABEL_51:
              CGuidStr::CGuidStr(&v166, &this->_appId);
              function[1] = v25;
              ComTraceHr(
                Permissions,
                "onecore\\com\\combase\\catalog\\storecat.cxx",
                "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
                3122,
                L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property AppID (%ws): %!HRESULT!");
              v18 = 0;
              if ( Permissions < 0 )
                goto LABEL_46;
              goto LABEL_52;
            }
          }
          if ( gfEnableTracing == (_DWORD)v18 )
            goto LABEL_53;
          if ( IsWppLevelEnabled(VERBOSE) )
            goto LABEL_51;
          goto LABEL_41;
        }
        goto LABEL_24;
      }
      Permissions = -2147024883;
    }
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_25;
LABEL_24:
    ComTraceHr(
      Permissions,
      "onecore\\com\\combase\\catalog\\storecat.cxx",
      "CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct",
      3096,
      L"Read Server entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ServerType (%d): %!HRESULT!",
      serverName,
      this->_registrationScope,
      this->_serverType,
      Permissions);
    v18 = 0;
    if ( Permissions < 0 )
    {
LABEL_25:
      v22 = 5217;
      goto LABEL_26;
    }
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x180141d28  push    rbp
0x180141d2a  push    rbx
0x180141d2b  push    rsi
0x180141d2c  push    rdi
0x180141d2d  push    r12
0x180141d2f  push    r13
0x180141d31  push    r14
0x180141d33  push    r15
0x180141d35  lea     rbp, [rsp-208h]
0x180141d3d  sub     rsp, 348h
0x180141d44  mov     rax, cs:__security_cookie
0x180141d4b  xor     rax, rsp
0x180141d4e  mov     [rbp+240h+var_50], rax
0x180141d55  mov     rax, [rbp+240h+arg_20]
0x180141d5c  mov     rdi, pUserToken
0x180141d5f  mov     rsi, [rbp+240h+arg_28]
0x180141d66  mov     r13, this
0x180141d69  mov     r15, [rbp+240h+arg_30]
0x180141d70  mov     r14, packageMoniker
0x180141d73  mov     rbx, [rbp+240h+arg_38]
0x180141d7a  mov     r12, serverName
0x180141d7d  mov     [rbp+240h+userToken], pUserToken
0x180141d81  lea     pUserToken, [this+40h]; copy
0x180141d85  mov     this, serverName; string
0x180141d88  mov     [rbp+240h+var_2A8], serverName
0x180141d8c  mov     [rbp+240h+dwMgotFlagsFromAppID], rax
0x180141d90  mov     [rbp+240h+var_250], rsi
0x180141d94  mov     qword ptr [rbp+240h+var_268], r15
0x180141d98  mov     [rbp+240h+fIsAppContainer], 0
0x180141d9f  call    ?DuplicatePWSTR@@YAJPEBGAEAPEAG@Z; DuplicatePWSTR(ushort const *,ushort * &)
0x180141da4  test    eax, eax
0x180141da6  js      loc_180142F23
0x180141dac  mov     rax, [rsi]
0x180141daf  mov     this, rsi
0x180141db2  mov     rax, [rax+18h]
0x180141db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141dbb  mov     [r13+0C4h], eax
0x180141dc2  cmp     eax, 1
0x180141dc5  jnz     short loc_180141E28
0x180141dc7  xor     eax, eax
0x180141dc9  test    rdi, rdi
0x180141dcc  jz      short loc_180141DF3
0x180141dce  mov     [rbp+240h+pComProcessInfo3], rax
0x180141dd2  lea     pUserToken, [rbp+240h+pComProcessInfo3]
0x180141dd6  mov     rax, [rdi]
0x180141dd9  mov     this, rdi
0x180141ddc  mov     rax, [rax+30h]
0x180141de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141de5  test    eax, eax
0x180141de7  js      loc_180142F23
0x180141ded  mov     this, [rbp+240h+pComProcessInfo3]
0x180141df1  jmp     short loc_180141E12
0x180141df3  lea     pUserToken, [rbp+240h+fIsAppContainer]; hToken
0x180141df7  call    ?IsTokenChildAppContainer@@YAJPEAXPEAH@Z; IsTokenChildAppContainer(void *,int *)
0x180141dfc  xor     ecx, ecx
0x180141dfe  test    eax, eax
0x180141e00  js      loc_180142F23
0x180141e06  cmp     [rbp+240h+fIsAppContainer], ecx
0x180141e09  jnz     short loc_180141E28
0x180141e0b  mov     this, 0FFFFFFFFFFFFFFFCh; hToken
0x180141e12  lea     serverName, [rbp+240h+fIsAppContainer]; isPresent
0x180141e16  mov     edx, 1Dh; type
0x180141e1b  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180141e20  test    eax, eax
0x180141e22  js      loc_180142F23
0x180141e28  mov     edx, [r13+0C4h]; scope
0x180141e2f  lea     this, [rbp+240h+serverHelper]; this
0x180141e33  call    ??0CServerInfoPropertiesHelper@CWinRTActivationStoreCatalog@@QEAA@W4RegistrationScope@Foundation@Windows@@@Z; CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::CServerInfoPropertiesHelper(Windows::Foundation::RegistrationScope)
0x180141e38  mov     packageMoniker, rbx; serverForMachineHandle
0x180141e3b  lea     this, [rbp+240h+serverHelper]; this
0x180141e3f  mov     serverName, r15; serverHandle
0x180141e42  mov     pUserToken, rsi; pRegistrationStore
0x180141e45  call    ?ReadServerRegistrationEntry@CServerInfoPropertiesHelper@CWinRTActivationStoreCatalog@@QEAAJPEAUIActivationCatalogContext@@PEAUServerHandleDetail@RegistrationStoreContext@@PEAUServerForMachineHandleDetail@5@@Z; CWinRTActivationStoreCatalog::CServerInfoPropertiesHelper::ReadServerRegistrationEntry(IActivationCatalogContext *,RegistrationStoreContext::ServerHandleDetail *,RegistrationStoreContext::ServerForMachineHandleDetail *)
0x180141e4a  mov     ebx, eax
0x180141e4c  mov     esi, 8007000Dh
0x180141e51  mov     eax, 80000000h
0x180141e56  mov     [rbp+240h+fIsAppContainer], esi
0x180141e59  lea     ecx, [rbx+rax]
0x180141e5c  test    eax, ecx
0x180141e5e  jnz     short loc_180141E80
0x180141e60  cmp     ebx, esi
0x180141e62  jz      short loc_180141E80
0x180141e64  lea     this, [rbp+240h+serverHelper._machineProperties]; this
0x180141e6b  call    ??1ServerMachineRegistrationEntryProperties@@QEAA@XZ; ServerMachineRegistrationEntryProperties::~ServerMachineRegistrationEntryProperties(void)
0x180141e70  lea     this, [rbp+240h+serverHelper._userProperties]; this
0x180141e74  call    ??1ServerRegistrationEntryProperties@@QEAA@XZ; ServerRegistrationEntryProperties::~ServerRegistrationEntryProperties(void)
0x180141e79  mov     eax, ebx
0x180141e7b  jmp     loc_180142F23
0x180141e80  xor     r9d, r9d
0x180141e83  lea     rdi, aOnecoreComComb_177; "onecore\\com\\combase\\catalog\\storeca"...
0x180141e8a  mov     ebx, 80070002h
0x180141e8f  cmp     [r13+0C4h], r9d
0x180141e96  jnz     loc_180141F8F
0x180141e9c  mov     r8b, [rbp+240h+serverHelper._machineMissingRequiredProperties]
0x180141ea3  mov     eax, [rbp+240h+serverHelper._machineProperties.ServerType]
0x180141ea9  mov     [r13+0B0h], eax
0x180141eb0  test    r8b, 20h
0x180141eb4  jz      short loc_180141EBB
0x180141eb6  mov     r15d, ebx
0x180141eb9  jmp     short loc_180141EC9
0x180141ebb  mov     dl, [rbp+240h+serverHelper._machineInvalidProperties]
0x180141ec1  test    dl, 20h
0x180141ec4  jz      short loc_180141EE9
0x180141ec6  mov     r15d, esi
0x180141ec9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180141ecf  test    eax, eax
0x180141ed1  jnz     short loc_180141F0B
0x180141ed3  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180141eda  jz      short loc_180141F57
0x180141edc  xor     ecx, ecx; level
0x180141ede  call    IsWppLevelEnabled
0x180141ee3  test    al, al
0x180141ee5  jnz     short loc_180141F0B
0x180141ee7  jmp     short loc_180141F57
0x180141ee9  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180141ef0  jz      loc_180141F9C
0x180141ef6  mov     ecx, 3; level
0x180141efb  mov     r15d, r9d
0x180141efe  call    IsWppLevelEnabled
0x180141f03  test    al, al
0x180141f05  jz      loc_180141F9C
0x180141f0b  mov     eax, [r13+0B0h]
0x180141f12  lea     serverName, aCwinrtactivati_5; "CWinRTActivationStoreCatalog::CServerIn"...
0x180141f19  mov     [rsp+380h+line], r15d
0x180141f1e  mov     r9d, 0C18h; line
0x180141f24  mov     [rsp+380h+function], eax
0x180141f28  mov     pUserToken, rdi; file
0x180141f2b  mov     eax, [r13+0C4h]
0x180141f32  mov     ecx, r15d; hr
0x180141f35  mov     [rsp+380h+file], eax
0x180141f39  lea     rax, aReadServerEntr_0; "Read Server entry %ws in scope %!Window"...
0x180141f40  mov     [rsp+380h+runtimeBehavior], r12
0x180141f45  mov     [rsp+380h+format], rax; format
0x180141f4a  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x180141f4f  xor     r9d, r9d
0x180141f52  test    r15d, r15d
0x180141f55  jns     short loc_180141F8F
0x180141f57  mov     ecx, 1461h; uResourceId
0x180141f5c  mov     [rbp+240h+uResourceId], r9w
0x180141f61  lea     serverName, [rbp+240h+pComProcessInfo3]; pcchResource
0x180141f65  mov     [rbp+240h+pComProcessInfo3], packageMoniker
0x180141f69  lea     packageMoniker, [rbp+240h+uResourceId]; uResourceId
0x180141f6d  call    LoadStringResource
0x180141f72  mov     ecx, r15d; error
0x180141f75  test    eax, eax
0x180141f77  js      loc_180142126
0x180141f7d  movzx   edx, [rbp+240h+uResourceId]; cchMax
0x180141f81  mov     serverName, [rbp+240h+pComProcessInfo3]; message
0x180141f85  call    RoOriginateErrorW
0x180141f8a  jmp     loc_180142F17
0x180141f8f  mov     dl, [rbp+240h+serverHelper._machineInvalidProperties]
0x180141f95  mov     r8b, [rbp+240h+serverHelper._machineMissingRequiredProperties]
0x180141f9c  cmp     [r13+0C4h], r9d
0x180141fa3  jnz     loc_1801420CF
0x180141fa9  test    r8b, 40h
0x180141fad  jnz     short loc_180141FEF
0x180141faf  test    dl, 40h
0x180141fb2  jz      short loc_180141FB9
0x180141fb4  mov     r15d, esi
0x180141fb7  jmp     short loc_18014201B
0x180141fb9  cmp     [rbp+240h+serverHelper._machineProperties.AppId.Present], r9b
0x180141fc0  jz      short loc_180141FEF
0x180141fc2  mov     this, [rbp+240h+serverHelper._machineProperties.AppId.Value.hstr_]; string
0x180141fc9  xor     edx, edx; length
0x180141fcb  call    WindowsGetStringRawBuffer
0x180141fd0  lea     pUserToken, [r13+4Ch]; lpiid
0x180141fd4  mov     this, rax; lpsz
0x180141fd7  call    IIDFromString
0x180141fdc  xor     r9d, r9d
0x180141fdf  mov     r15d, eax
0x180141fe2  test    eax, eax
0x180141fe4  cmovs   r15d, esi
0x180141fe8  cmp     r15d, ebx
0x180141feb  jz      short loc_180141FF2
0x180141fed  jmp     short loc_18014200D
0x180141fef  mov     r15d, ebx
0x180141ff2  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180141ff9  jz      loc_1801420CF
0x180141fff  mov     ecx, 3; level
0x180142004  call    IsWppLevelEnabled
0x180142009  test    al, al
0x18014200b  jnz     short loc_180142070
0x18014200d  test    r15d, r15d
0x180142010  jns     short loc_180142059
0x180142012  cmp     r15d, ebx
0x180142015  jz      loc_1801420CF
0x18014201b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180142021  test    eax, eax
0x180142023  jnz     short loc_180142070
0x180142025  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18014202c  jz      short loc_180142039
0x18014202e  xor     ecx, ecx; level
0x180142030  call    IsWppLevelEnabled
0x180142035  test    al, al
0x180142037  jnz     short loc_180142070
0x180142039  cmp     r15d, ebx
0x18014203c  jz      loc_1801420CF
0x180142042  cmp     r15d, 8007000Eh
0x180142049  jz      loc_180142F17
0x18014204f  mov     ecx, 1462h
0x180142054  jmp     loc_180141F5C
0x180142059  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180142060  jz      short loc_1801420CA
0x180142062  mov     ecx, 3; level
0x180142067  call    IsWppLevelEnabled
0x18014206c  test    al, al
0x18014206e  jz      short loc_1801420CA
0x180142070  lea     pUserToken, [r13+4Ch]; rguid
0x180142074  lea     this, [rbp+240h+var_A0]; this
0x18014207b  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180142080  mov     [rsp+380h+line], r15d
0x180142085  lea     serverName, aCwinrtactivati_5; "CWinRTActivationStoreCatalog::CServerIn"...
0x18014208c  mov     qword ptr [rsp+380h+function], rax
0x180142091  mov     r9d, 0C32h; line
0x180142097  mov     eax, [r13+0C4h]
0x18014209e  mov     pUserToken, rdi; file
0x1801420a1  mov     [rsp+380h+file], eax
0x1801420a5  mov     ecx, r15d; hr
0x1801420a8  lea     rax, aReadServerEntr_5; "Read Server entry %ws in scope %!Window"...
0x1801420af  mov     [rsp+380h+runtimeBehavior], r12
0x1801420b4  mov     [rsp+380h+format], rax; format
0x1801420b9  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801420be  xor     r9d, r9d
0x1801420c1  test    r15d, r15d
0x1801420c4  js      loc_180142039
0x1801420ca  mov     byte ptr [r13+48h], 1
0x1801420cf  test    r14, r14
0x1801420d2  jz      short loc_180142137
0x1801420d4  lea     rbx, [r13+88h]
0x1801420db  xor     edx, edx; ptr
0x1801420dd  mov     this, rbx; this
0x1801420e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801420e5  or      pUserToken, 0FFFFFFFFFFFFFFFFh
0x1801420e9  xor     eax, eax
0x1801420eb  inc     pUserToken; length
0x1801420ee  cmp     [r14+pUserToken*2], ax
0x1801420f3  jnz     short loc_1801420EB
0x1801420f5  mov     serverName, rbx; string
0x1801420f8  mov     this, r14; sourceString
0x1801420fb  call    WindowsCreateString
0x180142100  xor     r9d, r9d
0x180142103  mov     r15d, eax
0x180142106  test    eax, eax
0x180142108  jns     short loc_180142132
0x18014210a  mov     this, [rbp+248h]; callerReturnAddress
0x180142111  mov     r9d, eax; hr
0x180142114  mov     serverName, rdi; fileName
0x180142117  mov     edx, 0C49h; lineNumber
0x18014211c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180142121  jmp     loc_180142F17
0x180142126  xor     edx, edx; message
0x180142128  call    RoOriginateError
0x18014212d  jmp     loc_180142F17
0x180142132  mov     ebx, 80070002h
0x180142137  mov     rdi, packageMoniker
0x18014213a  mov     [rbp+240h+pComProcessInfo3], packageMoniker
0x18014213e  cmp     [rbp+240h+serverHelper._scope], r9d
0x180142142  jz      short loc_18014218B
0x180142144  test    [rbp+240h+serverHelper._userMissingRequiredProperties], 10h
0x18014214b  jnz     short loc_18014217A
0x18014214d  test    [rbp+240h+serverHelper._userInvalidProperties], 10h
0x180142154  jz      short loc_18014215B
0x180142156  mov     r15d, esi
0x180142159  jmp     short loc_18014217D
0x18014215b  cmp     [rbp+240h+serverHelper._userProperties.ExecutionPackageFamily.Present], r9b
0x18014215f  jz      short loc_18014217A
0x180142161  lea     pUserToken, [rbp+240h+serverHelper._userProperties.ExecutionPackageFamily.Value]; other
0x180142165  mov     r15d, r9d
0x180142168  lea     this, [rbp+240h+pComProcessInfo3]; this
0x18014216c  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x180142171  mov     rdi, [rbp+240h+pComProcessInfo3]
0x180142175  xor     r9d, r9d
0x180142178  jmp     short loc_18014217D
0x18014217a  mov     r15d, ebx
0x18014217d  mov     ebx, r15d
0x180142180  cmp     r15d, 80070002h
0x180142187  jnz     short loc_1801421AC
0x180142189  jmp     short loc_180142191
0x18014218b  mov     r15d, 80070002h
0x180142191  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180142198  jz      loc_18014233D
0x18014219e  mov     ecx, 3; level
0x1801421a3  call    IsWppLevelEnabled
0x1801421a8  test    al, al
0x1801421aa  jnz     short loc_1801421E6
0x1801421ac  test    ebx, ebx
0x1801421ae  jns     loc_18014229E
0x1801421b4  cmp     ebx, 80070002h
0x1801421ba  jz      loc_18014233D
0x1801421c0  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801421c6  test    eax, eax
0x1801421c8  jnz     short loc_1801421E6
0x1801421ca  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x1801421d1  jz      loc_1801422FC
0x1801421d7  xor     ecx, ecx; level
0x1801421d9  call    IsWppLevelEnabled
0x1801421de  test    al, al
0x1801421e0  jz      loc_1801422FC
0x1801421e6  mov     rax, packageMoniker
0x1801421e9  mov     [rsp+380h+line], ebx
  ... truncated ...
```
