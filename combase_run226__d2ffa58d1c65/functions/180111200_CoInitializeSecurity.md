# CoInitializeSecurity

- ea: `0x180111200`
- end: `0x180111ea3`
- name: `CoInitializeSecurity`
- size: `3235`
- prototype: `HRESULT __stdcall(PSECURITY_DESCRIPTOR pSecDesc, LONG cAuthSvc, SOLE_AUTHENTICATION_SERVICE *asAuthSvc, void *pReserved1, DWORD dwAuthnLevel, DWORD dwImpLevel, void *pAuthList, DWORD dwCapabilities, void *pReserved3)`
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801103d0`
- `0x180111150`

## callees

- `0x180006250`
- `0x180006390`
- `0x180028958`
- `0x180037d10`
- `0x18004c4d8`
- `0x18005d488`
- `0x1800844b0`
- `0x180087660`
- `0x18008a3d4`
- `0x18008a68c`
- `0x18008db2c`
- `0x1800e6dec`
- `0x180111200`
- `0x18011ff40`
- `0x180120b30`
- `0x180123c94`
- `0x18012498c`
- `0x180129f20`
- `0x18012c194`
- `0x180132268`
- `0x1801347a0`
- `0x18013d560`
- `0x180141030`
- `0x1801457c0`
- `0x18014cef0`
- `0x18014d5f4`
- `0x18014fa34`
- `0x180167c50`
- `0x1801874a4`
- `0x180187f14`
- `0x180189b6c`
- `0x1801999b0`
- `0x1801b2648`
- `0x1801dd7d0`
- `0x1802135dd`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `RPCRT4!I_RpcSetDCOMAppId` at `0x180111e4b`
- `RPCRT4!I_RpcSetDCOMAppId` at `0x180111e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801113ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801113ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111433`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801113e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801119cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111aab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111aee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801113e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801119cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111aab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111aee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111c15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111c15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180111e1f`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18011138b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18011138b`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801113bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180111429`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801113bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180111429`

## string_xrefs

- `0x18011135a`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18011147c`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111556`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1801115b5`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111608`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1801117cb`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1801118a3`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111a92`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111b7f`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111cf2`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180111d9a`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18011133e`: `CRpcResolver::GetConnection returned success, but gGotSecurityData is false`
- `0x1801117aa`: `CAuthInfo::Copy failed, hr=%!HRESULT!`
- `0x180111353`: `CoInitializeSecurity`
- `0x180111475`: `CoInitializeSecurity`
- `0x18011154f`: `CoInitializeSecurity`
- `0x1801115ae`: `CoInitializeSecurity`
- `0x180111601`: `CoInitializeSecurity`
- `0x1801117c4`: `CoInitializeSecurity`
- `0x180111a8b`: `CoInitializeSecurity`
- `0x180111b78`: `CoInitializeSecurity`
- `0x180111ceb`: `CoInitializeSecurity`
- `0x180111d93`: `CoInitializeSecurity`
- `0x180111d7e`: `GetDefaultAccessRestrictionsSD failed`
- `0x180111b5e`: `RegisterAuthnServices failed, hr=%!HRESULT!`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall CoInitializeSecurity(
        PSECURITY_DESCRIPTOR pSecDesc,
        LONG cAuthSvc,
        SOLE_AUTHENTICATION_SERVICE *asAuthSvc,
        void *pReserved1,
        DWORD dwAuthnLevel,
        DWORD dwImpLevel,
        void *pAuthList,
        DWORD dwCapabilities,
        void *pReserved3)
{
  tagSOLE_AUTHENTICATION_LIST *v9; // r15
  tagSOLE_AUTHENTICATION_SERVICE *p_sAuthSvc; // rsi
  LONG v12; // r12d
  StackTrace *ptr; // rbx
  unsigned __int16 v14; // r8
  ObjectLibrary::ReferencedPtr<StackTrace> *v15; // rax
  StackTrace *v16; // rcx
  CRpcResolver *v17; // rcx
  DWORD v19; // r13d
  int Connection; // edi
  _SECURITY_DESCRIPTOR *v21; // rax
  _SECURITY_DESCRIPTOR *v22; // rsi
  __int64 v23; // rdi
  unsigned int wAuthzSvc; // ecx
  DWORD v25; // eax
  void *v26; // rcx
  const char *v27; // r9
  HRESULT v28; // r14d
  int v29; // edx
  StackTrace *v30; // rcx
  char *v31; // rax
  int *v32; // rdx
  unsigned __int64 v33; // rcx
  char *v34; // r12
  wchar_t *v35; // rdx
  size_t v36; // rdi
  char *v37; // rcx
  char *v38; // rax
  char *v39; // rax
  unsigned int v40; // edi
  _SECURITY_DESCRIPTOR *v41; // rdi
  tagEventLogSD v42; // r8d
  unsigned __int64 m_size; // rdx
  unsigned int v44; // r8d
  __MIDL_ILocalObjectExporter_0002 *m_ptr; // r9
  __MIDL_ILocalObjectExporter_0002 v46; // xmm0
  __int64 v47; // rax
  _SECURITY_DESCRIPTOR_RELATIVE *v48; // rdi
  CRpcResolver *v49; // rcx
  unsigned int dwLenSecDescSelfRelative; // [rsp+30h] [rbp-D0h] BYREF
  _SECURITY_DESCRIPTOR *pSecDesca; // [rsp+38h] [rbp-C8h] BYREF
  int v52; // [rsp+40h] [rbp-C0h]
  wchar_t *pPrincName; // [rsp+48h] [rbp-B8h] BYREF
  ObjectLibrary::ReferencedPtr<StackTrace> result; // [rsp+50h] [rbp-B0h] BYREF
  _SECURITY_DESCRIPTOR *pNewerCopySecDesc; // [rsp+58h] [rbp-A8h] BYREF
  _SECURITY_DESCRIPTOR_RELATIVE *pSD; // [rsp+60h] [rbp-A0h]
  tagSOLE_AUTHENTICATION_LIST *pCopyAuthInfo; // [rsp+68h] [rbp-98h] BYREF
  IAccessControl *pAccessControl; // [rsp+70h] [rbp-90h] BYREF
  _GUID pCert; // [rsp+80h] [rbp-80h] BYREF
  tagSOLE_AUTHENTICATION_SERVICE sAuthSvc; // [rsp+90h] [rbp-70h] BYREF
  char v61; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t wszAppID[264]; // [rsp+C0h] [rbp-40h] BYREF

  v9 = (tagSOLE_AUTHENTICATION_LIST *)pAuthList;
  pSecDesca = (_SECURITY_DESCRIPTOR *)pSecDesc;
  *(_QWORD *)&pCert.Data1 = asAuthSvc;
  pSD = 0;
  pNewerCopySecDesc = 0;
  p_sAuthSvc = asAuthSvc;
  pAccessControl = 0;
  v12 = cAuthSvc;
  memset(&sAuthSvc, 0, sizeof(sAuthSvc));
  pCopyAuthInfo = 0;
  ptr = 0;
  pPrincName = 0;
  if ( FeatureDevelopmentProperties::Query(BreakOnRpcETooLate, *(bool **)&cAuthSvc) )
  {
    v15 = StackTrace::Capture(&result, 0, v14);
    if ( &v61 != (char *)v15 )
    {
      ptr = v15->ptr_;
      v15->ptr_ = 0;
    }
    v16 = result.ptr_;
    if ( result.ptr_ )
    {
      result.ptr_ = 0;
      ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(v16);
    }
  }
  if ( !IsApartmentInitialized() )
  {
    if ( ptr )
      ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
    return -2147221008;
  }
  v19 = dwCapabilities;
  if ( (dwCapabilities & 0x4000) != 0 )
  {
    Connection = SetExplicitWinstaDesktopString((unsigned __int64)L"WinSta0\\Default");
    if ( Connection < 0 )
      goto LABEL_12;
  }
  if ( !gGotSecurityData )
  {
    Connection = CRpcResolver::GetConnection(v17);
    if ( Connection < 0 )
    {
LABEL_12:
      if ( ptr )
        ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
      return Connection;
    }
    if ( !gGotSecurityData
      && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
    {
      ComTraceMessageT<>(
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CoInitializeSecurity",
        3154,
        ERRORS,
        L"CRpcResolver::GetConnection returned success, but gGotSecurityData is false");
    }
  }
  if ( (v19 & 0xC) == 0xC )
  {
LABEL_26:
    if ( ptr )
      ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
    return -2147024809;
  }
  v52 = 0;
  if ( !pSecDesca || (v19 & 0xC) != 0 )
    goto LABEL_44;
  if ( !IsValidSecurityDescriptor(pSecDesca) )
    goto LABEL_26;
  dwLenSecDescSelfRelative = 0;
  if ( !MakeSelfRelativeSD(pSecDesca, 0, &dwLenSecDescSelfRelative) )
  {
    Connection = GetLastError();
    if ( Connection != 122 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\dcomrem\\security.cxx",
          "CoInitializeSecurity",
          3210,
          ERRORS,
          L"%!WINERROR!",
          Connection);
      goto LABEL_41;
    }
    v21 = (_SECURITY_DESCRIPTOR *)HeapAlloc(g_hHeap, 0, dwLenSecDescSelfRelative);
    v22 = v21;
    if ( !v21 )
    {
      BreakOnCoInitializeSecurityRuntimeFailureIfRequested(-2147024882);
      if ( ptr )
        ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
      return -2147024882;
    }
    if ( !MakeSelfRelativeSD(pSecDesca, v21, &dwLenSecDescSelfRelative) )
    {
      Connection = GetLastError();
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\dcomrem\\security.cxx",
          "CoInitializeSecurity",
          3197,
          ERRORS,
          L"%!WINERROR!",
          Connection);
      HeapFree(g_hHeap, 0, v22);
LABEL_41:
      if ( Connection > 0 )
        Connection = (unsigned __int16)Connection | 0x80070000;
      goto LABEL_12;
    }
    pSecDesca = v22;
    p_sAuthSvc = *(tagSOLE_AUTHENTICATION_SERVICE **)&pCert.Data1;
    v52 = 1;
    genumAccessSD = EventLog_SERVERACCESSPERMISSIONSPROG;
LABEL_44:
    if ( !dwAuthnLevel )
      dwAuthnLevel = 2;
    lambda_b0dc4f2acc5dfa3920fff315afd6e4d9_::operator()();
    v23 = -1;
    if ( (v19 & 8) != 0 )
    {
      Connection = GetLegacyBlanket(
                     (_GUID *)pSecDesca,
                     (_SECURITY_DESCRIPTOR_RELATIVE **)&pSecDesca,
                     &dwCapabilities,
                     &dwAuthnLevel);
      if ( Connection < 0 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<long>(
            "onecore\\com\\combase\\dcomrem\\security.cxx",
            "CoInitializeSecurity",
            3261,
            ERRORS,
            L"GetLegacyBlanket failed, hr=%!HRESULT!",
            Connection);
        BreakOnCoInitializeSecurityRuntimeFailureIfRequested(Connection);
        goto LABEL_12;
      }
      v52 = 1;
      if ( gLegacySecurity.__ptr_.__value_ )
      {
        LookupPrincName((ProcessToken *)gLegacySecurity.__ptr_.__value_->wAuthnSvc, &pPrincName);
        p_sAuthSvc = &sAuthSvc;
        v12 = 1;
        sAuthSvc.dwAuthnSvc = gLegacySecurity.__ptr_.__value_->wAuthnSvc;
        wAuthzSvc = gLegacySecurity.__ptr_.__value_->wAuthzSvc;
        sAuthSvc.pPrincipalName = pPrincName;
        sAuthSvc.dwAuthzSvc = wAuthzSvc;
        if ( wAuthzSvc == 0xFFFF )
          sAuthSvc.dwAuthzSvc = 0;
        v23 = -1;
      }
      else
      {
        v23 = -1;
        v12 = -1;
      }
      pReserved1 = 0;
      v19 = gCapabilities | dwCapabilities;
      v9 = 0;
      v25 = gImpLevel;
      v26 = 0;
    }
    else
    {
      if ( !memcmp_0(&g_AppId, &GUID_NULL, 0x10u) && utGetAppIdForModule(wszAppID, 0x104u) >= 0 )
        wCLSIDFromString(wszAppID, &g_AppId);
      v25 = dwImpLevel;
      v26 = pReserved3;
    }
    dwLenSecDescSelfRelative = v25;
    if ( v25 - 1 > 3 )
      goto LABEL_93;
    if ( dwAuthnLevel > 6 )
      goto LABEL_93;
    if ( pReserved1 )
      goto LABEL_93;
    if ( v26 )
      goto LABEL_93;
    if ( (v19 & 0xFFFF8C80) != 0 )
      goto LABEL_93;
    LODWORD(result.ptr_) = v19 & 0x60;
    if ( LODWORD(result.ptr_) == 96 )
      goto LABEL_93;
    if ( dwAuthnLevel == 1 )
    {
      if ( (v19 & 2) != 0 )
        goto LABEL_93;
      if ( !v12 )
      {
LABEL_84:
        v28 = CAuthInfo::Copy(v9, &pCopyAuthInfo, v19);
        if ( v28 < 0 )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<long>(
              "onecore\\com\\combase\\dcomrem\\security.cxx",
              "CoInitializeSecurity",
              3358,
              ERRORS,
              L"CAuthInfo::Copy failed, hr=%!HRESULT!",
              v28);
          BreakOnCoInitializeSecurityRuntimeFailureIfRequested(v28);
          goto $Error_8;
        }
        if ( !p_sAuthSvc || (v29 = 0, v12 <= 0) )
        {
LABEL_105:
          if ( ComVerifierSettings::s_singleton._pSettingsState )
            CoVrfCheckClientSecurityBlanket(v12, dwAuthnLevel, 0);
          COleStaticMutexSem::Request(&gComLock, "onecore\\com\\combase\\dcomrem\\security.cxx", 0xD44u, v27);
          if ( gpsaSecurity )
          {
            v28 = RpcETooLate();
            if ( v28 < 0 )
            {
LABEL_109:
              COleStaticMutexSem::Release(&gComLock);
$Error_8:
              if ( v52 && pSecDesca )
              {
                if ( (v19 & 4) != 0 )
                  (*(void (__fastcall **)(_SECURITY_DESCRIPTOR *, __int64))(*(_QWORD *)&pSecDesca->Revision + 16LL))(
                    pSecDesca,
                    4);
                else
                  HeapFree(g_hHeap, 0, pSecDesca);
              }
              HeapFree(g_hHeap, 0, pPrincName);
              if ( v28 >= 0 )
              {
                if ( memcmp_0(&g_AppId, &GUID_NULL, 0x10u) )
                {
                  I_RpcSetDCOMAppId(&g_AppId);
                  pCert = g_AppId;
                  v28 = CRpcResolver::SetAppID(v49, &pCert);
                }
              }
              else
              {
                v48 = pSD;
                HeapFree(g_hHeap, 0, pSD);
                if ( v48 == gSecDesc )
                  gSecDesc = 0;
                HeapFree(g_hHeap, 0, pCopyAuthInfo);
              }
              if ( ptr )
                ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
              return v28;
            }
          }
          else
          {
            v30 = g_coInitializeSecurityStackTrace.ptr_;
            if ( g_coInitializeSecurityStackTrace.ptr_ != ptr )
            {
              if ( ptr )
              {
                _InterlockedIncrement((volatile signed __int32 *)&ptr->_cReferences);
                v30 = g_coInitializeSecurityStackTrace.ptr_;
              }
              g_coInitializeSecurityStackTrace.ptr_ = ptr;
              if ( v30 )
                ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(v30);
            }
          }
          if ( dwAuthnLevel == 1 )
          {
            if ( pSecDesca && (v19 & 8) == 0 )
              v28 = -2147024809;
          }
          else if ( (v19 & 4) != 0 )
          {
            if ( !pSecDesca )
            {
              v28 = -2147024809;
              goto LABEL_109;
            }
            v28 = (**(__int64 (__fastcall ***)(_SECURITY_DESCRIPTOR *, GUID *, IAccessControl **))&pSecDesca->Revision)(
                    pSecDesca,
                    &IID_IAccessControl,
                    &pAccessControl);
          }
          else
          {
            if ( !pSecDesca )
              goto LABEL_126;
            v28 = CopySecDesc(pSecDesca, &pNewerCopySecDesc);
            pSD = (_SECURITY_DESCRIPTOR_RELATIVE *)pNewerCopySecDesc;
          }
          if ( v28 < 0 )
            goto LABEL_109;
LABEL_126:
          if ( v12 == -1 )
          {
            v28 = LookupPrincName((ProcessToken *)0xA, &pPrincName);
            if ( v28 >= 0 )
            {
              do
                ++v23;
              while ( pPrincName[v23] );
              v31 = (char *)HeapAlloc(g_hHeap, 0, 2LL * (unsigned int)(v23 + 20) + 6);
              gpsaSecurity = (tagDUALSTRINGARRAY *)v31;
              v34 = v31;
              if ( v31 )
              {
                v35 = pPrincName;
                *(_DWORD *)(v31 + 2) = 2;
                *(_DWORD *)(v31 + 6) = 655360;
                *((_WORD *)v31 + 5) = -1;
                v36 = 2LL * (unsigned int)(v23 + 1);
                memcpy_0(v31 + 12, v35, v36);
                *(_WORD *)&v34[v36 + 12] = 0;
                v37 = &v34[v36 + 14];
                if ( v37 == v34 + 10 )
                {
                  *(_WORD *)v37 = 0;
                  v37 += 2;
                }
                gDefaultService = 1;
                v33 = (v37 - v34 - 4) >> 1;
                *(_WORD *)v34 = v33;
                goto LABEL_152;
              }
              goto LABEL_143;
            }
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
              ComTraceMessageT<long>(
                "onecore\\com\\combase\\dcomrem\\security.cxx",
                "CoInitializeSecurity",
                3482,
                ERRORS,
                L"LookupPrincName failed, hr=%!HRESULT!",
                v28);
            v38 = (char *)HeapAlloc(g_hHeap, 0, 0xCu);
            gpsaSecurity = (tagDUALSTRINGARRAY *)v38;
            if ( v38 )
            {
              v33 = 0;
              *(_DWORD *)v38 = 131076;
              *(_QWORD *)(v38 + 4) = 0;
              v28 = 0;
              gDefaultService = 1;
              goto LABEL_152;
            }
          }
          else
          {
            if ( v12 )
            {
              v40 = gCapabilities;
              gCapabilities = v19;
              v28 = RegisterAuthnServices(v12, p_sAuthSvc);
              if ( v28 < 0 )
              {
                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                  ComTraceMessageT<long>(
                    "onecore\\com\\combase\\dcomrem\\security.cxx",
                    "CoInitializeSecurity",
                    3534,
                    ERRORS,
                    L"RegisterAuthnServices failed, hr=%!HRESULT!",
                    v28);
                BreakOnCoInitializeSecurityRuntimeFailureIfRequested(v28);
              }
              gCapabilities = v40;
LABEL_151:
              if ( v28 < 0 )
                goto LABEL_109;
LABEL_152:
              v41 = (_SECURITY_DESCRIPTOR *)pSD;
              if ( pSD )
              {
                if ( !IsValidCOMSecurityDescriptor(pSD, v32) )
                {
                  if ( gfLogInvalidSecurityDescriptor )
                    LogInvalidSecurityDescriptor(
                      (_GUID *)v33,
                      18215 - (genumAccessSD != EventLog_SERVERACCESSPERMISSIONSPROG),
                      v42);
                  v28 = -2147024809;
                  goto LABEL_109;
                }
                if ( (g_GLBOPT_RoFlags & 0x40) != 0 )
                {
                  pNewerCopySecDesc = 0;
                  v28 = EnsureRestrictedCodePresent(v41, &pNewerCopySecDesc);
                  if ( v28 < 0 )
                  {
                    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                      || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                    {
                      ComTraceMessageT<long>(
                        "onecore\\com\\combase\\dcomrem\\security.cxx",
                        "CoInitializeSecurity",
                        3573,
                        ERRORS,
                        L"EnsureRestrictedCodePresent failed, hr=%!HRESULT!",
                        v28);
                    }
                    BreakOnCoInitializeSecurityRuntimeFailureIfRequested(v28);
                    goto LABEL_109;
                  }
                  HeapFree(g_hHeap, 0, v41);
                  v41 = pNewerCopySecDesc;
                  pSD = (_SECURITY_DESCRIPTOR_RELATIVE *)pNewerCopySecDesc;
                }
              }
              LODWORD(gAuthnLevel) = dwAuthnLevel;
              gImpLevel = dwLenSecDescSelfRelative;
              gAccessControl = pAccessControl;
              CAuthInfo::_sList = pCopyAuthInfo;
              gCapabilities = v19;
              gSecDesc = v41;
              CAuthInfo::_fNeedSSL = 1;
              if ( LODWORD(result.ptr_) )
              {
                m_size = gClientSvcList.m_size;
                v44 = 0;
                if ( gClientSvcList.m_size )
                {
                  m_ptr = gClientSvcList.m_ptr;
                  while ( 1 )
                  {
                    v33 = v44 + 1;
                    if ( gClientSvcList.m_ptr[v44].wId == 14 )
                      break;
                    ++v44;
                    if ( (unsigned int)v33 >= gClientSvcList.m_size )
                      goto LABEL_175;
                  }
                  if ( (unsigned int)v33 < gClientSvcList.m_size )
                  {
                    while ( 1 )
                    {
                      v46 = m_ptr[v44 + 1];
                      v47 = v44++;
                      v33 = v44 + 1;
                      m_ptr[v47] = v46;
                      m_size = gClientSvcList.m_size;
                      if ( v33 >= gClientSvcList.m_size )
                        break;
                      m_ptr = gClientSvcList.m_ptr;
                    }
                  }
                  gClientSvcList.m_size = m_size - 1;
                }
              }
LABEL_175:
              gSecDescRestrictions = CRpcResolver::GetDefaultAccessRestrictionsSD((CRpcResolver *)v33);
              if ( gSecDescRestrictions )
              {
                CalculateAnonymousGrantedRemoteAccessInRestrictions();
              }
              else
              {
                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                  ComTraceMessageT<>(
                    "onecore\\com\\combase\\dcomrem\\security.cxx",
                    "CoInitializeSecurity",
                    3612,
                    ERRORS,
                    L"GetDefaultAccessRestrictionsSD failed");
                BreakOnCoInitializeSecurityRuntimeFailureIfRequested(-2147024882);
                v28 = -2147024882;
              }
              CoVrfCheckSecuritySettings();
              goto LABEL_109;
            }
            v39 = (char *)HeapAlloc(g_hHeap, 0, 0xCu);
            gpsaSecurity = (tagDUALSTRINGARRAY *)v39;
            if ( v39 )
            {
              v33 = 0;
              *(_DWORD *)v39 = 131076;
              *(_QWORD *)(v39 + 4) = 0;
              goto LABEL_151;
            }
          }
          BreakOnCoInitializeSecurityRuntimeFailureIfRequested(-2147024882);
LABEL_143:
          v28 = -2147024882;
          goto LABEL_151;
        }
        while ( p_sAuthSvc[v29].dwAuthnSvc != 14 )
        {
          if ( ++v29 >= v12 )
            goto LABEL_105;
        }
        if ( !LODWORD(result.ptr_) )
        {
          CSSL::DefaultCert((const _CERT_CONTEXT **)&pCert);
          goto LABEL_105;
        }
LABEL_93:
        v28 = -2147024809;
        goto $Error_8;
      }
    }
    else if ( !v12 )
    {
      goto LABEL_93;
    }
    if ( v12 != -1 && !IsValidPtrOut(p_sAuthSvc, 24LL * v12) )
      goto LABEL_93;
    goto LABEL_84;
  }
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\dcomrem\\security.cxx",
      "CoInitializeSecurity",
      3215,
      ERRORS,
      L"%!HRESULT!",
      -2147418113);
  if ( ptr )
    ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(ptr);
  return -2147418113;
}

