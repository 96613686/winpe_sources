# CComRegCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x180062930`
- end: `0x1800635c4`
- name: `?GetClassInfoW@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `3220`
- prototype: `HRESULT __fastcall(CComRegCatalog *this, unsigned int dwFlags, IUserToken *pUserToken, const _GUID *guidConfiguredClsid, const _GUID *riid, void **ppv, void *pComCatalog)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180064240`

## callees

- `0x18000712c`
- `0x18001d0e8`
- `0x180022f94`
- `0x18003a8bc`
- `0x180040078`
- `0x180057834`
- `0x180057850`
- `0x180058e20`
- `0x180061ecc`
- `0x180062930`
- `0x180063660`
- `0x1800638d8`
- `0x180063ad0`
- `0x1800640c4`
- `0x180064444`
- `0x180064488`
- `0x1800646dc`
- `0x18006474c`
- `0x180069904`
- `0x1800865f4`
- `0x180086f14`
- `0x180086f50`
- `0x18008db2c`
- `0x180127550`
- `0x1801999b0`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062c35`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062c35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062f6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006302f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800630a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062f6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006302f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800630a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063151`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180247ab8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180247ab8`

## string_xrefs

- `0x180062a57`: `CLSID\%ls`
- `0x180062a7b`: `onecore\com\combase\catalog\services.cxx`
- `0x180062a9e`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180062af0`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180062f31`: `onecore\com\combase\catalog\regcat.cxx`
- `0x1800630b6`: `onecore\com\combase\catalog\regcat.cxx`
- `0x1800631da`: `onecore\com\combase\catalog\regcat.cxx`
- `0x1800631fa`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18006322e`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18006342e`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180063455`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18006348e`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18006350f`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180063552`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180247a53`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180247b2c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180063435`: `CLSID:%ls`
- `0x18006355e`: `CLSID:%ls`
- `0x18006349f`: `Excessive or cyclic chain of TreatAs values starting from CLSID %ls`
- `0x180247b08`: `CComRegCatalog::GetClassInfoW`
- `0x180247b0f`: `HRESULT:%#x, CLSID:%ls`

## pseudocode

