# CRpcResolver::DelegateActivationToSCM(bool,IActivationPropertiesIn *,IActivationPropertiesOut * *)

- ea: `0x180026984`
- end: `0x1800273a9`
- name: `?DelegateActivationToSCM@CRpcResolver@@AEAAJ_NPEAUIActivationPropertiesIn@@PEAPEAUIActivationPropertiesOut@@@Z`
- size: `2597`
- prototype: `__int64 __fastcall(CRpcResolver *this, bool isCreateInstance, IActivationPropertiesIn *pInActivationProperties, IActivationPropertiesOut **ppActOut)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025ea0`
- `0x180025ef0`
- `0x180026140`

## callees

- `0x1800071d4`
- `0x18000b408`
- `0x180012828`
- `0x1800129d4`
- `0x180013230`
- `0x180025720`
- `0x1800257d0`
- `0x1800257f4`
- `0x180026984`
- `0x1800288c8`
- `0x180030afc`
- `0x18003a8bc`
- `0x18006c4a4`
- `0x1800859ec`
- `0x180174800`
- `0x180182448`
- `0x1801999b0`
- `0x18019a654`
- `0x1801ad430`
- `0x1801ad710`
- `0x1801ad790`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027374`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180026d0a`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180026fa4`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180027061`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002712d`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002718a`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180026d0a`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180026fa4`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180027061`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002712d`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002718a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026ae7`

## string_xrefs

- `0x180026ca1`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180026fee`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x1800270c4`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x1800270e4`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x1800271b0`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18002720e`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18002723c`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180027275`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18002728d`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x1800272ad`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180027335`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180027351`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180027386`: `onecore\com\combase\dcomrem\resolver.cxx`

## pseudocode

```c
__int64 __fastcall CRpcResolver::DelegateActivationToSCM(
        CRpcResolver *this,
        bool isCreateInstance,
        IActivationPropertiesIn *pInActivationProperties,
        IActivationPropertiesOut **ppActOut)
{
  char *ReservedForOle; // rcx
  IActivationPropertiesIn_vtbl *v8; // rax
  HRESULT v9; // ebx
  IActivationPropertiesIn_vtbl *v10; // rax
  IActivationPropertiesIn_vtbl *v11; // rax
  unsigned int v12; // r15d
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v14; // eax
  HRESULT v15; // eax
  CRpcResolver *v16; // rcx
  CRpcResolver *v17; // rcx
  HRESULT (__fastcall *v18)(IUnknown *, const _GUID *, void **); // rbx
  int v19; // eax
  IActivationPropertiesIn_vtbl *v20; // rax
  HRESULT (__fastcall *v21)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v22; // eax
  IActivationPropertiesIn_vtbl *v23; // rax
  HRESULT (__fastcall *v24)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v25; // eax
  __int64 v26; // rdx
  CRpcResolver *v27; // rcx
  ISCMLocalActivator *SCM; // rdi
  ISCMLocalActivator_vtbl *v29; // rcx
  HRESULT (__fastcall *GetClassObject)(ISCMLocalActivator *, IActivationPropertiesIn *, IActivationPropertiesOut **); // rbx
  unsigned int v31; // edx
  HRESULT (__fastcall *CreateInstance)(ISCMLocalActivator *, IUnknown *, IActivationPropertiesIn *, IActivationPropertiesOut **); // rbx
  IActivationPropertiesOut *v33; // rcx
  ISpecialSystemProperties *v34; // rcx
  IScmRequestInfo *v35; // rcx
  ILegacyInfo *v36; // rcx
  IInitActivationPropertiesIn *ptr; // rcx
  void (*Release)(void); // rax
  IActivationPropertiesOut *v40; // rdi
  HRESULT (__fastcall *v41)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v42; // eax
  bool v43; // r8
  HRESULT v44; // eax
  IScmReplyInfo *v45; // rcx
  IActivationPropertiesOut *v46; // rcx
  ISpecialSystemProperties *v47; // rcx
  IScmRequestInfo *v48; // rcx
  ILegacyInfo *v49; // rcx
  IInitActivationPropertiesIn *v50; // rcx
  IActivationPropertiesOut *v51; // rcx
  ISpecialSystemProperties *v52; // rcx
  IScmRequestInfo *v53; // rcx
  ILegacyInfo *v54; // rcx
  IInitActivationPropertiesIn *v55; // rcx
  ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList> > > > > > *v56; // rcx
  unsigned int v57; // edx
  unsigned int v58; // edx
  HRESULT v59; // r9d
  unsigned int v60; // edx
  HRESULT PackageGraphForScm; // eax
  ComWinRTActivationProperties *v62; // rsi
  ActivationPropertiesIn *v63; // rdi
  unsigned int v64; // edx
  IActivationPropertiesIn_vtbl *v65; // rax
  HRESULT v66; // eax
  unsigned int v67; // edx
  HSTRING__ *const *v68; // rbx
  unsigned int v69; // eax
  Microsoft::WRL::ComPtr<ILegacyInfo> pLegacyInfo; // [rsp+50h] [rbp-B0h] BYREF
  Microsoft::WRL::ComPtr<IActivationPropertiesOut> pOutActivationProperties; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::WRL::ComPtr<ISpecialSystemProperties> pSpecialSystemProperties; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::WRL::ComPtr<IScmRequestInfo> pInScmResolverInfo; // [rsp+68h] [rbp-98h] BYREF
  Microsoft::WRL::ComPtr<IInitActivationPropertiesIn> pInitActivationPropertiesIn; // [rsp+70h] [rbp-90h] BYREF
  ComWinRTActivationProperties *comWinRTActivationProperties; // [rsp+78h] [rbp-88h] BYREF
  unsigned int dwActivationFlags; // [rsp+80h] [rbp-80h] BYREF
  Microsoft::WRL::ComPtr<IScmReplyInfo> pOutScmResolverInfo; // [rsp+88h] [rbp-78h] BYREF
  unsigned int dwClsctxFlags; // [rsp+90h] [rbp-70h] BYREF
  ObjectLibrary::ReferencedPtr<OXIDEntry> oxidEntry; // [rsp+98h] [rbp-68h] BYREF
  ActivationPropertiesIn *activationPropertiesIn; // [rsp+A0h] [rbp-60h] BYREF
  _PRIV_RESOLVER_INFO *pPrivateResolverInfo; // [rsp+A8h] [rbp-58h] BYREF
  _PRIV_SCM_INFO PrivateScmInfo; // [rsp+B0h] [rbp-50h] BYREF
  ActivationPropertiesOut *activationPropertiesOut; // [rsp+D8h] [rbp-28h] BYREF
  _COSERVERINFO *pServerInfo; // [rsp+E0h] [rbp-20h] BYREF
  wil::unique_struct<__MIDL_ILocalObjectExporter_0007,void (__cdecl*)(__MIDL_ILocalObjectExporter_0007 *),&ClearOxidInfo,std::nullptr_t,0> oxidInfo; // [rsp+F0h] [rbp-10h] BYREF
  void *retaddr; // [rsp+1D8h] [rbp+D8h]

  ReservedForOle = (char *)NtCurrentTeb()->ReservedForOle;
  if ( ReservedForOle && (ReservedForOle[20] < 0 || *((_DWORD *)ReservedForOle + 78)) )
    ExitProcessDiagnostics::g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc._Storage._Value = 1;
  v8 = pInActivationProperties->__vftable;
  dwActivationFlags = 0;
  v9 = v8->GetActivationFlags(pInActivationProperties, &dwActivationFlags);
  if ( v9 < 0 )
  {
    v57 = 2347;
LABEL_98:
    wil::details::in1diag3::Return_Hr(retaddr, v57, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v9);
    return (unsigned int)v9;
  }
  v10 = pInActivationProperties->__vftable;
  dwClsctxFlags = 0;
  v9 = v10->GetClsctx(pInActivationProperties, &dwClsctxFlags);
  if ( v9 < 0 )
  {
    v57 = 2350;
    goto LABEL_98;
  }
  v11 = pInActivationProperties->__vftable;
  v12 = dwActivationFlags & 0x40;
  pInitActivationPropertiesIn.ptr_ = 0;
  QueryInterface = v11->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInitActivationPropertiesIn);
  v14 = QueryInterface(
          pInActivationProperties,
          &GUID_000001a1_0000_0000_c000_000000000046,
          (void **)&pInitActivationPropertiesIn.ptr_);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x933u, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v14);
