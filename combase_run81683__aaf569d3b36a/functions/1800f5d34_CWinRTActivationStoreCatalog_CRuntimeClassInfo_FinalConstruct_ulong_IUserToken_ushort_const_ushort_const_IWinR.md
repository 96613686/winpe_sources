# CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct(ulong,IUserToken *,ushort const *,ushort const *,IWinRTCatalogInternal *,IActivationCatalogContext *,RegistrationStoreContext::ActivatableClassHandleDetail *,RegistrationStoreContext::ActivatableClassForMachineHandleDetail *,bool)

- ea: `0x1800f5d34`
- end: `0x1800f77c1`
- name: `?FinalConstruct@CRuntimeClassInfo@CWinRTActivationStoreCatalog@@QEAAJKPEAUIUserToken@@PEBG1PEAUIWinRTCatalogInternal@@PEAUIActivationCatalogContext@@PEAUActivatableClassHandleDetail@RegistrationStoreContext@@PEAUActivatableClassForMachineHandleDetail@7@_N@Z`
- size: `6797`
- prototype: `HRESULT __fastcall(CWinRTActivationStoreCatalog::CRuntimeClassInfo *this, unsigned int dwCatalogFlags, IUserToken *pUserToken, const wchar_t *activatableClassId, const wchar_t *packageMoniker, IWinRTCatalogInternal *pWinRTCatalogCallback, IActivationCatalogContext *pRegistrationStore, RegistrationStoreContext::ActivatableClassHandleDetail *activatableClassHandle, RegistrationStoreContext::ActivatableClassForMachineHandleDetail *activatableClassForMachineHandle, bool allowPrivate)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c54e0`

## callees

- `0x18000b408`
- `0x18003a8bc`
- `0x180041c90`
- `0x1800421e0`
- `0x1800450a0`
- `0x180053a60`
- `0x180055084`
- `0x180055d90`
- `0x180055e90`
- `0x180056ce0`
- `0x180058e20`
- `0x18005d12c`
- `0x180075a8c`
- `0x180076d30`
- `0x1800865b8`
- `0x180086714`
- `0x18008db2c`
- `0x1800c4250`
- `0x1800d419c`
- `0x1800d492c`
- `0x1800d49d8`
- `0x1800ddc40`
- `0x1800e93f0`
- `0x1800f5d34`
- `0x18010be7c`
- `0x18011b06c`
- `0x18011b5d4`
- `0x18011c070`
- `0x18011d1ec`
- `0x18012b924`
- `0x18012fc20`
- `0x18013a770`
- `0x1801457c0`
- `0x18015706c`
- `0x18019c9fc`
- `0x1801de790`
- `0x1801de8cc`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f660b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f660b`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800f70a8`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800f70a8`

## string_xrefs

- `0x1800f5fa0`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800f5fcb`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800f6dd0`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800f708b`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800f61ea`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property TrustLevel (%d): %!HRESULT!`
- `0x1800f62b7`: `ActivatableClassId %ws in scope %!Windows::Foundation::RegistrationScope!, default to full trust`
- `0x1800f603a`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivationType (%d): %!HRESULT!`
- `0x1800f6129`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Threading (%d): %!HRESULT!`
- `0x1800f5f7f`: `ActivatableClassId entry %ws is private and hence cannot be activated from outside its package dependency graph`
- `0x1800f6bac`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Server (%ws): %!HRESULT!`
- `0x1800f6cc6`: `ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, inproc but has Server`
- `0x1800f6912`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property DllPath (%ws): %!HRESULT!`
- `0x1800f6a67`: `ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, outofproc but has DllPath`
- `0x1800f672f`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivateInBrokerForMediumILContainer (%d): %!HRESULT!`
- `0x1800f681c`: `ActivatableClassId entry %ws specifies ActivateOnHostFlags but is not ActivationType_OutOfProcess`
- `0x1800f6367`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Permissions (%d): %!HRESULT!`
- `0x1800f64de`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivateInSharedBroker (%d): %!HRESULT!`
- `0x1800f763c`: `GetLastWriteTime result is %!TIME!`
- `0x1800f7417`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivateAsUser (%d): %!HRESULT!`
- `0x1800f71ce`: `Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property RemoteServerName (%ws): %!HRESULT!`
- `0x1800f733b`: `ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, local but has remote server name`
- `0x1800f6dee`: `GetServerInfo(%ws) for ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`

## pseudocode