```c
__int64 __fastcall CComRegCatalog::GetClassInfoW(
        CComRegCatalog *this,
        __int64 dwFlags,
        IUserToken *pUserToken,
        _GUID *guidConfiguredClsid,
        const _GUID *riid,
        void **ppv,
        __int64 (__fastcall ***pComCatalog)(_QWORD, GUID *, wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> *))
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> *); // r15
  CComRegCatalog *v8; // rdi
  IUserToken *v10; // r9
  int v11; // ebx
  IUserTokenInternal *v12; // rcx
  _GUID v13; // xmm0
  unsigned int v14; // r14d
  int v15; // esi
  HRESULT v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // edx
  HRESULT v19; // r9d
  IUserTokenInternal *m_ptr; // rcx
  HRESULT v21; // eax
  IUserTokenInternal *v22; // rcx
  __int64 v24; // r9
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  LSTATUS ValueW; // eax
  LSTATUS v29; // ebx
  HRESULT v30; // eax
  int v31; // eax
  CComClassInfo *v32; // rbx
  bool v33; // al
  CComClassInfo *v34; // rax
  CComRegCatalog_vtbl *v35; // rcx
  IGetProcessInfoInternal *v36; // rcx
  __int64 (__fastcall **v37)(_QWORD, GUID *, wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> *); // rax
  __int64 (__fastcall *v38)(_QWORD, GUID *, wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> *); // rbx
  HRESULT v39; // eax
  bool v40; // al
  CComRegCatalog_vtbl *v41; // rcx
  unsigned __int16 v42; // ax
  CComRegCatalog_vtbl *v43; // rcx
  bool v44; // al
  CComRegCatalog_vtbl *v45; // rcx
  unsigned __int16 v46; // ax
  CComRegCatalog_vtbl *v47; // rcx
  bool v48; // al
  CComRegCatalog_vtbl *v49; // rcx
  bool v50; // al
  CComRegCatalog_vtbl *v51; // rcx
  bool v52; // al
  CComRegCatalog_vtbl *v53; // rcx
  bool supportsDarwinId; // r13
  bool supports16BitRegistrations; // r15
  IGetProcessInfoInternal *v56; // r12
  unsigned int v57; // esi
  int fMachineHive; // r14d
  unsigned int dwCatFlagsForAppID; // ebx
  HKEY__ *m_hkeyClassesRoot; // rdi
  unsigned int v61; // eax
  CComClassInfo *v62; // rsi
  HRESULT v63; // eax
  void **v64; // r14
  HRESULT Interface; // eax
  IUserTokenInternal *v66; // rcx
  IUserTokenInternal *v67; // rcx
  HRESULT v68; // eax
  int v69; // eax
  __int64 v70; // rcx
  unsigned __int64 v71; // rdx
  unsigned __int8 v72; // cl
  wil::details::static_lazy<ComTrace> *v73; // rcx
  ComTrace *v74; // rcx
  CComRegCatalog *v75; // rcx
  CComRegCatalog_vtbl *v76; // rax
  IUserTokenInternal *v77; // rcx
  IUserToken *v78; // r9
  IUserToken_vtbl *v79; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  int v81; // eax
  IGetProcessInfoInternal *v82; // rbx
  __int64 v83; // rcx
  unsigned int v84; // edx
  unsigned int v85; // edx
  const wchar_t *v86; // rax
  GuidString *p_currentClsidString; // rax
  unsigned int v88; // edx
  HRESULT v89; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-100h]
  unsigned int regViewRegistration; // [rsp+48h] [rbp-E8h]
  bool releaseComRootKeyForUserToken; // [rsp+B0h] [rbp-80h] BYREF
  int impersonating; // [rsp+B4h] [rbp-7Ch] BYREF
  wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> userTokenInternal; // [rsp+B8h] [rbp-78h] BYREF
  IUserToken *v95; // [rsp+C0h] [rbp-70h] BYREF
  bool usingProviderHKLM; // [rsp+C8h] [rbp-68h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > clsidKey; // [rsp+D0h] [rbp-60h] BYREF
  bool readProgId; // [rsp+D8h] [rbp-58h]
  bool isPackaged; // [rsp+D9h] [rbp-57h]
  bool selectDllHostArchitectureBasedOnDllArchitecture; // [rsp+DAh] [rbp-56h]
  bool supportsGetProgId; // [rsp+DBh] [rbp-55h]
  bool supportsLUAAndDisplaySettings; // [rsp+DCh] [rbp-54h]
  wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> getProcessInfoCallback; // [rsp+E0h] [rbp-50h] BYREF
  int clsidKeyIsInHKLM; // [rsp+E8h] [rbp-48h] BYREF
  int v105; // [rsp+ECh] [rbp-44h]
  unsigned __int16 cbSid[2]; // [rsp+F0h] [rbp-40h] BYREF
  unsigned __int16 v107; // [rsp+F4h] [rbp-3Ch]
  unsigned __int16 defaultArchitectureForView; // [rsp+F6h] [rbp-3Ah]
  int v109; // [rsp+F8h] [rbp-38h]
  HKEY__ *rootKey; // [rsp+100h] [rbp-30h] BYREF
  unsigned int treatAsValueSize; // [rsp+108h] [rbp-28h] BYREF
  int forceToHKLM; // [rsp+10Ch] [rbp-24h] BYREF
  unsigned int catalogFlags; // [rsp+110h] [rbp-20h]
  wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy> comClassInfo; // [rsp+118h] [rbp-18h] BYREF
  CComRegCatalog *v115; // [rsp+120h] [rbp-10h]
  unsigned __int8 *pSid; // [rsp+128h] [rbp-8h] BYREF
  __int64 (__fastcall ***v117)(_QWORD, GUID *, wil::com_ptr_t<IGetProcessInfoInternal,wil::err_returncode_policy> *); // [rsp+130h] [rbp+0h]
  void **ppvObj; // [rsp+138h] [rbp+8h]
  _GUID *guid; // [rsp+140h] [rbp+10h]
  CComRegCatalog::GetClassInfoW::__l2::<lambda_6f6522c49679d9fbe761af3c1bc61942> setRootKeyToProviderHKLM; // [rsp+148h] [rbp+18h] BYREF
  _GUID currentClsid; // [rsp+170h] [rbp+40h] BYREF
  GuidString currentClsidString; // [rsp+180h] [rbp+50h] BYREF
  GuidString v123; // [rsp+1D0h] [rbp+A0h] BYREF
  wchar_t currentClsidKeyPath[48]; // [rsp+220h] [rbp+F0h] BYREF
  wchar_t treatAsValue[104]; // [rsp+280h] [rbp+150h] BYREF
  void *retaddr; // [rsp+3A8h] [rbp+278h]

  v7 = pComCatalog;
  v115 = this;
  v8 = this;
  guid = guidConfiguredClsid;
  v10 = pUserToken;
  catalogFlags = dwFlags;
  v95 = pUserToken;
  *ppv = 0;
  ppvObj = ppv;
  v117 = pComCatalog;
  if ( (dwFlags & 0xCE8) != 0 )
  {
    v17 = -2147024809;
    v84 = 178;
LABEL_133:
    wil::details::in1diag3::Return_Hr(retaddr, v84, "onecore\\com\\combase\\catalog\\regcat.cxx", v17);
    return v17;
  }
  v11 = dwFlags & 0x10000;
  if ( (dwFlags & 0x10000) == 0 )
    goto LABEL_3;
  if ( !((unsigned __int8 (__fastcall *)(CComRegCatalog *, __int64, IUserToken *, IUserToken *))this->SupportsForceHKLM)(
          this,
          dwFlags,
          pUserToken,
          pUserToken) )
  {
    v17 = -2147221164;
    v84 = 179;
    goto LABEL_133;
  }
  v10 = v95;
LABEL_3:
  impersonating = 0;
  setRootKeyToProviderHKLM.rootKey = &rootKey;
  setRootKeyToProviderHKLM.usingProviderHKLM = &usingProviderHKLM;
  setRootKeyToProviderHKLM.releaseComRootKeyForUserToken = &releaseComRootKeyForUserToken;
  setRootKeyToProviderHKLM.pUserToken = &v95;
  v12 = 0;
  userTokenInternal.m_ptr = 0;
  releaseComRootKeyForUserToken = 0;
  usingProviderHKLM = 0;
  rootKey = 0;
  setRootKeyToProviderHKLM.__this = v8;
  if ( !v10 )
  {
    rootKey = v8->m_hkeyClassesRoot;
    goto LABEL_5;
  }
  if ( v11 )
  {
    lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(&setRootKeyToProviderHKLM);
  }
  else
  {
    v69 = v8->GetComRootKeyForUserToken(v8, v10, &rootKey);
    v17 = v69;
    if ( v69 >= 0 )
    {
      releaseComRootKeyForUserToken = 1;
    }
    else
    {
      if ( v69 != -2147024894 )
      {
        v19 = v69;
        v18 = 263;
        goto LABEL_10;
      }
      if ( !v8->SupportsForceHKLM(v8) )
      {
        if ( ComTrace::IsEnabled(v72, v71) )
        {
          wil::details::static_lazy<ComTrace>::get(
            v73,
            _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
          ComTrace::LogVerbose_(v74, L"No private hive for package");
        }
        goto LABEL_65;
      }
      lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(&setRootKeyToProviderHKLM);
    }
    if ( !rootKey )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v70);
      v18 = 266;
      v17 = -2147418113;
LABEL_9:
      v19 = v17;
      goto LABEL_10;
    }
  }
  pSid = 0;
  cbSid[0] = 0;
  v89 = v95->GetUserSid(v95, &pSid, cbSid);
  v17 = v89;
  if ( v89 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x116u, "onecore\\com\\combase\\catalog\\regcat.cxx", v89);
    m_ptr = userTokenInternal.m_ptr;
    if ( !userTokenInternal.m_ptr )
    {
LABEL_13:
      if ( releaseComRootKeyForUserToken )
      {
        v76 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
        v75 = v8;
LABEL_144:
        v76->ReleaseComRootKeyForUserToken(v75, v95);
      }
      goto LABEL_14;
    }
LABEL_12:
    userTokenInternal.m_ptr->Revert(m_ptr, impersonating);
    goto LABEL_13;
  }
  if ( !EqualSid(pSid, gSidAnonymous) )
  {
    v77 = userTokenInternal.m_ptr;
    v78 = v95;
    v79 = v95->__vftable;
    userTokenInternal.m_ptr = 0;
    QueryInterface = v79->QueryInterface;
    if ( v77 )
    {
      v77->Release(v77);
      v78 = v95;
    }
    v81 = QueryInterface(v78, &GUID_000001fc_0000_0000_cfff_123045660046, (void **)&userTokenInternal.m_ptr);
    v17 = v81;
    if ( v81 < 0 )
    {
      v19 = v81;
      v18 = 281;
LABEL_10:
      wil::details::in1diag3::Return_Hr(retaddr, v18, "onecore\\com\\combase\\catalog\\regcat.cxx", v19);
      goto LABEL_11;
    }
  }
  v12 = userTokenInternal.m_ptr;
LABEL_5:
  if ( v12 )
  {
    v21 = v12->Impersonate(v12, 1, &impersonating);
    v17 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x128u, "onecore\\com\\combase\\catalog\\regcat.cxx", v21);
LABEL_17:
      v22 = userTokenInternal.m_ptr;
      if ( userTokenInternal.m_ptr )
      {
        userTokenInternal.m_ptr->Revert(userTokenInternal.m_ptr, impersonating);
        v22 = userTokenInternal.m_ptr;
      }
      if ( releaseComRootKeyForUserToken )
      {
        v8->ReleaseComRootKeyForUserToken(v8, v95);
        v22 = userTokenInternal.m_ptr;
      }
      if ( v22 )
        v22->Release(v22);
      return v17;
    }
  }
  v13 = *guidConfiguredClsid;
  v14 = 0;
  v109 = 0;
  v15 = 0;
  v105 = 0;
  currentClsid = v13;
  while ( 1 )
  {
    while ( 1 )
    {
      GuidString::GuidString(&currentClsidString, &currentClsid);
      memset_0(currentClsidKeyPath, 0, 0x5Au);
      GuidString::GuidString(&v123, &currentClsid);
      v16 = StringCchPrintfW(currentClsidKeyPath, 0x2Du, L"CLSID\\%ls", &v123);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x563u, "onecore\\com\\combase\\catalog\\services.cxx", v16);
        v18 = 315;
        goto LABEL_9;
      }
      clsidKey.m_ptr = 0;
      if ( v14 )
      {
        v25 = v8->OpenKeyInOtherView(v8, rootKey, currentClsidKeyPath, 131097u, &clsidKey.m_ptr);
        v24 = v25;
        if ( v25 != 2 )
          goto LABEL_29;
        if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        {
          LODWORD(pcbData) = -2147221164;
          ComTraceMessage(
            -2147221164,
            "onecore\\com\\combase\\catalog\\regcat.cxx",
            "CComRegCatalog::GetClassInfoW",
            382,
            (TraceLevel)v26,
            L"HRESULT:%#x, CLSID:%ls",
            pcbData,
            &currentClsidString);
        }
        if ( clsidKey.m_ptr )
          RegCloseKey(clsidKey.m_ptr);
LABEL_65:
        v67 = userTokenInternal.m_ptr;
        if ( userTokenInternal.m_ptr )
        {
          ((void (__fastcall *)(IUserTokenInternal *, _QWORD, __int64, __int64))userTokenInternal.m_ptr->Revert)(
            userTokenInternal.m_ptr,
            (unsigned int)impersonating,
            v27,
            v24);
          v67 = userTokenInternal.m_ptr;
        }
        if ( releaseComRootKeyForUserToken )
        {
          ((void (__fastcall *)(CComRegCatalog *, IUserToken *, __int64, __int64))v8->ReleaseComRootKeyForUserToken)(
            v8,
            v95,
            v27,
            v24);
          v67 = userTokenInternal.m_ptr;
        }
        if ( v67 )
          ((void (__fastcall *)(IUserTokenInternal *, __int64, __int64, __int64))v67->Release)(v67, v26, v27, v24);
        return 2147746132LL;
      }
      LODWORD(v24) = CComRegCatalog::OpenKeyInViewHelper(
                       rootKey,
                       currentClsidKeyPath,
                       0x20019u,
                       v8->m_regView,
                       v8->m_regWowArchitecture,
                       &clsidKey.m_ptr);
      if ( (_DWORD)v24 == 2 )
      {
        v14 = 1;
        v109 = 1;
        if ( clsidKey.m_ptr )
          RegCloseKey(clsidKey.m_ptr);
        goto LABEL_73;
      }
LABEL_29:
      if ( (_DWORD)v24 )
      {
        p_currentClsidString = &currentClsidString;
        v88 = 387;
        goto LABEL_130;
      }
      memset_0(treatAsValue, 0, 0xC8u);
      treatAsValueSize = 200;
      ValueW = RegGetValueW(
                 clsidKey.m_ptr,
                 Com::Catalog::Constants::TreatAs,
                 0,
                 0xFFFFu,
                 0,
                 treatAsValue,
                 &treatAsValueSize);
      v29 = ValueW;
      if ( ValueW )
        break;
      if ( (treatAsValueSize & 0xFFFFFFFE) < 0x4A )
      {
        v85 = 396;
LABEL_141:
        v17 = -2147221165;
LABEL_124:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          v85,
          "onecore\\com\\combase\\catalog\\regcat.cxx",
          v17,
          "CLSID:%ls",
          currentClsidString.m_string);
LABEL_84:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&clsidKey);
        goto LABEL_11;
      }
      if ( !CurlyStringToGUID(treatAsValue, &currentClsid) )
      {
        v85 = 397;
        goto LABEL_141;
      }
      v105 = ++v15;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&clsidKey);
LABEL_73:
      if ( v15 > 50 )
      {
        v64 = ppvObj;
LABEL_54:
        if ( *v64 )
        {
          v66 = userTokenInternal.m_ptr;
          if ( userTokenInternal.m_ptr )
          {
            userTokenInternal.m_ptr->Revert(userTokenInternal.m_ptr, impersonating);
            v66 = userTokenInternal.m_ptr;
          }
          if ( releaseComRootKeyForUserToken )
          {
            v8->ReleaseComRootKeyForUserToken(v8, v95);
            v66 = userTokenInternal.m_ptr;
          }
          if ( v66 )
            v66->Release(v66);
          return 0;
        }
        GuidString::GuidString(&v123, guid);
        v17 = -2147221165;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x202u,
          "onecore\\com\\combase\\catalog\\regcat.cxx",
          -2147221165,
          "Excessive or cyclic chain of TreatAs values starting from CLSID %ls",
          v86);
LABEL_11:
        m_ptr = userTokenInternal.m_ptr;
        if ( !userTokenInternal.m_ptr )
          goto LABEL_13;
        goto LABEL_12;
      }
    }
    if ( ValueW != 2 )
    {
      GuidString::GuidString(&v123, &currentClsid);
      LODWORD(v24) = v29;
      v88 = 405;
LABEL_130:
      v17 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              v88,
              "onecore\\com\\combase\\catalog\\regcat.cxx",
              v24,
              "CLSID:%ls",
              p_currentClsidString->m_string);
      goto LABEL_84;
    }
    clsidKeyIsInHKLM = 0;
    if ( usingProviderHKLM )
    {
      v31 = 1;
      clsidKeyIsInHKLM = 1;
    }
    else
    {
      v30 = v8->IsFromMachineHive(v8, clsidKey.m_ptr, &clsidKeyIsInHKLM);
      v17 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x1A8u, "onecore\\com\\combase\\catalog\\regcat.cxx", v30);
        goto LABEL_84;
      }
      v31 = clsidKeyIsInHKLM;
    }
    if ( !g_bInSCM || v31 )
      break;
    forceToHKLM = 0;
    v68 = CComRegCatalog::CheckForceHKLMForCLSID(v8, rootKey, clsidKey.m_ptr, &forceToHKLM);
    v17 = v68;
    if ( v68 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x1AEu, "onecore\\com\\combase\\catalog\\regcat.cxx", v68);
      goto LABEL_48;
    }
    if ( !forceToHKLM )
      break;
    if ( !v8->SupportsForceHKLM(v8) )
    {
      v17 = -2147221161;
      v85 = 442;
      goto LABEL_124;
    }
    lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(&setRootKeyToProviderHKLM);
    v15 = 0;
    v105 = 0;
    if ( clsidKey.m_ptr )
      RegCloseKey(clsidKey.m_ptr);
  }
  v32 = (CComClassInfo *)HeapAlloc(g_hHeap, 0, 0x198u);
  if ( !v32 )
  {
    comClassInfo.m_ptr = 0;
LABEL_82:
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, 0x1C1u, "onecore\\com\\combase\\catalog\\regcat.cxx", -2147024882);
LABEL_83:
    wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&comClassInfo);
    goto LABEL_84;
  }
  v33 = v8->DisableGetClassContextLie(v8);
  CComClassInfo::CComClassInfo(v32, (RegistrationSource)v8->m_source, v33);
  comClassInfo.m_ptr = v34;
  if ( !v34 )
    goto LABEL_82;
  _InterlockedAdd(&v34->m_cRef, 1u);
  v35 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  getProcessInfoCallback.m_ptr = 0;
  if ( v35->SupportsComCatalogCallback(v8) )
  {
    v36 = getProcessInfoCallback.m_ptr;
    v37 = *v7;
    getProcessInfoCallback.m_ptr = 0;
    v38 = *v37;
    if ( v36 )
      v36->Release(v36);
    v39 = v38(v7, &GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f, &getProcessInfoCallback);
    v17 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x1C6u, "onecore\\com\\combase\\catalog\\regcat.cxx", v39);
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&getProcessInfoCallback);
      goto LABEL_83;
    }
  }
  else
  {
    v82 = getProcessInfoCallback.m_ptr;
    getProcessInfoCallback.m_ptr = (IGetProcessInfoInternal *)((unsigned __int64)&v8->IGetProcessInfoInternal
                                                             & -(__int64)(v8 != 0));
    if ( getProcessInfoCallback.m_ptr )
    {
      v83 = (unsigned __int64)&v8->IGetProcessInfoInternal & -(__int64)(v8 != 0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 8LL))(v83);
    }
    if ( v82 )
      v82->Release(v82);
  }
  v40 = v8->ReadProgIdFromCatalogKey(v8);
  v41 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  readProgId = v40;
  v42 = v41->GetWowArchitectureFor(v8, (CComRegCatalog::WhichView)v14);
  v43 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  v107 = v42;
  v44 = v43->RegistrationsArePackaged(v8);
  v45 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  isPackaged = v44;
  v46 = v45->ExpectedOutofprocServerBinaryArchitecture(v8);
  v47 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  defaultArchitectureForView = v46;
  v48 = v47->SelectDllHostArchitectureBasedOnDllArchitecture(v8);
  v49 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  selectDllHostArchitectureBasedOnDllArchitecture = v48;
  v50 = v49->SupportsGetProgId(v8);
  v51 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  supportsGetProgId = v50;
  v52 = v51->SupportsLUAAndDisplaySettings(v8);
  v53 = v8->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
  supportsLUAAndDisplaySettings = v52;
  supportsDarwinId = v53->SupportsDarwinId(v8);
  supports16BitRegistrations = v8->Supports16BitRegistrations(v8);
  v56 = getProcessInfoCallback.m_ptr;
  v57 = v8->GetViewFlagFor(v8, (CComRegCatalog::WhichView)v14);
  fMachineHive = clsidKeyIsInHKLM;
  dwCatFlagsForAppID = v8->CatalogFlagsForAppID(v8);
  m_hkeyClassesRoot = v8->m_hkeyClassesRoot;
  v61 = v115->GetViewFlagFor(v115, This);
  regViewRegistration = v57;
  v62 = comClassInfo.m_ptr;
  v63 = CComClassInfo::FinalConstruct(
          comClassInfo.m_ptr,
          v95,
          &currentClsid,
          currentClsidKeyPath,
          clsidKey.m_ptr,
          v61,
          m_hkeyClassesRoot,
          dwCatFlagsForAppID,
          fMachineHive,
          regViewRegistration,
          v56,
          (catalogFlags & 0x8000) != 0,
          supports16BitRegistrations,
          supportsDarwinId,
          supportsLUAAndDisplaySettings,
          supportsGetProgId,
          selectDllHostArchitectureBasedOnDllArchitecture,
          defaultArchitectureForView,
          isPackaged,
          v107,
          readProgId);
  v17 = v63;
  if ( v63 >= 0 )
  {
    v8 = v115;
    if ( v115->ShouldLookInOtherViewForRegistrationNotMatchingClsctx(v115)
      && !v109
      && !ClassRegistrationMatchesRequestedClsctx(v62, catalogFlags, 0) )
    {
      v109 = 1;
      v14 = 1;
      if ( getProcessInfoCallback.m_ptr )
        getProcessInfoCallback.m_ptr->Release(getProcessInfoCallback.m_ptr);
      CComClassInfo::Release(v62);
      if ( clsidKey.m_ptr )
        RegCloseKey(clsidKey.m_ptr);
      v7 = v117;
      v15 = v105;
      goto LABEL_73;
    }
    v64 = ppvObj;
    Interface = CComClassInfo::QueryInterface(v62, riid, ppvObj);
    v17 = Interface;
    if ( Interface >= 0 )
    {
      if ( getProcessInfoCallback.m_ptr )
        getProcessInfoCallback.m_ptr->Release(getProcessInfoCallback.m_ptr);
      CComClassInfo::Release(v62);
      if ( clsidKey.m_ptr )
        RegCloseKey(clsidKey.m_ptr);
      goto LABEL_54;
    }
    wil::details::in1diag3::Return_Hr(retaddr, 0x1F9u, "onecore\\com\\combase\\catalog\\regcat.cxx", Interface);
    if ( getProcessInfoCallback.m_ptr )
      getProcessInfoCallback.m_ptr->Release(getProcessInfoCallback.m_ptr);
    CComClassInfo::Release(v62);
LABEL_48:
    if ( clsidKey.m_ptr )
      RegCloseKey(clsidKey.m_ptr);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x1E1u, "onecore\\com\\combase\\catalog\\regcat.cxx", v63);
  wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&getProcessInfoCallback);
  wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&comClassInfo);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&clsidKey);
  if ( userTokenInternal.m_ptr )
    userTokenInternal.m_ptr->Revert(userTokenInternal.m_ptr, impersonating);
  if ( releaseComRootKeyForUserToken )
  {
    v75 = v115;
    v76 = v115->IComCatalogInternalImpl::IComCatalogInternal::IUnknown::__vftable;
    goto LABEL_144;
  }
LABEL_14:
  wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&userTokenInternal);
  return v17;
}

```