LABEL_32:
    ptr = pInitActivationPropertiesIn.ptr_;
    if ( !pInitActivationPropertiesIn.ptr_ )
      return (unsigned int)v9;
    pInitActivationPropertiesIn.ptr_ = 0;
    Release = (void (*)(void))ptr->Release;
LABEL_34:
    Release();
    return (unsigned int)v9;
  }
  dwClsctxFlags &= ~0x400000u;
  dwActivationFlags &= 0xFFFF8FBF;
  v15 = ((__int64 (__fastcall *)(IInitActivationPropertiesIn *))pInitActivationPropertiesIn.ptr_->SetActivationFlags)(pInitActivationPropertiesIn.ptr_);
  v9 = v15;
  if ( v15 < 0 )
  {
    v58 = 2373;
LABEL_102:
    wil::details::in1diag3::Return_Hr(retaddr, v58, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v15);
    goto LABEL_86;
  }
  v15 = pInitActivationPropertiesIn.ptr_->SetClsctx(pInitActivationPropertiesIn.ptr_, dwClsctxFlags);
  v9 = v15;
  if ( v15 < 0 )
  {
    v58 = 2374;
    goto LABEL_102;
  }
  v15 = CRpcResolver::BindToSCMProxy(v16, v12);
  v9 = v15;
  if ( v15 < 0 )
  {
    v58 = 2376;
    goto LABEL_102;
  }
  v15 = CRpcResolver::SetImpersonatingFlag(v17, pInActivationProperties);
  v9 = v15;
  if ( v15 < 0 )
  {
    v58 = 2377;
    goto LABEL_102;
  }
  memset(&PrivateScmInfo, 0, sizeof(PrivateScmInfo));
  pLegacyInfo.ptr_ = 0;
  PrivateScmInfo.lThreadID = GetCurrentThreadId();
  PrivateScmInfo.pwszWinstaDesktop = CRpcResolver::_pwszWinstaDesktop;
  PrivateScmInfo.ProcessSignature = CRpcResolver::_ProcessSignature;
  v18 = pInActivationProperties->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pLegacyInfo);
  v19 = v18(pInActivationProperties, &GUID_000001ac_0000_0000_c000_000000000046, (void **)&pLegacyInfo.ptr_);
  v9 = v19;
  if ( v19 < 0 )
  {
    v59 = v19;
    v60 = 2385;
LABEL_106:
    wil::details::in1diag3::Return_Hr(retaddr, v60, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v59);
LABEL_85:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pLegacyInfo);
LABEL_86:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInitActivationPropertiesIn);
    return (unsigned int)v9;
  }
  pServerInfo = 0;
  pLegacyInfo.ptr_->GetCOSERVERINFO(pLegacyInfo.ptr_, &pServerInfo);
  if ( !GetEnvBlock(&PrivateScmInfo) )
  {
    v9 = -2147024882;
    v60 = 2390;
    v59 = -2147024882;
    goto LABEL_106;
  }
  v20 = pInActivationProperties->__vftable;
  pInScmResolverInfo.ptr_ = 0;
  v21 = v20->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInScmResolverInfo);
  v22 = v21(pInActivationProperties, &GUID_000001aa_0000_0000_c000_000000000046, (void **)&pInScmResolverInfo.ptr_);
  v9 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x960u, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v22);
