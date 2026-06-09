# ResolveHostRuntime(ushort const *,IUserTokenInternal *,ushort const *,HSTRING__ * *,AppModel::TrustLevel *,AppModel::RuntimeBehavior *)

- ea: `0x18012eebc`
- end: `0x18012f4d9`
- name: `?ResolveHostRuntime@@YAJPEBGPEAUIUserTokenInternal@@0PEAPEAUHSTRING__@@PEAW4TrustLevel@AppModel@@PEAW4RuntimeBehavior@4@@Z`
- size: `1565`
- prototype: `HRESULT __fastcall(const wchar_t *hostRuntimeId, IUserTokenInternal *userTokenInternal, const wchar_t *mainPackageFullName, HSTRING__ **executablePath, AppModel::TrustLevel *appTrustLevel, AppModel::RuntimeBehavior *runtimeBehavior)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180141d28`

## callees

- `0x18003a8bc`
- `0x18003c7ec`
- `0x18004f88c`
- `0x180053be0`
- `0x180058130`
- `0x18005c8d0`
- `0x1800859ec`
- `0x180105a24`
- `0x18012eebc`
- `0x18012f4e0`
- `0x18017cd08`
- `0x18017d00c`
- `0x18018cf50`
- `0x1801db90c`
- `0x1801db9c4`
- `0x1801dc400`
- `0x1801dc44c`
- `0x1801dc52c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012ef4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012ef4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18012efc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18012efc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f15c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f207`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f261`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f380`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f42b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f15c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f207`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f261`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f380`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f42b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f01d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f395`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f47d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f4b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f01d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f395`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f47d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18012f4b3`

## string_xrefs

