# ServiceMain

- ea: `0x180011720`
- end: `0x180011f13`
- name: `ServiceMain`
- size: `2035`
- prototype: `void()`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002bf0`
- `0x180002c40`
- `0x180006ab8`
- `0x180006c68`
- `0x1800071b0`
- `0x18000c620`
- `0x18000c880`
- `0x18000fc68`
- `0x18000fc88`
- `0x180010a34`
- `0x180010b74`
- `0x180010c14`
- `0x1800110f8`
- `0x180011720`
- `0x1800152d0`
- `0x18002867c`
- `0x18002fd04`
- `0x18002ff7c`
- `0x180031400`
- `0x1800c0f44`
- `0x1800c3e78`
- `0x1800ca1ac`
- `0x1800d1010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011dc8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011dc8`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180011d9b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180011d9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011862`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011862`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011d59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117f5`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001177f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001177f`

## string_xrefs

- `0x180011a7d`: `ServiceMain`
- `0x180011ba0`: `ServiceMain`
- `0x180011e2b`: `ServiceMain`
- `0x180011e68`: `ServiceMain`
- `0x180011ea9`: `ServiceMain`
- `0x180011ee7`: `ServiceMain`
- `0x180011e47`: `onecore\base\appcompat\inventory\service\dll\main.cpp`
- `0x180011e84`: `onecore\base\appcompat\inventory\service\dll\main.cpp`
- `0x180011ec6`: `onecore\base\appcompat\inventory\service\dll\main.cpp`
- `0x180011f03`: `onecore\base\appcompat\inventory\service\dll\main.cpp`
- `0x180011a70`: `InstallMon feature is %s`

## pseudocode

```c
void ServiceMain()
{
  DWORD LastError; // eax
  DWORD v1; // edi
  __int64 v2; // rdx
  __int64 v3; // r8
  HANDLE v4; // r8
  DWORD v5; // eax
  DWORD v6; // edi
  __int64 (__fastcall *v7)(void *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), __int64, int); // rax
  int v8; // eax
  unsigned int v9; // edi
  HKEY v10; // rdx
  HKEY v11; // r8
  struct Windows::Compat::Inventory::Service::InventoryScheduler *InventoryScheduler; // rax
  __int64 v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  Windows::Compat::Inventory::Service::WinRtHost *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  Windows::Compat::Inventory::Service::PnpListener *v19; // rax
  Windows::Compat::Inventory::Service::TraceController *v20; // rsi
  Windows::Compat::Inventory::Service::TraceController *v21; // rcx
  Windows::Compat::Inventory::Service::TraceController *v22; // rdi
  __int64 v23; // rcx
  Windows::Compat::Inventory::Service::PnpListener *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rcx
  char IsEnabled; // al
  const char *v30; // r14
  const char *v31; // rcx
  Windows::Compat::Inventory::Service::TraceController *v32; // rdi
  Windows::Compat::Inventory::Service::TraceController *v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // r8
  void (__fastcall ***v36)(_QWORD, __int64); // rcx
  Windows::Compat::Inventory::Service::TraceController *v37; // rsi
  __int64 v38; // rcx
  Windows::Compat::Inventory::Service::TraceController *v39; // rdi
  __int64 v40; // rdx
  __int64 v41; // r8
  Windows::Compat::Inventory::Service::TraceController *v42; // rsi
  __int64 v43; // rcx
  Windows::Compat::Inventory::Service::TraceController *v44; // rsi
  struct Windows::Compat::Inventory::Service::Tracer *v45; // rdi
  __int64 v46; // rcx
  Windows::Compat::Inventory::Service::TraceController *v47; // rdi
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rcx
  std::thread *v51; // rdi
  __int64 v52; // rax
  unsigned int v53; // [rsp+20h] [rbp-1D8h]
  unsigned int v54; // [rsp+20h] [rbp-1D8h]
  unsigned int v55; // [rsp+20h] [rbp-1D8h]
  unsigned int v56; // [rsp+20h] [rbp-1D8h]
  Windows::Compat::Inventory::Service::TraceController *v57; // [rsp+48h] [rbp-1B0h] BYREF
  void (__fastcall ***v58)(_QWORD, __int64); // [rsp+50h] [rbp-1A8h] BYREF
  Windows::Compat::Inventory::Service::TraceController *v59; // [rsp+58h] [rbp-1A0h] BYREF
  DWORD v60; // [rsp+60h] [rbp-198h]
  RTL_SRWLOCK *v61; // [rsp+68h] [rbp-190h]
  std::thread *v62; // [rsp+70h] [rbp-188h]
  _BYTE v63[136]; // [rsp+90h] [rbp-168h] BYREF
  signed __int64 v64; // [rsp+118h] [rbp-E0h] BYREF
  char v65[144]; // [rsp+120h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v60 = 0;
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"InventorySvc", InvSvcServiceHandler, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError )
    {
      AslLogCallPrintf(1, "ServiceMain", 353, "failed [%d]", LastError);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\dll\\main.cpp",
        (const char *)v1,
        v53);
    }
  }
  InvSvcUpdateServiceStatus(2u);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v63);
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v63,
    _InterlockedExchangeAdd64(&v64, 0),
    v65);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &hEvent,
    v2,
    v3,
    0);
  v4 = hEvent;
  if ( !hEvent )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 )
    {
      AslLogCallPrintf(1, "ServiceMain", 369, "failed [%d]", v5);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\dll\\main.cpp",
        (const char *)v6,
        v54);
    }
    v4 = hEvent;
  }
  v7 = *(__int64 (__fastcall **)(void *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), __int64, int))(qword_1800FEFB0 + 208);
  if ( !v7 )
  {
    AslLogCallPrintf(1, "ServiceMain", 374, "failed [%d]", 1);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\dll\\main.cpp",
      (const char *)1,
      v55);
  }
  v8 = v7(&g_serviceInfo, L"InventorySvc", v4, InvSvcHandleServiceShutdown, 1234, 8);
  v9 = v8;
  if ( v8 )
  {
    AslLogCallPrintf(1, "ServiceMain", 383, "failed [%d]", v8);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\dll\\main.cpp",
      (const char *)v9,
      v56);
  }
  AcquireSRWLockExclusive(&g_tenantVectorLock);
  v61 = &g_tenantVectorLock;
  InventoryScheduler = Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler(v65, v10, v11);
  v59 = 0;
  v58 = (void (__fastcall ***)(_QWORD, __int64))InventoryScheduler;
  if ( qword_1800FEF70 == qword_1800FEF78 )
  {
    std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(
      v13,
      qword_1800FEF70,
      &v58);
    v14 = v58;
  }
  else
  {
    v14 = 0;
    *(_QWORD *)qword_1800FEF70 = InventoryScheduler;
    qword_1800FEF70 += 8;
  }
  if ( v14 )
    (**v14)(v14, 1);
  v15 = (Windows::Compat::Inventory::Service::WinRtHost *)operator new(0x28u);
  v16 = Windows::Compat::Inventory::Service::WinRtHost::WinRtHost(v15);
  v57 = 0;
  v58 = (void (__fastcall ***)(_QWORD, __int64))v16;
  if ( qword_1800FEF70 == qword_1800FEF78 )
  {
    std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(
      v17,
      qword_1800FEF70,
      &v58);
    v18 = v58;
  }
  else
  {
    v18 = 0;
    *(_QWORD *)qword_1800FEF70 = v16;
    qword_1800FEF70 += 8;
  }
  if ( v18 )
    (**v18)(v18, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl'::`2'::impl) )
  {
    v19 = (Windows::Compat::Inventory::Service::PnpListener *)operator new(0x78u);
    v20 = (Windows::Compat::Inventory::Service::TraceController *)Windows::Compat::Inventory::Service::PnpListener::PnpListener(v19);
    v59 = v20;
    v21 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x48u);
    v22 = (Windows::Compat::Inventory::Service::TraceController *)Windows::Compat::Inventory::Service::TraceController::TraceController(v21);
    v58 = (void (__fastcall ***)(_QWORD, __int64))v22;
    v59 = 0;
    Windows::Compat::Inventory::Service::TraceController::AddTracer(v22, v20);
    Windows::Compat::Inventory::Service::TraceController::Start(v22);
    v58 = 0;
    v57 = v22;
    if ( qword_1800FEF70 == qword_1800FEF78 )
    {
      std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(
        v23,
        qword_1800FEF70,
        &v57);
    }
    else
    {
      *(_QWORD *)qword_1800FEF70 = v22;
      qword_1800FEF70 += 8;
    }
  }
  else
  {
    v24 = (Windows::Compat::Inventory::Service::PnpListener *)operator new(0x78u);
    v25 = Windows::Compat::Inventory::Service::PnpListener::PnpListener(v24);
    v57 = 0;
    v26 = v25 + 24;
    v27 = (v25 + 24) & -(__int64)(v25 != 0);
    v58 = (void (__fastcall ***)(_QWORD, __int64))v27;
    if ( qword_1800FEF70 == qword_1800FEF78 )
    {
      std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(
        v26,
        qword_1800FEF70,
        &v58);
      v28 = v58;
    }
    else
    {
      v28 = 0;
      *(_QWORD *)qword_1800FEF70 = v27;
      qword_1800FEF70 += 8;
    }
    if ( v28 )
      (**v28)(v28, 1);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl);
  v30 = "enabled";
  v31 = "enabled";
  if ( !IsEnabled )
    v31 = "disabled";
  AslLogCallPrintf(3, "ServiceMain", 405, "InstallMon feature is %s", v31);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    v32 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x20u);
    v57 = v32;
    *((_QWORD *)v32 + 2) = 0;
    *(_QWORD *)v32 = &Windows::Compat::Inventory::InstallMon::InstallMonTracer::`vftable';
    *((_QWORD *)v32 + 3) = 0;
    v33 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x10u);
    v59 = v33;
    *(_QWORD *)v33 = &Windows::Compat::Inventory::InstallMon::InstallMonHost::`vftable';
    *((_QWORD *)v33 + 1) = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (char *)v33 + 8,
      v34,
      v35,
      0);
    v36 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v32 + 3);
    *((_QWORD *)v32 + 3) = v33;
    if ( v36 )
      (**v36)(v36, 1);
    v57 = v32;
    v59 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x48u);
    v37 = (Windows::Compat::Inventory::Service::TraceController *)Windows::Compat::Inventory::Service::TraceController::TraceController(v59);
    v59 = v37;
    v57 = 0;
    Windows::Compat::Inventory::Service::TraceController::AddTracer(v37, v32);
    Windows::Compat::Inventory::Service::TraceController::Start(v37);
    v59 = 0;
    v58 = (void (__fastcall ***)(_QWORD, __int64))v37;
    if ( qword_1800FEF70 == qword_1800FEF78 )
    {
      std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(
        v38,
        qword_1800FEF70,
        &v58);
    }
    else
    {
      *(_QWORD *)qword_1800FEF70 = v37;
      qword_1800FEF70 += 8;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Aidd_InventorySvc>::GetImpl'::`2'::impl) )
    v30 = "disabled";
  AslLogCallPrintf(3, "ServiceMain", 417, "Aidd feature is %s", v30);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Aidd_InventorySvc>::GetImpl'::`2'::impl) )
  {
    v39 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x40u);
    v57 = v39;
    *((_QWORD *)v39 + 2) = 0;
    *(_QWORD *)v39 = &Windows::Compat::Inventory::Aidd::AiddTracer::`vftable';
    *((_QWORD *)v39 + 3) = 0;
    *((_QWORD *)v39 + 4) = 0;
    *((_QWORD *)v39 + 5) = 0;
    *((_QWORD *)v39 + 6) = 0;
    *((_QWORD *)v39 + 7) = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (char *)v39 + 56,
      v40,
      v41,
      0);
    v57 = v39;
    v59 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x48u);
    v42 = (Windows::Compat::Inventory::Service::TraceController *)Windows::Compat::Inventory::Service::TraceController::TraceController(v59);
    v59 = v42;
    v57 = 0;
    Windows::Compat::Inventory::Service::TraceController::AddTracer(v42, v39);
    Windows::Compat::Inventory::Service::TraceController::Start(v42);
    v59 = 0;
    v58 = (void (__fastcall ***)(_QWORD, __int64))v42;
    if ( qword_1800FEF70 == qword_1800FEF78 )
    {
      std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(
        v43,
        qword_1800FEF70,
        &v58);
    }
    else
    {
      *(_QWORD *)qword_1800FEF70 = v42;
      qword_1800FEF70 += 8;
    }
  }
  v57 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x48u);
  v44 = (Windows::Compat::Inventory::Service::TraceController *)Windows::Compat::Inventory::Service::TraceController::TraceController(v57);
  v57 = v44;
  v45 = (struct Windows::Compat::Inventory::Service::Tracer *)operator new(0x20u);
  *((_QWORD *)v45 + 2) = 0;
  *(_QWORD *)v45 = &Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::`vftable';
  *((_QWORD *)v45 + 3) = 0;
  Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::WriteStateToRegistry(v46, 3);
  v58 = 0;
  Windows::Compat::Inventory::Service::TraceController::AddTracer(v44, v45);
  v47 = (Windows::Compat::Inventory::Service::TraceController *)operator new(0x40u);
  v59 = v47;
  *((_QWORD *)v47 + 2) = 0;
  *(_QWORD *)v47 = &Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::`vftable';
  *((_QWORD *)v47 + 3) = 0;
  *((_QWORD *)v47 + 4) = 0;
  *((_QWORD *)v47 + 5) = 0;
  *((_QWORD *)v47 + 6) = 0;
  *((_QWORD *)v47 + 7) = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)v47 + 56,
    v48,
    v49,
    0);
  v62 = 0;
  Windows::Compat::Inventory::Service::TraceController::AddTracer(v44, v47);
  Windows::Compat::Inventory::Service::TraceController::Start(v44);
  v57 = 0;
  v59 = v44;
  if ( qword_1800FEF70 == qword_1800FEF78 )
  {
    std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(
      v50,
      qword_1800FEF70,
      &v59);
  }
  else
  {
    *(_QWORD *)qword_1800FEF70 = v44;
    qword_1800FEF70 += 8;
  }
  ReleaseSRWLockExclusive(&g_tenantVectorLock);
  v51 = (std::thread *)operator new(0x10u);
  v62 = v51;
  v61 = (RTL_SRWLOCK *)operator new(1u);
  v52 = _o__beginthreadex(
          0,
          0,
          std::thread::_Invoke_std::tuple__lambda_23c5cb8d789b2438fb5eac713d597173____0_,
          v61,
          0,
          (char *)v51 + 8);
  *(_QWORD *)v51 = v52;
  if ( v52 )
  {
    g_workDoneMonitorThread = v51;
    InvSvcUpdateServiceStatus(4u);
  }
  else
  {
    *((_DWORD *)v51 + 2) = 0;
    std::_Throw_Cpp_error(6);
    InvSvcHandleServiceShutdown((void *)0x162E, 1u);
    ServiceStatus.dwWin32ExitCode = v60;
    InvSvcUpdateServiceStatus(1u);
  }
}

```