LABEL_83:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInScmResolverInfo);
    if ( PrivateScmInfo.pEnvBlock )
      FreeEnvironmentStringsW(PrivateScmInfo.pEnvBlock);
    goto LABEL_85;
  }
  pInScmResolverInfo.ptr_->SetScmInfo(pInScmResolverInfo.ptr_, &PrivateScmInfo);
  v23 = pInActivationProperties->__vftable;
  pSpecialSystemProperties.ptr_ = 0;
  v24 = v23->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pSpecialSystemProperties);
  v25 = v24(
          pInActivationProperties,
          &GUID_000001b9_0000_0000_c000_000000000046,
          (void **)&pSpecialSystemProperties.ptr_);
  v9 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x96Bu, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v25);
    goto LABEL_82;
  }
  v26 = (unsigned int)gAuthnLevel;
  if ( gdwRaiseActivationAuthenticationLevel && (_DWORD)gAuthnLevel != 1 && (unsigned int)gAuthnLevel < 5 )
    v26 = 5;
  pSpecialSystemProperties.ptr_->SetDefaultAuthenticationLevel(pSpecialSystemProperties.ptr_, v26);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    comWinRTActivationProperties = 0;
    PackageGraphForScm = GetPackageGraphForScm((PackageGraphForScm **)&comWinRTActivationProperties);
    v9 = PackageGraphForScm;
    if ( PackageGraphForScm >= 0 )
    {
      GetComDependenciesOnPackages((ObjectLibrary::ReferencedPtr<IPackageList> *)&activationPropertiesIn);
      v62 = comWinRTActivationProperties;
      v63 = activationPropertiesIn;
      if ( comWinRTActivationProperties || activationPropertiesIn )
      {
        v65 = pInActivationProperties->__vftable;
        activationPropertiesIn = 0;
        v66 = v65->QueryInterface(
                pInActivationProperties,
                &CLSID_ActivationPropertiesIn,
                (void **)&activationPropertiesIn);
        v9 = v66;
        if ( v66 < 0 )
        {
          v67 = 2440;
LABEL_79:
          wil::details::in1diag3::Return_Hr(retaddr, v67, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v66);
          if ( v63 )
            v63->Release(v63);
          if ( !v62 )
            goto LABEL_82;
          v56 = (ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList> > > > > > *)v62;
          goto LABEL_114;
        }
        comWinRTActivationProperties = 0;
        v66 = ActivationPropertiesIn::GetComWinRTActivationProperties(
                activationPropertiesIn,
                &comWinRTActivationProperties);
        v9 = v66;
        if ( v66 < 0 )
        {
          v67 = 2443;
          goto LABEL_79;
        }
        if ( v62 )
        {
          v66 = ComWinRTActivationProperties::SetPackageGraphPackages(
                  comWinRTActivationProperties,
                  (unsigned int)v62->_comWinRTActivationPropertiesData.winrtActivationPropertiesData.activatableClassId,
                  *(HSTRING__ *const **)&v62->_unSerialized);
          v9 = v66;
          if ( v66 < 0 )
          {
            v67 = 2448;
            goto LABEL_79;
          }
        }
        if ( v63 )
        {
          v68 = (HSTRING__ *const *)((__int64 (__fastcall *)(ActivationPropertiesIn *))v63->GetMarshalSizeMax)(v63);
          v69 = ((__int64 (__fastcall *)(ActivationPropertiesIn *))v63->GetUnmarshalClass)(v63);
          v66 = ComWinRTActivationProperties::SetComDependencyMainPackageFamilies(
                  comWinRTActivationProperties,
                  v69,
                  v68);
          v9 = v66;
          if ( v66 < 0 )
          {
            v67 = 2454;
            goto LABEL_79;
          }
          v63->Release(v63);
        }
      }
      if ( v62 )
        ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList,>>>>>>::Release((ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList> > > > > > *)v62);
      goto LABEL_17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x980u,
      "onecore\\com\\combase\\dcomrem\\resolver.cxx",
      PackageGraphForScm);
    v56 = (ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList> > > > > > *)comWinRTActivationProperties;
    if ( comWinRTActivationProperties )
LABEL_114:
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<PackageGraphForScm,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<PackageGraphForScm,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<PackageGraphForScm,ObjectLibrary::Details::MixinBase<PackageGraphForScm,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IPackageList,>>>>>>::Release(v56);
LABEL_82:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pSpecialSystemProperties);
    goto LABEL_83;
  }
