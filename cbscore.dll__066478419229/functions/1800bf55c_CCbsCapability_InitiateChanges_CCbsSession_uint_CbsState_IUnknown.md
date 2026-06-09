# CCbsCapability::InitiateChanges(CCbsSession *,uint,CbsState,IUnknown *)

- ea: `0x1800bf55c`
- end: `0x1800c0033`
- name: `?InitiateChanges@CCbsCapability@@QEAAJPEAVCCbsSession@@IW4CbsState@@PEAUIUnknown@@@Z`
- size: `2775`
- prototype: ``
- caller_count: `4`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bf55c`
- `0x1801b46b0`
- `0x1801bb544`
- `0x1801ca688`

## callees

- `0x18000d910`
- `0x18000e780`
- `0x180010b60`
- `0x180010cc0`
- `0x180013250`
- `0x1800138b8`
- `0x18001e1a0`
- `0x18001ef60`
- `0x18001f508`
- `0x18002093c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800be858`
- `0x1800bf55c`
- `0x1800c0054`
- `0x1800e9f30`
- `0x1800eb920`
- `0x1801a1a28`
- `0x1801a28d4`
- `0x1801a33f0`
- `0x1801c2c30`
- `0x1801c8ac4`
- `0x1801c9ecc`
- `0x1801d2e38`
- `0x1801d5c44`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf6d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bfbb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bfc7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bffeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf6d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bfbb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bfc7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bffeb`

## string_xrefs

- `0x1800bf5d9`: `Attempt to change a finalized session`
- `0x1800bf723`: `No write operations (add/remove capability) are allowed on a container`
- `0x1800bfea5`: `Failed to decompress OC content.`
- `0x1800bfd8e`: `Failed to add an additional tasks for .NetFx3`
- `0x1800bfa54`: `LCU is postponed and this package is a FOD/LP. A reboot must be taken prior to installation of this package: {}`
- `0x1800bf79a`: `Removed capability cannot be used to make system change: {}`
- `0x1800bf932`: `Failed to check uninstall of FOD: {}`

## pseudocode