## disassembly

```asm
0x180011720  push    rbx
0x180011722  push    rsi
0x180011723  push    rdi
0x180011724  push    r12
0x180011726  push    r14
0x180011728  push    r15
0x18001172a  sub     rsp, 1C8h
0x180011731  mov     rax, cs:__security_cookie
0x180011738  xor     rax, rsp
0x18001173b  mov     [rsp+1F8h+var_48], rax
0x180011743  xor     ebx, ebx
0x180011745  mov     [rsp+1F8h+var_198], ebx
0x180011749  mov     [rsp+1F8h+var_1B8], bl
0x18001174d  xorps   xmm0, xmm0
0x180011750  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x180011757  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x18001175e  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180011768  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x18001176e  xor     r8d, r8d; lpContext
0x180011771  lea     rdx, ?InvSvcServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180011778  lea     rcx, ServiceName; "InventorySvc"
0x18001177f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011785  mov     cs:hServiceStatus, rax
0x18001178c  test    rax, rax
0x18001178f  jnz     short loc_1800117A1
0x180011791  call    cs:__imp_GetLastError
0x180011797  mov     edi, eax
0x180011799  test    eax, eax
0x18001179b  jnz     loc_180011E18
0x1800117a1  mov     ecx, 2; unsigned int
0x1800117a6  call    ?InvSvcUpdateServiceStatus@@YAXK@Z; InvSvcUpdateServiceStatus(ulong)
0x1800117ab  lea     rcx, [rsp+1F8h+var_168]; this
0x1800117b3  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800117b8  mov     rdx, rbx
0x1800117bb  lock xadd [rsp+1F8h+var_E0], rdx; unsigned __int64
0x1800117c5  lea     r8, [rsp+1F8h+var_D8]; char *
0x1800117cd  lea     rcx, [rsp+1F8h+var_168]; this
0x1800117d5  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800117da  xor     r9d, r9d
0x1800117dd  lea     rcx, hEvent
0x1800117e4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800117e9  mov     r8, cs:hEvent
0x1800117f0  test    r8, r8
0x1800117f3  jnz     short loc_18001180C
0x1800117f5  call    cs:__imp_GetLastError
0x1800117fb  mov     edi, eax
0x1800117fd  test    eax, eax
0x1800117ff  jnz     loc_180011E55
0x180011805  mov     r8, cs:hEvent
0x18001180c  mov     rax, cs:qword_1800FEFB0
0x180011813  mov     rax, [rax+0D0h]
0x18001181a  test    rax, rax
0x18001181d  jz      loc_180011E92
0x180011823  mov     dword ptr [rsp+1F8h+var_1D0], 8
0x18001182b  mov     qword ptr [rsp+1F8h+var_1D8], 4D2h
0x180011834  lea     r9, ?InvSvcHandleServiceShutdown@@YAXPEAXE@Z; InvSvcHandleServiceShutdown(void *,uchar)
0x18001183b  lea     rdx, ServiceName; "InventorySvc"
0x180011842  lea     rcx, ?g_serviceInfo@@3U_unnamed_type_g_serviceInfo_@@A; _unnamed_type_g_serviceInfo_ g_serviceInfo
0x180011849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001184e  mov     edi, eax
0x180011850  test    eax, eax
0x180011852  jnz     loc_180011ED4
0x180011858  lea     rdi, ?g_tenantVectorLock@@3Vsrwlock@wil@@A; wil::srwlock g_tenantVectorLock
0x18001185f  mov     rcx, rdi; SRWLock
0x180011862  call    cs:__imp_AcquireSRWLockExclusive
0x180011868  mov     [rsp+1F8h+var_190], rdi
0x18001186d  lea     rcx, [rsp+1F8h+var_D8]; char *
0x180011875  call    ?MakeInventoryScheduler@InventoryScheduler@Service@Inventory@Compat@Windows@@SAPEAV12345@PEBDPEAUHKEY__@@1@Z; Windows::Compat::Inventory::Service::InventoryScheduler::MakeInventoryScheduler(char const *,HKEY__ *,HKEY__ *)
0x18001187a  nop
0x18001187b  mov     [rsp+1F8h+var_1A0], rbx
0x180011880  mov     [rsp+1F8h+var_1A8], rax
0x180011885  mov     rdx, cs:qword_1800FEF70
0x18001188c  cmp     rdx, cs:qword_1800FEF78
0x180011893  jz      short loc_1800118A5
0x180011895  mov     rcx, rbx
0x180011898  mov     [rdx], rax
0x18001189b  add     cs:qword_1800FEF70, 8
0x1800118a3  jmp     short loc_1800118B4
0x1800118a5  lea     r8, [rsp+1F8h+var_1A8]
0x1800118aa  call    ??$_Emplace_reallocate@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> * const,std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> &&)
0x1800118af  mov     rcx, [rsp+1F8h+var_1A8]
0x1800118b4  test    rcx, rcx
0x1800118b7  jz      short loc_1800118CA
0x1800118b9  mov     rax, [rcx]
0x1800118bc  mov     edx, 1
0x1800118c1  mov     rax, [rax]
0x1800118c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c9  nop
0x1800118ca  mov     ecx, 28h ; '('; Size
0x1800118cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800118d4  mov     [rsp+1F8h+var_1B0], rax
0x1800118d9  mov     rcx, rax; this
0x1800118dc  call    ??0WinRtHost@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::WinRtHost::WinRtHost(void)
0x1800118e1  nop
0x1800118e2  mov     [rsp+1F8h+var_1B0], rbx
0x1800118e7  mov     [rsp+1F8h+var_1A8], rax
0x1800118ec  mov     rdx, cs:qword_1800FEF70
0x1800118f3  cmp     rdx, cs:qword_1800FEF78
0x1800118fa  jz      short loc_18001190C
0x1800118fc  mov     rcx, rbx
0x1800118ff  mov     [rdx], rax
0x180011902  add     cs:qword_1800FEF70, 8
0x18001190a  jmp     short loc_18001191B
0x18001190c  lea     r8, [rsp+1F8h+var_1A8]
0x180011911  call    ??$_Emplace_reallocate@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> * const,std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> &&)
0x180011916  mov     rcx, [rsp+1F8h+var_1A8]
0x18001191b  test    rcx, rcx
0x18001191e  jz      short loc_180011931
0x180011920  mov     rax, [rcx]
0x180011923  mov     edx, 1
0x180011928  mov     rax, [rax]
0x18001192b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011930  nop
0x180011931  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix> `wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl(void)'::`2'::impl
0x180011938  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(void)
0x18001193d  mov     ecx, 78h ; 'x'; Size
0x180011942  test    al, al
0x180011944  jz      loc_1800119D3
0x18001194a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001194f  mov     [rsp+1F8h+var_1B0], rax
0x180011954  mov     rcx, rax; this
0x180011957  call    ??0PnpListener@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::PnpListener::PnpListener(void)
0x18001195c  mov     rsi, rax
0x18001195f  mov     [rsp+1F8h+var_1A0], rax
0x180011964  mov     r15d, 48h ; 'H'
0x18001196a  mov     ecx, r15d; Size
0x18001196d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011972  mov     [rsp+1F8h+var_1B0], rax
0x180011977  mov     rcx, rax; this
0x18001197a  call    ??0TraceController@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::TraceController::TraceController(void)
0x18001197f  mov     rdi, rax
0x180011982  mov     [rsp+1F8h+var_1A8], rax
0x180011987  mov     [rsp+1F8h+var_1A0], rbx
0x18001198c  mov     rdx, rsi; struct Windows::Compat::Inventory::Service::Tracer *
0x18001198f  mov     rcx, rax; this
0x180011992  call    ?AddTracer@TraceController@Service@Inventory@Compat@Windows@@QEAAXPEAVTracer@2345@@Z; Windows::Compat::Inventory::Service::TraceController::AddTracer(Windows::Compat::Inventory::Service::Tracer *)
0x180011997  mov     rcx, rdi; this
0x18001199a  call    ?Start@TraceController@Service@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::Service::TraceController::Start(void)
0x18001199f  mov     [rsp+1F8h+var_1A8], rbx
0x1800119a4  mov     [rsp+1F8h+var_1B0], rdi
0x1800119a9  mov     rdx, cs:qword_1800FEF70
0x1800119b0  cmp     rdx, cs:qword_1800FEF78
0x1800119b7  jz      short loc_1800119C6
0x1800119b9  mov     [rdx], rdi
0x1800119bc  add     cs:qword_1800FEF70, 8
0x1800119c4  jmp     short loc_1800119D1
0x1800119c6  lea     r8, [rsp+1F8h+var_1B0]
0x1800119cb  call    ??$_Emplace_reallocate@PEAVTraceController@Service@Inventory@Compat@Windows@@@?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@1@QEAV21@$$QEAPEAVTraceController@Service@Inventory@Compat@Windows@@@Z; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> * const,Windows::Compat::Inventory::Service::TraceController * &&)
0x1800119d0  nop
0x1800119d1  jmp     short loc_180011A48
0x1800119d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119d8  mov     [rsp+1F8h+var_1B0], rax
0x1800119dd  mov     rcx, rax; this
0x1800119e0  call    ??0PnpListener@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::PnpListener::PnpListener(void)
0x1800119e5  nop
0x1800119e6  mov     [rsp+1F8h+var_1B0], rbx
0x1800119eb  lea     rcx, [rax+18h]
0x1800119ef  neg     rax
0x1800119f2  sbb     rax, rax
0x1800119f5  and     rax, rcx
0x1800119f8  mov     [rsp+1F8h+var_1A8], rax
0x1800119fd  mov     rdx, cs:qword_1800FEF70
0x180011a04  cmp     rdx, cs:qword_1800FEF78
0x180011a0b  jz      short loc_180011A1D
0x180011a0d  mov     rcx, rbx
0x180011a10  mov     [rdx], rax
0x180011a13  add     cs:qword_1800FEF70, 8
0x180011a1b  jmp     short loc_180011A2C
0x180011a1d  lea     r8, [rsp+1F8h+var_1A8]
0x180011a22  call    ??$_Emplace_reallocate@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> * const,std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> &&)
0x180011a27  mov     rcx, [rsp+1F8h+var_1A8]
0x180011a2c  test    rcx, rcx
0x180011a2f  jz      short loc_180011A42
0x180011a31  mov     rax, [rcx]
0x180011a34  mov     edx, 1
0x180011a39  mov     rax, [rax]
0x180011a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a41  nop
0x180011a42  mov     r15d, 48h ; 'H'
0x180011a48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x180011a4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x180011a54  lea     r14, aEnabled; "enabled"
0x180011a5b  mov     rcx, r14
0x180011a5e  lea     r12, aDisabled; "disabled"
0x180011a65  test    al, al
0x180011a67  cmovz   rcx, r12
0x180011a6b  mov     qword ptr [rsp+1F8h+var_1D8], rcx
0x180011a70  lea     r9, aInstallmonFeat; "InstallMon feature is %s"
0x180011a77  mov     r8d, 195h
0x180011a7d  lea     rdx, aServicemain_0; "ServiceMain"
0x180011a84  mov     ecx, 3
0x180011a89  call    AslLogCallPrintf
0x180011a8e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x180011a95  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x180011a9a  test    al, al
0x180011a9c  jz      loc_180011B7C
0x180011aa2  mov     ecx, 20h ; ' '; Size
0x180011aa7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011aac  mov     rdi, rax
0x180011aaf  mov     [rsp+1F8h+var_1B0], rax
0x180011ab4  mov     [rax+10h], rbx
0x180011ab8  lea     rax, ??_7InstallMonTracer@InstallMon@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InstallMon::InstallMonTracer::`vftable'
0x180011abf  mov     [rdi], rax
0x180011ac2  mov     [rdi+18h], rbx
0x180011ac6  mov     ecx, 10h; Size
0x180011acb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ad0  mov     rsi, rax
0x180011ad3  mov     [rsp+1F8h+var_1A0], rax
0x180011ad8  lea     rax, ??_7InstallMonHost@InstallMon@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InstallMon::InstallMonHost::`vftable'
0x180011adf  mov     [rsi], rax
0x180011ae2  lea     rcx, [rsi+8]
0x180011ae6  mov     [rcx], rbx
0x180011ae9  xor     r9d, r9d
0x180011aec  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011af1  nop
0x180011af2  mov     rcx, [rdi+18h]
0x180011af6  mov     [rdi+18h], rsi
0x180011afa  test    rcx, rcx
0x180011afd  jz      short loc_180011B10
0x180011aff  mov     rax, [rcx]
0x180011b02  mov     edx, 1
0x180011b07  mov     rax, [rax]
0x180011b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0f  nop
0x180011b10  mov     [rsp+1F8h+var_1B0], rdi
0x180011b15  mov     rcx, r15; Size
0x180011b18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b1d  mov     [rsp+1F8h+var_1A0], rax
0x180011b22  mov     rcx, rax; this
0x180011b25  call    ??0TraceController@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::TraceController::TraceController(void)
0x180011b2a  mov     rsi, rax
0x180011b2d  mov     [rsp+1F8h+var_1A0], rax
0x180011b32  mov     [rsp+1F8h+var_1B0], rbx
0x180011b37  mov     rdx, rdi; struct Windows::Compat::Inventory::Service::Tracer *
0x180011b3a  mov     rcx, rax; this
0x180011b3d  call    ?AddTracer@TraceController@Service@Inventory@Compat@Windows@@QEAAXPEAVTracer@2345@@Z; Windows::Compat::Inventory::Service::TraceController::AddTracer(Windows::Compat::Inventory::Service::Tracer *)
0x180011b42  mov     rcx, rsi; this
0x180011b45  call    ?Start@TraceController@Service@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::Service::TraceController::Start(void)
0x180011b4a  mov     [rsp+1F8h+var_1A0], rbx
0x180011b4f  mov     [rsp+1F8h+var_1A8], rsi
0x180011b54  mov     rdx, cs:qword_1800FEF70
0x180011b5b  cmp     rdx, cs:qword_1800FEF78
0x180011b62  jz      short loc_180011B71
0x180011b64  mov     [rdx], rsi
0x180011b67  add     cs:qword_1800FEF70, 8
0x180011b6f  jmp     short loc_180011B7C
0x180011b71  lea     r8, [rsp+1F8h+var_1A8]
0x180011b76  call    ??$_Emplace_reallocate@PEAVTraceController@Service@Inventory@Compat@Windows@@@?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@1@QEAV21@$$QEAPEAVTraceController@Service@Inventory@Compat@Windows@@@Z; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::_Emplace_reallocate<Windows::Compat::Inventory::Service::TraceController *>(std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant> * const,Windows::Compat::Inventory::Service::TraceController * &&)
0x180011b7b  nop
0x180011b7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc> `wil::Feature<__WilFeatureTraits_Feature_Aidd_InventorySvc>::GetImpl(void)'::`2'::impl
0x180011b83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc>::__private_IsEnabled(void)
0x180011b88  test    al, al
0x180011b8a  cmovz   r14, r12
0x180011b8e  mov     qword ptr [rsp+1F8h+var_1D8], r14
0x180011b93  lea     r9, aAiddFeatureIsS; "Aidd feature is %s"
0x180011b9a  mov     r8d, 1A1h
0x180011ba0  lea     rdx, aServicemain_0; "ServiceMain"
0x180011ba7  mov     ecx, 3
0x180011bac  call    AslLogCallPrintf
0x180011bb1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc> `wil::Feature<__WilFeatureTraits_Feature_Aidd_InventorySvc>::GetImpl(void)'::`2'::impl
0x180011bb8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Aidd_InventorySvc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Aidd_InventorySvc>::__private_IsEnabled(void)
0x180011bbd  test    al, al
0x180011bbf  jz      loc_180011C71
0x180011bc5  mov     ecx, 40h ; '@'; Size
0x180011bca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011bcf  mov     rdi, rax
0x180011bd2  mov     [rsp+1F8h+var_1B0], rax
0x180011bd7  mov     [rax+10h], rbx
0x180011bdb  lea     rax, ??_7AiddTracer@Aidd@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Aidd::AiddTracer::`vftable'
0x180011be2  mov     [rdi], rax
0x180011be5  mov     [rdi+18h], rbx
0x180011be9  mov     [rdi+20h], rbx
0x180011bed  mov     [rdi+28h], rbx
0x180011bf1  mov     [rdi+30h], rbx
0x180011bf5  lea     rcx, [rdi+38h]
0x180011bf9  mov     [rcx], rbx
0x180011bfc  xor     r9d, r9d
0x180011bff  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011c04  nop
0x180011c05  mov     [rsp+1F8h+var_1B0], rdi
0x180011c0a  mov     rcx, r15; Size
0x180011c0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c12  mov     [rsp+1F8h+var_1A0], rax
0x180011c17  mov     rcx, rax; this
0x180011c1a  call    ??0TraceController@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::TraceController::TraceController(void)
0x180011c1f  mov     rsi, rax
0x180011c22  mov     [rsp+1F8h+var_1A0], rax
0x180011c27  mov     [rsp+1F8h+var_1B0], rbx
0x180011c2c  mov     rdx, rdi; struct Windows::Compat::Inventory::Service::Tracer *
0x180011c2f  mov     rcx, rax; this
0x180011c32  call    ?AddTracer@TraceController@Service@Inventory@Compat@Windows@@QEAAXPEAVTracer@2345@@Z; Windows::Compat::Inventory::Service::TraceController::AddTracer(Windows::Compat::Inventory::Service::Tracer *)
0x180011c37  mov     rcx, rsi; this
0x180011c3a  call    ?Start@TraceController@Service@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::Service::TraceController::Start(void)
0x180011c3f  mov     [rsp+1F8h+var_1A0], rbx
0x180011c44  mov     [rsp+1F8h+var_1A8], rsi
0x180011c49  mov     rdx, cs:qword_1800FEF70
0x180011c50  cmp     rdx, cs:qword_1800FEF78
0x180011c57  jz      short loc_180011C66
0x180011c59  mov     [rdx], rsi
0x180011c5c  add     cs:qword_1800FEF70, 8
  ... truncated ...
```