```

## disassembly

```asm
0x180111200  mov     [rsp-8+arg_18], rbx
0x180111205  push    rbp
0x180111206  push    rsi
0x180111207  push    rdi
0x180111208  push    r12
0x18011120a  push    r13
0x18011120c  push    r14
0x18011120e  push    r15
0x180111210  lea     rbp, [rsp-1E0h]
0x180111218  sub     rsp, 2E0h
0x18011121f  mov     rax, cs:__security_cookie
0x180111226  xor     rax, rsp
0x180111229  mov     [rbp+210h+var_40], rax
0x180111230  mov     r15, [rbp+210h+pAuthList]
0x180111237  xor     edi, edi
0x180111239  mov     eax, edi
0x18011123b  mov     [rsp+310h+pSecDesc], pVoid
0x180111240  xorps   xmm0, xmm0
0x180111243  mov     qword ptr [rbp+210h+pCert], asAuthSvc
0x180111247  mov     r14, pReserved1
0x18011124a  mov     [rsp+310h+pSD], rax
0x18011124f  lea     ecx, [rdi+2]; whichProperty
0x180111252  mov     [rsp+310h+pNewerCopySecDesc], rax
0x180111257  mov     rsi, asAuthSvc
0x18011125a  mov     [rsp+310h+pAccessControl], rdi
0x18011125f  mov     r12d, cAuthSvc
0x180111262  mov     qword ptr [rbp+210h+sAuthSvc.hr], rax
0x180111266  movups  xmmword ptr [rbp+210h+sAuthSvc.dwAuthnSvc], xmm0
0x18011126a  mov     [rsp+310h+pCopyAuthInfo], rdi
0x18011126f  mov     ebx, edi
0x180111271  mov     [rsp+310h+pPrincName], rdi
0x180111276  call    ?Query@FeatureDevelopmentProperties@@YA_NW4BoolProperty@1@PEA_N@Z; FeatureDevelopmentProperties::Query(FeatureDevelopmentProperties::BoolProperty,bool *)
0x18011127b  test    al, al
0x18011127d  jz      short loc_1801112AE
0x18011127f  xor     cAuthSvc, cAuthSvc; framesToSkip
0x180111281  lea     pVoid, [rsp+310h+result]; result
0x180111286  call    ?Capture@StackTrace@@SA?AV?$ReferencedPtr@UStackTrace@@@ObjectLibrary@@GG@Z; StackTrace::Capture(ushort,ushort)
0x18011128b  lea     pVoid, [rbp+210h+var_260]
0x18011128f  cmp     pVoid, rax
0x180111292  jz      short loc_18011129A
0x180111294  mov     rbx, [rax]
0x180111297  mov     [rax], rdi
0x18011129a  mov     pVoid, [rsp+310h+result.ptr_]; this
0x18011129f  test    pVoid, pVoid
0x1801112a2  jz      short loc_1801112AE
0x1801112a4  mov     [rsp+310h+result.ptr_], rdi
0x1801112a9  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x1801112ae  call    IsApartmentInitialized
0x1801112b3  test    eax, eax
0x1801112b5  jnz     short loc_1801112CE
0x1801112b7  test    rbx, rbx
0x1801112ba  jz      short loc_1801112C4
0x1801112bc  mov     pVoid, rbx; this
0x1801112bf  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x1801112c4  mov     eax, 800401F0h
0x1801112c9  jmp     loc_180111E79
0x1801112ce  mov     r13d, [rbp+210h+dwCapabilities]
0x1801112d5  bt      r13d, 0Eh
0x1801112da  jnb     short loc_180111304
0x1801112dc  lea     pVoid, value; "WinSta0\\Default"
0x1801112e3  call    ?SetExplicitWinstaDesktopString@@YAJ_K@Z; SetExplicitWinstaDesktopString(unsigned __int64)
0x1801112e8  mov     edi, eax
0x1801112ea  test    eax, eax
0x1801112ec  jns     short loc_180111302
0x1801112ee  test    rbx, rbx
0x1801112f1  jz      short loc_1801112FB
0x1801112f3  mov     pVoid, rbx; this
0x1801112f6  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x1801112fb  mov     eax, edi
0x1801112fd  jmp     loc_180111E79
0x180111302  xor     edi, edi
0x180111304  cmp     cs:?gGotSecurityData@@3HA, edi; int gGotSecurityData
0x18011130a  jnz     short loc_180111366
0x18011130c  call    ?GetConnection@CRpcResolver@@QEAAJXZ; CRpcResolver::GetConnection(void)
0x180111311  mov     edi, eax
0x180111313  test    eax, eax
0x180111315  js      short loc_1801112EE
0x180111317  xor     edi, edi
0x180111319  cmp     cs:?gGotSecurityData@@3HA, edi; int gGotSecurityData
0x18011131f  jnz     short loc_180111366
0x180111321  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180111327  test    eax, eax
0x180111329  jnz     short loc_18011133E
0x18011132b  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180111331  jz      short loc_180111366
0x180111333  xor     ecx, ecx; level
0x180111335  call    IsWppLevelEnabled
0x18011133a  test    al, al
0x18011133c  jz      short loc_180111366
0x18011133e  lea     rax, aCrpcresolverGe_1; "CRpcResolver::GetConnection returned su"...
0x180111345  xor     r9d, r9d; level
0x180111348  mov     r8d, 0C52h; line
0x18011134e  mov     [rsp+310h+format], rax; format
0x180111353  lea     rdx, aCoinitializese_0; "CoInitializeSecurity"
0x18011135a  lea     pVoid, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180111361  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180111366  mov     eax, r13d
0x180111369  and     eax, 0Ch
0x18011136c  cmp     eax, 0Ch
0x18011136f  jz      short loc_180111395
0x180111371  mov     pVoid, [rsp+310h+pSecDesc]; pSecurityDescriptor
0x180111376  mov     [rsp+310h+var_2D0], edi
0x18011137a  test    pVoid, pVoid
0x18011137d  jz      loc_1801114CB
0x180111383  test    eax, eax
0x180111385  jnz     loc_1801114CB
0x18011138b  call    cs:__imp_IsValidSecurityDescriptor
0x180111391  test    eax, eax
0x180111393  jnz     short loc_1801113AC
0x180111395  test    rbx, rbx
0x180111398  jz      short loc_1801113A2
0x18011139a  mov     pVoid, rbx; this
0x18011139d  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x1801113a2  mov     eax, 80070057h
0x1801113a7  jmp     loc_180111E79
0x1801113ac  mov     pVoid, [rsp+310h+pSecDesc]; pAbsoluteSecurityDescriptor
0x1801113b1  lea     asAuthSvc, [rsp+310h+dwLenSecDescSelfRelative]; lpdwBufferLength
0x1801113b6  xor     cAuthSvc, cAuthSvc; pSelfRelativeSecurityDescriptor
0x1801113b8  mov     [rsp+310h+dwLenSecDescSelfRelative], edi
0x1801113bc  call    cs:__imp_MakeSelfRelativeSD
0x1801113c2  test    eax, eax
0x1801113c4  jnz     loc_1801115C6
0x1801113ca  call    cs:__imp_GetLastError
0x1801113d0  mov     edi, eax
0x1801113d2  cmp     eax, 7Ah ; 'z'
0x1801113d5  jnz     loc_18011156E
0x1801113db  mov     r8d, [rsp+310h+dwLenSecDescSelfRelative]; dwBytes
0x1801113e0  xor     cAuthSvc, cAuthSvc; dwFlags
0x1801113e2  mov     pVoid, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801113e9  call    cs:__imp_HeapAlloc
0x1801113ef  xor     edi, edi
0x1801113f1  mov     rsi, rax
0x1801113f4  test    rax, rax
0x1801113f7  jnz     short loc_18011141C
0x1801113f9  mov     r15d, 8007000Eh
0x1801113ff  mov     ecx, r15d; error
0x180111402  call    ?BreakOnCoInitializeSecurityRuntimeFailureIfRequested@@YAXJ@Z; BreakOnCoInitializeSecurityRuntimeFailureIfRequested(long)
0x180111407  test    rbx, rbx
0x18011140a  jz      short loc_180111414
0x18011140c  mov     pVoid, rbx; this
0x18011140f  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x180111414  mov     eax, r15d
0x180111417  jmp     loc_180111E79
0x18011141c  mov     pVoid, [rsp+310h+pSecDesc]; pAbsoluteSecurityDescriptor
0x180111421  lea     asAuthSvc, [rsp+310h+dwLenSecDescSelfRelative]; lpdwBufferLength
0x180111426  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x180111429  call    cs:__imp_MakeSelfRelativeSD
0x18011142f  test    eax, eax
0x180111431  jnz     short loc_1801114B0
0x180111433  call    cs:__imp_GetLastError
0x180111439  mov     edi, eax
0x18011143b  xor     r14d, r14d
0x18011143e  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180111444  test    eax, eax
0x180111446  jnz     short loc_18011145C
0x180111448  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18011144f  jz      short loc_180111488
0x180111451  xor     ecx, ecx; level
0x180111453  call    IsWppLevelEnabled
0x180111458  test    al, al
0x18011145a  jz      short loc_180111488
0x18011145c  lea     rax, aWinerror; "%!WINERROR!"
0x180111463  mov     [rsp+310h+var_2E8], edi; <args_0>
0x180111467  xor     r9d, r9d; level
0x18011146a  mov     [rsp+310h+format], rax; format
0x18011146f  mov     r8d, 0C7Dh; line
0x180111475  lea     rdx, aCoinitializese_0; "CoInitializeSecurity"
0x18011147c  lea     pVoid, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180111483  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x180111488  mov     pVoid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18011148f  mov     asAuthSvc, rsi; lpMem
0x180111492  xor     cAuthSvc, cAuthSvc; dwFlags
0x180111494  call    cs:__imp_HeapFree
0x18011149a  test    edi, edi
0x18011149c  jle     loc_1801112EE
0x1801114a2  movzx   edi, di
0x1801114a5  or      edi, 80070000h
0x1801114ab  jmp     loc_1801112EE
0x1801114b0  mov     [rsp+310h+pSecDesc], rsi
0x1801114b5  mov     rsi, qword ptr [rbp+210h+pCert]
0x1801114b9  mov     [rsp+310h+var_2D0], 1
0x1801114c1  mov     cs:?genumAccessSD@@3W4tagEventLogSD@@A, 6; tagEventLogSD genumAccessSD
0x1801114cb  cmp     [rbp+210h+dwAuthnLevel], edi
0x1801114d1  jnz     short loc_1801114DD
0x1801114d3  mov     [rbp+210h+dwAuthnLevel], 2
0x1801114dd  call    _lambda_b0dc4f2acc5dfa3920fff315afd6e4d9___operator__
0x1801114e2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801114e6  test    r13b, 8
0x1801114ea  jz      loc_1801116B4
0x1801114f0  mov     pVoid, [rsp+310h+pSecDesc]; pAppId
0x1801114f5  lea     pReserved1, [rbp+210h+dwAuthnLevel]; pAuthnLevel
0x1801114fc  lea     asAuthSvc, [rbp+210h+dwCapabilities]; pCapabilities
0x180111503  lea     rdx, [rsp+310h+pSecDesc]; ppSD
0x180111508  call    ?GetLegacyBlanket@@YAJPEAU_GUID@@PEAPEAU_SECURITY_DESCRIPTOR_RELATIVE@@PEAK2@Z; GetLegacyBlanket(_GUID *,_SECURITY_DESCRIPTOR_RELATIVE * *,ulong *,ulong *)
0x18011150d  xor     r8d, r8d
0x180111510  mov     edi, eax
0x180111512  test    eax, eax
0x180111514  jns     loc_180111628
0x18011151a  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x180111520  test    ecx, ecx
0x180111522  jnz     short loc_180111536
0x180111524  cmp     cs:?gfEnableTracing@@3HA, r8d; int gfEnableTracing
0x18011152b  jz      short loc_180111562
0x18011152d  call    IsWppLevelEnabled
0x180111532  test    al, al
0x180111534  jz      short loc_180111562
0x180111536  lea     rax, aGetlegacyblank_0; "GetLegacyBlanket failed, hr=%!HRESULT!"
0x18011153d  mov     [rsp+310h+var_2E8], edi; <args_0>
0x180111541  xor     r9d, r9d; level
0x180111544  mov     [rsp+310h+format], rax; format
0x180111549  mov     r8d, 0CBDh; line
0x18011154f  lea     rdx, aCoinitializese_0; "CoInitializeSecurity"
0x180111556  lea     pVoid, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18011155d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180111562  mov     ecx, edi; error
0x180111564  call    ?BreakOnCoInitializeSecurityRuntimeFailureIfRequested@@YAXJ@Z; BreakOnCoInitializeSecurityRuntimeFailureIfRequested(long)
0x180111569  jmp     loc_1801112EE
0x18011156e  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180111574  xor     esi, esi
0x180111576  test    eax, eax
0x180111578  jnz     short loc_180111595
0x18011157a  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x180111580  jz      loc_18011149A
0x180111586  xor     ecx, ecx; level
0x180111588  call    IsWppLevelEnabled
0x18011158d  test    al, al
0x18011158f  jz      loc_18011149A
0x180111595  lea     rax, aWinerror; "%!WINERROR!"
0x18011159c  mov     [rsp+310h+var_2E8], edi; <args_0>
0x1801115a0  xor     r9d, r9d; level
0x1801115a3  mov     [rsp+310h+format], rax; format
0x1801115a8  mov     r8d, 0C8Ah; line
0x1801115ae  lea     rdx, aCoinitializese_0; "CoInitializeSecurity"
0x1801115b5  lea     pVoid, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1801115bc  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x1801115c1  jmp     loc_18011149A
0x1801115c6  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801115cc  mov     esi, 8000FFFFh
0x1801115d1  test    eax, eax
0x1801115d3  jnz     short loc_1801115E8
0x1801115d5  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1801115db  jz      short loc_180111614
0x1801115dd  xor     ecx, ecx; level
0x1801115df  call    IsWppLevelEnabled
0x1801115e4  test    al, al
0x1801115e6  jz      short loc_180111614
0x1801115e8  lea     rax, aHresult; "%!HRESULT!"
0x1801115ef  mov     [rsp+310h+var_2E8], esi; <args_0>
0x1801115f3  xor     r9d, r9d; level
0x1801115f6  mov     [rsp+310h+format], rax; format
0x1801115fb  mov     r8d, 0C8Fh; line
0x180111601  lea     rdx, aCoinitializese_0; "CoInitializeSecurity"
0x180111608  lea     pVoid, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18011160f  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180111614  test    rbx, rbx
0x180111617  jz      short loc_180111621
0x180111619  mov     pVoid, rbx; this
0x18011161c  call    ?Release@?$AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer@UStackTrace@@V?$AddComReferenceCounting_WeakReferenceCountLayer@UStackTrace@@V?$AddComReferenceCounting_ReferenceCountLayer@UStackTrace@@V?$Allocation_SealedClassDeleteSelfLayer@UStackTrace@@V?$ContainedBy@U?$ContainmentSpecification@VGlobalStackTraceMap@StackTraceDetails@@UStackTrace@@UOrderedMap@ContainerKind@ObjectLibrary@@$00@ObjectLibrary@@UStackTrace@@VNil@Details@2@@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_WeaklyReferenceableReferenceCountingLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_WeakReferenceCountLayer<StackTrace,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<StackTrace,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<StackTrace,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<StackTraceDetails::GlobalStackTraceMap,StackTrace,ObjectLibrary::ContainerKind::OrderedMap,1>,StackTrace,ObjectLibrary::Details::Nil>>>>>::Release(void)
0x180111621  mov     eax, esi
0x180111623  jmp     loc_180111E79
0x180111628  mov     pVoid, cs:?gLegacySecurity@@3V?$unique_ptr@UtagSECURITYBINDING@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@A.__ptr_.__value_; wistd::unique_ptr<tagSECURITYBINDING,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>> gLegacySecurity ...
0x18011162f  mov     [rsp+310h+var_2D0], 1
0x180111637  test    pVoid, pVoid
0x18011163a  jz      short loc_180111685
0x18011163c  movzx   ecx, word ptr [pVoid]; wAuthnSvc
0x18011163f  lea     rdx, [rsp+310h+pPrincName]; pPrincName
0x180111644  call    ?LookupPrincName@@YAJGPEAPEAG@Z; LookupPrincName(ushort,ushort * *)
0x180111649  mov     rax, cs:?gLegacySecurity@@3V?$unique_ptr@UtagSECURITYBINDING@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@A.__ptr_.__value_; wistd::unique_ptr<tagSECURITYBINDING,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>> gLegacySecurity ...
0x180111650  lea     rsi, [rbp+210h+sAuthSvc]
0x180111654  mov     r12d, 1
0x18011165a  movzx   ecx, word ptr [rax]
0x18011165d  mov     [rbp+210h+sAuthSvc.dwAuthnSvc], ecx
0x180111660  movzx   ecx, word ptr [rax+2]
0x180111664  mov     rax, [rsp+310h+pPrincName]
0x180111669  mov     [rbp+210h+sAuthSvc.pPrincipalName], rax
0x18011166d  mov     [rbp+210h+sAuthSvc.dwAuthzSvc], ecx
0x180111670  cmp     ecx, 0FFFFh
0x180111676  jnz     short loc_18011168E
0x180111678  xor     r8d, r8d
0x18011167b  mov     [rbp+210h+sAuthSvc.dwAuthzSvc], r8d
0x18011167f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180111683  jmp     short loc_180111695
0x180111685  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180111689  mov     r12d, edi
0x18011168c  jmp     short loc_180111695
0x18011168e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180111692  xor     r8d, r8d
0x180111695  mov     r13d, [rbp+210h+dwCapabilities]
0x18011169c  mov     r14, asAuthSvc
0x18011169f  or      r13d, cs:?gCapabilities@@3KA; ulong gCapabilities
0x1801116a6  mov     r15, asAuthSvc
0x1801116a9  mov     eax, cs:?gImpLevel@@3KA; ulong gImpLevel
0x1801116af  mov     pVoid, asAuthSvc
0x1801116b2  jmp     short loc_180111700
0x1801116b4  mov     r8d, 10h; Size
0x1801116ba  lea     rdx, GUID_NULL; Buf2
0x1801116c1  lea     pVoid, ?g_AppId@@3U_GUID@@A; Buf1
0x1801116c8  call    memcmp_0
0x1801116cd  test    eax, eax
0x1801116cf  jnz     short loc_1801116F3
  ... truncated ...
```