```c
__int64 __fastcall CCbsCapability::InitiateChanges(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64))
{
  struct CCbsSession *v9; // rdx
  unsigned int v10; // ebx
  int v11; // edx
  __int64 v12; // rdx
  int CurrentState; // eax
  int v14; // edx
  void *v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // edx
  CCbsCapabilityManager *v20; // rbx
  struct CCbsCapability **InitPointer; // rax
  int v22; // eax
  int v23; // edx
  int v24; // eax
  int v25; // edx
  int Property; // eax
  int v27; // edx
  int v28; // edx
  int InternalProperty; // eax
  int v30; // edx
  int v31; // eax
  int v32; // edx
  int v33; // eax
  int v34; // edx
  __int64 v35; // rdx
  unsigned __int64 v36; // r9
  int v37; // eax
  int v38; // eax
  int v39; // edx
  int v40; // eax
  int v41; // edx
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // edx
  __int64 (__fastcall **v46)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64); // rbx
  __int64 v48; // rax
  int v49; // eax
  int v50; // edx
  unsigned __int64 v51; // r9
  __int64 v52; // rdx
  int v53; // eax
  int v55; // [rsp+20h] [rbp-61h]
  int v56; // [rsp+20h] [rbp-61h]
  LPVOID pv; // [rsp+40h] [rbp-41h] BYREF
  int v58[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v59; // [rsp+50h] [rbp-31h] BYREF
  CCbsCapability *FastCbsIdentityString; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v61; // [rsp+60h] [rbp-21h] BYREF
  struct ICbsUIHandler *v62; // [rsp+68h] [rbp-19h] BYREF
  __int64 v63; // [rsp+70h] [rbp-11h] BYREF
  __int64 v64; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v64 = 0;
  v63 = 0;
  pv = 0;
  v59 = 0;
  v61 = 4096;
  if ( (unsigned int)CCbsSession::IsLocked((CCbsSession *)a2) && !*((_DWORD *)v9 + 191) )
  {
    v10 = -2146498494;
    v61 = -2146498494;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Attempt to change a finalized session");
      FastCbsIdentityString = (CCbsCapability *)&v61;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&FastCbsIdentityString);
    }
    v12 = 123;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscapability.cpp",
      (const char *)v10,
      v55);
    goto LABEL_11;
  }
  CurrentState = CCbsCapability::GetCurrentState((CCbsCapability *)a1, v9, (enum CbsState *)&v61, 0);
  v10 = CurrentState;
  if ( CurrentState < 0 )
  {
    v61 = CurrentState;
    if ( LogAdapter::g_Logger )
    {
      FastCbsIdentityString = (CCbsCapability *)GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get current state for package: {}",
        (__int64)&FastCbsIdentityString);
      v62 = (struct ICbsUIHandler *)&v61;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&v62);
    }
    v12 = 129;
    goto LABEL_10;
  }
  if ( CCbsSession::IsImageReadOnly((CCbsSession *)a2) && v61 != a4 )
  {
    if ( !vbInTestMode )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = -2146498493;
    v61 = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "No write operations (add/remove capability) are allowed on a container");
      FastCbsIdentityString = (CCbsCapability *)&v61;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)&FastCbsIdentityString);
    }
    v12 = 137;
    goto LABEL_10;
  }
  if ( !CCbsCapability::GetInternalPackage((CCbsCapability *)a1) )
  {
    v10 = -2146498555;
    v61 = -2146498555;
    if ( LogAdapter::g_Logger )
    {
      FastCbsIdentityString = (CCbsCapability *)GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Removed capability cannot be used to make system change: {}",
        (__int64)&FastCbsIdentityString);
      v62 = (struct ICbsUIHandler *)&v61;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v19,
        3,
        (unsigned int)": {}",
        (__int64)&v62);
    }
    v12 = 141;
    goto LABEL_10;
  }
  if ( !*(_QWORD *)(a1 + 32) )
  {
    v20 = vpCapabilityManager;
    FastCbsIdentityString = 0;
    InitPointer = (struct CCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&FastCbsIdentityString);
    v22 = CCbsCapabilityManager::ResolveCapability(
            v20,
            (struct CCbsSession *)a2,
            *(const struct CCbsIdentity **)(a1 + 136),
            InitPointer);
    v10 = v22;
    if ( v22 >= 0 )
    {
      *(_QWORD *)v58 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "Redirecting Capability InitiateChange using FOD metadata package: {}",
        v58);
      v10 = CCbsCapability::InitiateChanges(FastCbsIdentityString, a2, a3, (unsigned int)a4, a5);
    }
    else
    {
      v61 = v22;
      if ( LogAdapter::g_Logger )
      {
        v62 = (struct ICbsUIHandler *)GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to resolve the capability in the fod metadata: {}",
          (__int64)&v62);
        *(_QWORD *)v58 = &v61;
        LOBYTE(v23) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v23,
          3,
          (unsigned int)": {}",
          (__int64)v58);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\base\\cbs\\core\\cbscapability.cpp",
        (const char *)v10,
        v55);
    }
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&FastCbsIdentityString);
LABEL_11:
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v59);
    v15 = pv;
    if ( pv )
      goto LABEL_60;
    goto LABEL_97;
  }
  v24 = CCbsCapability::CheckForUninstall(v17, a2, v18, (unsigned int)a4);
  v10 = v24;
  if ( v24 < 0 )
  {
    v61 = v24;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v58 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to check uninstall of FOD: {}",
        (__int64)v58);
      FastCbsIdentityString = (CCbsCapability *)&v61;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&FastCbsIdentityString);
    }
    v12 = 159;
    goto LABEL_10;
  }
  v55 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
  Property = CCbsCapability::GetProperty(a1, a2, 0, 47);
  v10 = Property;
  if ( Property < 0 )
  {
    v61 = Property;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get package property CbsPackagePropertyRequiresPriorReboot");
      *(_QWORD *)v58 = &v61;
      LOBYTE(v27) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v27,
        3,
        (unsigned int)": {}",
        (__int64)v58);
    }
    v12 = 166;
    goto LABEL_10;
  }
  if ( (unsigned __int8)StringsAreEqual(L"1", pv, 1) && a4 >= 112 )
  {
    v10 = -2146498554;
    v61 = -2146498554;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v58 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"LCU is postponed and this package is a FOD/LP. A reboot must be taken prior to installation of this package: {}",
        (__int64)v58);
      FastCbsIdentityString = (CCbsCapability *)&v61;
      LOBYTE(v28) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v28,
        3,
        (unsigned int)": {}",
        (__int64)&FastCbsIdentityString);
    }
    v12 = 170;
    goto LABEL_10;
  }
  InternalProperty = CCbsCapability::GetInternalProperty(a1, a2, 2, &v64);
  v10 = InternalProperty;
  if ( InternalProperty < 0 )
  {
    v61 = InternalProperty;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get displayname");
      *(_QWORD *)v58 = &v61;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)v58);
    }
    v12 = 172;
    goto LABEL_10;
  }
  v31 = CCbsCapability::GetInternalProperty(a1, a2, 3, &v63);
  v10 = v31;
  if ( v31 < 0 )
  {
    v61 = v31;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get description");
      *(_QWORD *)v58 = &v61;
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v32,
        3,
        (unsigned int)": {}",
        (__int64)v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscapability.cpp",
      (const char *)v10,
      v55);
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v59);
    v15 = pv;
    if ( pv )
      goto LABEL_60;
    goto LABEL_97;
  }
  v56 = v64;
  v33 = CCbsSession::AddCapabilityTask(a2, a3, a1, 0);
  v10 = v33;
  if ( v33 < 0 )
  {
    v61 = v33;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add capability.");
      *(_QWORD *)v58 = &v61;
      LOBYTE(v34) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v34,
        3,
        (unsigned int)": {}",
        (__int64)v58);
    }
    v35 = 182;
LABEL_57:
    v36 = v10;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscapability.cpp",
      (const char *)v36,
      v56);
    goto LABEL_59;
  }
  v37 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)(a2 + 1824), *(const wchar_t **)(a1 + 48));
  v10 = v37;
  if ( v37 < 0 )
  {
    v36 = (unsigned int)v37;
    v35 = 187;
    goto LABEL_58;
  }
  if ( (unsigned __int8)StringsAreEqual(*(_QWORD *)(a1 + 136) + 30LL, L"NetFx3", 1) )
  {
    v61 = 4096;
    v38 = CCbsCapability::GetCurrentState((CCbsCapability *)a1, (struct CCbsSession *)a2, (enum CbsState *)&v61, 0);
    v10 = v38;
    if ( v38 < 0 )
    {
      v61 = v38;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v58 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a1 + 136));
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get current state for package: {}",
          (__int64)v58);
        FastCbsIdentityString = (CCbsCapability *)&v61;
        LOBYTE(v39) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v39,
          3,
          (unsigned int)": {}",
          (__int64)&FastCbsIdentityString);
      }
      v35 = 196;
      goto LABEL_57;
    }
    v40 = CCbsSession::AddingAdditionalTasksForNetFx3FeatureOnDemandPackage(a2, v61, (unsigned int)a4);
    v10 = v40;
    if ( v40 < 0 )
    {
      v61 = v40;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add an additional tasks for .NetFx3");
        *(_QWORD *)v58 = &v61;
        LOBYTE(v41) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {}",
          (__int64)v58);
      }
      v35 = 199;
      goto LABEL_57;
    }
  }
  else if ( a4 >= 112
         && ((unsigned __int8)StringsAreEqual(*(_QWORD *)(a1 + 136) + 30LL, L"Container.Win3CtrRuntime.Metadata", 1)
          || (unsigned __int8)StringsAreEqual(*(_QWORD *)(a1 + 136) + 30LL, L"Container.Professional.Metadata", 1)) )
  {
    v42 = CCbsSession::SetEnhancedOptions((CCbsSession *)a2, 0x40u);
    v10 = v42;
    if ( v42 < 0 )
    {
      v61 = v42;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to set the enhanced option on the session.");
        *(_QWORD *)v58 = &v61;
        LOBYTE(v43) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v43,
          3,
          (unsigned int)": {}",
          (__int64)v58);
      }
      v35 = 208;
      goto LABEL_57;
    }
    v44 = CCbsSession::DecompressOCContent((CCbsSession *)a2);
    v10 = v44;
    if ( v44 < 0 )
    {
      v61 = v44;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to decompress OC content.");
        *(_QWORD *)v58 = &v61;
        LOBYTE(v45) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v45,
          3,
          (unsigned int)": {}",
          (__int64)v58);
      }
      v35 = 210;
      goto LABEL_57;
    }
  }
  if ( !a5 )
  {
LABEL_94:
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v59);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v10 = 0;
    goto LABEL_97;
  }
  v46 = *a5;
  v62 = 0;
  v47 = *v46;
  v48 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v62);
  v49 = v47(a5, &GUID_75207392_23f2_4396_85f0_8fdb879ed0ed, v48);
  v10 = v49;
  if ( v49 < 0 )
  {
    v61 = v49;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to query interface passed in handler for IID_ICbsUIHandler.");
      *(_QWORD *)v58 = &v61;
      LOBYTE(v50) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v50,
        3,
        (unsigned int)": {}",
        (__int64)v58);
    }
    v51 = v10;
    v52 = 218;
    goto LABEL_88;
  }
  v53 = CCbsSession::RegisterCbsUIHandler((CCbsSession *)a2, v62);
  v10 = v53;
  if ( v53 >= 0 )
  {
    if ( v62 )
      (*(void (__fastcall **)(struct ICbsUIHandler *))(*(_QWORD *)v62 + 16LL))(v62);
    goto LABEL_94;
  }
  v51 = (unsigned int)v53;
  v52 = 220;
LABEL_88:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v52,
    (unsigned int)"onecore\\base\\cbs\\core\\cbscapability.cpp",
    (const char *)v51,
    v56);
  if ( v62 )
  {
    (*(void (__fastcall **)(struct ICbsUIHandler *))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
LABEL_59:
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v59);
  v15 = pv;
  if ( pv )
  {
LABEL_60:
    CoTaskMemFree(v15);
    pv = 0;
  }
LABEL_97:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v63);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v64);
  return v10;
}

```