LABEL_17:
  pOutActivationProperties.ptr_ = 0;
  SCM = CRpcResolver::GetSCM(v27, v12);
  v29 = SCM->__vftable;
  if ( isCreateInstance )
  {
    CreateInstance = v29->CreateInstance;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutActivationProperties);
    v9 = CreateInstance(SCM, 0, pInActivationProperties, &pOutActivationProperties.ptr_);
    if ( v9 < 0 )
    {
      v31 = 2463;
      goto LABEL_22;
    }
  }
  else
  {
    GetClassObject = v29->GetClassObject;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutActivationProperties);
    v9 = GetClassObject(SCM, pInActivationProperties, &pOutActivationProperties.ptr_);
    if ( v9 < 0 )
    {
      v31 = 2467;
LABEL_22:
      wil::details::in1diag3::Return_Hr(retaddr, v31, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v9);
      v33 = pOutActivationProperties.ptr_;
      if ( pOutActivationProperties.ptr_ )
      {
        pOutActivationProperties.ptr_ = 0;
        v33->Release(v33);
      }
      v34 = pSpecialSystemProperties.ptr_;
      if ( pSpecialSystemProperties.ptr_ )
      {
        pSpecialSystemProperties.ptr_ = 0;
        v34->Release(v34);
      }
      v35 = pInScmResolverInfo.ptr_;
      if ( pInScmResolverInfo.ptr_ )
      {
        pInScmResolverInfo.ptr_ = 0;
        v35->Release(v35);
      }
      if ( PrivateScmInfo.pEnvBlock )
        FreeEnvironmentStringsW(PrivateScmInfo.pEnvBlock);
      v36 = pLegacyInfo.ptr_;
      if ( pLegacyInfo.ptr_ )
      {
        pLegacyInfo.ptr_ = 0;
        v36->Release(v36);
      }
      goto LABEL_32;
    }
  }
  if ( !pOutActivationProperties.ptr_ )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(retaddr, 0x9A6u, "onecore\\com\\combase\\dcomrem\\resolver.cxx", -2147418113);
    v51 = pOutActivationProperties.ptr_;
    if ( pOutActivationProperties.ptr_ )
    {
      pOutActivationProperties.ptr_ = 0;
      v51->Release(v51);
    }
    v52 = pSpecialSystemProperties.ptr_;
    if ( pSpecialSystemProperties.ptr_ )
    {
      pSpecialSystemProperties.ptr_ = 0;
      v52->Release(v52);
    }
    v53 = pInScmResolverInfo.ptr_;
    if ( pInScmResolverInfo.ptr_ )
    {
      pInScmResolverInfo.ptr_ = 0;
      v53->Release(v53);
    }
    if ( PrivateScmInfo.pEnvBlock )
      FreeEnvironmentStringsW(PrivateScmInfo.pEnvBlock);
    v54 = pLegacyInfo.ptr_;
    if ( pLegacyInfo.ptr_ )
    {
      pLegacyInfo.ptr_ = 0;
      v54->Release(v54);
    }
    v55 = pInitActivationPropertiesIn.ptr_;
    if ( !pInitActivationPropertiesIn.ptr_ )
      return (unsigned int)v9;
    pInitActivationPropertiesIn.ptr_ = 0;
    Release = (void (*)(void))v55->Release;
    goto LABEL_34;
  }
  activationPropertiesOut = 0;
  v9 = pOutActivationProperties.ptr_->QueryInterface(
         pOutActivationProperties.ptr_,
         &CLSID_ActivationPropertiesOut,
         (void **)&activationPropertiesOut);
  if ( v9 < 0 )
  {
    v31 = 2474;
    goto LABEL_22;
  }
  activationPropertiesOut->_isWinrtActivation = (dwActivationFlags & 0x400) != 0;
  v40 = pOutActivationProperties.ptr_;
  pOutScmResolverInfo.ptr_ = 0;
  v41 = pOutActivationProperties.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutScmResolverInfo);
  v42 = v41(v40, &GUID_000001b6_0000_0000_c000_000000000046, (void **)&pOutScmResolverInfo.ptr_);
  v9 = v42;
  if ( v42 < 0 )
  {
    v64 = 2479;
LABEL_117:
    wil::details::in1diag3::Return_Hr(retaddr, v64, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v42);
LABEL_131:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutScmResolverInfo);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutActivationProperties);
    goto LABEL_82;
  }
  pPrivateResolverInfo = 0;
  pOutScmResolverInfo.ptr_->GetResolverInfo(pOutScmResolverInfo.ptr_, &pPrivateResolverInfo);
  if ( !pPrivateResolverInfo || !pPrivateResolverInfo->OxidServer )
  {
    *ppActOut = pOutActivationProperties.ptr_;
    pOutActivationProperties.ptr_ = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutScmResolverInfo);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pOutActivationProperties);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pSpecialSystemProperties);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInScmResolverInfo);
    if ( PrivateScmInfo.pEnvBlock )
      FreeEnvironmentStringsW(PrivateScmInfo.pEnvBlock);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pLegacyInfo);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pInitActivationPropertiesIn);
    return 0;
  }
  v42 = ValidateOxidInfoFromResolver(&pPrivateResolverInfo->OxidInfo);
  v9 = v42;
  if ( v42 < 0 )
  {
    v64 = 2491;
    goto LABEL_117;
  }
  memset_0((void *)&oxidInfo, 0, sizeof(oxidInfo));
  v44 = CopyOxidInfo(&pPrivateResolverInfo->OxidInfo, &oxidInfo.__MIDL_ILocalObjectExporter_0007, v43);
  v9 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x9BEu, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v44);
