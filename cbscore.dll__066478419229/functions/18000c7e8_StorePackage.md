# StorePackage

- ea: `0x18000c7e8`
- end: `0x18000d90a`
- name: `StorePackage`
- size: `4386`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027790`

## callees

- `0x18000b46c`
- `0x18000b4b8`
- `0x18000b5fc`
- `0x18000c7e8`
- `0x18000d910`
- `0x18000e928`
- `0x180010f54`
- `0x1800110d0`
- `0x180013018`
- `0x180013250`
- `0x180013280`
- `0x1800132a4`
- `0x180015420`
- `0x180028e24`
- `0x180048fc0`
- `0x180069d10`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ae508`
- `0x1800b3248`
- `0x1800b693c`
- `0x1800b6a6c`
- `0x1800b980c`
- `0x1800bce9c`
- `0x1800c0054`
- `0x1800c2430`
- `0x1800cc844`
- `0x1800eb500`
- `0x1800eb920`
- `0x180167884`
- `0x1801a43e0`
- `0x1801b5b30`
- `0x1801e9cf8`
- `0x1801ea414`
- `0x1801ebcac`

## string_xrefs

- `0x18000d0af`: `InstallGroup`
- `0x18000cf70`: `InstallClient`
- `0x18000c9fd`: `LastMappingPackageCache`
- `0x18000cfa0`: `InstallName`
- `0x18000d19e`: `SelfUpdate`
- `0x18000cff1`: `InstallLocation`
- `0x18000cb8e`: `Failed to stage package manifest.`
- `0x18000cb21`: `Expected to find file in package manifest path: {}`
- `0x18000ca10`: `Not able to write last mapping package caching time`
- `0x18000ca6c`: `Failed to get manifest path for Package: {}`
- `0x18000cf09`: `Failed to get package store registry key to write package manifest location for package: {}`
- `0x18000d008`: `Unable to store package install location: {}, continuing...`
- `0x18000d0d1`: `Unable to store package install group: {}, continuing...`
- `0x18000cf8b`: `Unable to store package install client: {}, continuing...`
- `0x18000cfbb`: `Unable to store package install name: {}, continuing...`
- `0x18000d25e`: `Failed to write visibility for package: {}`
- `0x18000d1cd`: `Failed to set SelfUpdate property for package: {}`
- `0x18000d404`: `Failed to write baseline for package: {}`
- `0x18000d5b4`: `Failed to write baseline for package: {}`
- `0x18000d683`: `Failed to write baseline for package: {}`
- `0x18000d7e1`: `Failed to persist update detects.`
- `0x18000d848`: `Failed to persist component dependencies.`

## pseudocode

```c
__int64 __fastcall StorePackage(struct CCbsSession *a1, CCbsPackage *a2, void *a3, wchar_t *a4, int a5, __int64 a6)
{
  wchar_t *v7; // rbx
  int StoreObject; // r14d
  int v11; // edx
  __int64 v12; // rdx
  int v13; // edx
  int v14; // edx
  int v15; // eax
  int ManifestPath; // eax
  CCbsSession *v17; // r12
  int v18; // edx
  __int64 v19; // rdx
  wchar_t *v20; // rdi
  int v21; // edx
  int v22; // eax
  int v23; // edx
  CCbsIdentity *v24; // rcx
  int VersionlessStringId; // eax
  CCbsSession *v26; // r12
  int v27; // edx
  __int64 v28; // rdx
  wchar_t *v29; // rsi
  int v30; // edx
  CCbsSession *v31; // r12
  const wchar_t *v32; // rdx
  int v33; // eax
  int v34; // edx
  wchar_t *SpecialPackageIndex; // rax
  __int64 v36; // r8
  int v37; // edx
  const wchar_t *v38; // rdx
  int v39; // eax
  int v40; // edx
  const wchar_t *v41; // rdx
  int v42; // edx
  int v43; // eax
  int v44; // eax
  CCbsSession *v45; // r14
  struct CCbsSession *v46; // rdx
  unsigned int v47; // eax
  int TargetState; // eax
  __int64 v49; // rdx
  int v50; // eax
  int v51; // eax
  const wchar_t *v52; // rax
  int v53; // edx
  int v54; // edx
  int v55; // eax
  int v56; // edx
  int v57; // edx
  __int64 v58; // r14
  int v59; // edx
  unsigned __int64 i; // rax
  const wchar_t *v61; // rdx
  const wchar_t *v62; // rax
  int v63; // edx
  const struct std::nothrow_t *v64; // rdx
  const struct std::nothrow_t *v65; // rdx
  const wchar_t *v66; // rax
  int v67; // eax
  int v68; // edx
  const wchar_t *v69; // rax
  int v70; // eax
  int v71; // edx
  int v72; // eax
  int v73; // edx
  int v74; // eax
  int v75; // edx
  int updated; // eax
  int v77; // edx
  int v78; // eax
  int v79; // edx
  int *v81; // [rsp+20h] [rbp-E0h]
  CCbsSession *v82; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v83; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v84; // [rsp+40h] [rbp-C0h] BYREF
  int *v85; // [rsp+48h] [rbp-B8h] BYREF
  int v86[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v87; // [rsp+58h] [rbp-A8h] BYREF
  int v88[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v89; // [rsp+68h] [rbp-98h]
  __int128 v90; // [rsp+70h] [rbp-90h] BYREF
  __int64 v91; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v92[2]; // [rsp+88h] [rbp-78h] BYREF
  char v93; // [rsp+98h] [rbp-68h]
  __int64 v94; // [rsp+A0h] [rbp-60h] BYREF
  int v95; // [rsp+A8h] [rbp-58h]
  __int128 v96; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v97; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-38h] BYREF
  int v99; // [rsp+D0h] [rbp-30h]
  __int128 v100; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h] BYREF
  int v103; // [rsp+F8h] [rbp-8h]
  __int128 v104; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v106; // [rsp+118h] [rbp+18h] BYREF
  wchar_t *v107; // [rsp+120h] [rbp+20h] BYREF
  int v108; // [rsp+128h] [rbp+28h] BYREF
  int v109[2]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v110; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)v86 = a6;
  v82 = a1;
  v92[1] = &vPackageStoreLock;
  v107 = a4;
  v7 = 0;
  v92[0] = &PackageTrackerLocker::`vftable';
  v106 = 0;
  *(_QWORD *)v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v110 = 0;
  v87 = 0;
  v108 = 0;
  v93 = 0;
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v92);
  if ( !a1 )
  {
    StoreObject = -2147024809;
    v108 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
      v82 = (CCbsSession *)&v108;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v82);
    }
    v12 = 2926;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)0x80070057LL,
      (int)v81);