## disassembly

```asm
0x1800bf55c  push    rbp
0x1800bf55e  push    rbx
0x1800bf55f  push    rsi
0x1800bf560  push    rdi
0x1800bf561  push    r12
0x1800bf563  push    r13
0x1800bf565  push    r14
0x1800bf567  push    r15
0x1800bf569  lea     rbp, [rsp-17h]
0x1800bf56e  sub     rsp, 98h
0x1800bf575  mov     rax, cs:__security_cookie
0x1800bf57c  xor     rax, rsp
0x1800bf57f  mov     [rbp+4Fh+var_50], rax
0x1800bf583  mov     r12, [rbp+4Fh+arg_20]
0x1800bf587  xor     edi, edi
0x1800bf589  mov     rsi, rcx
0x1800bf58c  mov     [rbp+4Fh+var_58], rdi
0x1800bf590  mov     rcx, rdx; this
0x1800bf593  mov     [rbp+4Fh+var_60], rdi
0x1800bf597  mov     [rbp+4Fh+pv], rdi
0x1800bf59b  mov     r15d, r9d
0x1800bf59e  mov     [rbp+4Fh+var_80], rdi
0x1800bf5a2  mov     r13d, r8d
0x1800bf5a5  mov     r14, rdx
0x1800bf5a8  mov     [rbp+4Fh+var_70], 1000h
0x1800bf5af  call    ?IsLocked@CCbsSession@@QEAAHXZ; CCbsSession::IsLocked(void)
0x1800bf5b4  test    eax, eax
0x1800bf5b6  jz      short loc_1800BF61F
0x1800bf5b8  cmp     [rdx+2FCh], edi
0x1800bf5be  jnz     short loc_1800BF61F
0x1800bf5c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf5c7  mov     ebx, 800F0842h
0x1800bf5cc  mov     [rbp+4Fh+var_70], ebx
0x1800bf5cf  test    rcx, rcx
0x1800bf5d2  jz      short loc_1800BF615
0x1800bf5d4  mov     edi, 3
0x1800bf5d9  lea     r9, aAttemptToChang; "Attempt to change a finalized session"
0x1800bf5e0  mov     r8d, edi
0x1800bf5e3  xor     edx, edx
0x1800bf5e5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800bf5ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf5f1  lea     rax, [rbp+4Fh+var_70]
0x1800bf5f5  mov     [rbp+4Fh+var_78], rax
0x1800bf5f9  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf600  lea     rax, [rbp+4Fh+var_78]
0x1800bf604  mov     r8d, edi
0x1800bf607  mov     dl, 1
0x1800bf609  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf60e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf613  xor     edi, edi
0x1800bf615  mov     edx, 7Bh ; '{'
0x1800bf61a  jmp     loc_1800BF6AA
0x1800bf61f  xor     r9d, r9d; bool
0x1800bf622  lea     r8, [rbp+4Fh+var_70]; enum CbsState *
0x1800bf626  mov     rcx, rsi; this
0x1800bf629  call    ?GetCurrentState@CCbsCapability@@QEAAJPEAVCCbsSession@@PEAW4CbsState@@_N@Z; CCbsCapability::GetCurrentState(CCbsSession *,CbsState *,bool)
0x1800bf62e  mov     ebx, eax
0x1800bf630  test    eax, eax
0x1800bf632  jns     loc_1800BF6E8
0x1800bf638  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf63f  mov     [rbp+4Fh+var_70], eax
0x1800bf642  jz      short loc_1800BF6A5
0x1800bf644  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bf64b  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bf650  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf657  lea     r9, aFailedToGetCur_14; "Failed to get current state for package"...
0x1800bf65e  mov     [rbp+4Fh+var_78], rax
0x1800bf662  mov     edi, 3
0x1800bf667  lea     rax, [rbp+4Fh+var_78]
0x1800bf66b  mov     r8d, edi
0x1800bf66e  xor     edx, edx
0x1800bf670  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf675  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800bf67a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf681  lea     rax, [rbp+4Fh+var_70]
0x1800bf685  mov     [rbp+4Fh+var_68], rax
0x1800bf689  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf690  lea     rax, [rbp+4Fh+var_68]
0x1800bf694  mov     r8d, edi
0x1800bf697  mov     dl, 1
0x1800bf699  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800bf69e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf6a3  xor     edi, edi
0x1800bf6a5  mov     edx, 81h; void *
0x1800bf6aa  mov     rcx, [rbp+57h]; this
0x1800bf6ae  lea     r8, aOnecoreBaseCbs_36; "onecore\\base\\cbs\\core\\cbscapability"...
0x1800bf6b5  mov     r9d, ebx; char *
0x1800bf6b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf6bd  lea     rcx, [rbp+4Fh+var_80]
0x1800bf6c1  call    ?Close@?$AutoComPtr@VCCbsDriverDeployment@@@Windows@@QEAAXXZ; Windows::AutoComPtr<CCbsDriverDeployment>::Close(void)
0x1800bf6c6  mov     rcx, [rbp+4Fh+pv]; pv
0x1800bf6ca  test    rcx, rcx
0x1800bf6cd  jz      loc_1800BFFFE
0x1800bf6d3  call    cs:__imp_CoTaskMemFree
0x1800bf6da  nop     dword ptr [rax+rax+00h]
0x1800bf6df  mov     [rbp+4Fh+pv], rdi
0x1800bf6e3  jmp     loc_1800BFFFE
0x1800bf6e8  mov     rcx, r14; this
0x1800bf6eb  call    ?IsImageReadOnly@CCbsSession@@QEAA_NXZ; CCbsSession::IsImageReadOnly(void)
0x1800bf6f0  mov     r8d, [rbp+4Fh+var_70]
0x1800bf6f4  test    al, al
0x1800bf6f6  jz      short loc_1800BF769
0x1800bf6f8  cmp     r8d, r15d
0x1800bf6fb  jz      short loc_1800BF769
0x1800bf6fd  cmp     cs:?vbInTestMode@@3HA, edi; int vbInTestMode
0x1800bf703  jnz     short loc_1800BF70A
0x1800bf705  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bf70a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf711  mov     ebx, 800F0843h
0x1800bf716  mov     [rbp+4Fh+var_70], ebx
0x1800bf719  test    rcx, rcx
0x1800bf71c  jz      short loc_1800BF75F
0x1800bf71e  mov     edi, 3
0x1800bf723  lea     r9, aNoWriteOperati_3; "No write operations (add/remove capabil"...
0x1800bf72a  mov     r8d, edi
0x1800bf72d  xor     edx, edx
0x1800bf72f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800bf734  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf73b  lea     rax, [rbp+4Fh+var_70]
0x1800bf73f  mov     [rbp+4Fh+var_78], rax
0x1800bf743  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf74a  lea     rax, [rbp+4Fh+var_78]
0x1800bf74e  mov     r8d, edi
0x1800bf751  mov     dl, 1
0x1800bf753  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf758  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf75d  xor     edi, edi
0x1800bf75f  mov     edx, 89h
0x1800bf764  jmp     loc_1800BF6AA
0x1800bf769  mov     rcx, rsi; this
0x1800bf76c  call    ?GetInternalPackage@CCbsCapability@@QEBAPEAVCCbsPackage@@XZ; CCbsCapability::GetInternalPackage(void)
0x1800bf771  test    rax, rax
0x1800bf774  jnz     short loc_1800BF7F2
0x1800bf776  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf77d  mov     ebx, 800F0805h
0x1800bf782  mov     [rbp+4Fh+var_70], ebx
0x1800bf785  jz      short loc_1800BF7E8
0x1800bf787  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bf78e  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bf793  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf79a  lea     r9, aRemovedCapabil; "Removed capability cannot be used to ma"...
0x1800bf7a1  mov     [rbp+4Fh+var_78], rax
0x1800bf7a5  mov     edi, 3
0x1800bf7aa  lea     rax, [rbp+4Fh+var_78]
0x1800bf7ae  mov     r8d, edi
0x1800bf7b1  xor     edx, edx
0x1800bf7b3  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf7b8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800bf7bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf7c4  lea     rax, [rbp+4Fh+var_70]
0x1800bf7c8  mov     [rbp+4Fh+var_68], rax
0x1800bf7cc  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf7d3  lea     rax, [rbp+4Fh+var_68]
0x1800bf7d7  mov     r8d, edi
0x1800bf7da  mov     dl, 1
0x1800bf7dc  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf7e1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf7e6  xor     edi, edi
0x1800bf7e8  mov     edx, 8Dh
0x1800bf7ed  jmp     loc_1800BF6AA
0x1800bf7f2  cmp     [rsi+20h], rdi
0x1800bf7f6  jnz     loc_1800BF902
0x1800bf7fc  mov     rbx, cs:?vpCapabilityManager@@3PEAVCCbsCapabilityManager@@EA; CCbsCapabilityManager * vpCapabilityManager
0x1800bf803  lea     rcx, [rbp+4Fh+var_78]
0x1800bf807  mov     [rbp+4Fh+var_78], rdi
0x1800bf80b  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800bf810  mov     r8, [rsi+88h]; struct CCbsIdentity *
0x1800bf817  mov     r9, rax; struct CCbsCapability **
0x1800bf81a  mov     rdx, r14; struct CCbsSession *
0x1800bf81d  mov     rcx, rbx; this
0x1800bf820  call    ?ResolveCapability@CCbsCapabilityManager@@QEAAJPEAVCCbsSession@@PEBVCCbsIdentity@@PEAPEAVCCbsCapability@@@Z; CCbsCapabilityManager::ResolveCapability(CCbsSession *,CCbsIdentity const *,CCbsCapability * *)
0x1800bf825  mov     ebx, eax
0x1800bf827  test    eax, eax
0x1800bf829  jns     loc_1800BF8C2
0x1800bf82f  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf836  mov     [rbp+4Fh+var_70], eax
0x1800bf839  jz      short loc_1800BF89C
0x1800bf83b  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bf842  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bf847  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf84e  lea     r9, aFailedToResolv_2; "Failed to resolve the capability in the"...
0x1800bf855  mov     [rbp+4Fh+var_68], rax
0x1800bf859  mov     edi, 3
0x1800bf85e  lea     rax, [rbp+4Fh+var_68]
0x1800bf862  mov     r8d, edi
0x1800bf865  xor     edx, edx
0x1800bf867  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf86c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800bf871  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf878  lea     rax, [rbp+4Fh+var_70]
0x1800bf87c  mov     qword ptr [rbp+4Fh+var_88], rax
0x1800bf880  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf887  lea     rax, [rbp+4Fh+var_88]
0x1800bf88b  mov     r8d, edi
0x1800bf88e  mov     dl, 1
0x1800bf890  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800bf895  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf89a  xor     edi, edi
0x1800bf89c  mov     rcx, [rbp+57h]; this
0x1800bf8a0  lea     r8, aOnecoreBaseCbs_36; "onecore\\base\\cbs\\core\\cbscapability"...
0x1800bf8a7  mov     r9d, ebx; char *
0x1800bf8aa  mov     edx, 97h; void *
0x1800bf8af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf8b4  lea     rcx, [rbp+4Fh+var_78]
0x1800bf8b8  call    ?Close@?$AutoComPtr@VCCbsDriverDeployment@@@Windows@@QEAAXXZ; Windows::AutoComPtr<CCbsDriverDeployment>::Close(void)
0x1800bf8bd  jmp     loc_1800BF6BD
0x1800bf8c2  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bf8c9  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bf8ce  lea     r8, [rbp+4Fh+var_88]
0x1800bf8d2  mov     qword ptr [rbp+4Fh+var_88], rax
0x1800bf8d6  lea     rdx, aRedirectingCap; "Redirecting Capability InitiateChange u"...
0x1800bf8dd  mov     ecx, 1
0x1800bf8e2  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800bf8e7  mov     rcx, [rbp+4Fh+var_78]
0x1800bf8eb  mov     r9d, r15d
0x1800bf8ee  mov     r8d, r13d
0x1800bf8f1  mov     qword ptr [rsp+0D0h+var_B0], r12
0x1800bf8f6  mov     rdx, r14
0x1800bf8f9  call    ?InitiateChanges@CCbsCapability@@QEAAJPEAVCCbsSession@@IW4CbsState@@PEAUIUnknown@@@Z; CCbsCapability::InitiateChanges(CCbsSession *,uint,CbsState,IUnknown *)
0x1800bf8fe  mov     ebx, eax
0x1800bf900  jmp     short loc_1800BF8B4
0x1800bf902  mov     r9d, r15d
0x1800bf905  mov     rdx, r14
0x1800bf908  call    ?CheckForUninstall@CCbsCapability@@AEAAJPEAVCCbsSession@@W4CbsState@@1@Z; CCbsCapability::CheckForUninstall(CCbsSession *,CbsState,CbsState)
0x1800bf90d  mov     ebx, eax
0x1800bf90f  test    eax, eax
0x1800bf911  jns     short loc_1800BF98A
0x1800bf913  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf91a  mov     [rbp+4Fh+var_70], eax
0x1800bf91d  jz      short loc_1800BF980
0x1800bf91f  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bf926  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bf92b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf932  lea     r9, aFailedToCheckU; "Failed to check uninstall of FOD: {}"
0x1800bf939  mov     qword ptr [rbp+4Fh+var_88], rax
0x1800bf93d  mov     edi, 3
0x1800bf942  lea     rax, [rbp+4Fh+var_88]
0x1800bf946  mov     r8d, edi
0x1800bf949  xor     edx, edx
0x1800bf94b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf950  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800bf955  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf95c  lea     rax, [rbp+4Fh+var_70]
0x1800bf960  mov     [rbp+4Fh+var_78], rax
0x1800bf964  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf96b  lea     rax, [rbp+4Fh+var_78]
0x1800bf96f  mov     r8d, edi
0x1800bf972  mov     dl, 1
0x1800bf974  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf979  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf97e  xor     edi, edi
0x1800bf980  mov     edx, 9Fh
0x1800bf985  jmp     loc_1800BF6AA
0x1800bf98a  lea     rcx, [rbp+4Fh+pv]
0x1800bf98e  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800bf993  mov     r9d, 2Fh ; '/'
0x1800bf999  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf99e  xor     r8d, r8d
0x1800bf9a1  mov     rdx, r14
0x1800bf9a4  mov     rcx, rsi
0x1800bf9a7  call    ?GetProperty@CCbsCapability@@QEAAJPEAVCCbsSession@@PEAXW4_CbsPackageProperty@@PEAPEA_W@Z; CCbsCapability::GetProperty(CCbsSession *,void *,_CbsPackageProperty,wchar_t * *)
0x1800bf9ac  mov     ebx, eax
0x1800bf9ae  test    eax, eax
0x1800bf9b0  jns     short loc_1800BFA0C
0x1800bf9b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf9b9  mov     [rbp+4Fh+var_70], eax
0x1800bf9bc  test    rcx, rcx
0x1800bf9bf  jz      short loc_1800BFA02
0x1800bf9c1  mov     edi, 3
0x1800bf9c6  lea     r9, aFailedToGetPac_17; "Failed to get package property CbsPacka"...
0x1800bf9cd  mov     r8d, edi
0x1800bf9d0  xor     edx, edx
0x1800bf9d2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800bf9d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf9de  lea     rax, [rbp+4Fh+var_70]
0x1800bf9e2  mov     qword ptr [rbp+4Fh+var_88], rax
0x1800bf9e6  lea     r9, asc_1802EE7AC; ": {}"
0x1800bf9ed  lea     rax, [rbp+4Fh+var_88]
0x1800bf9f1  mov     r8d, edi
0x1800bf9f4  mov     dl, 1
0x1800bf9f6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800bf9fb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bfa00  xor     edi, edi
0x1800bfa02  mov     edx, 0A6h
0x1800bfa07  jmp     loc_1800BF6AA
0x1800bfa0c  mov     rdx, [rbp+4Fh+pv]
0x1800bfa10  lea     rcx, a1; "1"
0x1800bfa17  mov     r8d, 1
0x1800bfa1d  call    StringsAreEqual
0x1800bfa22  test    al, al
0x1800bfa24  jz      loc_1800BFAAC
0x1800bfa2a  cmp     r15d, 70h ; 'p'
0x1800bfa2e  jl      short loc_1800BFAAC
0x1800bfa30  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bfa37  mov     ebx, 800F0806h
0x1800bfa3c  mov     [rbp+4Fh+var_70], ebx
0x1800bfa3f  jz      short loc_1800BFAA2
0x1800bfa41  mov     rcx, [rsi+88h]; struct CCbsIdentity *
0x1800bfa48  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1800bfa4d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