- `0x18012ef21`: `onecore\com\combase\catalog\services.cxx`
- `0x18012ef8b`: `onecore\com\combase\catalog\services.cxx`
- `0x18012effa`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f1d2`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f227`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f2a6`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f3b3`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f3e6`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f404`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f437`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f456`: `onecore\com\combase\catalog\services.cxx`
- `0x18012f48b`: `onecore\com\combase\catalog\services.cxx`
- `0x18012efe2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18012f1ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall ResolveHostRuntime(
        const wchar_t *hostRuntimeId,
        IUserTokenInternal *userTokenInternal,
        const wchar_t *mainPackageFullName,
        HSTRING__ **executablePath,
        AppModel::TrustLevel *appTrustLevel,
        AppModel::RuntimeBehavior *runtimeBehavior)
{
  HRESULT FilteredStaticPackageGraphPackagesForMainPackage; // eax
  unsigned int v11; // ebx
  HRESULT FilteredPackagesForMainPackage; // eax
  AppModel::RuntimeBehavior v13; // ebx
  HRESULT v14; // edi
  SRCacheManager *value; // rcx
  PACKAGE_INFO *m_ptr; // rdi
  PACKAGE_INFO *v17; // r14
  const wchar_t *packageFullName; // rdx
  HRESULT v19; // eax
  HRESULT v20; // esi
  StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags v21; // edx
  StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags v22; // edx
  StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags v23; // r8d
  unsigned int v24; // edx
  __int64 v25; // rdx
  SRCacheContext *v26; // rcx
  HRESULT v27; // eax
  __int64 v28; // rdx
  SRCacheContext *v29; // rcx
  SRCacheManager *v30; // rcx
  __int64 v31; // rdx
  SRCacheContext *v32; // rcx
  SRCacheManager *v33; // rcx
  HRESULT PackagedFileAbsolutePath; // eax
  __int64 v35; // rdx
  SRCacheContext *v36; // rcx
  AppModel::TrustLevel v37; // ecx
  __int64 v38; // rdx
  SRCacheContext *v39; // rcx
  SRCacheManager *v40; // rcx
  unsigned int v41; // edx
  __int64 v42; // rdx
  SRCacheContext *v43; // rcx
  bool activationFound; // [rsp+30h] [rbp-D0h] BYREF
  StateRepository::Cache::Manager_NoThrow manager; // [rsp+38h] [rbp-C8h] BYREF
  bool packageExtensionFound; // [rsp+40h] [rbp-C0h] BYREF
  StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow packageExtensionIterator; // [rsp+48h] [rbp-B8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > localExecutablePath; // [rsp+60h] [rbp-A0h] BYREF
  wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64> dependencyPackages; // [rsp+68h] [rbp-98h] BYREF
  __int64 packageId; // [rsp+78h] [rbp-88h] BYREF
  StateRepository::Cache::Entity::PackageExtension_NoThrow packageExtension; // [rsp+80h] [rbp-80h] BYREF
  StateRepository::Cache::Entity::Activation_NoThrow activation; // [rsp+C0h] [rbp-40h] BYREF
  void *retaddr; // [rsp+158h] [rbp+58h]

  dependencyPackages.m_ptr = 0;
  dependencyPackages.m_size = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    FilteredStaticPackageGraphPackagesForMainPackage = GetFilteredStaticPackageGraphPackagesForMainPackage(
                                                         userTokenInternal,
                                                         mainPackageFullName,
                                                         0x200000u,
                                                         &dependencyPackages);
    v11 = FilteredStaticPackageGraphPackagesForMainPackage;
    if ( FilteredStaticPackageGraphPackagesForMainPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xC0Bu,
        "onecore\\com\\combase\\catalog\\services.cxx",
        FilteredStaticPackageGraphPackagesForMainPackage);
      if ( dependencyPackages.m_ptr )
        HeapFree(g_hHeap, 0, dependencyPackages.m_ptr);
      return v11;
    }
  }
  else
  {
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>,wil::empty_deleter,unsigned __int64>::reset((wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (__cdecl*)(void *),&MIDL_user_free>,wil::empty_deleter,unsigned __int64> *)&dependencyPackages);
    FilteredPackagesForMainPackage = GetFilteredPackagesForMainPackage(
                                       userTokenInternal,
                                       mainPackageFullName,
                                       0x200000u,
                                       &dependencyPackages.m_size,
                                       &dependencyPackages.m_ptr);
    v11 = FilteredPackagesForMainPackage;
    if ( FilteredPackagesForMainPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xC10u,
        "onecore\\com\\combase\\catalog\\services.cxx",
        FilteredPackagesForMainPackage);
      goto LABEL_74;
    }
  }
  manager.m_cacheManager.__ptr_.__value_ = 0;
  v13 = RuntimeBehavior_DesktopBridge;
  packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = (SRCacheContext *)&manager;
  LOBYTE(packageExtensionIterator.m_manager) = 1;
  *(_QWORD *)&packageExtensionIterator.m_index = 0;
  v14 = SRCacheManager_Open(0, &packageExtensionIterator.m_index);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>((wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter> > *)&packageExtensionIterator);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xA5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      v14);
    wil::details::in1diag3::Return_Hr(retaddr, 0xC14u, "onecore\\com\\combase\\catalog\\services.cxx", v14);
    value = manager.m_cacheManager.__ptr_.__value_;
    manager.m_cacheManager.__ptr_.__value_ = 0;
    goto LABEL_9;
  }
  m_ptr = dependencyPackages.m_ptr;
  v17 = &dependencyPackages.m_ptr[dependencyPackages.m_size];
  while ( 1 )
  {
    if ( m_ptr == v17 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              0xC66u,
              "onecore\\com\\combase\\catalog\\services.cxx",
              0x490u);
LABEL_71:
      v33 = manager.m_cacheManager.__ptr_.__value_;
      manager.m_cacheManager.__ptr_.__value_ = 0;
LABEL_72:
      if ( v33 )
        SRCacheManager_Close();
      goto LABEL_74;
    }
    packageFullName = m_ptr->packageFullName;
    packageId = 0;
    v19 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&manager, packageFullName, &packageId);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xC1Au, "onecore\\com\\combase\\catalog\\services.cxx", v19);
      goto LABEL_66;
    }
    if ( !packageId )
    {
      v11 = -2147023728;
      wil::details::in1diag3::Return_Hr(retaddr, 0xC1Bu, "onecore\\com\\combase\\catalog\\services.cxx", -2147023728);
      goto LABEL_71;
    }
    packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
    packageExtensionIterator.m_index = 0;
    packageExtensionIterator.m_manager = 0;
    v20 = StateRepository::Cache::Entity::PackageExtension_NoThrow::FindByPackageAndCategory(
            &manager,
            packageId,
            Appx::Packaging::Manifest::Attribute::ExtensionCategoryHostRuntime,
            &packageExtensionIterator);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xC20u, "onecore\\com\\combase\\catalog\\services.cxx", v20);
LABEL_62:
      v43 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
      packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
      if ( v43 )
        SRCacheContext_Close(v43, v42);
LABEL_66:
      v30 = manager.m_cacheManager.__ptr_.__value_;
      manager.m_cacheManager.__ptr_.__value_ = 0;
LABEL_67:
      if ( v30 )
        SRCacheManager_Close();
      v11 = v20;
      goto LABEL_74;
    }
    memset(&packageExtension, 0, sizeof(packageExtension));
    packageExtensionFound = 0;
    v20 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(
            &packageExtensionIterator,
            v21,
            &packageExtension,
            &packageExtensionFound);
    if ( v20 < 0 )
    {
      v24 = 3108;
LABEL_60:
      wil::details::in1diag3::Return_Hr(retaddr, v24, "onecore\\com\\combase\\catalog\\services.cxx", v20);
      StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
      goto LABEL_62;
    }
LABEL_18:
    if ( packageExtensionFound )
      break;
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
    v26 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
    packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v26 )
      SRCacheContext_Close(v26, v25);
    ++m_ptr;
  }
  activationFound = 0;
  v20 = StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(
          &manager,
          hostRuntimeId,
          packageExtension.m__cacheId,
          &activationFound);
  if ( v20 < 0 )
  {
    v24 = 3114;
    goto LABEL_60;
  }
  if ( !activationFound )
  {
    ++packageExtensionIterator.m_index;
    v20 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(
            &packageExtensionIterator,
            v22,
            &packageExtension,
            &packageExtensionFound);
    if ( v20 < 0 )
    {
      v24 = 3170;
      goto LABEL_60;
    }
    goto LABEL_18;
  }
  activationFound = 0;
  memset(&activation, 0, 20);
  memset(&activation.m_hostId, 0, 48);
  v27 = StateRepository::Cache::Entity::Activation_NoThrow::Get(
          &manager,
          packageExtension.m_activation,
          v23,
          &activation,
          &activationFound);
  v20 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x32Fu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      v27);
    wil::details::in1diag3::Return_Hr(retaddr, 0xC30u, "onecore\\com\\combase\\catalog\\services.cxx", v20);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(&activation);
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
    v29 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
    packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v29 )
      SRCacheContext_Close(v29, v28);
    v30 = manager.m_cacheManager.__ptr_.__value_;
    manager.m_cacheManager.__ptr_.__value_ = 0;
    goto LABEL_67;
  }
  if ( !activationFound )
  {
    v11 = -2147023728;
    wil::details::in1diag3::Return_Hr(retaddr, 0xC31u, "onecore\\com\\combase\\catalog\\services.cxx", -2147023728);
LABEL_32:
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(&activation);
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
    v32 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
    packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v32 )
      SRCacheContext_Close(v32, v31);
    v33 = manager.m_cacheManager.__ptr_.__value_;
    manager.m_cacheManager.__ptr_.__value_ = 0;
    goto LABEL_72;
  }
  localExecutablePath.m_ptr = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &localExecutablePath,
    0);
  PackagedFileAbsolutePath = GetPackagedFileAbsolutePath(
                               userTokenInternal,
                               m_ptr->packageFullName,
                               activation.m_executable.__ptr_.__value_,
                               &localExecutablePath.m_ptr);
  v14 = PackagedFileAbsolutePath;
  if ( PackagedFileAbsolutePath >= 0 )
  {
    if ( (char)activation.m_flags[0] >= 0 )
    {
      if ( (activation.m_flags[0] & 4) == 0 )
      {
        v41 = 3138;
        goto LABEL_57;
      }
      v37 = TrustLevel_FullTrust;
    }
    else
    {
      v37 = TrustLevel_PartialTrust;
    }
    if ( (*(_WORD *)activation.m_flags & 0x100) != 0 )
    {
      v13 = RuntimeBehavior_Universal;
LABEL_50:
      *executablePath = localExecutablePath.m_ptr;
      localExecutablePath.m_ptr = 0;
      *appTrustLevel = v37;
      *runtimeBehavior = v13;
      Windows::Internal::String::~String((Windows::Internal::String *)&localExecutablePath);
      StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(&activation);
      StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
      v39 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
      packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
      if ( v39 )
        SRCacheContext_Close(v39, v38);
      v40 = manager.m_cacheManager.__ptr_.__value_;
      manager.m_cacheManager.__ptr_.__value_ = 0;
      if ( v40 )
        SRCacheManager_Close();
      v11 = 0;
      goto LABEL_74;
    }
    if ( (activation.m_flags[0] & 0x10) != 0 )
      goto LABEL_50;
    if ( (activation.m_flags[0] & 0x20) != 0 )
    {
      v13 = RuntimeBehavior_Win32alacarte;
      goto LABEL_50;
    }
    if ( (*(_WORD *)activation.m_flags & 0x200) != 0 )
    {
      v13 = RuntimeBehavior_AppSilo;
      goto LABEL_50;
    }
    v41 = 3160;
LABEL_57:
    v11 = -2147418113;
    wil::details::in1diag3::Return_Hr(retaddr, v41, "onecore\\com\\combase\\catalog\\services.cxx", -2147418113);
    Windows::Internal::String::~String((Windows::Internal::String *)&localExecutablePath);
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    0xC35u,
    "onecore\\com\\combase\\catalog\\services.cxx",
    PackagedFileAbsolutePath);
  Windows::Internal::String::~String((Windows::Internal::String *)&localExecutablePath);
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(&activation);
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(&packageExtension);
  v36 = packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_;
  packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v36 )
    SRCacheContext_Close(v36, v35);
  value = manager.m_cacheManager.__ptr_.__value_;
  manager.m_cacheManager.__ptr_.__value_ = 0;
LABEL_9:
  if ( value )
    SRCacheManager_Close();
  v11 = v14;
LABEL_74:
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>,wil::empty_deleter,unsigned __int64>::reset((wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (__cdecl*)(void *),&MIDL_user_free>,wil::empty_deleter,unsigned __int64> *)&dependencyPackages);
  return v11;
}

```