LABEL_183:
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v92);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v87);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v102);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v94);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v98);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v88);
    return (unsigned int)StoreObject;
  }
  if ( !a2 )
  {
    StoreObject = -2147024809;
    v108 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No package specified");
      v82 = (CCbsSession *)&v108;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&v82);
    }
    v12 = 2927;
    goto LABEL_13;
  }
  if ( !a5 )
  {
    StoreObject = -2147024809;
    v108 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Cannot add a package that is absent");
      v82 = (CCbsSession *)&v108;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&v82);
    }
    v12 = 2928;
    goto LABEL_13;
  }
  v15 = PackageStoreSetProperty(a1, L"LastMappingPackageCache", 0);
  if ( v15 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v15, "Not able to write last mapping package caching time");
  v84 = 0;
  ManifestPath = CCbsPackage::GetManifestPath(a2, a1, &v84);
  StoreObject = ManifestPath;
  if ( ManifestPath < 0 )
  {
    v108 = ManifestPath;
    if ( LogAdapter::g_Logger )
    {
      v17 = (CCbsSession *)&qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v17 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get manifest path for Package: {}",
        (__int64)&v82);
      v83 = (wchar_t *)&v108;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {}",
        (__int64)&v83);
    }
    v19 = 2940;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)(unsigned int)StoreObject,
      (int)v81);