## disassembly

```asm
0x180062930  push    rbp
0x180062932  push    rbx
0x180062933  push    rsi
0x180062934  push    rdi
0x180062935  push    r12
0x180062937  push    r13
0x180062939  push    r14
0x18006293b  push    r15
0x18006293d  lea     rbp, [rsp-238h]
0x180062945  sub     rsp, 368h
0x18006294c  mov     rax, cs:__security_cookie
0x180062953  xor     rax, rsp
0x180062956  mov     [rbp+270h+var_50], rax
0x18006295d  mov     r15, [rbp+270h+arg_30]
0x180062964  xor     r12d, r12d
0x180062967  mov     [rbp+270h+var_280], this
0x18006296b  mov     rdi, this
0x18006296e  mov     this, [rbp+270h+arg_28]
0x180062975  mov     rsi, guidConfiguredClsid
0x180062978  mov     [rbp+270h+guid], guidConfiguredClsid
0x18006297c  mov     guidConfiguredClsid, pUserToken
0x18006297f  mov     [rbp+270h+catalogFlags], dwFlags
0x180062982  mov     [rbp+270h+var_2E0], pUserToken
0x180062986  mov     [this], r12
0x180062989  mov     [rbp+270h+ppvObj], this
0x18006298d  mov     [rbp+270h+var_270], r15
0x180062991  test    dwFlags, 0CE8h
0x180062997  jnz     loc_18006330F
0x18006299d  mov     ebx, dwFlags
0x18006299f  and     ebx, 10000h
0x1800629a5  jnz     loc_18006331E
0x1800629ab  mov     [rbp+270h+impersonating], r12d
0x1800629af  lea     rax, [rbp+270h+rootKey]
0x1800629b3  mov     [rbp+270h+setRootKeyToProviderHKLM.rootKey], rax
0x1800629b7  lea     rax, [rbp+270h+usingProviderHKLM]
0x1800629bb  mov     [rbp+270h+setRootKeyToProviderHKLM.usingProviderHKLM], rax
0x1800629bf  lea     rax, [rbp+270h+releaseComRootKeyForUserToken]
0x1800629c3  mov     [rbp+270h+setRootKeyToProviderHKLM.releaseComRootKeyForUserToken], rax
0x1800629c7  lea     rax, [rbp+270h+var_2E0]
0x1800629cb  mov     [rbp+270h+setRootKeyToProviderHKLM.pUserToken], rax
0x1800629cf  mov     this, r12
0x1800629d2  mov     [rbp+270h+userTokenInternal.m_ptr], this
0x1800629d6  mov     r13d, 1
0x1800629dc  mov     [rbp+270h+releaseComRootKeyForUserToken], r12b
0x1800629e0  mov     [rbp+270h+usingProviderHKLM], r12b
0x1800629e4  mov     [rbp+270h+rootKey], r12
0x1800629e8  mov     [rbp+270h+setRootKeyToProviderHKLM.__this], rdi
0x1800629ec  test    guidConfiguredClsid, guidConfiguredClsid
0x1800629ef  jnz     loc_18006315C
0x1800629f5  mov     rax, [rdi+18h]
0x1800629f9  mov     [rbp+270h+rootKey], rax
0x1800629fd  test    this, this
0x180062a00  jnz     loc_180062ACC
0x180062a06  movups  xmm0, xmmword ptr [rsi]
0x180062a09  mov     r14d, r12d
0x180062a0c  mov     [rbp+270h+var_2A8], r12d
0x180062a10  mov     esi, r12d
0x180062a13  mov     [rbp+270h+var_2B4], r12d
0x180062a17  movdqu  xmmword ptr [rbp+270h+currentClsid.Data1], xmm0
0x180062a1c  lea     rdx, [rbp+270h+currentClsid]; guid
0x180062a20  lea     this, [rbp+270h+currentClsidString]; this
0x180062a24  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180062a29  xor     dwFlags, dwFlags; Val
0x180062a2b  lea     this, [rbp+270h+currentClsidKeyPath]; void *
0x180062a32  lea     r8d, [rdx+5Ah]; Size
0x180062a36  call    memset_0
0x180062a3b  lea     rdx, [rbp+270h+currentClsid]; guid
0x180062a3f  lea     this, [rbp+270h+var_1D0]; this
0x180062a46  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180062a4b  lea     guidConfiguredClsid, [rbp+270h+var_1D0]
0x180062a52  mov     dwFlags, 2Dh ; '-'; cchDest
0x180062a57  lea     pUserToken, aClsidLs; "CLSID\\%ls"
0x180062a5e  lea     this, [rbp+270h+currentClsidKeyPath]; pszDest
0x180062a65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180062a6a  mov     ebx, eax
0x180062a6c  test    eax, eax
0x180062a6e  jns     loc_180062B51
0x180062a74  mov     this, [rbp+278h]; callerReturnAddress
0x180062a7b  lea     pUserToken, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x180062a82  mov     r9d, eax; hr
0x180062a85  mov     dwFlags, 563h; lineNumber
0x180062a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062a8f  mov     dwFlags, 13Bh; lineNumber
0x180062a94  mov     r9d, ebx; hr
0x180062a97  mov     this, [rbp+278h]; callerReturnAddress
0x180062a9e  lea     pUserToken, aOnecoreComComb_68; "onecore\\com\\combase\\catalog\\regcat."...
0x180062aa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062aaa  mov     this, [rbp+270h+userTokenInternal.m_ptr]
0x180062aae  test    this, this
0x180062ab1  jnz     loc_1800635AD
0x180062ab7  cmp     [rbp+270h+releaseComRootKeyForUserToken], r12b
0x180062abb  jnz     loc_1800635B9
0x180062ac1  lea     this, [rbp+270h+userTokenInternal]; this
0x180062ac5  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x180062aca  jmp     short loc_180062B2C
0x180062acc  mov     rax, [this]
0x180062acf  lea     pUserToken, [rbp+270h+impersonating]
0x180062ad3  mov     dwFlags, r13d
0x180062ad6  mov     rax, [rax+60h]
0x180062ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062adf  mov     ebx, eax
0x180062ae1  test    eax, eax
0x180062ae3  jns     loc_180062A06
0x180062ae9  mov     this, [rbp+278h]; callerReturnAddress
0x180062af0  lea     pUserToken, aOnecoreComComb_68; "onecore\\com\\combase\\catalog\\regcat."...
0x180062af7  mov     r9d, eax; hr
0x180062afa  mov     dwFlags, 128h; lineNumber
0x180062aff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062b04  mov     this, [rbp+270h+userTokenInternal.m_ptr]
0x180062b08  test    this, this
0x180062b0b  jnz     loc_180063375
0x180062b11  cmp     [rbp+270h+releaseComRootKeyForUserToken], r12b
0x180062b15  jnz     loc_18006338D
0x180062b1b  test    this, this
0x180062b1e  jz      short loc_180062B2C
0x180062b20  mov     rax, [this]
0x180062b23  mov     rax, [rax+10h]
0x180062b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b2c  mov     eax, ebx
0x180062b2e  mov     this, [rbp+270h+var_50]
0x180062b35  xor     this, rsp; StackCookie
0x180062b38  call    __security_check_cookie
0x180062b3d  add     rsp, 368h
0x180062b44  pop     r15
0x180062b46  pop     r14
0x180062b48  pop     r13
0x180062b4a  pop     r12
0x180062b4c  pop     rdi
0x180062b4d  pop     rsi
0x180062b4e  pop     rbx
0x180062b4f  pop     rbp
0x180062b50  retn
0x180062b51  mov     [rbp+270h+clsidKey.m_ptr], r12
0x180062b55  test    r14d, r14d
0x180062b58  jnz     short loc_180062BAD
0x180062b5a  mov     r9d, [rdi+10h]; regView
0x180062b5e  lea     rax, [rbp+270h+clsidKey]
0x180062b62  mov     this, [rbp+270h+rootKey]; hKeyRoot
0x180062b66  lea     rdx, [rbp+270h+currentClsidKeyPath]; pszSubKeyPath
0x180062b6d  mov     [rsp+3A0h+phKey], rax; phKey
0x180062b72  mov     r8d, 20019h; samDesired
0x180062b78  movzx   eax, word ptr [rdi+14h]
0x180062b7c  mov     [rsp+3A0h+regWowArchitecture], ax; regWowArchitecture
0x180062b81  call    ?OpenKeyInViewHelper@CComRegCatalog@@KAJPEAUHKEY__@@PEBGKKGPEAPEAU2@@Z; CComRegCatalog::OpenKeyInViewHelper(HKEY__ *,ushort const *,ulong,ulong,ushort,HKEY__ * *)
0x180062b86  mov     r9d, eax
0x180062b89  cmp     eax, 2
0x180062b8c  jnz     short loc_180062BE5
0x180062b8e  mov     this, [rbp+270h+clsidKey.m_ptr]; hKey
0x180062b92  mov     r14d, r13d
0x180062b95  mov     [rbp+270h+var_2A8], r13d
0x180062b99  test    this, this
0x180062b9c  jz      loc_18006303E
0x180062ba2  call    cs:__imp_RegCloseKey
0x180062ba8  jmp     loc_18006303E
0x180062bad  mov     rax, [rdi]
0x180062bb0  lea     this, [rbp+270h+clsidKey]
0x180062bb4  mov     rdx, [rbp+270h+rootKey]
0x180062bb8  lea     pUserToken, [rbp+270h+currentClsidKeyPath]
0x180062bbf  mov     qword ptr [rsp+3A0h+regWowArchitecture], this
0x180062bc4  mov     r9d, 20019h
0x180062bca  mov     this, rdi
0x180062bcd  mov     rax, [rax+98h]
0x180062bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062bd9  mov     r9d, eax; err
0x180062bdc  cmp     eax, 2
0x180062bdf  jz      loc_180062FDC
0x180062be5  test    r9d, r9d
0x180062be8  jnz     loc_180063542
0x180062bee  mov     ebx, 0C8h
0x180062bf3  lea     this, [rbp+270h+treatAsValue]; void *
0x180062bfa  mov     r8d, ebx; Size
0x180062bfd  xor     dwFlags, dwFlags; Val
0x180062bff  call    memset_0
0x180062c04  mov     this, [rbp+270h+clsidKey.m_ptr]; hkey
0x180062c08  lea     rax, [rbp+270h+treatAsValueSize]
0x180062c0c  mov     [rsp+3A0h+pcbData], rax; pcbData
0x180062c11  lea     rdx, ?TreatAs@Constants@Catalog@Com@@3QBGB; lpSubKey
0x180062c18  lea     rax, [rbp+270h+treatAsValue]
0x180062c1f  mov     [rbp+270h+treatAsValueSize], ebx
0x180062c22  mov     [rsp+3A0h+phKey], rax; pvData
0x180062c27  mov     r9d, 0FFFFh; dwFlags
0x180062c2d  xor     r8d, r8d; lpValue
0x180062c30  mov     qword ptr [rsp+3A0h+regWowArchitecture], r12; pdwType
0x180062c35  call    cs:__imp_RegGetValueW
0x180062c3b  mov     ebx, eax
0x180062c3d  test    eax, eax
0x180062c3f  jz      loc_1800633AC
0x180062c45  cmp     eax, 2
0x180062c48  jnz     loc_180063528
0x180062c4e  mov     [rbp+270h+clsidKeyIsInHKLM], r12d
0x180062c52  cmp     [rbp+270h+usingProviderHKLM], r12b
0x180062c56  jnz     loc_1800633E7
0x180062c5c  mov     rax, [rdi]
0x180062c5f  lea     pUserToken, [rbp+270h+clsidKeyIsInHKLM]
0x180062c63  mov     rdx, [rbp+270h+clsidKey.m_ptr]
0x180062c67  mov     this, rdi
0x180062c6a  mov     rax, [rax+0A0h]
0x180062c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c76  mov     ebx, eax
0x180062c78  test    eax, eax
0x180062c7a  js      loc_180063508
0x180062c80  mov     eax, [rbp+270h+clsidKeyIsInHKLM]
0x180062c83  cmp     cs:?g_bInSCM@@3JA, r12d; long g_bInSCM
0x180062c8a  jnz     loc_1800630E6
0x180062c90  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062c97  xor     dwFlags, dwFlags; dwFlags
0x180062c99  mov     r8d, 198h; dwBytes
0x180062c9f  call    cs:__imp_HeapAlloc
0x180062ca5  mov     rbx, rax
0x180062ca8  test    rax, rax
0x180062cab  jz      loc_1800630AB
0x180062cb1  mov     this, [rdi]
0x180062cb4  mov     rax, [this+168h]
0x180062cbb  mov     this, rdi
0x180062cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cc3  mov     dwFlags, [rdi+20h]; source
0x180062cc6  mov     r8b, al; disableGetClassContextLie
0x180062cc9  mov     this, rbx; this
0x180062ccc  call    ??0CComClassInfo@@QEAA@W4RegistrationSource@@_N@Z; CComClassInfo::CComClassInfo(RegistrationSource,bool)
0x180062cd1  mov     [rbp+270h+comClassInfo.m_ptr], rax
0x180062cd5  test    rax, rax
0x180062cd8  jz      loc_1800630AF
0x180062cde  lock add [rax+38h], r13d
0x180062ce3  mov     this, [rdi]
0x180062ce6  mov     [rbp+270h+getProcessInfoCallback.m_ptr], r12
0x180062cea  mov     rax, [this+158h]
0x180062cf1  mov     this, rdi
0x180062cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cf9  test    al, al
0x180062cfb  jz      loc_1800632D4
0x180062d01  mov     this, [rbp+270h+getProcessInfoCallback.m_ptr]
0x180062d05  mov     rax, [r15]
0x180062d08  mov     [rbp+270h+getProcessInfoCallback.m_ptr], r12
0x180062d0c  mov     rbx, [rax]
0x180062d0f  test    this, this
0x180062d12  jnz     loc_1800633F2
0x180062d18  lea     pUserToken, [rbp+270h+getProcessInfoCallback]
0x180062d1c  mov     this, r15
0x180062d1f  lea     rdx, _GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f
0x180062d26  mov     rax, rbx
0x180062d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d2e  mov     ebx, eax
0x180062d30  test    eax, eax
0x180062d32  js      loc_18006344E
0x180062d38  mov     rax, [rdi]
0x180062d3b  mov     this, rdi
0x180062d3e  mov     rax, [rax+150h]
0x180062d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d4a  mov     this, [rdi]
0x180062d4d  mov     dwFlags, r14d
0x180062d50  mov     [rbp+270h+var_2C8], al
0x180062d53  mov     rax, [this+90h]
0x180062d5a  mov     this, rdi
0x180062d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d62  mov     this, [rdi]
0x180062d65  mov     [rbp+270h+var_2AC], ax
0x180062d69  mov     rax, [this+138h]
0x180062d70  mov     this, rdi
0x180062d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d78  mov     this, [rdi]
0x180062d7b  mov     [rbp+270h+var_2C7], al
0x180062d7e  mov     rax, [this+148h]
0x180062d85  mov     this, rdi
0x180062d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d8d  mov     this, [rdi]
0x180062d90  mov     [rbp+270h+var_2AA], ax
0x180062d94  mov     rax, [this+130h]
0x180062d9b  mov     this, rdi
0x180062d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062da3  mov     this, [rdi]
0x180062da6  mov     [rbp+270h+var_2C6], al
0x180062da9  mov     rax, [this+120h]
0x180062db0  mov     this, rdi
0x180062db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062db8  mov     this, [rdi]
0x180062dbb  mov     [rbp+270h+var_2C5], al
0x180062dbe  mov     rax, [this+0C0h]
0x180062dc5  mov     this, rdi
0x180062dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dcd  mov     this, [rdi]
0x180062dd0  mov     [rbp+270h+var_2C4], al
0x180062dd3  mov     rax, [this+0B8h]
0x180062dda  mov     this, rdi
0x180062ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062de2  mov     this, [rdi]
0x180062de5  mov     r13b, al
0x180062de8  mov     rax, [this+0B0h]
0x180062def  mov     this, rdi
0x180062df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062df7  mov     this, [rdi]
0x180062dfa  mov     r15b, al
0x180062dfd  mov     r12, [rbp+270h+getProcessInfoCallback.m_ptr]
0x180062e01  mov     dwFlags, r14d
0x180062e04  mov     rax, [this+88h]
0x180062e0b  mov     this, rdi
0x180062e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e13  mov     this, [rdi]
0x180062e16  mov     esi, eax
0x180062e18  mov     r14d, [rbp+270h+clsidKeyIsInHKLM]
0x180062e1c  mov     rax, [this+140h]
  ... truncated ...
```