```c
HRESULT __fastcall CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct(
        CWinRTActivationStoreCatalog::CRuntimeClassInfo *this,
        unsigned int dwCatalogFlags,
        IUserToken *pUserToken,
        wchar_t *activatableClassId,
        wchar_t *packageMoniker,
        IWinRTCatalogInternal *pWinRTCatalogCallback,
        IActivationCatalogContext *pRegistrationStore,
        RegistrationStoreContext::ActivatableClassHandleDetail *activatableClassHandle,
        RegistrationStoreContext::ActivatableClassHandleDetail *activatableClassForMachineHandle,
        bool allowPrivate)
{
  HRESULT result; // eax
  IActivationCatalogContext *v13; // rbx
  Windows::Foundation::RegistrationScope v14; // eax
  ProcessToken *v15; // rcx
  Microsoft::WRL::Details::Dummy v16; // r8
  IActivationCatalogContext_vtbl *v17; // rax
  RegistrationStoreContext::ActivatableClassHandleDetail *v18; // rdx
  wchar_t *machineMissingRequiredProperties; // rcx
  __int64 (__fastcall *ReadPackageActivatableClassEntry)(IActivationCatalogContext *, RegistrationStoreContext::ActivatableClassHandleDetail *, Optional<OpaqueString> *, _BYTE *); // rax
  _BYTE *userInvalidProperties; // r9
  Optional<OpaqueString> *p_Server; // r8
  const wchar_t *v23; // rdx
  int v24; // ebx
  HRESULT v25; // r12d
  HRESULT ActivationType; // r14d
  Windows::Foundation::ActivationType *p_activationType; // rbx
  __int64 v28; // rdx
  int v29; // r9d
  unsigned __int16 v30; // cx
  int StringResource; // eax
  HRESULT v32; // ecx
  HRESULT v33; // ebx
  const char *v34; // rcx
  unsigned __int16 *p_cbSecurityDescriptor; // rbx
  HRESULT v36; // ebx
  int v37; // eax
  int v38; // eax
  bool *p_activateInBrokerForMediumILContainer; // rbx
  HRESULT ActivateInBrokerForMediumILContainer; // eax
  const wchar_t *v41; // rdx
  int v42; // eax
  HRESULT v43; // ecx
  int ActivateOnHostFlags; // eax
  HRESULT v45; // r9d
  unsigned int v46; // edx
  int v47; // eax
  HRESULT v48; // eax
  unsigned __int64 v49; // rdx
  Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *v50; // rbx
  int v51; // r8d
  PCWSTR StringRawBuffer; // rax
  const char *v53; // rcx
  char v54; // dl
  HRESULT ServerName; // eax
  unsigned __int64 v56; // rdx
  Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *ptr; // rdi
  int v58; // r8d
  PCWSTR v59; // rax
  wchar_t *v60; // rbx
  const char *v61; // rcx
  IWinRTCatalogInternal *v62; // rsi
  IWinRTServerInfo *m_ptr; // rcx
  IWinRTCatalogInternal_vtbl *v64; // rax
  HRESULT (__fastcall *GetServerInfo)(IWinRTCatalogInternal *, unsigned int, IUserToken *, const wchar_t *, const wchar_t *, const _GUID *, void **, IComCatalogSCM *); // r14
  PCWSTR v66; // rax
  const wchar_t *v67; // rdx
  const wchar_t *v68; // rdx
  Windows::Foundation::RegistrationScope v69; // esi
  Windows::Foundation::RegistrationScope registrationScope; // ebx
  const wchar_t *function; // rax
  const char *v72; // rdx
  int v73; // r8d
  TraceLevel v74; // r9d
  IMetaDataImport2 *v75; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *const, void **); // rsi
  int v77; // ebx
  ProcessToken *v78; // rcx
  AppModelPolicy_PolicyValue AppModelPolicyValue; // eax
  const wchar_t *v80; // rdx
  unsigned __int64 v81; // rdx
  int v82; // r8d
  PCWSTR v83; // rax
  const char *v84; // rcx
  const wchar_t *v85; // rax
  int v86; // eax
  HRESULT v87; // ecx
  IActivationCatalogContext *v88; // r12
  HRESULT v89; // eax
  unsigned int v90; // edx
  int v91; // eax
  TraceLevel v92; // edx
  TraceLevel v93; // edx
  int Attributes; // eax
  const char *v95; // rdx
  const char *v96; // r9
  const char *line; // rax
  wchar_t *format; // [rsp+28h] [rbp-E0h]
  wil::com_ptr_t<IWinRTServerInfo,wil::err_returncode_policy> *file; // [rsp+38h] [rbp-D0h]
  __int64 level; // [rsp+40h] [rbp-C8h]
  __int64 v101; // [rsp+48h] [rbp-C0h]
  ExpandableString dllPath; // [rsp+88h] [rbp-80h] BYREF
  Microsoft::WRL::ComPtr<IWinRTServerInfo> serverInfo; // [rsp+98h] [rbp-70h]
  Microsoft::WRL::ComPtr<IMetaDataImport2> dwServerRegistrationScope; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int trustLevel; // [rsp+A8h] [rbp-60h] BYREF
  int v106; // [rsp+ACh] [rbp-5Ch] BYREF
  CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper activatableClassHelper; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v108; // [rsp+1B0h] [rbp+A8h] BYREF
  void *retaddr; // [rsp+200h] [rbp+F8h]
  EntryPropertyStore propertyStore; // [rsp+208h] [rbp+100h] BYREF
  unsigned int v111; // [rsp+210h] [rbp+108h]
  IUserToken *userToken; // [rsp+218h] [rbp+110h]
  wchar_t *strRef; // [rsp+220h] [rbp+118h] BYREF

  strRef = activatableClassId;
  userToken = pUserToken;
  v111 = dwCatalogFlags;
  result = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
             &this->_activatableClassId,
             (const wchar_t *const *)&strRef,
             (Microsoft::WRL::Details::Dummy)pUserToken);
  if ( result >= 0 )
  {
    v13 = pRegistrationStore;
    v14 = pRegistrationStore->GetRegistrationStoreScope(pRegistrationStore);
    this->_registrationScope = v14;
    if ( v14 == RegistrationScope_PerUser )
      ProcessToken::IsAppContainer(v15);
    if ( !packageMoniker
      || (result = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
                     &this->_packageMoniker,
                     (const wchar_t *const *)&packageMoniker,
                     v16),
          result >= 0) )
    {
      v17 = v13->__vftable;
      activatableClassHelper._userProperties.ActivationType = this->_registrationScope;
      LOBYTE(activatableClassHelper._userProperties.Server.Value.hstr_) = 0;
      *(_QWORD *)&activatableClassHelper._userProperties.DllPath.Present = 0;
      LOBYTE(activatableClassHelper._userProperties.DllPath.Value.Unexpanded.hstr_) = 0;
      *((_BYTE *)&activatableClassHelper._userProperties.Threading + 8) = 0;
      LODWORD(activatableClassHelper._userProperties.CustomAttributes.MapView.ptr_) = 0;
      *(_QWORD *)&activatableClassHelper._userProperties.Private.Present = 0;
      LOWORD(activatableClassHelper._machineProperties.ActivationType) = 0;
      LOBYTE(activatableClassHelper._machineProperties.Server.Value.hstr_) = 0;
      *(_QWORD *)&activatableClassHelper._machineProperties.DllPath.Present = 0;
      LOBYTE(activatableClassHelper._machineProperties.DllPath.Value.Unexpanded.hstr_) = 0;
      activatableClassHelper._machineProperties.TrustLevel.Value = BaseTrust;
      LOBYTE(activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_) = 0;
      HIDWORD(activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_) = 0;
      *(_QWORD *)&activatableClassHelper._machineProperties.RemoteServer.Present = 0;
      LOBYTE(activatableClassHelper._machineProperties.RemoteServer.Value.hstr_) = 0;
      activatableClassHelper._machineProperties.ActivateAsUser = 0;
      activatableClassHelper._machineProperties.ActivateInSharedBroker.Present = 0;
      *(_QWORD *)(&activatableClassHelper._machineProperties.ActivateInBrokerForMediumILContainer + 1) = 0;
      LOBYTE(activatableClassHelper._machineProperties.Permissions.Value._pSecurityDescriptor) = 0;
      memset(&activatableClassHelper._userMissingRequiredProperties[4], 0, 28);
      v108 = 0;
      memset(&activatableClassHelper._machineProperties.Permissions.Value._cbSecurityDescriptor, 0, 17);
      memset(&activatableClassHelper._userProperties.DllPath.Value.IsExpandable, 0, 18);
      memset(&activatableClassHelper._machineProperties.DllPath.Value.IsExpandable, 0, 17);
      if ( activatableClassHelper._userProperties.ActivationType )
      {
        v18 = activatableClassHandle;
        machineMissingRequiredProperties = (wchar_t *)activatableClassHelper._machineMissingRequiredProperties;
        ReadPackageActivatableClassEntry = (__int64 (__fastcall *)(IActivationCatalogContext *, RegistrationStoreContext::ActivatableClassHandleDetail *, Optional<OpaqueString> *, _BYTE *))v17->ReadPackageActivatableClassEntry;
        userInvalidProperties = activatableClassHelper._userInvalidProperties;
        p_Server = &activatableClassHelper._userProperties.Server;
      }
      else
      {
        v18 = activatableClassForMachineHandle;
        machineMissingRequiredProperties = (wchar_t *)&v108;
        ReadPackageActivatableClassEntry = (__int64 (__fastcall *)(IActivationCatalogContext *, RegistrationStoreContext::ActivatableClassHandleDetail *, Optional<OpaqueString> *, _BYTE *))v17->ReadMachineActivatableClassEntry;
        userInvalidProperties = activatableClassHelper._machineInvalidProperties;
        p_Server = &activatableClassHelper._machineProperties.Server;
      }
      format = machineMissingRequiredProperties;
      v24 = ReadPackageActivatableClassEntry(v13, v18, p_Server, userInvalidProperties);
      v25 = -2147024883;
      if ( (int)(v24 + 0x80000000) >= 0 && v24 != -2147024883 )
      {
        ActivatableClassMachineRegistrationEntryProperties::~ActivatableClassMachineRegistrationEntryProperties((ActivatableClassMachineRegistrationEntryProperties *)&activatableClassHelper._machineProperties.Server);
        ActivatableClassRegistrationEntryProperties::~ActivatableClassRegistrationEntryProperties((ActivatableClassRegistrationEntryProperties *)&activatableClassHelper._userProperties.Server);
        return v24;
      }
      if ( !allowPrivate
        && activatableClassHelper._userProperties.ActivationType
        && (BYTE1(activatableClassHelper._machineProperties.ActivationType)
          & (unsigned __int8)-(LOBYTE(activatableClassHelper._machineProperties.ActivationType) != 0)) != 0 )
      {
        dllPath.Unexpanded.hstr_ = 0;
        LOWORD(propertyStore.MapView.ptr_) = 0;
        ActivationType = -2147024891;
        if ( LoadStringResource(0x1460u, v23, (const wchar_t **)&dllPath, (unsigned __int16 *)&propertyStore) < 0 )
          RoOriginateError(-2147024891, 0);
        else
          RoOriginateErrorW(-2147024891, LOWORD(propertyStore.MapView.ptr_), (const wchar_t *)dllPath.Unexpanded.hstr_);
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<void *>(
            "onecore\\com\\combase\\catalog\\storecat.cxx",
            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
            1358,
            ERRORS,
            L"ActivatableClassId entry %ws is private and hence cannot be activated from outside its package dependency graph",
            activatableClassId);
        goto LABEL_351;
      }
      p_activationType = &this->_activationType;
      ActivationType = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetActivationType(
                         (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                         &this->_activationType);
      if ( ActivationType >= 0 )
      {
        v29 = gfEnableTracing;
        if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
          goto LABEL_36;
      }
      else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      {
        goto LABEL_30;
      }
      ComTraceHr(
        ActivationType,
        "onecore\\com\\combase\\catalog\\storecat.cxx",
        "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
        1368,
        L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivationType (%d): %!HRESULT!",
        activatableClassId,
        this->_registrationScope,
        *p_activationType,
        ActivationType);
      if ( ActivationType < 0 )
      {
LABEL_30:
        if ( ActivationType == -2147024882 )
        {
LABEL_351:
          CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::~CActivatableClassPropertiesHelper((CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties);
          return ActivationType;
        }
        v30 = 5204;
        goto LABEL_32;
      }
      v29 = gfEnableTracing;
LABEL_36:
      if ( *p_activationType )
        goto LABEL_48;
      ActivationType = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetThreadingModel(
                         (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                         &this->_threadingModel);
      if ( ActivationType >= 0 )
      {
        if ( !v29 || !IsWppLevelEnabled(VERBOSE) )
          goto LABEL_48;
      }
      else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      {
        goto LABEL_45;
      }
      LODWORD(v101) = ActivationType;
      SLODWORD(level) = *p_activationType;
      LODWORD(file) = this->_registrationScope;
      ComTraceHr(
        ActivationType,
        "onecore\\com\\combase\\catalog\\storecat.cxx",
        "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
        1386,
        L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Threading (%d): %!HRESULT!",
        activatableClassId,
        file,
        level,
        v101);
      if ( ActivationType < 0 )
      {
LABEL_45:
        if ( ActivationType == -2147024882 )
          goto LABEL_351;
        v30 = 5205;
LABEL_32:
        LOWORD(propertyStore.MapView.ptr_) = 0;
        dllPath.Unexpanded.hstr_ = 0;
        StringResource = LoadStringResource(
                           v30,
                           (const wchar_t *)v28,
                           (const wchar_t **)&dllPath,
                           (unsigned __int16 *)&propertyStore);
        v32 = ActivationType;
        if ( StringResource < 0 )
        {
          RoOriginateError(ActivationType, 0);
          goto LABEL_351;
        }
        goto LABEL_33;
      }
      v29 = gfEnableTracing;
LABEL_48:
      v28 = 2147942402LL;
      if ( this->_registrationScope )
      {
        this->_trustLevel = BaseTrust;
      }
      else
      {
        if ( (activatableClassHelper._machineInvalidProperties[0] & 0x10) != 0 )
          goto LABEL_60;
        if ( (v108 & 0x10) != 0 )
        {
          v33 = -2147024883;
          ActivationType = -2147024883;
          if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
          {
            v29 = gfEnableTracing;
            if ( !gfEnableTracing || !IsWppLevelEnabled(ERRORS) )
            {
LABEL_57:
              if ( v33 != (_DWORD)v28 )
              {
LABEL_58:
                if ( ActivationType < 0 )
                {
                  v30 = 5206;
                  goto LABEL_32;
                }
                goto LABEL_72;
              }
              goto LABEL_68;
            }
          }
LABEL_56:
          LODWORD(v101) = v33;
          LODWORD(level) = this->_trustLevel;
          LODWORD(file) = this->_registrationScope;
          ComTraceHr(
            v33,
            "onecore\\com\\combase\\catalog\\storecat.cxx",
            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
            1413,
            L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property TrustLevel (%d): %!HRESULT!",
            activatableClassId,
            file,
            level,
            v101);
          v29 = gfEnableTracing;
          v28 = 2147942402LL;
          goto LABEL_57;
        }
        if ( !LOBYTE(activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_) )
        {
LABEL_60:
          ActivationType = -2147024894;
          v33 = -2147024894;
          if ( !v29 )
            goto LABEL_68;
          if ( IsWppLevelEnabled(VERBOSE) )
            goto LABEL_56;
          if ( (int)v28 < 0 )
          {
LABEL_68:
            this->_trustLevel = FullTrust;
            if ( v29 && IsWppLevelEnabled(VERBOSE) )
            {
              ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                v34,
                "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                1424,
                VERBOSE,
                L"ActivatableClassId %ws in scope %!Windows::Foundation::RegistrationScope!, default to full trust",
                activatableClassId,
                this->_registrationScope);
              v29 = gfEnableTracing;
              v28 = 2147942402LL;
            }
            goto LABEL_72;
          }
        }
        else
        {
          v33 = 0;
          ActivationType = 0;
          this->_trustLevel = HIDWORD(activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_);
        }
        if ( v29 )
        {
          if ( !IsWppLevelEnabled(VERBOSE) )
            goto LABEL_58;
          goto LABEL_56;
        }
      }
LABEL_72:
      if ( this->_registrationScope )
        goto LABEL_83;
      p_cbSecurityDescriptor = 0;
      if ( (*(_WORD *)activatableClassHelper._machineInvalidProperties & 0x400) != 0 )
        goto LABEL_87;
      if ( (v108 & 0x400) != 0 )
      {
        ActivationType = -2147024883;
        if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
        {
          v29 = gfEnableTracing;
          if ( !gfEnableTracing || !IsWppLevelEnabled(ERRORS) )
          {
LABEL_96:
            if ( (int)(ActivationType + 0x80000000) >= 0 && ActivationType != -2147024894 )
            {
              if ( ActivationType == -2147024882 )
                goto LABEL_351;
              v30 = 5309;
              goto LABEL_32;
            }
LABEL_83:
            if ( this->_registrationScope )
              goto LABEL_149;
            if ( (*(_WORD *)activatableClassHelper._machineInvalidProperties & 0x100) == 0 )
            {
              if ( (v108 & 0x100) != 0 )
              {
                v36 = -2147024883;
                ActivationType = -2147024883;
                if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                  && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                {
LABEL_115:
                  if ( v36 != -2147024894 )
                  {
                    dllPath.Unexpanded.hstr_ = 0;
                    LOWORD(propertyStore.MapView.ptr_) = 0;
                    v38 = LoadStringResource(
                            0x14BCu,
                            (const wchar_t *)v28,
                            (const wchar_t **)&dllPath,
                            (unsigned __int16 *)&propertyStore);
                    v32 = v36;
                    if ( v38 >= 0 )
                    {
                      RoOriginateErrorW(
                        v36,
                        LOWORD(propertyStore.MapView.ptr_),
                        (const wchar_t *)dllPath.Unexpanded.hstr_);
LABEL_107:
                      if ( ActivationType < 0 )
                        goto LABEL_351;
                      goto LABEL_119;
                    }
LABEL_106:
                    RoOriginateError(v32, 0);
                    goto LABEL_107;
                  }
LABEL_118:
                  InitOnceExecuteOnce(
                    &stru_18031B5D8,
                    DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck,
                    0,
                    0);
                  this->_activateInSharedBroker = !g_isPerAppBrokerInstancingDefaultForActivation;
LABEL_119:
                  if ( this->_registrationScope )
                    goto LABEL_149;
                  p_activateInBrokerForMediumILContainer = &this->_activateInBrokerForMediumILContainer;
                  ActivateInBrokerForMediumILContainer = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetActivateInBrokerForMediumILContainer(
                                                           (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                                                           &this->_activateInBrokerForMediumILContainer);
                  v41 = (const wchar_t *)(unsigned int)gfEnableTracing;
                  ActivationType = ActivateInBrokerForMediumILContainer;
                  if ( ActivateInBrokerForMediumILContainer != -2147024894 )
                    goto LABEL_123;
                  if ( !gfEnableTracing )
                    goto LABEL_135;
                  if ( !IsWppLevelEnabled(VERBOSE) )
                  {
LABEL_123:
                    if ( ActivationType >= 0 )
                    {
                      if ( !(_DWORD)v41 || !IsWppLevelEnabled(VERBOSE) )
                        goto LABEL_139;
                    }
                    else
                    {
                      if ( ActivationType == -2147024894 )
                        goto LABEL_135;
                      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                        && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                      {
LABEL_128:
                        if ( ActivationType == -2147024882 )
                          goto LABEL_143;
                        dllPath.Unexpanded.hstr_ = 0;
                        LOWORD(propertyStore.MapView.ptr_) = 0;
                        v42 = LoadStringResource(
                                0x14BFu,
                                v41,
                                (const wchar_t **)&dllPath,
                                (unsigned __int16 *)&propertyStore);
                        v43 = ActivationType;
                        if ( v42 >= 0 )
                        {
                          RoOriginateErrorW(
                            ActivationType,
                            LOWORD(propertyStore.MapView.ptr_),
                            (const wchar_t *)dllPath.Unexpanded.hstr_);
                          goto LABEL_143;
                        }
                        goto LABEL_142;
                      }
                    }
                  }
                  LODWORD(v101) = ActivationType;
                  LODWORD(level) = *p_activateInBrokerForMediumILContainer;
                  LODWORD(file) = this->_registrationScope;
                  ComTraceHr(
                    ActivationType,
                    "onecore\\com\\combase\\catalog\\storecat.cxx",
                    "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                    1530,
                    L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Activ"
                     "ateInBrokerForMediumILContainer (%d): %!HRESULT!",
                    activatableClassId,
                    file,
                    level,
                    v101);
                  if ( ActivationType < 0 )
                  {
                    if ( ActivationType != -2147024894 )
                      goto LABEL_128;
LABEL_135:
                    *p_activateInBrokerForMediumILContainer = 0;
LABEL_136:
                    if ( this->_registrationScope == RegistrationScope_PerMachine )
                    {
                      ActivateOnHostFlags = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetActivateOnHostFlags(
                                              (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                                              &this->_activateOnHostFlags);
                      ActivationType = ActivateOnHostFlags;
                      if ( ActivateOnHostFlags < 0 )
                      {
                        v45 = ActivateOnHostFlags;
                        v46 = 1557;
LABEL_145:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          v46,
                          "onecore\\com\\combase\\catalog\\storecat.cxx",
                          v45);
                        goto LABEL_351;
                      }
                      if ( this->_activateOnHostFlags && this->_activationType != ActivationType_OutOfProcess )
                      {
                        wil::details::in1diag3::Return_HrMsg(
                          retaddr,
                          0x61Du,
                          "onecore\\com\\combase\\catalog\\storecat.cxx",
                          -2147221165,
                          "ActivatableClassId entry %ws specifies ActivateOnHostFlags but is not ActivationType_OutOfProcess",
                          activatableClassId);
                        ActivationType = -2147221165;
                        goto LABEL_351;
                      }
                    }
LABEL_149:
                    *(_QWORD *)&dllPath.IsExpandable = 0;
                    v48 = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetDllPath(
                            (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                            (ExpandableString *)&dllPath.IsExpandable);
                    v49 = (unsigned int)this->_activationType;
                    v50 = 0;
                    v51 = gfEnableTracing;
                    ActivationType = v48;
                    if ( (_DWORD)v49 && v48 == -2147024894 )
                    {
                      if ( !gfEnableTracing )
                      {
LABEL_154:
                        v49 = (unsigned int)-(int)v49;
                        if ( ActivationType == ((_DWORD)v49 != 0 ? 0x80070002 : 0)
                          || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                          && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                        {
                          goto LABEL_163;
                        }
                        goto LABEL_158;
                      }
                      if ( IsWppLevelEnabled(VERBOSE) )
                      {
LABEL_158:
                        StringRawBuffer = 0;
                        goto LABEL_162;
                      }
                    }
                    if ( ActivationType >= 0 )
                    {
                      if ( !v51 || !IsWppLevelEnabled(VERBOSE) )
                        goto LABEL_172;
                      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&dllPath.IsExpandable, 0);
LABEL_162:
                      LODWORD(v101) = ActivationType;
                      LODWORD(file) = this->_registrationScope;
                      ComTraceHr(
                        ActivationType,
                        "onecore\\com\\combase\\catalog\\storecat.cxx",
                        "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                        1579,
                        L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property D"
                         "llPath (%ws): %!HRESULT!",
                        activatableClassId,
                        file,
                        StringRawBuffer,
                        v101);
                      if ( ActivationType < 0 )
                      {
LABEL_163:
                        if ( ActivationType == -2147024894 )
                        {
                          if ( this->_activationType == ActivationType_InProcess )
                          {
                            dllPath.Unexpanded.hstr_ = 0;
                            LOWORD(propertyStore.MapView.ptr_) = 0;
                            ActivationType = -2147221165;
                            if ( LoadStringResource(
                                   0x1458u,
                                   (const wchar_t *)v49,
                                   (const wchar_t **)&dllPath,
                                   (unsigned __int16 *)&propertyStore) < 0 )
                              RoOriginateError(-2147221165, 0);
                            else
                              RoOriginateErrorW(
                                -2147221165,
                                LOWORD(propertyStore.MapView.ptr_),
                                (const wchar_t *)dllPath.Unexpanded.hstr_);
                            goto LABEL_185;
                          }
                          goto LABEL_186;
                        }
                        if ( ActivationType != -2147024882 )
                        {
                          dllPath.Unexpanded.hstr_ = 0;
                          LOWORD(propertyStore.MapView.ptr_) = 0;
                          if ( LoadStringResource(
                                 0x1459u,
                                 (const wchar_t *)v49,
                                 (const wchar_t **)&dllPath,
                                 (unsigned __int16 *)&propertyStore) < 0 )
                            RoOriginateError(ActivationType, 0);
                          else
                            RoOriginateErrorW(
                              ActivationType,
                              LOWORD(propertyStore.MapView.ptr_),
                              (const wchar_t *)dllPath.Unexpanded.hstr_);
                        }
LABEL_184:
                        if ( ActivationType < 0 )
                        {
LABEL_185:
                          OpaqueString::~OpaqueString((OpaqueString *)&dllPath.IsExpandable);
                          goto LABEL_351;
                        }
LABEL_186:
                        propertyStore.MapView.ptr_ = 0;
                        ServerName = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetServerName(
                                       (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                                       (OpaqueString *)&propertyStore);
                        v56 = (unsigned int)this->_activationType;
                        ActivationType = ServerName;
                        ptr = propertyStore.MapView.ptr_;
                        v58 = gfEnableTracing;
                        if ( (_DWORD)v56 != 1 && ServerName == -2147024894 )
                        {
                          if ( !gfEnableTracing )
                          {
LABEL_191:
                            v56 = (unsigned int)(1 - v56);
                            if ( ActivationType == ((_DWORD)v56 != 0 ? 0x80070002 : 0)
                              || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                              && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                            {
LABEL_201:
                              if ( ActivationType == -2147024894 )
                              {
                                if ( this->_activationType == ActivationType_OutOfProcess )
                                {
                                  dllPath.Unexpanded.hstr_ = 0;
                                  LOWORD(propertyStore.MapView.ptr_) = 0;
                                  ActivationType = -2147221165;
                                  if ( LoadStringResource(
                                         0x145Du,
                                         (const wchar_t *)v56,
                                         (const wchar_t **)&dllPath,
                                         (unsigned __int16 *)&propertyStore) < 0 )
                                  {
                                    RoOriginateError(-2147221165, 0);
                                    goto LABEL_231;
                                  }
LABEL_204:
                                  RoOriginateErrorW(
                                    -2147221165,
                                    LOWORD(propertyStore.MapView.ptr_),
                                    (const wchar_t *)dllPath.Unexpanded.hstr_);
LABEL_231:
                                  WindowsDeleteString((HSTRING)ptr);
                                  goto LABEL_185;
                                }
LABEL_256:
                                if ( !IsGetEndPointMapperCrossVmPipeNamespacePresent()
                                  || (unsigned int)RemoteWinRTActivation() != 1
                                  || this->_registrationScope )
                                {
                                  this->_remoteServerName = 0;
                                  goto LABEL_300;
                                }
                                propertyStore.MapView.ptr_ = 0;
                                if ( (activatableClassHelper._machineInvalidProperties[0] & 0x40) == 0 )
                                {
                                  if ( (v108 & 0x40) != 0 )
                                  {
                                    ActivationType = -2147024883;
LABEL_265:
                                    v81 = (unsigned int)this->_activationType;
                                    v82 = gfEnableTracing;
                                    if ( (_DWORD)v81 != 2 && ActivationType == -2147024894 )
                                    {
                                      if ( !gfEnableTracing )
                                      {
LABEL_270:
                                        v81 = (unsigned int)(2 - v81);
                                        if ( ActivationType == ((_DWORD)v81 != 0 ? 0x80070002 : 0)
                                          || !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                          && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                                        {
                                          goto LABEL_279;
                                        }
                                        goto LABEL_274;
                                      }
                                      if ( IsWppLevelEnabled(VERBOSE) )
                                      {
LABEL_274:
                                        v83 = 0;
                                        goto LABEL_278;
                                      }
                                    }
                                    if ( ActivationType >= 0 )
                                    {
                                      if ( !v82 || !IsWppLevelEnabled(VERBOSE) )
                                        goto LABEL_287;
                                      v83 = WindowsGetStringRawBuffer((HSTRING)v50, 0);
LABEL_278:
                                      LODWORD(v101) = ActivationType;
                                      LODWORD(file) = this->_registrationScope;
                                      ComTraceHr(
                                        ActivationType,
                                        "onecore\\com\\combase\\catalog\\storecat.cxx",
                                        "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                        1782,
                                        L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationSc"
                                         "ope!, property RemoteServerName (%ws): %!HRESULT!",
                                        strRef,
                                        file,
                                        v83,
                                        v101);
                                      if ( ActivationType < 0 )
                                      {
LABEL_279:
                                        if ( ActivationType == -2147024894 )
                                        {
                                          if ( this->_activationType == ActivationType_RemoteProcess )
                                          {
                                            dllPath.Unexpanded.hstr_ = 0;
                                            LOWORD(propertyStore.MapView.ptr_) = 0;
                                            ActivationType = -2147221165;
                                            if ( LoadStringResource(
                                                   0x14B7u,
                                                   (const wchar_t *)v81,
                                                   (const wchar_t **)&dllPath,
                                                   (unsigned __int16 *)&propertyStore) < 0 )
                                              RoOriginateError(-2147221165, 0);
                                            else
                                              RoOriginateErrorW(
                                                -2147221165,
                                                LOWORD(propertyStore.MapView.ptr_),
                                                (const wchar_t *)dllPath.Unexpanded.hstr_);
                                            goto LABEL_297;
                                          }
LABEL_298:
                                          WindowsDeleteString((HSTRING)v50);
LABEL_300:
                                          if ( this->_registrationScope )
                                            goto LABEL_313;
                                          if ( (char)activatableClassHelper._machineInvalidProperties[0] < 0 )
                                            goto LABEL_317;
                                          if ( (v108 & 0x80u) != 0LL )
                                          {
                                            ActivationType = -2147024883;
                                            if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                              && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                                            {
LABEL_324:
                                              if ( v25 == -2147024894 )
                                                goto LABEL_313;
                                              dllPath.Unexpanded.hstr_ = 0;
                                              LOWORD(propertyStore.MapView.ptr_) = 0;
                                              v91 = LoadStringResource(
                                                      0x14BAu,
                                                      v80,
                                                      (const wchar_t **)&dllPath,
                                                      (unsigned __int16 *)&propertyStore);
                                              v87 = v25;
                                              if ( v91 >= 0 )
                                              {
                                                RoOriginateErrorW(
                                                  v25,
                                                  LOWORD(propertyStore.MapView.ptr_),
                                                  (const wchar_t *)dllPath.Unexpanded.hstr_);
LABEL_312:
                                                if ( ActivationType < 0 )
                                                  goto LABEL_231;
LABEL_313:
                                                v88 = pRegistrationStore;
                                                if ( activatableClassHandle )
                                                {
                                                  v89 = pRegistrationStore->GetRefreshPolicyForActivatableClassEntry(
                                                          pRegistrationStore,
                                                          activatableClassHandle,
                                                          &this->_registrationRefreshPolicy);
                                                  ActivationType = v89;
                                                  if ( v89 < 0 )
                                                  {
                                                    v90 = 1869;
LABEL_316:
                                                    wil::details::in1diag3::Return_Hr(
                                                      retaddr,
                                                      v90,
                                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                      v89);
                                                    goto LABEL_231;
                                                  }
                                                  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
                                                    ComTraceMessageT<unsigned int>(
                                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                      "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                                      1870,
                                                      v92,
                                                      L"GetRefreshPolicy result is %d",
                                                      this->_registrationRefreshPolicy);
                                                }
                                                if ( this->_registrationScope == RegistrationScope_PerUser )
                                                {
                                                  v89 = v88->GetLastWriteTimeForActivatableClassEntry(
                                                          v88,
                                                          activatableClassHandle,
                                                          &this->_lLastWriteTime);
                                                  ActivationType = v89;
                                                  if ( v89 < 0 )
                                                  {
                                                    v90 = 1876;
                                                    goto LABEL_316;
                                                  }
                                                  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
                                                    ComTraceMessageT<void *>(
                                                      "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                      "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                                      1878,
                                                      v93,
                                                      L"GetLastWriteTime result is %!TIME!",
                                                      (wchar_t *)this->_lLastWriteTime);
                                                }
                                                if ( !g_bInSCM )
                                                {
                                                  propertyStore.MapView.ptr_ = 0;
                                                  Attributes = CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetAttributes(
                                                                 (CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *)&activatableClassHelper._userProperties,
                                                                 &propertyStore);
                                                  ActivationType = Attributes;
                                                  if ( Attributes < 0 )
                                                  {
                                                    if ( Attributes != -2147024894 )
                                                    {
LABEL_340:
                                                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&propertyStore);
                                                      goto LABEL_231;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    ActivationType = EntryPropertyStore::ForceToMemory(&propertyStore);
                                                    if ( ActivationType < 0 )
                                                      goto LABEL_340;
                                                    ActivationType = propertyStore.MapView.ptr_->QueryInterface(
                                                                       propertyStore.MapView.ptr_,
                                                                       &GUID_00000000_0000_0000_c000_000000000046,
                                                                       (void **)&this->_pAttributes);
                                                    if ( ActivationType < 0 )
                                                      goto LABEL_340;
                                                  }
                                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&propertyStore);
                                                }
                                                if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
                                                {
                                                  if ( this->_pAttributes )
                                                  {
                                                    line = "exist";
                                                  }
                                                  else
                                                  {
                                                    line = "do not exist";
                                                    v96 = "ignored";
                                                    if ( (_DWORD)v95 )
                                                      line = "ignored";
                                                  }
                                                  ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,enum Windows::Foundation::ActivationType,enum Windows::Foundation::ThreadingType,enum TrustLevel,enum Windows::Foundation::ActivateAsUser,unsigned short *,char const *,int,__int64>(
                                                    (const char *)this->_lLastWriteTime,
                                                    v95,
                                                    this->_registrationRefreshPolicy,
                                                    (TraceLevel)v96,
                                                    format,
                                                    strRef,
                                                    this->_registrationScope,
                                                    this->_activationType,
                                                    this->_threadingModel,
                                                    this->_trustLevel,
                                                    this->_activateAsUser,
                                                    this->_dllPath,
                                                    line,
                                                    this->_registrationRefreshPolicy,
                                                    this->_lLastWriteTime);
                                                }
                                                WindowsDeleteString((HSTRING)ptr);
                                                OpaqueString::~OpaqueString((OpaqueString *)&dllPath.IsExpandable);
                                                ActivationType = 0;
                                                goto LABEL_351;
                                              }
LABEL_311:
                                              RoOriginateError(v87, 0);
                                              goto LABEL_312;
                                            }
                                            goto LABEL_308;
                                          }
                                          if ( activatableClassHelper._machineProperties.ActivateInSharedBroker.Present )
                                          {
                                            v25 = 0;
                                            this->_activateAsUser = *(_DWORD *)(&activatableClassHelper._machineProperties.ActivateInBrokerForMediumILContainer
                                                                              + 1);
                                            ActivationType = 0;
                                          }
                                          else
                                          {
LABEL_317:
                                            ActivationType = -2147024894;
                                            v25 = -2147024894;
                                            if ( !gfEnableTracing )
                                              goto LABEL_313;
                                            if ( IsWppLevelEnabled(VERBOSE) )
                                            {
LABEL_308:
                                              LODWORD(v101) = v25;
                                              LODWORD(level) = this->_activateAsUser;
                                              LODWORD(file) = this->_registrationScope;
                                              ComTraceHr(
                                                v25,
                                                "onecore\\com\\combase\\catalog\\storecat.cxx",
                                                "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                                1838,
                                                L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::Regist"
                                                 "rationScope!, property ActivateAsUser (%d): %!HRESULT!",
                                                strRef,
                                                file,
                                                level,
                                                v101);
                                              if ( v25 < 0 )
                                                goto LABEL_324;
LABEL_309:
                                              if ( this->_trustLevel == PartialTrust )
                                                goto LABEL_312;
                                              dllPath.Unexpanded.hstr_ = 0;
                                              LOWORD(propertyStore.MapView.ptr_) = 0;
                                              ActivationType = -2147221165;
                                              v86 = LoadStringResource(
                                                      0x14B9u,
                                                      v80,
                                                      (const wchar_t **)&dllPath,
                                                      (unsigned __int16 *)&propertyStore);
                                              v87 = -2147221165;
                                              if ( v86 >= 0 )
                                                goto LABEL_204;
                                              goto LABEL_311;
                                            }
                                            if ( (int)v80 < 0 )
                                              goto LABEL_324;
                                          }
                                          if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
                                            goto LABEL_309;
                                          goto LABEL_308;
                                        }
                                        dllPath.Unexpanded.hstr_ = 0;
                                        LOWORD(propertyStore.MapView.ptr_) = 0;
                                        if ( LoadStringResource(
                                               0x14B8u,
                                               (const wchar_t *)v81,
                                               (const wchar_t **)&dllPath,
                                               (unsigned __int16 *)&propertyStore) < 0 )
                                          RoOriginateError(ActivationType, 0);
                                        else
                                          RoOriginateErrorW(
                                            ActivationType,
                                            LOWORD(propertyStore.MapView.ptr_),
                                            (const wchar_t *)dllPath.Unexpanded.hstr_);
LABEL_296:
                                        if ( ActivationType < 0 )
                                        {
LABEL_297:
                                          WindowsDeleteString((HSTRING)v50);
                                          goto LABEL_231;
                                        }
                                        goto LABEL_298;
                                      }
LABEL_287:
                                      if ( this->_activationType != ActivationType_RemoteProcess )
                                      {
                                        dllPath.Unexpanded.hstr_ = 0;
                                        LOWORD(propertyStore.MapView.ptr_) = 0;
                                        ActivationType = -2147221165;
                                        if ( LoadStringResource(
                                               0x14B6u,
                                               (const wchar_t *)v81,
                                               (const wchar_t **)&dllPath,
                                               (unsigned __int16 *)&propertyStore) < 0 )
                                          RoOriginateError(-2147221165, 0);
                                        else
                                          RoOriginateErrorW(
                                            -2147221165,
                                            LOWORD(propertyStore.MapView.ptr_),
                                            (const wchar_t *)dllPath.Unexpanded.hstr_);
                                        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                          || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                                        {
                                          ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                            v84,
                                            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                            1795,
                                            ERRORS,
                                            L"ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationSco"
                                             "pe!, local but has remote server name",
                                            strRef,
                                            this->_registrationScope);
                                        }
                                        goto LABEL_297;
                                      }
                                      v85 = WindowsGetStringRawBuffer((HSTRING)v50, 0);
                                      ActivationType = DuplicatePWSTR(v85, &this->_remoteServerName);
                                      goto LABEL_296;
                                    }
                                    goto LABEL_270;
                                  }
                                  if ( LOBYTE(activatableClassHelper._machineProperties.RemoteServer.Value.hstr_) )
                                  {
                                    ActivationType = 0;
                                    OpaqueString::operator=(
                                      (OpaqueString *)&propertyStore,
                                      (const OpaqueString *)&activatableClassHelper._machineProperties.ActivateAsUser);
                                    v50 = propertyStore.MapView.ptr_;
                                    goto LABEL_265;
                                  }
                                }
                                ActivationType = -2147024894;
                                goto LABEL_265;
                              }
LABEL_255:
                              if ( ActivationType < 0 )
                                goto LABEL_231;
                              goto LABEL_256;
                            }
                            goto LABEL_195;
                          }
                          if ( IsWppLevelEnabled(VERBOSE) )
                          {
LABEL_195:
                            v59 = 0;
                            goto LABEL_199;
                          }
                        }
                        if ( ActivationType >= 0 )
                        {
                          if ( !v58 || !IsWppLevelEnabled(VERBOSE) )
                          {
                            v60 = strRef;
                            goto LABEL_207;
                          }
                          v59 = WindowsGetStringRawBuffer((HSTRING)ptr, 0);
LABEL_199:
                          v60 = strRef;
                          LODWORD(v101) = ActivationType;
                          LODWORD(file) = this->_registrationScope;
                          ComTraceHr(
                            ActivationType,
                            "onecore\\com\\combase\\catalog\\storecat.cxx",
                            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                            1633,
                            L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, proper"
                             "ty Server (%ws): %!HRESULT!",
                            strRef,
                            file,
                            v59,
                            v101);
                          if ( ActivationType < 0 )
                          {
                            v50 = 0;
                            goto LABEL_201;
                          }
LABEL_207:
                          if ( this->_activationType == ActivationType_InProcess )
                          {
                            dllPath.Unexpanded.hstr_ = 0;
                            LOWORD(propertyStore.MapView.ptr_) = 0;
                            ActivationType = -2147221165;
                            if ( LoadStringResource(
                                   0x145Au,
                                   (const wchar_t *)v56,
                                   (const wchar_t **)&dllPath,
                                   (unsigned __int16 *)&propertyStore) < 0 )
                              RoOriginateError(-2147221165, 0);
                            else
                              RoOriginateErrorW(
                                -2147221165,
                                LOWORD(propertyStore.MapView.ptr_),
                                (const wchar_t *)dllPath.Unexpanded.hstr_);
                            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                              || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                            {
                              ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                                v61,
                                "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                                1646,
                                ERRORS,
                                L"ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, inproc but has Server",
                                v60,
                                this->_registrationScope);
                            }
                            goto LABEL_231;
                          }
                          v62 = pWinRTCatalogCallback;
                          m_ptr = this->_pServerInfo.m_ptr;
                          v64 = pWinRTCatalogCallback->__vftable;
                          this->_pServerInfo.m_ptr = 0;
                          GetServerInfo = v64->GetServerInfo;
                          if ( m_ptr )
                            m_ptr->Release(m_ptr);
                          v66 = WindowsGetStringRawBuffer((HSTRING)ptr, 0);
                          HIDWORD(level) = 0;
                          file = &this->_pServerInfo;
                          format = packageMoniker;
                          ActivationType = ((__int64 (__fastcall *)(IWinRTCatalogInternal *, _QWORD, IUserToken *, PCWSTR))GetServerInfo)(
                                             v62,
                                             v111,
                                             userToken,
                                             v66);
                          if ( ActivationType >= 0 )
                          {
                            if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
                              goto LABEL_232;
                          }
                          else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                          {
LABEL_225:
                            if ( ActivationType == -2147221164 )
                            {
                              dllPath.Unexpanded.hstr_ = 0;
                              LOWORD(propertyStore.MapView.ptr_) = 0;
                              if ( LoadStringResource(
                                     0x145Bu,
                                     v67,
                                     (const wchar_t **)&dllPath,
                                     (unsigned __int16 *)&propertyStore) < 0 )
                                RoOriginateError(-2147221165, 0);
                              else
                                RoOriginateErrorW(
                                  -2147221165,
                                  LOWORD(propertyStore.MapView.ptr_),
                                  (const wchar_t *)dllPath.Unexpanded.hstr_);
                              WindowsDeleteString((HSTRING)ptr);
                              OpaqueString::~OpaqueString((OpaqueString *)&dllPath.IsExpandable);
                              ActivationType = -2147221165;
                              goto LABEL_351;
                            }
                            if ( ActivationType < 0 )
                              goto LABEL_231;
LABEL_232:
                            dwServerRegistrationScope.ptr_ = 0;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&dwServerRegistrationScope);
                            CWinRTActivationStoreCatalog::CRuntimeClassInfo::GetProcess(
                              (CWinRTActivationStoreCatalog::CRuntimeClassInfo *)&this->IClassClassicInfoImpl,
                              &GUID_5868bd9b_be16_4c83_a560_0121173c48f1,
                              (void **)&dwServerRegistrationScope.ptr_);
                            trustLevel = 0;
                            ((void (__fastcall *)(IMetaDataImport2 *, unsigned int *))dwServerRegistrationScope.ptr_->EnumMethods)(
                              dwServerRegistrationScope.ptr_,
                              &trustLevel);
                            v69 = trustLevel;
                            if ( trustLevel == this->_registrationScope )
                            {
                              LODWORD(propertyStore.MapView.ptr_) = 0;
                              ((void (__fastcall *)(IMetaDataImport2 *, EntryPropertyStore *))dwServerRegistrationScope.ptr_->EnumMembers)(
                                dwServerRegistrationScope.ptr_,
                                &propertyStore);
                              if ( !LODWORD(propertyStore.MapView.ptr_) )
                                this->_isNormalExe = 1;
                            }
                            else
                            {
                              dllPath.Unexpanded.hstr_ = 0;
                              LOWORD(propertyStore.MapView.ptr_) = 0;
                              ActivationType = -2147221165;
                              if ( LoadStringResource(
                                     0x145Cu,
                                     v68,
                                     (const wchar_t **)&dllPath,
                                     (unsigned __int16 *)&propertyStore) < 0 )
                                RoOriginateError(-2147221165, 0);
                              else
                                RoOriginateErrorW(
                                  -2147221165,
                                  LOWORD(propertyStore.MapView.ptr_),
                                  (const wchar_t *)dllPath.Unexpanded.hstr_);
                              if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                                || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                              {
                                registrationScope = this->_registrationScope;
                                function = WindowsGetStringRawBuffer((HSTRING)ptr, 0);
                                ComTraceMessageT<unsigned short const *,unsigned short const *,enum Windows::Foundation::RegistrationScope,enum Windows::Foundation::RegistrationScope>(
                                  (const char *)strRef,
                                  v72,
                                  v73,
                                  v74,
                                  format,
                                  function,
                                  strRef,
                                  registrationScope,
                                  v69);
                              }
                            }
                            if ( g_bInSCM )
                              goto LABEL_254;
                            if ( activatableClassHelper._userProperties.ActivationType == ActivationType_InProcess )
                              goto LABEL_254;
                            if ( (BYTE1(activatableClassHelper._machineProperties.ActivationType)
                                & (unsigned __int8)-(LOBYTE(activatableClassHelper._machineProperties.ActivationType) != 0)) == 0 )
                              goto LABEL_254;
                            LODWORD(propertyStore.MapView.ptr_) = 0;
                            ((void (__fastcall *)(IMetaDataImport2 *, EntryPropertyStore *))dwServerRegistrationScope.ptr_->GetTypeDefProps)(
                              dwServerRegistrationScope.ptr_,
                              &propertyStore);
                            if ( LODWORD(propertyStore.MapView.ptr_) != 2 )
                              goto LABEL_254;
                            activatableClassHelper._scope = RegistrationScope_PerMachine;
                            dllPath.Unexpanded.hstr_ = 0;
                            v75 = dwServerRegistrationScope.ptr_;
                            QueryInterface = dwServerRegistrationScope.ptr_->QueryInterface;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&dllPath);
                            QueryInterface(
                              v75,
                              &GUID_6c41cb64_51a5_4177_b4ae_3e1d2e3f0157,
                              (void **)&dllPath.Unexpanded.hstr_);
                            (*(void (__fastcall **)(HSTRING__ *, CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper *))(*(_QWORD *)dllPath.Unexpanded.hstr_ + 32LL))(
                              dllPath.Unexpanded.hstr_,
                              &activatableClassHelper);
                            v106 = 0;
                            (*(void (__fastcall **)(HSTRING__ *, int *))(*(_QWORD *)dllPath.Unexpanded.hstr_ + 24LL))(
                              dllPath.Unexpanded.hstr_,
                              &v106);
                            v77 = v106;
                            AppModelPolicyValue = ProcessToken::GetAppModelPolicyValue(
                                                    v78,
                                                    AppModelPolicy_Type_LifecycleManager);
                            if ( (unsigned int)(v77 - 1) > 1
                              || AppModelPolicyValue == AppModelPolicy_LifecycleManager_Unmanaged )
                            {
                              if ( v77 || AppModelPolicyValue == AppModelPolicy_LifecycleManager_ManagedByPLM )
                                goto LABEL_253;
                              ActivationType = -2147483615;
                            }
                            else
                            {
                              ActivationType = -2147483616;
                            }
                            RoOriginateError(ActivationType, 0);
LABEL_253:
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&dllPath);
LABEL_254:
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&dwServerRegistrationScope);
                            v50 = 0;
                            goto LABEL_255;
                          }
                          WindowsGetStringRawBuffer((HSTRING)ptr, 0);
                          HIDWORD(file) = HIDWORD(strRef);
                          ComTraceHr(
                            ActivationType,
                            "onecore\\com\\combase\\catalog\\storecat.cxx",
                            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                            1661,
                            L"GetServerInfo(%ws) for ActivatableClassId entry %ws in scope %!Windows::Foundation::Registra"
                             "tionScope!: %!HRESULT!");
                          goto LABEL_225;
                        }
                        goto LABEL_191;
                      }
LABEL_172:
                      if ( this->_activationType )
                      {
                        dllPath.Unexpanded.hstr_ = 0;
                        LOWORD(propertyStore.MapView.ptr_) = 0;
                        ActivationType = -2147221165;
                        if ( LoadStringResource(
                               0x1457u,
                               (const wchar_t *)v49,
                               (const wchar_t **)&dllPath,
                               (unsigned __int16 *)&propertyStore) < 0 )
                          RoOriginateError(-2147221165, 0);
                        else
                          RoOriginateErrorW(
                            -2147221165,
                            LOWORD(propertyStore.MapView.ptr_),
                            (const wchar_t *)dllPath.Unexpanded.hstr_);
                        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                          || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                        {
                          ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
                            v53,
                            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
                            1592,
                            ERRORS,
                            L"ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, outofproc but has DllPath",
                            activatableClassId,
                            this->_registrationScope);
                        }
                        goto LABEL_185;
                      }
                      if ( activatableClassHelper._userProperties.ActivationType )
                        v54 = LOBYTE(activatableClassHelper._userProperties.Threading.Value) != 0
                            ? BYTE1(activatableClassHelper._userProperties.Threading.Value)
                            : 0;
                      else
                        v54 = 0;
                      ActivationType = GetAbsoluteExpandedPathAsPWSTR(
                                         (const ExpandableString *)&dllPath.IsExpandable,
                                         v54,
                                         packageMoniker,
                                         userToken,
                                         &this->_dllPath);
                      goto LABEL_184;
                    }
                    goto LABEL_154;
                  }
LABEL_139:
                  if ( this->_trustLevel == PartialTrust )
                    goto LABEL_143;
                  dllPath.Unexpanded.hstr_ = 0;
                  LOWORD(propertyStore.MapView.ptr_) = 0;
                  ActivationType = -2147221165;
                  v47 = LoadStringResource(0x14BEu, v41, (const wchar_t **)&dllPath, (unsigned __int16 *)&propertyStore);
                  v43 = -2147221165;
                  if ( v47 >= 0 )
                  {
                    RoOriginateErrorW(
                      -2147221165,
                      LOWORD(propertyStore.MapView.ptr_),
                      (const wchar_t *)dllPath.Unexpanded.hstr_);
LABEL_144:
                    v45 = ActivationType;
                    v46 = 1550;
                    goto LABEL_145;
                  }
LABEL_142:
                  RoOriginateError(v43, 0);
LABEL_143:
                  if ( ActivationType < 0 )
                    goto LABEL_144;
                  goto LABEL_136;
                }
                goto LABEL_103;
              }
              if ( activatableClassHelper._machineProperties.Permissions.Present )
              {
                v36 = 0;
                this->_activateInSharedBroker = *(&activatableClassHelper._machineProperties.Permissions.Present + 1);
                ActivationType = 0;
                if ( !v29 || !IsWppLevelEnabled(VERBOSE) )
                  goto LABEL_104;
                goto LABEL_103;
              }
            }
            ActivationType = -2147024894;
            v36 = -2147024894;
            if ( !v29 || !IsWppLevelEnabled(VERBOSE) )
              goto LABEL_118;
LABEL_103:
            LODWORD(v101) = v36;
            LODWORD(level) = this->_activateInSharedBroker;
            LODWORD(file) = this->_registrationScope;
            ComTraceHr(
              v36,
              "onecore\\com\\combase\\catalog\\storecat.cxx",
              "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
              1489,
              L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property ActivateInS"
               "haredBroker (%d): %!HRESULT!",
              activatableClassId,
              file,
              level,
              v101);
            if ( v36 < 0 )
              goto LABEL_115;
LABEL_104:
            if ( this->_trustLevel == PartialTrust )
              goto LABEL_107;
            dllPath.Unexpanded.hstr_ = 0;
            LOWORD(propertyStore.MapView.ptr_) = 0;
            ActivationType = -2147221165;
            v37 = LoadStringResource(
                    0x14BBu,
                    (const wchar_t *)v28,
                    (const wchar_t **)&dllPath,
                    (unsigned __int16 *)&propertyStore);
            v32 = -2147221165;
            if ( v37 >= 0 )
            {
LABEL_33:
              RoOriginateErrorW(v32, LOWORD(propertyStore.MapView.ptr_), (const wchar_t *)dllPath.Unexpanded.hstr_);
              goto LABEL_351;
            }
            goto LABEL_106;
          }
        }
        goto LABEL_80;
      }
      if ( !LOBYTE(activatableClassHelper._machineProperties.Permissions.Value._pSecurityDescriptor) )
      {
LABEL_87:
        ActivationType = v28;
        if ( !v29 )
          goto LABEL_83;
        if ( IsWppLevelEnabled(VERBOSE) )
        {
LABEL_80:
          LODWORD(v101) = ActivationType;
          LODWORD(file) = this->_registrationScope;
          ComTraceHr(
            ActivationType,
            "onecore\\com\\combase\\catalog\\storecat.cxx",
            "CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct",
            1453,
            L"Read ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!, property Permissions (%d): %!HRESULT!",
            activatableClassId,
            file,
            this->_permissions.pBlobData,
            v101);
          if ( ActivationType < 0 )
          {
            v29 = gfEnableTracing;
            goto LABEL_96;
          }
LABEL_81:
          *(_DWORD *)&dllPath.IsExpandable = p_cbSecurityDescriptor[4];
          *((_DWORD *)&dllPath.IsExpandable + 1) = 0;
          serverInfo.ptr_ = *(IWinRTServerInfo **)p_cbSecurityDescriptor;
          ActivationType = AutoBlob::Initialize(&this->_permissions, (const tagBLOB *)&dllPath.IsExpandable);
          if ( ActivationType < 0 )
            goto LABEL_351;
          v29 = gfEnableTracing;
          goto LABEL_83;
        }
        if ( (int)v28 < 0 )
          goto LABEL_96;
      }
      else
      {
        ActivationType = 0;
        p_cbSecurityDescriptor = &activatableClassHelper._machineProperties.Permissions.Value._cbSecurityDescriptor;
      }
      if ( !v29 || !IsWppLevelEnabled(VERBOSE) )
        goto LABEL_81;
      goto LABEL_80;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f5d34  mov     rax, rsp
0x1800f5d37  mov     [rax+20h], activatableClassId
0x1800f5d3b  mov     [rax+18h], pUserToken
0x1800f5d3f  mov     [rax+10h], dwCatalogFlags
0x1800f5d42  push    rbp
0x1800f5d43  push    rbx
0x1800f5d44  push    rsi
0x1800f5d45  push    rdi
0x1800f5d46  push    r12
0x1800f5d48  push    r13
0x1800f5d4a  push    r14
0x1800f5d4c  push    r15
0x1800f5d4e  lea     rbp, [rax-0F8h]
0x1800f5d55  sub     rsp, 1B8h
0x1800f5d5c  mov     r15, this
0x1800f5d5f  lea     rdx, [rbp+0F0h+strRef]; strRef
0x1800f5d66  add     this, 48h ; 'H'; this
0x1800f5d6a  mov     rdi, activatableClassId
0x1800f5d6d  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800f5d72  xor     esi, esi
0x1800f5d74  test    eax, eax
0x1800f5d76  js      loc_1800F77AD
0x1800f5d7c  mov     rbx, [rbp+0F0h+arg_30]
0x1800f5d83  mov     this, rbx
0x1800f5d86  mov     rax, [rbx]
0x1800f5d89  mov     rax, [rax+18h]
0x1800f5d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5d92  mov     [r15+90h], eax
0x1800f5d99  cmp     eax, 1
0x1800f5d9c  jnz     short loc_1800F5DA3
0x1800f5d9e  call    ?IsAppContainer@ProcessToken@@QEAA_NXZ; ProcessToken::IsAppContainer(void)
0x1800f5da3  cmp     [rbp+0F0h+packageFullName], rsi
0x1800f5daa  jz      short loc_1800F5DC4
0x1800f5dac  lea     this, [r15+60h]; this
0x1800f5db0  lea     rdx, [rbp+0F0h+packageFullName]; strRef
0x1800f5db7  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800f5dbc  test    eax, eax
0x1800f5dbe  js      loc_1800F77AD
0x1800f5dc4  mov     ecx, [r15+90h]
0x1800f5dcb  xorps   xmm0, xmm0
0x1800f5dce  mov     rax, [rbx]
0x1800f5dd1  mov     [rbp+0F0h+activatableClassHelper._userProperties.ActivationType], ecx
0x1800f5dd4  mov     byte ptr [rbp+0F0h+activatableClassHelper._userProperties.Server.Value.hstr_], sil
0x1800f5dd8  mov     qword ptr [rbp+0F0h+activatableClassHelper._userProperties.DllPath.Present], rsi
0x1800f5ddc  mov     byte ptr [rbp+0F0h+activatableClassHelper._userProperties.DllPath.Value.Unexpanded.hstr_], sil
0x1800f5de0  mov     word ptr [rbp+0F0h+activatableClassHelper._userProperties.Threading.Value], si
0x1800f5de4  mov     byte ptr [rbp+0F0h+activatableClassHelper._userProperties+3Ch], sil
0x1800f5de8  mov     dword ptr [rbp+0F0h+activatableClassHelper._userProperties.CustomAttributes.MapView.ptr_], esi
0x1800f5deb  mov     qword ptr [rbp+0F0h+activatableClassHelper._userProperties.Private.Present], rsi
0x1800f5def  mov     word ptr [rbp+0F0h+activatableClassHelper._machineProperties.ActivationType], si
0x1800f5df3  mov     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.Server.Value.hstr_], sil
0x1800f5df7  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties.DllPath.Present], rsi
0x1800f5dfb  mov     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.DllPath.Value.Unexpanded.hstr_], sil
0x1800f5dff  mov     [rbp+0F0h+activatableClassHelper._machineProperties.TrustLevel.Present], sil
0x1800f5e03  mov     [rbp+0F0h+activatableClassHelper._machineProperties.TrustLevel.Value], esi
0x1800f5e06  mov     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_], sil
0x1800f5e0a  mov     dword ptr [rbp+0F0h+activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_+4], esi
0x1800f5e0d  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties.RemoteServer.Present], rsi
0x1800f5e11  mov     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.RemoteServer.Value.hstr_], sil
0x1800f5e15  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties.ActivateAsUser.Present], rsi
0x1800f5e19  mov     [rbp+0F0h+activatableClassHelper._machineProperties.ActivateInSharedBroker.Present], sil
0x1800f5e1d  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties+64h], rsi
0x1800f5e21  mov     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.Permissions.Value._pSecurityDescriptor], sil
0x1800f5e25  mov     [rbp+0F0h+activatableClassHelper._userMissingRequiredProperties], sil
0x1800f5e2c  mov     dword ptr [rbp+0F0h+activatableClassHelper._userMissingRequiredProperties+4], esi
0x1800f5e32  mov     qword ptr [rbp+0F0h+activatableClassHelper._userInvalidProperties], rsi
0x1800f5e39  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineMissingRequiredProperties], rsi
0x1800f5e40  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineInvalidProperties], rsi
0x1800f5e47  mov     [rbp+0F0h+var_48], rsi
0x1800f5e4e  movups  xmmword ptr [rbp+0F0h+activatableClassHelper._machineProperties.Permissions.Value._cbSecurityDescriptor], xmm0
0x1800f5e52  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties.Permissions.Value._cbSecurityDescriptor], rsi
0x1800f5e56  mov     word ptr [rbp+0F0h+activatableClassHelper._machineProperties.ActivateOnHostFlags.Present], si
0x1800f5e5d  movups  xmmword ptr [rbp+0F0h+activatableClassHelper._userProperties.DllPath.Value.IsExpandable], xmm0
0x1800f5e61  mov     qword ptr [rbp+0F0h+activatableClassHelper._userProperties.DllPath.Value.IsExpandable], rsi
0x1800f5e65  movups  xmmword ptr [rbp+0F0h+activatableClassHelper._machineProperties.DllPath.Value.IsExpandable], xmm0
0x1800f5e69  mov     qword ptr [rbp+0F0h+activatableClassHelper._machineProperties.DllPath.Value.IsExpandable], rsi
0x1800f5e6d  test    ecx, ecx
0x1800f5e6f  jz      short loc_1800F5E90
0x1800f5e71  mov     rdx, [rbp+0F0h+arg_38]
0x1800f5e78  lea     this, [rbp+0F0h+activatableClassHelper._machineMissingRequiredProperties]
0x1800f5e7f  mov     rax, [rax+70h]
0x1800f5e83  lea     activatableClassId, [rbp+0F0h+activatableClassHelper._userInvalidProperties]
0x1800f5e8a  lea     pUserToken, [rbp+0F0h+activatableClassHelper._userProperties.Server]
0x1800f5e8e  jmp     short loc_1800F5EAD
0x1800f5e90  mov     rdx, [rbp+0F0h+arg_40]
0x1800f5e97  lea     this, [rbp+0F0h+var_48]
0x1800f5e9e  mov     rax, [rax+78h]
0x1800f5ea2  lea     activatableClassId, [rbp+0F0h+activatableClassHelper._machineInvalidProperties]
0x1800f5ea9  lea     pUserToken, [rbp+0F0h+activatableClassHelper._machineProperties.Server]
0x1800f5ead  mov     [rsp+1F0h+format], this
0x1800f5eb2  mov     this, rbx
0x1800f5eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5eba  mov     ecx, 80000000h
0x1800f5ebf  mov     ebx, eax
0x1800f5ec1  mov     r12d, 8007000Dh
0x1800f5ec7  lea     eax, [rax+this]
0x1800f5eca  test    ecx, eax
0x1800f5ecc  jnz     short loc_1800F5EEC
0x1800f5ece  cmp     ebx, r12d
0x1800f5ed1  jz      short loc_1800F5EEC
0x1800f5ed3  lea     this, [rbp+0F0h+activatableClassHelper._machineProperties.Server]; this
0x1800f5ed7  call    ??1ActivatableClassMachineRegistrationEntryProperties@@QEAA@XZ; ActivatableClassMachineRegistrationEntryProperties::~ActivatableClassMachineRegistrationEntryProperties(void)
0x1800f5edc  lea     this, [rbp+0F0h+activatableClassHelper._userProperties.Server]; this
0x1800f5ee0  call    ??1ActivatableClassRegistrationEntryProperties@@QEAA@XZ; ActivatableClassRegistrationEntryProperties::~ActivatableClassRegistrationEntryProperties(void)
0x1800f5ee5  mov     eax, ebx
0x1800f5ee7  jmp     loc_1800F77AD
0x1800f5eec  cmp     [rbp+0F0h+arg_48], sil
0x1800f5ef3  jnz     loc_1800F5FB1
0x1800f5ef9  cmp     [rbp+0F0h+activatableClassHelper._userProperties.ActivationType], esi
0x1800f5efc  jz      loc_1800F5FB1
0x1800f5f02  mov     al, byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.ActivationType]
0x1800f5f05  neg     al
0x1800f5f07  sbb     cl, cl
0x1800f5f09  and     cl, byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.ActivationType+1]
0x1800f5f0c  jz      loc_1800F5FB1
0x1800f5f12  xor     eax, eax
0x1800f5f14  mov     [rbp+0F0h+dllPath.Unexpanded.hstr_], rsi
0x1800f5f18  mov     ecx, 1460h; uResourceId
0x1800f5f1d  mov     word ptr [rbp+0F0h+propertyStore.MapView.ptr_], ax
0x1800f5f24  lea     activatableClassId, [rbp+0F0h+propertyStore]; uResourceId
0x1800f5f2b  lea     pUserToken, [rbp+0F0h+dllPath]; pcchResource
0x1800f5f2f  call    LoadStringResource
0x1800f5f34  mov     r14d, 80070005h
0x1800f5f3a  mov     ecx, r14d; error
0x1800f5f3d  test    eax, eax
0x1800f5f3f  js      short loc_1800F5F53
0x1800f5f41  movzx   dwCatalogFlags, word ptr [rbp+0F0h+propertyStore.MapView.ptr_]; cchMax
0x1800f5f48  mov     pUserToken, [rbp+0F0h+dllPath.Unexpanded.hstr_]; message
0x1800f5f4c  call    RoOriginateErrorW
0x1800f5f51  jmp     short loc_1800F5F5A
0x1800f5f53  xor     dwCatalogFlags, dwCatalogFlags; message
0x1800f5f55  call    RoOriginateError
0x1800f5f5a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800f5f60  test    eax, eax
0x1800f5f62  jnz     short loc_1800F5F7F
0x1800f5f64  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800f5f6a  jz      loc_1800F77A1
0x1800f5f70  xor     ecx, ecx; level
0x1800f5f72  call    IsWppLevelEnabled
0x1800f5f77  test    al, al
0x1800f5f79  jz      loc_1800F77A1
0x1800f5f7f  lea     rax, aActivatablecla; "ActivatableClassId entry %ws is private"...
0x1800f5f86  mov     [rsp+1F0h+function], rdi; <args_0>
0x1800f5f8b  xor     r9d, r9d; level
0x1800f5f8e  mov     [rsp+1F0h+format], rax; format
0x1800f5f93  mov     r8d, 54Eh; line
0x1800f5f99  lea     rdx, aCwinrtactivati_6; "CWinRTActivationStoreCatalog::CRuntimeC"...
0x1800f5fa0  lea     this, aOnecoreComComb_177; "onecore\\com\\combase\\catalog\\storeca"...
0x1800f5fa7  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x1800f5fac  jmp     loc_1800F77A1
0x1800f5fb1  lea     rbx, [r15+68h]
0x1800f5fb5  mov     rdx, rbx; activationType
0x1800f5fb8  lea     this, [rbp+0F0h+activatableClassHelper._userProperties]; this
0x1800f5fbc  call    ?GetActivationType@CActivatableClassPropertiesHelper@CWinRTActivationStoreCatalog@@QEAAJAEAW4ActivationType@Foundation@Windows@@@Z; CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetActivationType(Windows::Foundation::ActivationType &)
0x1800f5fc1  lea     r13, aCwinrtactivati_6; "CWinRTActivationStoreCatalog::CRuntimeC"...
0x1800f5fc8  mov     r14d, eax
0x1800f5fcb  lea     rsi, aOnecoreComComb_177; "onecore\\com\\combase\\catalog\\storeca"...
0x1800f5fd2  test    eax, eax
0x1800f5fd4  jns     short loc_1800F5FF3
0x1800f5fd6  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x1800f5fdc  test    ecx, ecx
0x1800f5fde  jnz     short loc_1800F6015
0x1800f5fe0  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800f5fe6  jz      short loc_1800F6055
0x1800f5fe8  call    IsWppLevelEnabled
0x1800f5fed  test    al, al
0x1800f5fef  jnz     short loc_1800F6015
0x1800f5ff1  jmp     short loc_1800F6055
0x1800f5ff3  mov     r9d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800f5ffa  test    r9d, r9d
0x1800f5ffd  jz      loc_1800F60B5
0x1800f6003  mov     ecx, 3; level
0x1800f6008  call    IsWppLevelEnabled
0x1800f600d  test    al, al
0x1800f600f  jz      loc_1800F60B5
0x1800f6015  mov     eax, [rbx]
0x1800f6017  mov     r9d, 558h; line
0x1800f601d  mov     dword ptr [rsp+1F0h+var_1B0], r14d
0x1800f6022  mov     pUserToken, r13; function
0x1800f6025  mov     [rsp+1F0h+level], eax
0x1800f6029  mov     rdx, rsi; file
0x1800f602c  mov     eax, [r15+90h]
0x1800f6033  mov     ecx, r14d; hr
0x1800f6036  mov     [rsp+1F0h+file], eax
0x1800f603a  lea     rax, aReadActivatabl_7; "Read ActivatableClassId entry %ws in sc"...
0x1800f6041  mov     [rsp+1F0h+function], rdi
0x1800f6046  mov     [rsp+1F0h+format], rax; format
0x1800f604b  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800f6050  test    r14d, r14d
0x1800f6053  jns     short loc_1800F60AE
0x1800f6055  mov     r13d, 8007000Eh
0x1800f605b  cmp     r14d, r13d
0x1800f605e  jz      loc_1800F77A1
0x1800f6064  mov     ecx, 1454h; uResourceId
0x1800f6069  xor     eax, eax
0x1800f606b  lea     activatableClassId, [rbp+0F0h+propertyStore]; uResourceId
0x1800f6072  lea     pUserToken, [rbp+0F0h+dllPath]; pcchResource
0x1800f6076  mov     word ptr [rbp+0F0h+propertyStore.MapView.ptr_], ax
0x1800f607d  mov     [rbp+0F0h+dllPath.Unexpanded.hstr_], rax
0x1800f6081  call    LoadStringResource
0x1800f6086  mov     ecx, r14d; error
0x1800f6089  test    eax, eax
0x1800f608b  js      short loc_1800F60A2
0x1800f608d  movzx   dwCatalogFlags, word ptr [rbp+0F0h+propertyStore.MapView.ptr_]; cchMax
0x1800f6094  mov     pUserToken, [rbp+0F0h+dllPath.Unexpanded.hstr_]; message
0x1800f6098  call    RoOriginateErrorW
0x1800f609d  jmp     loc_1800F77A1
0x1800f60a2  xor     dwCatalogFlags, dwCatalogFlags; message
0x1800f60a4  call    RoOriginateError
0x1800f60a9  jmp     loc_1800F77A1
0x1800f60ae  mov     r9d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800f60b5  cmp     dword ptr [rbx], 0
0x1800f60b8  jnz     loc_1800F6164
0x1800f60be  lea     rdx, [r15+6Ch]; threadingType
0x1800f60c2  lea     this, [rbp+0F0h+activatableClassHelper._userProperties]; this
0x1800f60c6  call    ?GetThreadingModel@CActivatableClassPropertiesHelper@CWinRTActivationStoreCatalog@@QEAAJAEAW4ThreadingType@Foundation@Windows@@@Z; CWinRTActivationStoreCatalog::CActivatableClassPropertiesHelper::GetThreadingModel(Windows::Foundation::ThreadingType &)
0x1800f60cb  mov     r14d, eax
0x1800f60ce  test    eax, eax
0x1800f60d0  jns     short loc_1800F60F1
0x1800f60d2  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800f60d8  test    eax, eax
0x1800f60da  jnz     short loc_1800F6104
0x1800f60dc  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f60e2  jz      short loc_1800F6144
0x1800f60e4  xor     ecx, ecx; level
0x1800f60e6  call    IsWppLevelEnabled
0x1800f60eb  test    al, al
0x1800f60ed  jnz     short loc_1800F6104
0x1800f60ef  jmp     short loc_1800F6144
0x1800f60f1  test    r9d, r9d
0x1800f60f4  jz      short loc_1800F6164
0x1800f60f6  mov     ecx, 3; level
0x1800f60fb  call    IsWppLevelEnabled
0x1800f6100  test    al, al
0x1800f6102  jz      short loc_1800F6164
0x1800f6104  mov     eax, [rbx]
0x1800f6106  mov     r9d, 56Ah; line
0x1800f610c  mov     dword ptr [rsp+1F0h+var_1B0], r14d
0x1800f6111  mov     pUserToken, r13; function
0x1800f6114  mov     [rsp+1F0h+level], eax
0x1800f6118  mov     rdx, rsi; file
0x1800f611b  mov     eax, [r15+90h]
0x1800f6122  mov     ecx, r14d; hr
0x1800f6125  mov     [rsp+1F0h+file], eax
0x1800f6129  lea     rax, aReadActivatabl_6; "Read ActivatableClassId entry %ws in sc"...
0x1800f6130  mov     [rsp+1F0h+function], rdi
0x1800f6135  mov     [rsp+1F0h+format], rax; format
0x1800f613a  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800f613f  test    r14d, r14d
0x1800f6142  jns     short loc_1800F615D
0x1800f6144  mov     r13d, 8007000Eh
0x1800f614a  cmp     r14d, r13d
0x1800f614d  jz      loc_1800F77A1
0x1800f6153  mov     ecx, 1455h
0x1800f6158  jmp     loc_1800F6069
0x1800f615d  mov     r9d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800f6164  cmp     dword ptr [r15+90h], 0
0x1800f616c  mov     dwCatalogFlags, 80070002h
0x1800f6171  jnz     loc_1800F62DE
0x1800f6177  test    [rbp+0F0h+activatableClassHelper._machineInvalidProperties], 10h
0x1800f617e  jnz     loc_1800F6232
0x1800f6184  test    byte ptr [rbp+0F0h+var_48], 10h
0x1800f618b  jz      short loc_1800F6198
0x1800f618d  mov     ebx, r12d
0x1800f6190  mov     r14d, r12d
0x1800f6193  jmp     loc_1800F625A
0x1800f6198  cmp     byte ptr [rbp+0F0h+activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_], 0
0x1800f619c  jz      loc_1800F6232
0x1800f61a2  mov     eax, dword ptr [rbp+0F0h+activatableClassHelper._machineProperties.CustomAttributes.MapView.ptr_+4]
0x1800f61a5  xor     ebx, ebx
0x1800f61a7  xor     r14d, r14d
0x1800f61aa  mov     [r15+74h], eax
0x1800f61ae  test    r9d, r9d
0x1800f61b1  jz      loc_1800F62E6
0x1800f61b7  mov     ecx, 3; level
0x1800f61bc  call    IsWppLevelEnabled
0x1800f61c1  test    al, al
0x1800f61c3  jz      short loc_1800F6210
0x1800f61c5  mov     eax, [r15+74h]
0x1800f61c9  mov     r9d, 585h; line
0x1800f61cf  mov     dword ptr [rsp+1F0h+var_1B0], ebx
0x1800f61d3  mov     pUserToken, r13; function
0x1800f61d6  mov     [rsp+1F0h+level], eax
0x1800f61da  mov     rdx, rsi; file
0x1800f61dd  mov     eax, [r15+90h]
0x1800f61e4  mov     ecx, ebx; hr
0x1800f61e6  mov     [rsp+1F0h+file], eax
0x1800f61ea  lea     rax, aReadActivatabl_1; "Read ActivatableClassId entry %ws in sc"...
0x1800f61f1  mov     [rsp+1F0h+function], rdi
0x1800f61f6  mov     [rsp+1F0h+format], rax; format
0x1800f61fb  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800f6200  mov     r9d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800f6207  mov     dwCatalogFlags, 80070002h
0x1800f620c  cmp     ebx, dwCatalogFlags
0x1800f620e  jz      short loc_1800F6285
0x1800f6210  test    r14d, r14d
0x1800f6213  jns     loc_1800F62E6
0x1800f6219  mov     r13d, 8007000Eh
0x1800f621f  cmp     r14d, r13d
0x1800f6222  jz      loc_1800F77A1
  ... truncated ...
```