LABEL_23:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
    goto LABEL_183;
  }
  v20 = v84;
  v106 = (wchar_t *)FileFromPath(v84);
  if ( !v106 )
  {
    StoreObject = -2147024809;
    v108 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      v82 = (CCbsSession *)v20;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Expected to find file in package manifest path: {}",
        (__int64)&v82);
      v83 = (wchar_t *)&v108;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)&v83);
    }
    v19 = 2943;
    goto LABEL_22;
  }
  v22 = StorePackageManifestAndCatalog(a1, (CCbsPackage **)a2, a3);
  StoreObject = v22;
  if ( v22 < 0 )
  {
    v108 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to stage package manifest.");
      v82 = (CCbsSession *)&v108;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&v82);
    }
    v19 = 2949;
    goto LABEL_22;
  }
  v24 = (CCbsIdentity *)*((_QWORD *)a2 + 14);
  v83 = 0;
  VersionlessStringId = CCbsIdentity::GetVersionlessStringId(v24, &v83);
  StoreObject = VersionlessStringId;
  if ( VersionlessStringId < 0 )
  {
    v108 = VersionlessStringId;
    if ( LogAdapter::g_Logger )
    {
      v26 = (CCbsSession *)&qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v26 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v26;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get versionless identity for package: {}",
        (__int64)&v82);
      *(_QWORD *)v109 = &v108;
      LOBYTE(v27) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v27,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    v28 = 2957;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)(unsigned int)StoreObject,
      (int)v81);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
    goto LABEL_23;
  }
  v29 = v83;
  v81 = (int *)&v98;
  StoreObject = CCbsSession::GetStoreObject(a1, v83, 3);
  if ( StoreObject < 0 )
  {
    v108 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get package index store object for package ");
      v82 = (CCbsSession *)&v108;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)&v82);
    }
    v28 = 2961;
    goto LABEL_38;
  }
  v31 = (CCbsSession *)&qword_1802EB518;
  v32 = &qword_1802EB518;
  if ( *((_QWORD *)a2 + 15) )
    v32 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v33 = CCbsStoreObject::SetValue((CCbsStoreObject *)&v98, v32, 0);
  StoreObject = v33;
  if ( v33 < 0 )
  {
    v108 = v33;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to store package index for package: {}",
        (__int64)&v82);
      *(_QWORD *)v109 = &v108;
      LOBYTE(v34) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v34,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    v28 = 2965;
    goto LABEL_38;
  }
  SpecialPackageIndex = CCbsPackage::GetSpecialPackageIndex(a2);
  if ( SpecialPackageIndex )
  {
    v81 = (int *)&v94;
    StoreObject = CCbsSession::GetStoreObject(v82, SpecialPackageIndex, 3);
    if ( StoreObject < 0 )
    {
      v108 = StoreObject;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get system index store object");
        v82 = (CCbsSession *)&v108;
        LOBYTE(v37) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {}",
          (__int64)&v82);
      }
      v28 = 2976;
      goto LABEL_38;
    }
    v38 = &qword_1802EB518;
    if ( *((_QWORD *)a2 + 15) )
      v38 = (const wchar_t *)*((_QWORD *)a2 + 15);
    v39 = CCbsStoreObject::SetValue((CCbsStoreObject *)&v94, v38, 0);
    v36 = 0;
    StoreObject = v39;
    if ( v39 < 0 )
    {
      v108 = v39;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)a2 + 15) )
          v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
        v82 = v31;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to store package index for package: {}",
          (__int64)&v82);
        *(_QWORD *)v109 = &v108;
        LOBYTE(v40) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v40,
          3,
          (unsigned int)": {}",
          (__int64)v109);
      }
      v28 = 2979;
      goto LABEL_38;
    }
  }
  v41 = &qword_1802EB518;
  v81 = v88;
  if ( *((_QWORD *)a2 + 15) != v36 )
    v41 = (const wchar_t *)*((_QWORD *)a2 + 15);
  StoreObject = CCbsSession::GetStoreObject(v82, v41, 2);
  if ( StoreObject < 0 )
  {
    v108 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get package store registry key to write package manifest location for package: {}",
        (__int64)&v82);
      *(_QWORD *)v109 = &v108;
      LOBYTE(v42) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v42,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    v28 = 2983;
    goto LABEL_38;
  }
  if ( v107 )
  {
    if ( *v107 )
    {
      v43 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"InstallClient", v107);
      if ( v43 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          (unsigned int)v43,
          "Unable to store package install client: {}, continuing...",
          &v107);
    }
  }
  v44 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"InstallName", v106);
  if ( v44 < 0 )
    LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
      2,
      (unsigned int)v44,
      "Unable to store package install name: {}, continuing...",
      &v106);
  v45 = v82;
  v46 = v82;
  *v106 = 0;
  if ( (int)CCbsPackage::GetInstallLocation(a2, v46, &v110) >= 0 )
  {
    v47 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"InstallLocation", v110);
    LogAdapter::TraceAtLevelIfFailed<long,AutoScz>(
      2,
      v47,
      "Unable to store package install location: {}, continuing...",
      &v110,
      v88);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UninstallInstallGroup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UninstallInstallGroup>::GetImpl'::`2'::impl) )
  {
    TargetState = CCbsPackage::GetTargetState(a2, v45, 0, (enum CbsState *)&v108);
    v49 = (unsigned int)TargetState;
    if ( TargetState < 0 )
    {
      v52 = &qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v52 = (const wchar_t *)*((_QWORD *)a2 + 15);
      *(_QWORD *)v109 = v52;
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        1,
        v49,
        "Unable to get package target state for package: {}, continuing...",
        v109);
    }
    else if ( *((_BYTE *)v45 + 2254) && CCbsPackage::IsLCUPackage(a2) && a5 <= 64 )
    {
      v50 = SczAllocFromSz(&v87, *((_QWORD *)v45 + 80));
      if ( v50 >= 0 )
      {
        v7 = v87;
        *(_QWORD *)v109 = v87;
        v51 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"InstallGroup", v87);
        if ( v51 < 0 )
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
            2,
            (unsigned int)v51,
            "Unable to store package install group: {}, continuing...",
            v109);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageplanning.cpp",
          (const char *)(unsigned int)v50,
          (int)v81);
        v7 = v87;
      }
    }
  }
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"CurrentState", a5);
  if ( StoreObject < 0 )
  {
    v108 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to store current state for package: {}",
        (__int64)&v82);
      *(_QWORD *)v109 = &v108;
      LOBYTE(v53) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v53,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    v28 = 3029;
    goto LABEL_38;
  }
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"SelfUpdate", *((_DWORD *)a2 + 149));
  if ( StoreObject < 0 )
  {
    v108 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to set SelfUpdate property for package: {}",
        (__int64)&v82);
      *(_QWORD *)v109 = &v108;
      LOBYTE(v54) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v54,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    v28 = 3032;
    goto LABEL_38;
  }
  v55 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"Visibility", 2u);
  StoreObject = v55;
  if ( v55 < 0 )
  {
    v109[0] = v55;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to write visibility for package: {}",
        (__int64)&v82);
      *(_QWORD *)v86 = v109;
      LOBYTE(v57) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v57,
        3,
        (unsigned int)": {}",
        (__int64)v86);
    }
    v28 = 3040;
    goto LABEL_38;
  }
  v58 = *(_QWORD *)v86 + 152LL;
  if ( *(_QWORD *)v86 == -152 )
  {
    StoreObject = -2147467261;
    v108 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v82 = v31;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get package owners for package: {}",
        (__int64)&v82);
      *(_QWORD *)v86 = &v108;
      LOBYTE(v59) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v59,
        3,
        (unsigned int)": {}",
        (__int64)v86);
    }
    v28 = 3054;
    goto LABEL_38;
  }
  if ( *(_QWORD *)(*(_QWORD *)v86 + 176LL) )
  {
    v108 = 0;
    for ( i = 0; ; i = *(_QWORD *)v109 + 1LL )
    {
      *(_QWORD *)v109 = i;
      if ( i >= *(_QWORD *)(v58 + 24) )
        break;
      v61 = &qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v61 = (const wchar_t *)*((_QWORD *)a2 + 15);
      if ( (unsigned __int8)StringsAreEqual(*(_QWORD *)(*(_QWORD *)(v58 + 40) + 8 * i), v61, 1) )
        goto LABEL_123;
    }
  }
  else
  {
LABEL_123:
    v108 = 1;
  }
  if ( !*((_BYTE *)a2 + 1062) )
    goto LABEL_143;
  v62 = &qword_1802EB518;
  if ( *((_QWORD *)a2 + 15) )
    v62 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v85 = (int *)v62;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v56) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      v56,
      1,
      (unsigned int)"Client specified that package {} is a baseline.",
      (__int64)&v85);
  }
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"Baseline", 1u);
  if ( StoreObject >= 0 )
  {
LABEL_143:
    if ( v108 )
    {
      if ( (unsigned int)CCbsSession::IsOffline(v82) && *((char *)v82 + 692) < 0 )
      {
        v66 = &qword_1802EB518;
        if ( *((_QWORD *)a2 + 15) )
          v66 = (const wchar_t *)*((_QWORD *)a2 + 15);
        v85 = (int *)v66;
        LogAdapter::TraceAtLevel<wchar_t const *>(
          1,
          "Client specified that session contains all baseline packages: {}",
          &v85);
        v67 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"Baseline", 1u);
        StoreObject = v67;
        if ( v67 < 0 )
        {
          v109[0] = v67;
          if ( LogAdapter::g_Logger )
          {
            if ( *((_QWORD *)a2 + 15) )
              v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
            v85 = (int *)v31;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to write baseline for package: {}",
              (__int64)&v85);
            *(_QWORD *)v86 = v109;
            LOBYTE(v68) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v68,
              3,
              (unsigned int)": {}",
              (__int64)v86);
          }
          v28 = 3083;
          goto LABEL_38;
        }
      }
      if ( CCbsPackage::IsFODorLPPackage(a2) && !*((_BYTE *)a2 + 1063) )
      {
        v69 = &qword_1802EB518;
        if ( *((_QWORD *)a2 + 15) )
          v69 = (const wchar_t *)*((_QWORD *)a2 + 15);
        v85 = (int *)v69;
        LogAdapter::TraceAtLevel<wchar_t const *>(1, "Found baseline FOD or LP Package {}", &v85);
        v70 = CCbsStoreObject::SetValue((CCbsStoreObject *)v88, L"Baseline", 1u);
        StoreObject = v70;
        if ( v70 < 0 )
        {
          v109[0] = v70;
          if ( LogAdapter::g_Logger )
          {
            if ( *((_QWORD *)a2 + 15) )
              v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
            v85 = (int *)v31;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to write baseline for package: {}",
              (__int64)&v85);
            *(_QWORD *)v86 = v109;
            LOBYTE(v71) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v71,
              3,
              (unsigned int)": {}",
              (__int64)v86);
          }
          v28 = 3090;
          goto LABEL_38;
        }
      }
    }
    v72 = StorePackageSources((CCbsStoreObject *)v88, a2);
    StoreObject = v72;
    if ( v72 >= 0 )
    {
      v74 = StorePackageDetects(v82, a2);
      StoreObject = v74;
      if ( v74 >= 0 )
      {
        updated = StoreUpdateDetects(v82, a2);
        StoreObject = updated;
        if ( updated >= 0 )
        {
          v78 = StoreComponentDependencies(v82, a2);
          StoreObject = v78;
          if ( v78 >= 0 )
          {
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
            StoreObject = 0;
            goto LABEL_183;
          }
          v109[0] = v78;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist component dependencies.");
            v85 = v109;
            LOBYTE(v79) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v79,
              3,
              (unsigned int)": {}",
              (__int64)&v85);
          }
          v28 = 3104;
        }
        else
        {
          v109[0] = updated;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist update detects.");
            v85 = v109;
            LOBYTE(v77) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v77,
              3,
              (unsigned int)": {}",
              (__int64)&v85);
          }
          v28 = 3102;
        }
      }
      else
      {
        v109[0] = v74;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist package detects.");
          v85 = v109;
          LOBYTE(v75) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v75,
            3,
            (unsigned int)": {}",
            (__int64)&v85);
        }
        v28 = 3100;
      }
    }
    else
    {
      v109[0] = v72;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)a2 + 15) )
          v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
        v85 = (int *)v31;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to persist sources for package: {}",
          (__int64)&v85);
        *(_QWORD *)v86 = v109;
        LOBYTE(v73) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v73,
          3,
          (unsigned int)": {}",
          (__int64)v86);
      }
      v28 = 3095;
    }
    goto LABEL_38;
  }
  v109[0] = StoreObject;
  if ( LogAdapter::g_Logger )
  {
    if ( *((_QWORD *)a2 + 15) )
      v31 = (CCbsSession *)*((_QWORD *)a2 + 15);
    v85 = (int *)v31;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to write baseline for package: {}",
      (__int64)&v85);
    *(_QWORD *)v86 = v109;
    LOBYTE(v63) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v63,
      3,
      (unsigned int)": {}",
      (__int64)v86);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC04,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)(unsigned int)StoreObject,
    (int)v81);
  if ( v29 )
    operator delete(v29 - 4, v64);
  if ( v20 )
    operator delete(v20 - 4, v64);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v92);
  if ( v7 )
    operator delete(v7 - 4, v65);
  if ( v110 )
  {
    operator delete(v110 - 4, v65);
    v110 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v105);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v104 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v104);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v97);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v96 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v101);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v100 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v100);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v91);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v90 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v90);
  return (unsigned int)StoreObject;
}