LABEL_130:
    ClearOxidInfo(&oxidInfo.__MIDL_ILocalObjectExporter_0007);
    goto LABEL_131;
  }
  oxidEntry.ptr_ = 0;
  ObjectLibrary::ReferencedPtr<OXIDEntry>::InternalRelease(&oxidEntry);
  comWinRTActivationProperties = 0;
  v9 = COXIDTable::FindOrCreateOXIDEntry(
         &gOXIDTbl,
         (OXIDEntry *)pPrivateResolverInfo->OxidServer,
         &oxidInfo,
         (const char *)1,
         pPrivateResolverInfo->pServerORBindings,
         pPrivateResolverInfo->LocalMidOfRemote,
         0,
         (std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo> *)&comWinRTActivationProperties,
         0xFFFFFFFF,
         &oxidEntry.ptr_);
  if ( comWinRTActivationProperties )
    HeapFree(g_hHeap, 0, comWinRTActivationProperties);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x9C5u, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v9);
    ObjectLibrary::ReferencedPtr<OXIDEntry>::InternalRelease(&oxidEntry);
    goto LABEL_130;
  }
  activationPropertiesIn = (ActivationPropertiesIn *)oxidEntry.ptr_;
  comWinRTActivationProperties = 0;
  oxidEntry.ptr_ = 0;
  ObjectLibrary::ReferencedPtr<OXIDEntry>::InternalRelease((ObjectLibrary::ReferencedPtr<OXIDEntry> *)&activationPropertiesIn);
  ObjectLibrary::ReferencedPtr<OXIDEntry>::InternalRelease((ObjectLibrary::ReferencedPtr<OXIDEntry> *)&comWinRTActivationProperties);
  *ppActOut = pOutActivationProperties.ptr_;
  pOutActivationProperties.ptr_ = 0;
  ObjectLibrary::ReferencedPtr<OXIDEntry>::InternalRelease(&oxidEntry);
  ClearOxidInfo(&oxidInfo.__MIDL_ILocalObjectExporter_0007);
  v45 = pOutScmResolverInfo.ptr_;
  if ( pOutScmResolverInfo.ptr_ )
  {
    pOutScmResolverInfo.ptr_ = 0;
    v45->Release(v45);
  }
  v46 = pOutActivationProperties.ptr_;
  if ( pOutActivationProperties.ptr_ )
  {
    pOutActivationProperties.ptr_ = 0;
    v46->Release(v46);
  }
  v47 = pSpecialSystemProperties.ptr_;
  if ( pSpecialSystemProperties.ptr_ )
  {
    pSpecialSystemProperties.ptr_ = 0;
    v47->Release(v47);
  }
  v48 = pInScmResolverInfo.ptr_;
  if ( pInScmResolverInfo.ptr_ )
  {
    pInScmResolverInfo.ptr_ = 0;
    v48->Release(v48);
  }
  if ( PrivateScmInfo.pEnvBlock )
    FreeEnvironmentStringsW(PrivateScmInfo.pEnvBlock);
  v49 = pLegacyInfo.ptr_;
  if ( pLegacyInfo.ptr_ )
  {
    pLegacyInfo.ptr_ = 0;
    v49->Release(v49);
  }
  v50 = pInitActivationPropertiesIn.ptr_;
  if ( pInitActivationPropertiesIn.ptr_ )
  {
    pInitActivationPropertiesIn.ptr_ = 0;
    v50->Release(v50);
  }
  return 0;
}