## disassembly

```asm
0x18012eebc  push    rbp
0x18012eebe  push    rbx
0x18012eebf  push    rsi
0x18012eec0  push    rdi
0x18012eec1  push    r12
0x18012eec3  push    r13
0x18012eec5  push    r14
0x18012eec7  push    r15
0x18012eec9  lea     rbp, [rsp-18h]
0x18012eece  sub     rsp, 118h
0x18012eed5  xor     esi, esi
0x18012eed7  mov     r13, executablePath
0x18012eeda  mov     [rsp+150h+dependencyPackages.m_ptr], rsi
0x18012eedf  mov     rbx, mainPackageFullName
0x18012eee2  mov     [rsp+150h+dependencyPackages.m_size], rsi
0x18012eee7  mov     r15, userTokenInternal
0x18012eeea  mov     r12, hostRuntimeId
0x18012eeed  lea     hostRuntimeId, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x18012eef4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18012eef9  test    al, al
0x18012eefb  jz      short loc_18012EF57
0x18012eefd  lea     executablePath, [rsp+150h+dependencyPackages]; packages
0x18012ef02  mov     r8d, 200000h; flags
0x18012ef08  mov     userTokenInternal, rbx; mainPackageFullName
0x18012ef0b  mov     hostRuntimeId, r15; userTokenInternal
0x18012ef0e  call    ?GetFilteredStaticPackageGraphPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGIAEAV?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@@Z; GetFilteredStaticPackageGraphPackagesForMainPackage(IUserTokenInternal *,ushort const *,uint,wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64> &)
0x18012ef13  mov     ebx, eax
0x18012ef15  test    eax, eax
0x18012ef17  jns     loc_18012EFA4
0x18012ef1d  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012ef21  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012ef28  mov     r9d, eax; hr
0x18012ef2b  mov     edx, 0C0Bh; lineNumber
0x18012ef30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ef35  mov     mainPackageFullName, [rsp+150h+dependencyPackages.m_ptr]; lpMem
0x18012ef3a  test    mainPackageFullName, mainPackageFullName
0x18012ef3d  jz      loc_18012F4C3
0x18012ef43  mov     hostRuntimeId, cs:?g_hHeap@@3QEAXEA; hHeap
0x18012ef4a  xor     edx, edx; dwFlags
0x18012ef4c  call    cs:__imp_HeapFree
0x18012ef52  jmp     loc_18012F4C3
0x18012ef57  lea     hostRuntimeId, [rsp+150h+dependencyPackages]; this
0x18012ef5c  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18012ef61  lea     rax, [rsp+150h+dependencyPackages]
0x18012ef66  mov     r8d, 200000h; flags
0x18012ef6c  lea     executablePath, [rsp+150h+dependencyPackages.m_size]; packageCount
0x18012ef71  mov     [rsp+150h+packages], rax; packages
0x18012ef76  mov     userTokenInternal, rbx; mainPackageFullName
0x18012ef79  mov     hostRuntimeId, r15; userTokenInternal
0x18012ef7c  call    ?GetFilteredPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGIPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetFilteredPackagesForMainPackage(IUserTokenInternal *,ushort const *,uint,unsigned __int64 *,PACKAGE_INFO * *)
0x18012ef81  mov     ebx, eax
0x18012ef83  test    eax, eax
0x18012ef85  jns     short loc_18012EFA4
0x18012ef87  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012ef8b  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012ef92  mov     r9d, eax; hr
0x18012ef95  mov     edx, 0C10h; lineNumber
0x18012ef9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ef9f  jmp     loc_18012F4B9
0x18012efa4  lea     rax, [rsp+150h+manager]
0x18012efa9  mov     [rsp+150h+manager.m_cacheManager.__ptr_.__value_], rsi
0x18012efae  mov     ebx, 1
0x18012efb3  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], rax
0x18012efb8  lea     userTokenInternal, [rsp+150h+packageExtensionIterator.m_index]
0x18012efbd  mov     byte ptr [rsp+150h+packageExtensionIterator.m_manager], bl
0x18012efc1  xor     ecx, ecx
0x18012efc3  mov     qword ptr [rsp+150h+packageExtensionIterator.m_index], rsi
0x18012efc8  call    cs:__imp_SRCacheManager_Open
0x18012efce  lea     hostRuntimeId, [rsp+150h+packageExtensionIterator]; this
0x18012efd3  mov     edi, eax
0x18012efd5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18012efda  test    edi, edi
0x18012efdc  jns     short loc_18012F02A
0x18012efde  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012efe2  lea     mainPackageFullName, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012efe9  mov     r9d, edi; hr
0x18012efec  mov     edx, 0A5h; lineNumber
0x18012eff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012eff6  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012effa  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012f001  mov     r9d, edi; hr
0x18012f004  mov     edx, 0C14h; lineNumber
0x18012f009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f00e  mov     hostRuntimeId, [rsp+150h+manager.m_cacheManager.__ptr_.__value_]
0x18012f013  mov     [rsp+150h+manager.m_cacheManager.__ptr_.__value_], rsi
0x18012f018  test    hostRuntimeId, hostRuntimeId
0x18012f01b  jz      short loc_18012F023
0x18012f01d  call    cs:__imp_SRCacheManager_Close
0x18012f023  mov     ebx, edi
0x18012f025  jmp     loc_18012F4B9
0x18012f02a  mov     rax, [rsp+150h+dependencyPackages.m_size]
0x18012f02f  mov     rdi, [rsp+150h+dependencyPackages.m_ptr]
0x18012f034  lea     r14, [rax+rax*4]
0x18012f038  shl     r14, 4
0x18012f03c  add     r14, rdi
0x18012f03f  cmp     rdi, r14
0x18012f042  jz      loc_18012F487
0x18012f048  mov     userTokenInternal, [rdi+10h]; packageFullName
0x18012f04c  lea     mainPackageFullName, [rsp+150h+packageId]; cacheId
0x18012f051  lea     hostRuntimeId, [rsp+150h+manager]; manager
0x18012f056  mov     [rsp+150h+packageId], rsi
0x18012f05b  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18012f060  mov     esi, eax
0x18012f062  test    eax, eax
0x18012f064  js      loc_18012F452
0x18012f06a  mov     userTokenInternal, [rsp+150h+packageId]; package
0x18012f06f  xor     esi, esi
0x18012f071  test    userTokenInternal, userTokenInternal
0x18012f074  jz      loc_18012F433
0x18012f07a  lea     executablePath, [rsp+150h+packageExtensionIterator]; iterator
0x18012f07f  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], rsi
0x18012f084  lea     mainPackageFullName, ?ExtensionCategoryHostRuntime@Attribute@Manifest@Packaging@Appx@@3QBGB; category
0x18012f08b  mov     [rsp+150h+packageExtensionIterator.m_index], esi
0x18012f08f  lea     hostRuntimeId, [rsp+150h+manager]; manager
0x18012f094  mov     [rsp+150h+packageExtensionIterator.m_manager], rsi
0x18012f099  call    ?FindByPackageAndCategory@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEAVPackageExtensionIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::FindByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow &)
0x18012f09e  mov     esi, eax
0x18012f0a0  xor     eax, eax
0x18012f0a2  test    esi, esi
0x18012f0a4  js      loc_18012F400
0x18012f0aa  xorps   xmm0, xmm0
0x18012f0ad  mov     qword ptr [rbp+50h+packageExtension.m_index], rax
0x18012f0b1  xorps   xmm1, xmm1
0x18012f0b4  movdqa  xmmword ptr [rbp+50h+packageExtension.m__cacheId], xmm0
0x18012f0b9  lea     executablePath, [rsp+150h+packageExtensionFound]; cacheFlags
0x18012f0be  movdqa  xmmword ptr [rbp+50h+packageExtension.m_activation], xmm0
0x18012f0c3  lea     mainPackageFullName, [rbp+50h+packageExtension]; found
0x18012f0c7  movdqa  xmmword ptr [rbp+50h+packageExtension.m_parameters.__ptr_.__value_], xmm1
0x18012f0cc  lea     hostRuntimeId, [rsp+150h+packageExtensionIterator]; this
0x18012f0d1  mov     [rbp+50h+packageExtension.m_category.__ptr_.__value_], rax
0x18012f0d5  mov     [rsp+150h+packageExtensionFound], al
0x18012f0d9  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18012f0de  mov     esi, eax
0x18012f0e0  test    eax, eax
0x18012f0e2  js      loc_18012F3DD
0x18012f0e8  xor     esi, esi
0x18012f0ea  cmp     [rsp+150h+packageExtensionFound], sil
0x18012f0ef  jz      short loc_18012F144
0x18012f0f1  mov     mainPackageFullName, [rbp+50h+packageExtension.m__cacheId]; packageExtension
0x18012f0f5  lea     executablePath, [rsp+150h+activationFound]; found
0x18012f0fa  mov     userTokenInternal, r12; hostId
0x18012f0fd  mov     [rsp+150h+activationFound], sil
0x18012f102  lea     hostRuntimeId, [rsp+150h+manager]; manager
0x18012f107  call    ?ExistsByHostIdAndPackageExtension@HostRuntime_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBG_JAEA_N@Z; StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64,bool &)
0x18012f10c  mov     esi, eax
0x18012f10e  test    eax, eax
0x18012f110  js      loc_18012F3D6
0x18012f116  cmp     [rsp+150h+activationFound], 0
0x18012f11b  jnz     short loc_18012F16B
0x18012f11d  add     [rsp+150h+packageExtensionIterator.m_index], ebx
0x18012f121  lea     executablePath, [rsp+150h+packageExtensionFound]; cacheFlags
0x18012f126  lea     mainPackageFullName, [rbp+50h+packageExtension]; found
0x18012f12a  lea     hostRuntimeId, [rsp+150h+packageExtensionIterator]; this
0x18012f12f  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18012f134  mov     esi, eax
0x18012f136  test    eax, eax
0x18012f138  jns     short loc_18012F0E8
0x18012f13a  mov     edx, 0C62h
0x18012f13f  jmp     loc_18012F3E2
0x18012f144  lea     hostRuntimeId, [rbp+50h+packageExtension]; this
0x18012f148  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18012f14d  mov     hostRuntimeId, [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_]
0x18012f152  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], rsi
0x18012f157  test    hostRuntimeId, hostRuntimeId
0x18012f15a  jz      short loc_18012F162
0x18012f15c  call    cs:__imp_SRCacheContext_Close
0x18012f162  add     rdi, 50h ; 'P'
0x18012f166  jmp     loc_18012F03F
0x18012f16b  mov     userTokenInternal, [rbp+50h+packageExtension.m_activation]; cacheId
0x18012f16f  lea     rax, [rsp+150h+activationFound]
0x18012f174  xor     r14d, r14d
0x18012f177  mov     [rsp+150h+packages], rax; manager
0x18012f17c  xorps   xmm0, xmm0
0x18012f17f  mov     [rsp+150h+activationFound], r14b
0x18012f184  xorps   xmm1, xmm1
0x18012f187  movdqa  xmmword ptr [rbp+50h+activation.m__cacheId], xmm0
0x18012f18c  lea     executablePath, [rbp+50h+activation]; found
0x18012f190  mov     dword ptr [rbp+50h+activation.m_flags], r14d
0x18012f194  lea     hostRuntimeId, [rsp+150h+manager]; manager
0x18012f199  mov     [rbp+50h+activation.m_hostId.__ptr_.__value_], r14
0x18012f19d  movdqa  xmmword ptr [rbp+50h+activation.m_executable.__ptr_.__value_], xmm0
0x18012f1a2  movdqa  xmmword ptr [rbp+50h+activation.m_runtimeType.__ptr_.__value_], xmm1
0x18012f1a7  mov     [rbp+50h+activation.m_resourceGroup.__ptr_.__value_], r14
0x18012f1ab  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18012f1b0  mov     esi, eax
0x18012f1b2  test    eax, eax
0x18012f1b4  jns     short loc_18012F21C
0x18012f1b6  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012f1ba  lea     mainPackageFullName, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f1c1  mov     r9d, eax; hr
0x18012f1c4  mov     edx, 32Fh; lineNumber
0x18012f1c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f1ce  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012f1d2  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012f1d9  mov     r9d, esi; hr
0x18012f1dc  mov     edx, 0C30h; lineNumber
0x18012f1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f1e6  lea     hostRuntimeId, [rbp+50h+activation]; this
0x18012f1ea  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012f1ef  lea     hostRuntimeId, [rbp+50h+packageExtension]; this
0x18012f1f3  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18012f1f8  mov     hostRuntimeId, [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_]
0x18012f1fd  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x18012f202  test    hostRuntimeId, hostRuntimeId
0x18012f205  jz      short loc_18012F20D
0x18012f207  call    cs:__imp_SRCacheContext_Close
0x18012f20d  mov     hostRuntimeId, [rsp+150h+manager.m_cacheManager.__ptr_.__value_]
0x18012f212  mov     [rsp+150h+manager.m_cacheManager.__ptr_.__value_], r14
0x18012f217  jmp     loc_18012F478
0x18012f21c  cmp     [rsp+150h+activationFound], r14b
0x18012f221  jnz     short loc_18012F276
0x18012f223  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012f227  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012f22e  mov     ebx, 80070490h
0x18012f233  mov     edx, 0C31h; lineNumber
0x18012f238  mov     r9d, ebx; hr
0x18012f23b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f240  lea     hostRuntimeId, [rbp+50h+activation]; this
0x18012f244  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012f249  lea     hostRuntimeId, [rbp+50h+packageExtension]; this
0x18012f24d  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18012f252  mov     hostRuntimeId, [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_]
0x18012f257  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x18012f25c  test    hostRuntimeId, hostRuntimeId
0x18012f25f  jz      short loc_18012F267
0x18012f261  call    cs:__imp_SRCacheContext_Close
0x18012f267  mov     hostRuntimeId, [rsp+150h+manager.m_cacheManager.__ptr_.__value_]
0x18012f26c  mov     [rsp+150h+manager.m_cacheManager.__ptr_.__value_], r14
0x18012f271  jmp     loc_18012F4AE
0x18012f276  xor     edx, edx; ptr
0x18012f278  mov     [rsp+150h+localExecutablePath.m_ptr], r14
0x18012f27d  lea     hostRuntimeId, [rsp+150h+localExecutablePath]; this
0x18012f282  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18012f287  mov     mainPackageFullName, [rbp+50h+activation.m_executable.__ptr_.__value_]; relativePath
0x18012f28b  lea     executablePath, [rsp+150h+localExecutablePath]; absolutePath
0x18012f290  mov     userTokenInternal, [rdi+10h]; packageFullName
0x18012f294  mov     hostRuntimeId, r15; userTokenInternal
0x18012f297  call    ?GetPackagedFileAbsolutePath@@YAJPEAUIUserTokenInternal@@PEBG1PEAPEAUHSTRING__@@@Z; GetPackagedFileAbsolutePath(IUserTokenInternal *,ushort const *,ushort const *,HSTRING__ * *)
0x18012f29c  mov     edi, eax
0x18012f29e  test    eax, eax
0x18012f2a0  jns     short loc_18012F2FA
0x18012f2a2  mov     hostRuntimeId, [rbp+58h]; callerReturnAddress
0x18012f2a6  lea     mainPackageFullName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18012f2ad  mov     r9d, eax; hr
0x18012f2b0  mov     edx, 0C35h; lineNumber
0x18012f2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f2ba  lea     hostRuntimeId, [rsp+150h+localExecutablePath]; this
0x18012f2bf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18012f2c4  lea     hostRuntimeId, [rbp+50h+activation]; this
0x18012f2c8  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012f2cd  lea     hostRuntimeId, [rbp+50h+packageExtension]; this
0x18012f2d1  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18012f2d6  mov     hostRuntimeId, [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_]
0x18012f2db  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x18012f2e0  test    hostRuntimeId, hostRuntimeId
0x18012f2e3  jz      short loc_18012F2EB
0x18012f2e5  call    cs:__imp_SRCacheContext_Close
0x18012f2eb  mov     hostRuntimeId, [rsp+150h+manager.m_cacheManager.__ptr_.__value_]
0x18012f2f0  mov     [rsp+150h+manager.m_cacheManager.__ptr_.__value_], r14
0x18012f2f5  jmp     loc_18012F018
0x18012f2fa  mov     eax, dword ptr [rbp+50h+activation.m_flags]
0x18012f2fd  test    al, al
0x18012f2ff  jns     short loc_18012F306
0x18012f301  mov     ecx, r14d
0x18012f304  jmp     short loc_18012F310
0x18012f306  test    al, 4
0x18012f308  jz      loc_18012F3AA
0x18012f30e  mov     ecx, ebx
0x18012f310  bt      eax, 8
0x18012f314  jnb     short loc_18012F31B
0x18012f316  mov     ebx, r14d
0x18012f319  jmp     short loc_18012F335
0x18012f31b  test    al, 10h
0x18012f31d  jnz     short loc_18012F335
0x18012f31f  test    al, 20h
0x18012f321  jz      short loc_18012F32A
0x18012f323  mov     ebx, 2
0x18012f328  jmp     short loc_18012F335
0x18012f32a  bt      eax, 9
0x18012f32e  jnb     short loc_18012F3A3
0x18012f330  mov     ebx, 3
0x18012f335  mov     rax, [rsp+150h+localExecutablePath.m_ptr]
0x18012f33a  mov     [r13+0], rax
0x18012f33e  mov     rax, [rbp+50h+arg_20]
0x18012f345  mov     [rsp+150h+localExecutablePath.m_ptr], r14
0x18012f34a  mov     [rax], ecx
0x18012f34c  lea     hostRuntimeId, [rsp+150h+localExecutablePath]; this
0x18012f351  mov     rax, [rbp+50h+arg_28]
0x18012f358  mov     [rax], ebx
0x18012f35a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18012f35f  lea     hostRuntimeId, [rbp+50h+activation]; this
0x18012f363  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012f368  lea     hostRuntimeId, [rbp+50h+packageExtension]; this
0x18012f36c  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18012f371  mov     hostRuntimeId, [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_]
0x18012f376  mov     [rsp+150h+packageExtensionIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x18012f37b  test    hostRuntimeId, hostRuntimeId
0x18012f37e  jz      short loc_18012F386
0x18012f380  call    cs:__imp_SRCacheContext_Close
0x18012f386  mov     hostRuntimeId, [rsp+150h+manager.m_cacheManager.__ptr_.__value_]
  ... truncated ...
```