```

## disassembly

```asm
0x18000c7e8  push    rbp
0x18000c7ea  push    rbx
0x18000c7eb  push    rsi
0x18000c7ec  push    rdi
0x18000c7ed  push    r12
0x18000c7ef  push    r13
0x18000c7f1  push    r14
0x18000c7f3  push    r15
0x18000c7f5  lea     rbp, [rsp-58h]
0x18000c7fa  sub     rsp, 158h
0x18000c801  mov     rax, cs:__security_cookie
0x18000c808  xor     rax, rsp
0x18000c80b  mov     [rbp+90h+var_50], rax
0x18000c80f  mov     rax, [rbp+90h+arg_28]
0x18000c816  xor     r15d, r15d
0x18000c819  xorps   xmm0, xmm0
0x18000c81c  mov     qword ptr [rsp+190h+var_140], rax
0x18000c821  lea     rax, ?vPackageStoreLock@@3UMonitoredCritSec@@A; MonitoredCritSec vPackageStoreLock
0x18000c828  mov     [rsp+190h+var_160], rcx
0x18000c82d  mov     [rbp+90h+var_100], rax
0x18000c831  mov     r12, rcx
0x18000c834  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x18000c83b  mov     [rbp+90h+var_70], r9
0x18000c83f  mov     ebx, r15d
0x18000c842  mov     [rbp+90h+var_108], rax
0x18000c846  lea     rcx, [rbp+90h+var_108]; this
0x18000c84a  mov     [rbp+90h+var_78], r15
0x18000c84e  mov     rsi, r8
0x18000c851  mov     qword ptr [rsp+190h+var_130], r15
0x18000c856  mov     r13, rdx
0x18000c859  mov     [rsp+190h+var_128], r15d
0x18000c85e  movdqu  [rsp+190h+var_120], xmm0
0x18000c864  mov     [rbp+90h+var_110], r15
0x18000c868  mov     [rbp+90h+var_C8], r15
0x18000c86c  mov     [rbp+90h+var_C0], r15d
0x18000c870  movdqu  [rbp+90h+var_B8], xmm0
0x18000c875  mov     [rbp+90h+var_A8], r15
0x18000c879  mov     [rbp+90h+var_F0], r15
0x18000c87d  mov     [rbp+90h+var_E8], r15d
0x18000c881  movdqu  [rbp+90h+var_E0], xmm0
0x18000c886  mov     [rbp+90h+var_D0], r15
0x18000c88a  mov     [rbp+90h+var_A0], r15
0x18000c88e  mov     [rbp+90h+var_98], r15d
0x18000c892  movdqu  [rbp+90h+var_90], xmm0
0x18000c897  mov     [rbp+90h+var_80], r15
0x18000c89b  mov     [rbp+90h+var_58], r15
0x18000c89f  mov     [rsp+190h+var_138], rbx
0x18000c8a4  mov     [rbp+90h+var_68], r15d
0x18000c8a8  mov     [rbp+90h+var_F8], r15b
0x18000c8ac  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x18000c8b1  test    r12, r12
0x18000c8b4  jnz     short loc_18000C917
0x18000c8b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c8bd  mov     r14d, 80070057h
0x18000c8c3  mov     [rbp+90h+var_68], r14d
0x18000c8c7  test    rcx, rcx
0x18000c8ca  jz      short loc_18000C90D
0x18000c8cc  lea     r15d, [r12+3]
0x18000c8d1  xor     edx, edx
0x18000c8d3  mov     r8d, r15d
0x18000c8d6  lea     r9, aNoSessionSpeci_0; "No session specified"
0x18000c8dd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c8e2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c8e9  lea     rax, [rbp+90h+var_68]
0x18000c8ed  mov     [rsp+190h+var_160], rax
0x18000c8f2  lea     r9, asc_1802EE7AC; ": {}"
0x18000c8f9  lea     rax, [rsp+190h+var_160]
0x18000c8fe  mov     r8d, r15d
0x18000c901  mov     dl, 1
0x18000c903  mov     qword ptr [rsp+190h+var_170], rax
0x18000c908  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c90d  mov     edx, 0B6Eh
0x18000c912  jmp     loc_18000C9DF
0x18000c917  test    r13, r13
0x18000c91a  jnz     short loc_18000C979
0x18000c91c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c923  mov     r14d, 80070057h
0x18000c929  mov     [rbp+90h+var_68], r14d
0x18000c92d  test    rcx, rcx
0x18000c930  jz      short loc_18000C972
0x18000c932  lea     r15d, [r13+3]
0x18000c936  xor     edx, edx
0x18000c938  mov     r8d, r15d
0x18000c93b  lea     r9, aNoPackageSpeci; "No package specified"
0x18000c942  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c947  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c94e  lea     rax, [rbp+90h+var_68]
0x18000c952  mov     [rsp+190h+var_160], rax
0x18000c957  lea     r9, asc_1802EE7AC; ": {}"
0x18000c95e  lea     rax, [rsp+190h+var_160]
0x18000c963  mov     r8d, r15d
0x18000c966  mov     dl, 1
0x18000c968  mov     qword ptr [rsp+190h+var_170], rax
0x18000c96d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c972  mov     edx, 0B6Fh
0x18000c977  jmp     short loc_18000C9DF
0x18000c979  cmp     [rbp+90h+arg_20], r15d
0x18000c980  jnz     short loc_18000C9FA
0x18000c982  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c989  mov     r14d, 80070057h
0x18000c98f  mov     [rbp+90h+var_68], r14d
0x18000c993  test    rcx, rcx
0x18000c996  jz      short loc_18000C9DA
0x18000c998  mov     r15d, 3
0x18000c99e  lea     r9, aCannotAddAPack; "Cannot add a package that is absent"
0x18000c9a5  mov     r8d, r15d
0x18000c9a8  xor     edx, edx
0x18000c9aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c9af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c9b6  lea     rax, [rbp+90h+var_68]
0x18000c9ba  mov     [rsp+190h+var_160], rax
0x18000c9bf  lea     r9, asc_1802EE7AC; ": {}"
0x18000c9c6  lea     rax, [rsp+190h+var_160]
0x18000c9cb  mov     r8d, r15d
0x18000c9ce  mov     dl, 1
0x18000c9d0  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000c9d5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c9da  mov     edx, 0B70h; void *
0x18000c9df  mov     rcx, [rbp+98h]; this
0x18000c9e6  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000c9ed  mov     r9d, r14d; char *
0x18000c9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9f5  jmp     loc_18000D8A5
0x18000c9fa  xor     r8d, r8d; unsigned int
0x18000c9fd  lea     rdx, aLastmappingpac; "LastMappingPackageCache"
0x18000ca04  mov     rcx, r12; struct CCbsSession *
0x18000ca07  call    ?PackageStoreSetProperty@@YAJPEAVCCbsSession@@PEB_WK@Z; PackageStoreSetProperty(CCbsSession *,wchar_t const *,ulong)
0x18000ca0c  test    eax, eax
0x18000ca0e  jns     short loc_18000CA23
0x18000ca10  lea     r8, aNotAbleToWrite; "Not able to write last mapping package "...
0x18000ca17  mov     edx, eax
0x18000ca19  mov     ecx, 2
0x18000ca1e  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18000ca23  lea     r8, [rsp+190h+var_150]; wchar_t **
0x18000ca28  mov     [rsp+190h+var_150], r15
0x18000ca2d  mov     rdx, r12; struct CCbsSession *
0x18000ca30  mov     rcx, r13; this
0x18000ca33  call    ?GetManifestPath@CCbsPackage@@QEAAJPEAVCCbsSession@@PEAPEA_W@Z; CCbsPackage::GetManifestPath(CCbsSession *,wchar_t * *)
0x18000ca38  mov     r14d, eax
0x18000ca3b  test    eax, eax
0x18000ca3d  jns     loc_18000CADD
0x18000ca43  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ca4a  mov     [rbp+90h+var_68], eax
0x18000ca4d  test    rcx, rcx
0x18000ca50  jz      short loc_18000CAB3
0x18000ca52  cmp     [r13+78h], r15
0x18000ca56  lea     rax, [rsp+190h+var_160]
0x18000ca5b  lea     r12, qword_1802EB518
0x18000ca62  mov     qword ptr [rsp+190h+var_170], rax
0x18000ca67  cmovnz  r12, [r13+78h]
0x18000ca6c  lea     r9, aFailedToGetMan_1; "Failed to get manifest path for Package"...
0x18000ca73  mov     r15d, 3
0x18000ca79  mov     [rsp+190h+var_160], r12
0x18000ca7e  xor     edx, edx
0x18000ca80  mov     r8d, r15d
0x18000ca83  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000ca88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ca8f  lea     rax, [rbp+90h+var_68]
0x18000ca93  mov     [rsp+190h+var_158], rax
0x18000ca98  lea     r9, asc_1802EE7AC; ": {}"
0x18000ca9f  lea     rax, [rsp+190h+var_158]
0x18000caa4  mov     r8d, r15d
0x18000caa7  mov     dl, 1
0x18000caa9  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000caae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cab3  mov     edx, 0B7Ch; void *
0x18000cab8  mov     rcx, [rbp+98h]; this
0x18000cabf  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000cac6  mov     r9d, r14d; char *
0x18000cac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cace  lea     rcx, [rsp+190h+var_150]
0x18000cad3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000cad8  jmp     loc_18000D8A5
0x18000cadd  mov     rdi, [rsp+190h+var_150]
0x18000cae2  mov     rcx, rdi
0x18000cae5  call    FileFromPath
0x18000caea  mov     [rbp+90h+var_78], rax
0x18000caee  test    rax, rax
0x18000caf1  jnz     short loc_18000CB64
0x18000caf3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cafa  mov     r14d, 80070057h
0x18000cb00  mov     [rbp+90h+var_68], r14d
0x18000cb04  test    rcx, rcx
0x18000cb07  jz      short loc_18000CB5A
0x18000cb09  lea     rax, [rsp+190h+var_160]
0x18000cb0e  mov     [rsp+190h+var_160], rdi
0x18000cb13  mov     r15d, 3
0x18000cb19  mov     qword ptr [rsp+190h+var_170], rax
0x18000cb1e  mov     r8d, r15d
0x18000cb21  lea     r9, aExpectedToFind; "Expected to find file in package manife"...
0x18000cb28  xor     edx, edx
0x18000cb2a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000cb2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cb36  lea     rax, [rbp+90h+var_68]
0x18000cb3a  mov     [rsp+190h+var_158], rax
0x18000cb3f  lea     r9, asc_1802EE7AC; ": {}"
0x18000cb46  lea     rax, [rsp+190h+var_158]
0x18000cb4b  mov     r8d, r15d
0x18000cb4e  mov     dl, 1
0x18000cb50  mov     qword ptr [rsp+190h+var_170], rax
0x18000cb55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cb5a  mov     edx, 0B7Fh
0x18000cb5f  jmp     loc_18000CAB8
0x18000cb64  mov     r8, rsi
0x18000cb67  mov     rdx, r13
0x18000cb6a  mov     rcx, r12
0x18000cb6d  call    StorePackageManifestAndCatalog
0x18000cb72  mov     r14d, eax
0x18000cb75  test    eax, eax
0x18000cb77  jns     short loc_18000CBD4
0x18000cb79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cb80  mov     [rbp+90h+var_68], eax
0x18000cb83  test    rcx, rcx
0x18000cb86  jz      short loc_18000CBCA
0x18000cb88  mov     r15d, 3
0x18000cb8e  lea     r9, aFailedToStageP; "Failed to stage package manifest."
0x18000cb95  mov     r8d, r15d
0x18000cb98  xor     edx, edx
0x18000cb9a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000cb9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cba6  lea     rax, [rbp+90h+var_68]
0x18000cbaa  mov     [rsp+190h+var_160], rax
0x18000cbaf  lea     r9, asc_1802EE7AC; ": {}"
0x18000cbb6  lea     rax, [rsp+190h+var_160]
0x18000cbbb  mov     r8d, r15d
0x18000cbbe  mov     dl, 1
0x18000cbc0  mov     qword ptr [rsp+190h+var_170], rax
0x18000cbc5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cbca  mov     edx, 0B85h
0x18000cbcf  jmp     loc_18000CAB8
0x18000cbd4  mov     rcx, [r13+70h]; this
0x18000cbd8  lea     rdx, [rsp+190h+var_158]; wchar_t **
0x18000cbdd  mov     [rsp+190h+var_158], r15
0x18000cbe2  call    ?GetVersionlessStringId@CCbsIdentity@@QEAAJPEAPEA_W@Z; CCbsIdentity::GetVersionlessStringId(wchar_t * *)
0x18000cbe7  mov     r14d, eax
0x18000cbea  test    eax, eax
0x18000cbec  jns     loc_18000CC8A
0x18000cbf2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cbf9  mov     [rbp+90h+var_68], eax
0x18000cbfc  test    rcx, rcx
0x18000cbff  jz      short loc_18000CC60
0x18000cc01  cmp     [r13+78h], r15
0x18000cc05  lea     rax, [rsp+190h+var_160]
0x18000cc0a  lea     r12, qword_1802EB518
0x18000cc11  mov     qword ptr [rsp+190h+var_170], rax
0x18000cc16  cmovnz  r12, [r13+78h]
0x18000cc1b  lea     r9, aFailedToGetVer_6; "Failed to get versionless identity for "...
0x18000cc22  mov     r15d, 3
0x18000cc28  mov     [rsp+190h+var_160], r12
0x18000cc2d  xor     edx, edx
0x18000cc2f  mov     r8d, r15d
0x18000cc32  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000cc37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cc3e  lea     rax, [rbp+90h+var_68]
0x18000cc42  mov     qword ptr [rbp+90h+var_60], rax
0x18000cc46  lea     r9, asc_1802EE7AC; ": {}"
0x18000cc4d  lea     rax, [rbp+90h+var_60]
0x18000cc51  mov     r8d, r15d
0x18000cc54  mov     dl, 1
0x18000cc56  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000cc5b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cc60  mov     edx, 0B8Dh; void *
0x18000cc65  mov     rcx, [rbp+98h]; this
0x18000cc6c  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000cc73  mov     r9d, r14d; char *
0x18000cc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc7b  lea     rcx, [rsp+190h+var_158]
0x18000cc80  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000cc85  jmp     loc_18000CACE
0x18000cc8a  mov     rsi, [rsp+190h+var_158]
0x18000cc8f  lea     rax, [rbp+90h+var_C8]
0x18000cc93  mov     r9d, 1
0x18000cc99  mov     qword ptr [rsp+190h+var_170], rax
0x18000cc9e  mov     rdx, rsi
0x18000cca1  mov     rcx, r12
0x18000cca4  lea     r15d, [r9+2]
0x18000cca8  mov     r8d, r15d
0x18000ccab  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x18000ccb0  mov     r14d, eax
0x18000ccb3  xor     eax, eax
0x18000ccb5  test    r14d, r14d
0x18000ccb8  jns     short loc_18000CD10
0x18000ccba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ccc1  mov     [rbp+90h+var_68], r14d
0x18000ccc5  test    rcx, rcx
0x18000ccc8  jz      short loc_18000CD06
0x18000ccca  lea     r9, aFailedToGetPac_25; "Failed to get package index store objec"...
0x18000ccd1  mov     r8d, r15d
0x18000ccd4  xor     edx, edx
0x18000ccd6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000ccdb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cce2  lea     rax, [rbp+90h+var_68]
0x18000cce6  mov     [rsp+190h+var_160], rax
0x18000cceb  lea     r9, asc_1802EE7AC; ": {}"
0x18000ccf2  lea     rax, [rsp+190h+var_160]
0x18000ccf7  mov     r8d, r15d
0x18000ccfa  mov     dl, 1
0x18000ccfc  mov     qword ptr [rsp+190h+var_170], rax
0x18000cd01  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cd06  mov     edx, 0B91h
  ... truncated ...
```