```

## disassembly

```asm
0x180026984  mov     [rsp-8+arg_0], rbx
0x180026989  push    rbp
0x18002698a  push    rsi
0x18002698b  push    rdi
0x18002698c  push    r12
0x18002698e  push    r13
0x180026990  push    r14
0x180026992  push    r15
0x180026994  lea     rbp, [rsp-0A0h]
0x18002699c  sub     rsp, 1A0h
0x1800269a3  mov     rax, cs:__security_cookie
0x1800269aa  xor     rax, rsp
0x1800269ad  mov     [rbp+0D0h+var_40], rax
0x1800269b4  mov     rax, gs:30h
0x1800269bd  xor     esi, esi
0x1800269bf  mov     r12, ppActOut
0x1800269c2  mov     r14, pInActivationProperties
0x1800269c5  mov     r13b, isCreateInstance
0x1800269c8  mov     rcx, [rax+1758h]
0x1800269cf  test    rcx, rcx
0x1800269d2  jz      short loc_1800269EA
0x1800269d4  test    byte ptr [rcx+14h], 80h
0x1800269d8  jnz     loc_180026DAA
0x1800269de  cmp     [rcx+138h], esi
0x1800269e4  ja      loc_180026DAA
0x1800269ea  mov     rax, [pInActivationProperties]
0x1800269ed  lea     rdx, [rbp+0D0h+dwActivationFlags]
0x1800269f1  mov     rcx, r14
0x1800269f4  mov     [rbp+0D0h+dwActivationFlags], esi
0x1800269f7  mov     rax, [rax+30h]
0x1800269fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a00  mov     ebx, eax
0x180026a02  test    eax, eax
0x180026a04  js      loc_1800271FB
0x180026a0a  mov     rax, [r14]
0x180026a0d  lea     rdx, [rbp+0D0h+dwClsctxFlags]
0x180026a11  mov     rcx, r14
0x180026a14  mov     [rbp+0D0h+dwClsctxFlags], esi
0x180026a17  mov     rax, [rax+28h]
0x180026a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a20  mov     ebx, eax
0x180026a22  test    eax, eax
0x180026a24  js      loc_180027202
0x180026a2a  mov     rax, [r14]
0x180026a2d  lea     rcx, [rsp+1D0h+pInitActivationPropertiesIn]; this
0x180026a32  mov     r15d, [rbp+0D0h+dwActivationFlags]
0x180026a36  and     r15d, 40h
0x180026a3a  mov     [rsp+1D0h+pInitActivationPropertiesIn.ptr_], rsi
0x180026a3f  mov     rbx, [rax]
0x180026a42  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026a47  lea     pInActivationProperties, [rsp+1D0h+pInitActivationPropertiesIn]
0x180026a4c  mov     rcx, r14
0x180026a4f  lea     rdx, _GUID_000001a1_0000_0000_c000_000000000046
0x180026a56  mov     rax, rbx
0x180026a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a5e  mov     ebx, eax
0x180026a60  test    eax, eax
0x180026a62  js      loc_1800270BD
0x180026a68  mov     edx, [rbp+0D0h+dwActivationFlags]
0x180026a6b  mov     rcx, [rsp+1D0h+pInitActivationPropertiesIn.ptr_]
0x180026a70  and     edx, 0FFFF8FBFh
0x180026a76  btr     [rbp+0D0h+dwClsctxFlags], 16h
0x180026a7b  mov     [rbp+0D0h+dwActivationFlags], edx
0x180026a7e  mov     rax, [rcx]
0x180026a81  mov     rax, [rax+20h]
0x180026a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a8a  mov     ebx, eax
0x180026a8c  test    eax, eax
0x180026a8e  js      loc_180027222
0x180026a94  mov     rcx, [rsp+1D0h+pInitActivationPropertiesIn.ptr_]
0x180026a99  mov     edx, [rbp+0D0h+dwClsctxFlags]
0x180026a9c  mov     rax, [rcx]
0x180026a9f  mov     rax, [rax+18h]
0x180026aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aa8  mov     ebx, eax
0x180026aaa  test    eax, eax
0x180026aac  js      loc_180027229
0x180026ab2  mov     edx, r15d; fCloaking
0x180026ab5  call    ?BindToSCMProxy@CRpcResolver@@AEAAJH@Z; CRpcResolver::BindToSCMProxy(int)
0x180026aba  mov     ebx, eax
0x180026abc  test    eax, eax
0x180026abe  js      loc_180027250
0x180026ac4  mov     rdx, r14; pIActPropsIn
0x180026ac7  call    ?SetImpersonatingFlag@CRpcResolver@@AEAAJPEAUIActivationPropertiesIn@@@Z; CRpcResolver::SetImpersonatingFlag(IActivationPropertiesIn *)
0x180026acc  mov     ebx, eax
0x180026ace  test    eax, eax
0x180026ad0  js      loc_180027230
0x180026ad6  xorps   xmm0, xmm0
0x180026ad9  xor     eax, eax
0x180026adb  movups  xmmword ptr [rbp+0D0h+PrivateScmInfo.lThreadID], xmm0
0x180026adf  mov     qword ptr [rbp+0D0h+PrivateScmInfo.EnvBlockLength], rax
0x180026ae3  movups  xmmword ptr [rbp+0D0h+PrivateScmInfo.ProcessSignature], xmm0
0x180026ae7  call    cs:__imp_GetCurrentThreadId
0x180026aed  lea     rcx, [rsp+1D0h+pLegacyInfo]; this
0x180026af2  mov     [rsp+1D0h+pLegacyInfo.ptr_], rsi
0x180026af7  mov     [rbp+0D0h+PrivateScmInfo.lThreadID], eax
0x180026afa  mov     rax, cs:?_pwszWinstaDesktop@CRpcResolver@@0PEAGEA; ushort * CRpcResolver::_pwszWinstaDesktop
0x180026b01  mov     [rbp+0D0h+PrivateScmInfo.pwszWinstaDesktop], rax
0x180026b05  mov     rax, cs:?_ProcessSignature@CRpcResolver@@0_KA; unsigned __int64 CRpcResolver::_ProcessSignature
0x180026b0c  mov     [rbp+0D0h+PrivateScmInfo.ProcessSignature], rax
0x180026b10  mov     rax, [r14]
0x180026b13  mov     rbx, [rax]
0x180026b16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026b1b  lea     pInActivationProperties, [rsp+1D0h+pLegacyInfo]
0x180026b20  mov     rcx, r14
0x180026b23  lea     rdx, _GUID_000001ac_0000_0000_c000_000000000046
0x180026b2a  mov     rax, rbx
0x180026b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b32  mov     ebx, eax
0x180026b34  test    eax, eax
0x180026b36  js      loc_180027257
0x180026b3c  mov     rcx, [rsp+1D0h+pLegacyInfo.ptr_]
0x180026b41  lea     rdx, [rbp+0D0h+pServerInfo]
0x180026b45  mov     [rbp+0D0h+pServerInfo], rsi
0x180026b49  mov     rax, [rcx]
0x180026b4c  mov     rax, [rax+20h]
0x180026b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b55  lea     rcx, [rbp+0D0h+PrivateScmInfo]; pScmInfo
0x180026b59  call    ?GetEnvBlock@@YAHPEAU_PRIV_SCM_INFO@@@Z; GetEnvBlock(_PRIV_SCM_INFO *)
0x180026b5e  test    eax, eax
0x180026b60  jz      loc_180027261
0x180026b66  mov     rax, [r14]
0x180026b69  lea     rcx, [rsp+1D0h+pInScmResolverInfo]; this
0x180026b6e  mov     [rsp+1D0h+pInScmResolverInfo.ptr_], rsi
0x180026b73  mov     rbx, [rax]
0x180026b76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026b7b  lea     pInActivationProperties, [rsp+1D0h+pInScmResolverInfo]
0x180026b80  mov     rcx, r14
0x180026b83  lea     rdx, _GUID_000001aa_0000_0000_c000_000000000046
0x180026b8a  mov     rax, rbx
0x180026b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b92  mov     ebx, eax
0x180026b94  test    eax, eax
0x180026b96  js      loc_180027286
0x180026b9c  mov     rcx, [rsp+1D0h+pInScmResolverInfo.ptr_]
0x180026ba1  lea     rdx, [rbp+0D0h+PrivateScmInfo]
0x180026ba5  mov     rax, [rcx]
0x180026ba8  mov     rax, [rax+18h]
0x180026bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bb1  mov     rax, [r14]
0x180026bb4  lea     rcx, [rsp+1D0h+pSpecialSystemProperties]; this
0x180026bb9  mov     [rsp+1D0h+pSpecialSystemProperties.ptr_], rsi
0x180026bbe  mov     rbx, [rax]
0x180026bc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026bc6  lea     pInActivationProperties, [rsp+1D0h+pSpecialSystemProperties]
0x180026bcb  mov     rcx, r14
0x180026bce  lea     rdx, _GUID_000001b9_0000_0000_c000_000000000046
0x180026bd5  mov     rax, rbx
0x180026bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bdd  mov     ebx, eax
0x180026bdf  test    eax, eax
0x180026be1  js      loc_1800272A6
0x180026be7  cmp     cs:gdwRaiseActivationAuthenticationLevel, esi
0x180026bed  mov     edx, cs:?gAuthnLevel@@3KA; ulong gAuthnLevel
0x180026bf3  ja      loc_1800270A1
0x180026bf9  mov     rcx, [rsp+1D0h+pSpecialSystemProperties.ptr_]
0x180026bfe  mov     rax, [rcx]
0x180026c01  mov     rax, [rax+78h]
0x180026c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x180026c11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180026c16  test    al, al
0x180026c18  jnz     loc_1800272C6
0x180026c1e  mov     edx, r15d; fCloaking
0x180026c21  mov     [rsp+1D0h+pOutActivationProperties.ptr_], rsi
0x180026c26  call    ?GetSCM@CRpcResolver@@AEAAPEAUISCMLocalActivator@@H@Z; CRpcResolver::GetSCM(int)
0x180026c2b  mov     rdi, rax
0x180026c2e  mov     rcx, [rax]
0x180026c31  test    r13b, r13b
0x180026c34  jnz     short loc_180026C68
0x180026c36  mov     rbx, [rcx+18h]
0x180026c3a  lea     rcx, [rsp+1D0h+pOutActivationProperties]; this
0x180026c3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c44  lea     pInActivationProperties, [rsp+1D0h+pOutActivationProperties]
0x180026c49  mov     rdx, r14
0x180026c4c  mov     rcx, rdi
0x180026c4f  mov     rax, rbx
0x180026c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c57  mov     ebx, eax
0x180026c59  test    eax, eax
0x180026c5b  jns     loc_180026D72
0x180026c61  mov     edx, 9A3h
0x180026c66  jmp     short loc_180026C9A
0x180026c68  mov     rbx, [rcx+20h]
0x180026c6c  lea     rcx, [rsp+1D0h+pOutActivationProperties]; this
0x180026c71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c76  lea     ppActOut, [rsp+1D0h+pOutActivationProperties]
0x180026c7b  mov     pInActivationProperties, r14
0x180026c7e  xor     edx, edx
0x180026c80  mov     rcx, rdi
0x180026c83  mov     rax, rbx
0x180026c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c8b  mov     ebx, eax
0x180026c8d  test    eax, eax
0x180026c8f  jns     loc_180026D72
0x180026c95  mov     edx, 99Fh; lineNumber
0x180026c9a  mov     rcx, [rbp+0D8h]; callerReturnAddress
0x180026ca1  lea     pInActivationProperties, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x180026ca8  mov     r9d, ebx; hr
0x180026cab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026cb0  mov     rcx, [rsp+1D0h+pOutActivationProperties.ptr_]
0x180026cb5  test    rcx, rcx
0x180026cb8  jz      short loc_180026CCB
0x180026cba  mov     [rsp+1D0h+pOutActivationProperties.ptr_], rsi
0x180026cbf  mov     rax, [rcx]
0x180026cc2  mov     rax, [rax+10h]
0x180026cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ccb  mov     rcx, [rsp+1D0h+pSpecialSystemProperties.ptr_]
0x180026cd0  test    rcx, rcx
0x180026cd3  jz      short loc_180026CE6
0x180026cd5  mov     [rsp+1D0h+pSpecialSystemProperties.ptr_], rsi
0x180026cda  mov     rax, [rcx]
0x180026cdd  mov     rax, [rax+10h]
0x180026ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce6  mov     rcx, [rsp+1D0h+pInScmResolverInfo.ptr_]
0x180026ceb  test    rcx, rcx
0x180026cee  jz      short loc_180026D01
0x180026cf0  mov     [rsp+1D0h+pInScmResolverInfo.ptr_], rsi
0x180026cf5  mov     rax, [rcx]
0x180026cf8  mov     rax, [rax+10h]
0x180026cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d01  mov     rcx, [rbp+0D0h+PrivateScmInfo.pEnvBlock]; penv
0x180026d05  test    rcx, rcx
0x180026d08  jz      short loc_180026D10
0x180026d0a  call    cs:__imp_FreeEnvironmentStringsW
0x180026d10  mov     rcx, [rsp+1D0h+pLegacyInfo.ptr_]
0x180026d15  test    rcx, rcx
0x180026d18  jz      short loc_180026D2B
0x180026d1a  mov     [rsp+1D0h+pLegacyInfo.ptr_], rsi
0x180026d1f  mov     rax, [rcx]
0x180026d22  mov     rax, [rax+10h]
0x180026d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d2b  mov     rcx, [rsp+1D0h+pInitActivationPropertiesIn.ptr_]
0x180026d30  test    rcx, rcx
0x180026d33  jz      short loc_180026D46
0x180026d35  mov     [rsp+1D0h+pInitActivationPropertiesIn.ptr_], rsi
0x180026d3a  mov     rax, [rcx]
0x180026d3d  mov     rax, [rax+10h]
0x180026d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d46  mov     eax, ebx
0x180026d48  mov     rcx, [rbp+0D0h+var_40]
0x180026d4f  xor     rcx, rsp; StackCookie
0x180026d52  call    __security_check_cookie
0x180026d57  mov     rbx, [rsp+1D0h+arg_0]
0x180026d5f  add     rsp, 1A0h
0x180026d66  pop     r15
0x180026d68  pop     r14
0x180026d6a  pop     r13
0x180026d6c  pop     r12
0x180026d6e  pop     rdi
0x180026d6f  pop     rsi
0x180026d70  pop     rbp
0x180026d71  retn
0x180026d72  mov     rcx, [rsp+1D0h+pOutActivationProperties.ptr_]
0x180026d77  test    rcx, rcx
0x180026d7a  jz      loc_180026FE7
0x180026d80  mov     [rbp+0D0h+activationPropertiesOut], rsi
0x180026d84  lea     pInActivationProperties, [rbp+0D0h+activationPropertiesOut]
0x180026d88  mov     rax, [rcx]
0x180026d8b  lea     rdx, CLSID_ActivationPropertiesOut
0x180026d92  mov     rax, [rax]
0x180026d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d9a  mov     ebx, eax
0x180026d9c  test    eax, eax
0x180026d9e  jns     short loc_180026DBA
0x180026da0  mov     edx, 9AAh
0x180026da5  jmp     loc_180026C9A
0x180026daa  mov     eax, 1
0x180026daf  xchg    al, cs:?g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc@ExitProcessDiagnostics@@3U?$atomic@_N@std@@A._Storage._Value; std::atomic<bool> ExitProcessDiagnostics::g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc ...
0x180026db5  jmp     loc_1800269EA
0x180026dba  mov     ecx, [rbp+0D0h+dwActivationFlags]
0x180026dbd  mov     rax, [rbp+0D0h+activationPropertiesOut]
0x180026dc1  shr     ecx, 0Ah
0x180026dc4  and     cl, 1
0x180026dc7  mov     [rax+3B8h], cl
0x180026dcd  lea     rcx, [rbp+0D0h+pOutScmResolverInfo]; this
0x180026dd1  mov     rdi, [rsp+1D0h+pOutActivationProperties.ptr_]
0x180026dd6  mov     [rbp+0D0h+pOutScmResolverInfo.ptr_], rsi
0x180026dda  mov     rax, [rdi]
0x180026ddd  mov     rbx, [rax]
0x180026de0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026de5  lea     pInActivationProperties, [rbp+0D0h+pOutScmResolverInfo]
0x180026de9  mov     rcx, rdi
0x180026dec  lea     rdx, _GUID_000001b6_0000_0000_c000_000000000046
0x180026df3  mov     rax, rbx
0x180026df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dfb  mov     ebx, eax
0x180026dfd  test    eax, eax
0x180026dff  js      loc_180027322
0x180026e05  mov     rcx, [rbp+0D0h+pOutScmResolverInfo.ptr_]
0x180026e09  lea     rdx, [rbp+0D0h+pPrivateResolverInfo]
0x180026e0d  mov     [rbp+0D0h+pPrivateResolverInfo], rsi
0x180026e11  mov     rax, [rcx]
0x180026e14  mov     rax, [rax+20h]
0x180026e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e1d  mov     rcx, [rbp+0D0h+pPrivateResolverInfo]
0x180026e21  test    rcx, rcx
0x180026e24  jz      loc_18002714C
0x180026e2a  cmp     [rcx], rsi
0x180026e2d  jz      loc_18002714C
  ... truncated ...
```
