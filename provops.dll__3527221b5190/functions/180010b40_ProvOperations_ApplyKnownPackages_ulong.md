# ProvOperations::ApplyKnownPackages(ulong)

- ea: `0x180010b40`
- end: `0x180011798`
- name: `?ApplyKnownPackages@ProvOperations@@UEAAJK@Z`
- size: `3160`
- prototype: `__int64 __fastcall(ProvOperations *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800092a0`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180007674`
- `0x18000ac08`
- `0x18000acfc`
- `0x18000d0fc`
- `0x18000d9f4`
- `0x18000e454`
- `0x18000ebbc`
- `0x180010b40`
- `0x180011884`
- `0x180011b88`
- `0x1800120bc`
- `0x180012e94`
- `0x180013198`
- `0x180013e9c`
- `0x1800184b4`
- `0x180018e80`
- `0x18001b388`
- `0x18001b3c8`
- `0x18001b50c`
- `0x18001cea0`
- `0x18001f8ac`
- `0x18001f8e4`
- `0x180020c5c`
- `0x180020e98`
- `0x180020fe0`
- `0x1800225e8`
- `0x18002490c`
- `0x180027208`
- `0x18002a170`
- `0x18002a414`
- `0x18002a488`
- `0x18002a5e4`
- `0x18002a858`
- `0x18002ac38`
- `0x18002ad64`
- `0x180033bcc`
- `0x180033d6c`
- `0x180033e9a`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011357`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800113f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001164f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011357`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800113f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001164f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001145d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001145d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010f4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010f4f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001141f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001141f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010efb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010efb`
- `OLEAUT32!__imp_VariantInit` at `0x18001117f`
- `OLEAUT32!__imp_VariantInit` at `0x18001117f`
- `OLEAUT32!__imp_VariantClear` at `0x18001120f`
- `OLEAUT32!__imp_VariantClear` at `0x18001120f`
- `ntdll!RtlNtStatusToDosError` at `0x180010e50`
- `ntdll!RtlNtStatusToDosError` at `0x180010e50`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180011442`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180011442`
- `ntdll!RtlPublishWnfStateData` at `0x180010ec0`
- `ntdll!RtlPublishWnfStateData` at `0x18001153f`
- `ntdll!RtlPublishWnfStateData` at `0x180010ec0`
- `ntdll!RtlPublishWnfStateData` at `0x18001153f`
- `ntdll!RtlQueryWnfStateData` at `0x180010e44`
- `ntdll!RtlQueryWnfStateData` at `0x180010e44`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180010d4f`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180010d4f`
- `dmenterprisediagnostics!SetupAutoLog` at `0x180011007`
- `dmenterprisediagnostics!SetupAutoLog` at `0x180011007`
- `dmenterprisediagnostics!StartAutoLog` at `0x180011018`
- `dmenterprisediagnostics!StartAutoLog` at `0x180011018`
- `dmenterprisediagnostics!StopAutoLog` at `0x180011418`
- `dmenterprisediagnostics!StopAutoLog` at `0x180011418`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 __fastcall ProvOperations::ApplyKnownPackages(ProvOperations *this, unsigned int a2)
{
  unsigned int v3; // r15d
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  _QWORD *v8; // rax
  NTSTATUS v9; // eax
  char *v10; // rax
  char *v11; // r8
  int v12; // edx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // r8d
  HRESULT v16; // eax
  LPVOID v17; // rcx
  HRESULT v18; // eax
  char *v19; // rdx
  int v20; // eax
  unsigned int v21; // r8d
  const unsigned __int16 *v22; // rcx
  int Configuration; // eax
  __int64 v24; // r8
  void *v25; // rcx
  _DWORD *i; // rbx
  _DWORD *v27; // rsi
  char *v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned __int64 v32; // rax
  const struct _tlgProvider_t *v33; // rax
  int v34; // eax
  int v35; // edx
  const struct _tlgProvider_t *v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  LPVOID v39; // rcx
  int v40; // eax
  unsigned int v41; // r8d
  void *v42; // rbx
  void **v43; // rdx
  LPVOID v44; // rcx
  wil *v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-5B8h]
  int ppva; // [rsp+20h] [rbp-5B8h]
  int ppvb; // [rsp+20h] [rbp-5B8h]
  int ppvc; // [rsp+20h] [rbp-5B8h]
  unsigned int v53; // [rsp+40h] [rbp-598h] BYREF
  char v54; // [rsp+48h] [rbp-590h] BYREF
  char v55; // [rsp+49h] [rbp-58Fh] BYREF
  unsigned int v56; // [rsp+50h] [rbp-588h] BYREF
  LPVOID v57; // [rsp+58h] [rbp-580h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-578h] BYREF
  int v59; // [rsp+68h] [rbp-570h] BYREF
  unsigned int v60; // [rsp+70h] [rbp-568h] BYREF
  int v61; // [rsp+78h] [rbp-560h] BYREF
  char v62; // [rsp+7Dh] [rbp-55Bh]
  int pExceptionObject; // [rsp+80h] [rbp-558h] BYREF
  __int128 v64; // [rsp+88h] [rbp-550h] BYREF
  __int64 v65; // [rsp+98h] [rbp-540h]
  struct IMVEngine **v66; // [rsp+A0h] [rbp-538h]
  unsigned int *v67; // [rsp+A8h] [rbp-530h]
  char *v68; // [rsp+B0h] [rbp-528h]
  int *v69; // [rsp+B8h] [rbp-520h]
  ProvOperations *v70; // [rsp+C0h] [rbp-518h]
  void ***v71; // [rsp+C8h] [rbp-510h]
  char v72; // [rsp+D0h] [rbp-508h]
  LPVOID *v73; // [rsp+D8h] [rbp-500h]
  char v74; // [rsp+E0h] [rbp-4F8h]
  char *v75; // [rsp+E8h] [rbp-4F0h]
  char v76; // [rsp+F0h] [rbp-4E8h]
  void **v77; // [rsp+100h] [rbp-4D8h] BYREF
  __int64 v78; // [rsp+108h] [rbp-4D0h]
  HANDLE hObject[2]; // [rsp+110h] [rbp-4C8h]
  __int64 v80; // [rsp+120h] [rbp-4B8h]
  __int64 v81; // [rsp+128h] [rbp-4B0h]
  __int128 v82; // [rsp+130h] [rbp-4A8h] BYREF
  void **v83; // [rsp+140h] [rbp-498h] BYREF
  int v84; // [rsp+148h] [rbp-490h] BYREF
  char v85; // [rsp+14Ch] [rbp-48Ch]
  int v86; // [rsp+170h] [rbp-468h] BYREF
  const char *v87; // [rsp+178h] [rbp-460h]
  __int64 v88; // [rsp+180h] [rbp-458h]
  char v89; // [rsp+188h] [rbp-450h]
  int v90; // [rsp+190h] [rbp-448h]
  _BYTE v91[168]; // [rsp+198h] [rbp-440h] BYREF
  int v92; // [rsp+240h] [rbp-398h]
  __int64 v93; // [rsp+248h] [rbp-390h]
  int *v94; // [rsp+250h] [rbp-388h]
  __int64 v95; // [rsp+258h] [rbp-380h]
  __int64 v96; // [rsp+260h] [rbp-378h]
  void ***v97; // [rsp+268h] [rbp-370h]
  __int64 v98; // [rsp+270h] [rbp-368h]
  int v99; // [rsp+278h] [rbp-360h]
  int *v100; // [rsp+280h] [rbp-358h]
  char v101; // [rsp+288h] [rbp-350h]
  void *Src[2]; // [rsp+290h] [rbp-348h] BYREF
  void *v103; // [rsp+2A0h] [rbp-338h]
  unsigned __int64 v104; // [rsp+2A8h] [rbp-330h]
  unsigned int *v105; // [rsp+2B0h] [rbp-328h]
  __int64 v106; // [rsp+2B8h] [rbp-320h]
  VARIANTARG pvarg; // [rsp+2C0h] [rbp-318h] BYREF
  __int128 v108; // [rsp+2E0h] [rbp-2F8h] BYREF
  LPVOID *p_pv; // [rsp+2F0h] [rbp-2E8h]
  __int64 v110; // [rsp+2F8h] [rbp-2E0h]
  char Destination[144]; // [rsp+300h] [rbp-2D8h] BYREF
  unsigned __int8 v112[528]; // [rsp+390h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+0h]

  v56 = a2;
  v84 = 0;
  v85 = 0;
  v89 = 0;
  v86 = 0;
  v87 = "ProvOpsApplyKnownPackages";
  v88 = 0;
  v90 = 0;
  *(_OWORD *)&v91[152] = 0;
  memset_0(v91, 0, 0x98u);
  v3 = 1;
  v92 = 1;
  v93 = 0;
  v94 = &v84;
  v95 = 0;
  v96 = 0;
  v97 = &v83;
  v98 = 0;
  v99 = 0;
  v100 = &v86;
  v101 = 0;
  v83 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *)&v83);
  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    v53 = v56;
    v103 = &v53;
    v104 = 4;
    ppv = Src;
    McGenEventWrite_EventWriteTransfer(v4, ProvOpsApplyKnownPackagesInitiated, v5, 2);
  }
  if ( !v56 )
  {
    v6 = 712;
LABEL_5:
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
LABEL_6:
    v83 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v83);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v83);
    return v3;
  }
  if ( v56 >= 9 )
  {
    v6 = 713;
    goto LABEL_5;
  }
  if ( (unsigned __int8)IsGeneralized() )
  {
    v8 = (_QWORD *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) >= 8u )
      v8 = (_QWORD *)*v8;
    pv = v8;
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::ProvOpsGeneralizeSkipApply<unsigned long &,unsigned short const *>(
      &v83,
      &v56,
      &pv);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v83);
    goto LABEL_6;
  }
  v59 = 0;
  OOBEComplete(&v59);
  v54 = 0;
  v57 = 0;
  v66 = (struct IMVEngine **)&v57;
  v67 = &v56;
  v68 = &v54;
  v69 = &v59;
  v70 = this;
  v71 = &v83;
  v72 = 1;
  try
  {
    ProvAgent::ProvAgent((ProvAgent *)Src);
    ProvAgent::LockForProvisioning((ProvAgent *)Src);
    v77 = &WnfSubscriberT<unsigned long>::`vftable';
    v78 = WNF_DEVM_PROVISIONING_COMPLETE;
    *(_OWORD *)hObject = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    *(_QWORD *)&v82 = std::_Tree_alloc<0,std::_Tree_base_types<std::shared_ptr<std::function<void (unsigned long const &)>>>>::_Buyheadnode();
    v61 = 0;
    ppva = 0;
    v9 = RtlQueryWnfStateData(&v61, v78, WnfSubscriberT<unsigned long>::CallbackWrapper, &v77);
    if ( v9 < 0 )
      RtlNtStatusToDosError(v9);
    if ( !v61 )
    {
      v10 = (char *)this + 16;
      if ( *((_QWORD *)this + 5) >= 8u )
        v10 = *(char **)v10;
      v11 = (char *)((char *)L"PhoneProvisioner" - v10);
      do
      {
        v12 = *(unsigned __int16 *)&v11[(_QWORD)v10];
        v13 = *(unsigned __int16 *)v10 - v12;
        if ( v13 )
          break;
        v10 += 2;
      }
      while ( v12 );
      if ( v13 )
      {
        if ( (unsigned int)ProvAgent::GetCurrentTurn(Src) )
        {
          v53 = 1;
          ppva = 0;
          v14 = RtlPublishWnfStateData(WNF_DEVM_PROVISIONING_COMPLETE, 0, &v53, 4);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x308, v15, (const char *)(unsigned int)v14, 0);
        }
        else
        {
          v54 = 1;
        }
      }
    }
    ProvAgent::SetCurrentTurn(Src, v56);
    v16 = CoInitializeEx(0, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x315,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)(unsigned int)v16,
        ppva);
    v62 = 1;
    v17 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = CoCreateInstance(
            &GUID_fb647f50_2192_49e0_a68f_5775434058c7,
            0,
            1u,
            &GUID_7b967ffd_bc01_4a23_aedd_055f4002710f,
            &v57);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x319,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)(unsigned int)v18,
        ppvb);
    if ( *((_QWORD *)this + 5) < 8u )
      v19 = (char *)this + 16;
    else
      v19 = (char *)*((_QWORD *)this + 2);
    (*(void (__fastcall **)(LPVOID, char *))(*(_QWORD *)v57 + 32LL))(v57, v19);
    if ( v56 == 1 && ProvAgent::InUpgrade() )
      UpgradeClearSettingsGroups();
    v20 = ProvOperations::CheckFirstRun(this);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x31E, v21, (const char *)(unsigned int)v20, ppvb);
    v55 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl'::`2'::impl) )
    {
      if ( v59 )
        ProvOperations::CleanupOOBEProvisioningLogs(this);
    }
    else if ( !v59 )
    {
      EnableTask(L"MdmDiagnosticsCleanup");
    }
    if ( (int)SetupAutoLog(L"DeviceProvisioning", 0, v59) >= 0 && (int)StartAutoLog(L"DeviceProvisioning") >= 0 )
      v55 = 1;
    v75 = &v55;
    v76 = 1;
    memset_0(v112, 0, 0x20Au);
    v53 = 522;
    Configuration = MvGetConfiguration(v22, v112, &v53);
    if ( Configuration < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x347,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)(unsigned int)Configuration,
        ppvb);
    TraceLoggingCorrelationVector::ToString(*((TraceLoggingCorrelationVector **)this + 7), Destination);
    ProvAgent::GetContexts(&v64, v56);
    __SET_PAIR__((unsigned __int64)v27, (unsigned __int64)v25, v64);
    for ( i = (_DWORD *)v64; i != v27; i += 4 )
    {
      if ( *((_QWORD *)this + 5) < 8u )
        v28 = (char *)this + 16;
      else
        v28 = (char *)*((_QWORD *)this + 2);
      *(_QWORD *)&pvarg.vt = v28;
      v53 = i[3];
      v60 = i[1];
      LODWORD(pv) = *i;
      Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::ProvOpsContext<unsigned int,unsigned int,unsigned long const &,unsigned int,unsigned short const *>(
        (unsigned int)&v83,
        (unsigned int)&pv,
        (unsigned int)&v60,
        (_DWORD)i + 8,
        (__int64)&v53,
        (__int64)&pvarg,
        (__int64)Destination);
      v29 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int8 *, const unsigned __int16 *))(*(_QWORD *)v57 + 24LL))(
              v57,
              v112,
              L"Software\\Microsoft\\Multivariant\\Handlers");
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x352,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)v29,
          ppvc);
      v73 = &v57;
      v74 = 1;
      if ( (unsigned int)(*i - 2) <= 1 )
      {
        VariantInit(&pvarg);
        pvarg.lVal = i[2];
        pvarg.vt = 19;
        v30 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v57 + 64LL))(
                v57,
                L"slot",
                &pvarg);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x35B,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v30,
            ppvc);
        pvarg.lVal = i[3];
        v31 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v57 + 64LL))(
                v57,
                L"slotstatus",
                &pvarg);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x35E,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v31,
            ppvc);
        VariantClear(&pvarg);
      }
      *(_OWORD *)&pvarg.vt = *(_OWORD *)i;
      ProvAgent::GetRelevantStates(&v108, &pvarg);
      v32 = (__int64)(*((_QWORD *)&v108 + 1) - v108) >> 2;
      v53 = v32;
      if ( v32 > 0x7FFFFFFF )
      {
        v53 = -1;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x364,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          v32 > 0x7FFFFFFF ? (const char *)0x80070216LL : 0,
          ppvc);
      }
      v33 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
      if ( *(_DWORD *)v33 > 5u )
      {
        ppvc = 2;
        tlgWriteTransfer_EventWriteTransfer(v33, byte_18003F8A3, v94 + 2, 0);
      }
      v34 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 40LL))(v57, v108, v53, v56);
      if ( (unsigned int)(v34 + 2147024893) <= 0xF )
      {
        v35 = 33025;
        if ( _bittest(&v35, v34 + 2147024893) )
        {
          pExceptionObject = v34;
          throw (long *)&pExceptionObject;
        }
      }
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x371,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)v34,
          ppvc);
      v36 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
      if ( *(_DWORD *)v36 > 5u )
        tlgWriteTransfer_EventWriteTransfer(v36, byte_18003F8CD, v94 + 2, 0);
      if ( (_QWORD)v108 )
      {
        operator delete((void *)v108);
        v108 = 0;
        p_pv = 0;
      }
      v74 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 104LL))(v57);
      v25 = (void *)v64;
    }
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      LODWORD(pv) = v56;
      p_pv = &pv;
      v110 = 4;
      McGenEventWrite_EventWriteTransfer(v25, "G", v24, 2);
      v25 = (void *)v64;
    }
    if ( v25 )
    {
      operator delete(v25);
      v64 = 0;
      v65 = 0;
    }
    if ( v55 )
      StopAutoLog(L"DeviceProvisioning");
    CoUninitialize();
    v77 = &WnfSubscriberT<unsigned long>::`vftable';
    if ( hObject[0] )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      hObject[0] = 0;
    }
    if ( hObject[1] )
    {
      CloseHandle(hObject[1]);
      hObject[1] = 0;
    }
    std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>(&v82);
    if ( hObject[1] )
      CloseHandle(hObject[1]);
    ProvAgent::~ProvAgent((ProvAgent *)Src);
    v72 = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x379, v37, v38);
    v46 = wil::ResultFromCaughtException(v45);
    v53 = v46;
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v60 = v46;
      LODWORD(pv) = v56;
      v103 = &pv;
      v104 = 4;
      v105 = &v60;
      v106 = 4;
      McGenEventWrite_EventWriteTransfer(v47, ProvOpsApplyKnownPackagesFailed, v48, 3);
    }
    PostProvisioningActivities(*v66, *v67);
    if ( *v68 )
    {
      LODWORD(pv) = 1;
      v40 = RtlPublishWnfStateData(WNF_DEVM_PROVISIONING_COMPLETE, 0, &pv, 4);
      if ( v40 < 0 )
        wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x2E0, v41, (const char *)(unsigned int)v40, 0);
    }
    if ( !*v69 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl'::`2'::impl) )
      {
        pv = 0;
        ProvOperations::GetOOBEProvisioningLogsPath((unsigned __int16 **)&pv);
        v42 = pv;
        (*(void (__fastcall **)(ProvOperations *, LPVOID))(*(_QWORD *)v70 + 80LL))(v70, pv);
        if ( v42 )
          CoTaskMemFree(v42);
      }
      else
      {
        ProvisioningPaths::GetProvisioningDiagnosticsFolderPath();
        v104 = 7;
        v103 = 0;
        LOWORD(Src[0]) = 0;
        std::wstring::assign(Src);
        std::wstring::append(Src, L"DeviceProvisioning-Diagnostics-GetLogs.cab");
        v43 = Src;
        if ( v104 >= 8 )
          v43 = (void **)Src[0];
        (*(void (__fastcall **)(ProvOperations *, void **))(*(_QWORD *)v70 + 80LL))(v70, v43);
        if ( v104 >= 8 )
          operator delete(Src[0]);
      }
    }
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v71);
    v44 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v83 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v83);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v83);
    return v53;
  }
  lambda_155a96e974d72e0aba78def5a3e98f3d_::operator()();
  v39 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v83 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v83);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v83);
  return 0;
}

```

## disassembly

```asm
0x180010b40  mov     r11, rsp
0x180010b43  mov     [r11+18h], rbx
0x180010b47  mov     [r11+20h], rsi
0x180010b4b  push    rdi
0x180010b4c  push    r12
0x180010b4e  push    r13
0x180010b50  push    r14
0x180010b52  push    r15
0x180010b54  sub     rsp, 5B0h
0x180010b5b  mov     rax, cs:__security_cookie
0x180010b62  xor     rax, rsp
0x180010b65  mov     [rsp+5D8h+var_38], rax
0x180010b6d  mov     r13, rcx
0x180010b70  mov     [rsp+5D8h+var_588], edx
0x180010b74  xor     r14d, r14d
0x180010b77  mov     [r11-490h], r14d
0x180010b7e  mov     [r11-48Ch], r14b
0x180010b85  mov     [r11-450h], r14b
0x180010b8c  mov     [r11-468h], r14d
0x180010b93  lea     rax, aProvopsapplykn; "ProvOpsApplyKnownPackages"
0x180010b9a  mov     [r11-460h], rax
0x180010ba1  mov     [r11-458h], r14
0x180010ba8  mov     [r11-448h], r14d
0x180010baf  xorps   xmm0, xmm0
0x180010bb2  movdqa  [rsp+5D8h+var_3A8], xmm0
0x180010bbb  xor     edx, edx; Val
0x180010bbd  mov     r8d, 98h; Size
0x180010bc3  lea     rcx, [r11-440h]; void *
0x180010bca  call    memset_0
0x180010bcf  lea     r15d, [r14+1]
0x180010bd3  mov     [rsp+5D8h+var_398], r15d
0x180010bdb  xor     eax, eax
0x180010bdd  mov     [rsp+5D8h+var_390], rax
0x180010be5  lea     rax, [rsp+5D8h+var_490]
0x180010bed  mov     [rsp+5D8h+var_388], rax
0x180010bf5  mov     [rsp+5D8h+var_380], r14
0x180010bfd  mov     [rsp+5D8h+var_378], r14
0x180010c05  lea     rax, [rsp+5D8h+var_498]
0x180010c0d  mov     [rsp+5D8h+var_370], rax
0x180010c15  mov     [rsp+5D8h+var_368], r14
0x180010c1d  mov     [rsp+5D8h+var_360], r14d
0x180010c25  lea     rax, [rsp+5D8h+var_468]
0x180010c2d  mov     [rsp+5D8h+var_358], rax
0x180010c35  mov     [rsp+5D8h+var_350], r14b
0x180010c3d  lea     r12, ??_7ProvOpsApplyKnownPackages@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::`vftable'
0x180010c44  mov     [rsp+5D8h+var_498], r12
0x180010c4c  lea     rcx, [rsp+5D8h+var_498]; this
0x180010c54  call    ?StartActivity@ProvOpsApplyKnownPackages@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StartActivity(void)
0x180010c59  nop
0x180010c5a  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, r15b
0x180010c61  jz      short loc_180010CA1
0x180010c63  mov     eax, [rsp+5D8h+var_588]
0x180010c67  mov     [rsp+5D8h+var_598], eax
0x180010c6b  lea     rax, [rsp+5D8h+var_598]
0x180010c70  mov     [rsp+5D8h+var_338], rax
0x180010c78  mov     [rsp+5D8h+var_330], 4
0x180010c84  lea     rax, [rsp+5D8h+Src]
0x180010c8c  mov     [rsp+5D8h+ppv], rax; int
0x180010c91  lea     r9d, [r14+2]
0x180010c95  lea     rdx, ProvOpsApplyKnownPackagesInitiated
0x180010c9c  call    McGenEventWrite_EventWriteTransfer
0x180010ca1  cmp     [rsp+5D8h+var_588], r14d
0x180010ca6  jnz     short loc_180010CF5
0x180010ca8  mov     edx, 2C8h; void *
0x180010cad  mov     r15d, 80070057h
0x180010cb3  mov     r9d, r15d; char *
0x180010cb6  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180010cbd  mov     rcx, [rsp+5D8h]; this
0x180010cc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cca  nop
0x180010ccb  mov     [rsp+5D8h+var_498], r12
0x180010cd3  lea     rcx, [rsp+5D8h+var_498]
0x180010cdb  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010ce0  lea     rcx, [rsp+5D8h+var_498]
0x180010ce8  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010ced  mov     eax, r15d
0x180010cf0  jmp     loc_1800116AC
0x180010cf5  cmp     [rsp+5D8h+var_588], 9
0x180010cfa  jb      short loc_180010D03
0x180010cfc  mov     edx, 2C9h
0x180010d01  jmp     short loc_180010CAD
0x180010d03  call    IsGeneralized
0x180010d08  test    al, al
0x180010d0a  jz      short loc_180010D45
0x180010d0c  lea     rax, [r13+10h]
0x180010d10  cmp     qword ptr [rax+18h], 8
0x180010d15  jb      short loc_180010D1A
0x180010d17  mov     rax, [rax]
0x180010d1a  mov     [rsp+5D8h+pv], rax
0x180010d1f  lea     r8, [rsp+5D8h+pv]
0x180010d24  lea     rdx, [rsp+5D8h+var_588]
0x180010d29  lea     rcx, [rsp+5D8h+var_498]
0x180010d31  call    ??$ProvOpsGeneralizeSkipApply@AEAKPEBG@ProvOpsApplyKnownPackages@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXAEAK$$QEAPEBG@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::ProvOpsGeneralizeSkipApply<ulong &,ushort const *>(ulong &,ushort const * &&)
0x180010d36  lea     rcx, [rsp+5D8h+var_498]
0x180010d3e  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010d43  jmp     short loc_180010CCB
0x180010d45  mov     [rsp+5D8h+var_570], r14d
0x180010d4a  lea     rcx, [rsp+5D8h+var_570]
0x180010d4f  call    cs:__imp_OOBEComplete
0x180010d55  mov     [rsp+5D8h+var_590], r14b
0x180010d5a  mov     [rsp+5D8h+var_580], r14
0x180010d5f  lea     rax, [rsp+5D8h+var_580]
0x180010d64  mov     [rsp+5D8h+var_538], rax
0x180010d6c  lea     rax, [rsp+5D8h+var_588]
0x180010d71  mov     [rsp+5D8h+var_530], rax
0x180010d79  lea     rax, [rsp+5D8h+var_590]
0x180010d7e  mov     [rsp+5D8h+var_528], rax
0x180010d86  lea     rax, [rsp+5D8h+var_570]
0x180010d8b  mov     [rsp+5D8h+var_520], rax
0x180010d93  mov     [rsp+5D8h+var_518], r13
0x180010d9b  lea     rax, [rsp+5D8h+var_498]
0x180010da3  mov     [rsp+5D8h+var_510], rax
0x180010dab  mov     [rsp+5D8h+var_508], r15b
0x180010db3  lea     rcx, [rsp+5D8h+Src]; this
0x180010dbb  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x180010dc0  nop
0x180010dc1  lea     rcx, [rsp+5D8h+Src]; this
0x180010dc9  call    ?LockForProvisioning@ProvAgent@@QEAAXXZ; ProvAgent::LockForProvisioning(void)
0x180010dce  lea     rax, ??_7?$WnfSubscriberT@K@@6B@; const WnfSubscriberT<ulong>::`vftable'
0x180010dd5  mov     [rsp+5D8h+var_4D8], rax
0x180010ddd  mov     rax, cs:WNF_DEVM_PROVISIONING_COMPLETE
0x180010de4  mov     [rsp+5D8h+var_4D0], rax
0x180010dec  xorps   xmm0, xmm0
0x180010def  movdqa  xmmword ptr [rsp+5D8h+hObject], xmm0
0x180010df8  mov     [rsp+5D8h+var_4B8], r14
0x180010e00  mov     [rsp+5D8h+var_4B0], r14
0x180010e08  movdqa  [rsp+5D8h+var_4A8], xmm0
0x180010e11  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::shared_ptr<std::function<void (ulong const &)>>>>::_Buyheadnode(void)
0x180010e16  mov     qword ptr [rsp+5D8h+var_4A8], rax
0x180010e1e  mov     [rsp+5D8h+var_560], r14d
0x180010e23  mov     [rsp+5D8h+ppv], r14; int
0x180010e28  lea     r9, [rsp+5D8h+var_4D8]
0x180010e30  lea     r8, ?CallbackWrapper@?$WnfSubscriberT@K@@KAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WnfSubscriberT<ulong>::CallbackWrapper(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180010e37  mov     rdx, [rsp+5D8h+var_4D0]
0x180010e3f  lea     rcx, [rsp+5D8h+var_560]
0x180010e44  call    cs:__imp_RtlQueryWnfStateData
0x180010e4a  test    eax, eax
0x180010e4c  jns     short loc_180010E56
0x180010e4e  mov     ecx, eax; Status
0x180010e50  call    cs:__imp_RtlNtStatusToDosError
0x180010e56  cmp     [rsp+5D8h+var_560], r14d
0x180010e5b  jnz     loc_180010EE6
0x180010e61  lea     rax, [r13+10h]
0x180010e65  cmp     qword ptr [rax+18h], 8
0x180010e6a  jb      short loc_180010E6F
0x180010e6c  mov     rax, [rax]
0x180010e6f  lea     r8, aPhoneprovision; "PhoneProvisioner"
0x180010e76  sub     r8, rax
0x180010e79  movzx   ecx, word ptr [rax]
0x180010e7c  movzx   edx, word ptr [rax+r8]
0x180010e81  sub     ecx, edx
0x180010e83  jnz     short loc_180010E8D
0x180010e85  add     rax, 2
0x180010e89  test    edx, edx
0x180010e8b  jnz     short loc_180010E79
0x180010e8d  test    ecx, ecx
0x180010e8f  jz      short loc_180010EE6
0x180010e91  lea     rcx, [rsp+5D8h+Src]
0x180010e99  call    ?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ; ProvAgent::GetCurrentTurn(void)
0x180010e9e  test    eax, eax
0x180010ea0  jz      short loc_180010EE1
0x180010ea2  mov     [rsp+5D8h+var_598], r15d
0x180010ea7  mov     [rsp+5D8h+ppv], r14; int
0x180010eac  mov     r9d, 4
0x180010eb2  lea     r8, [rsp+5D8h+var_598]
0x180010eb7  xor     edx, edx
0x180010eb9  mov     rcx, cs:WNF_DEVM_PROVISIONING_COMPLETE
0x180010ec0  call    cs:__imp_RtlPublishWnfStateData
0x180010ec6  mov     rcx, [rsp+5D8h]; this
0x180010ece  test    eax, eax
0x180010ed0  jns     short loc_180010EE6
0x180010ed2  mov     r9d, eax; char *
0x180010ed5  mov     edx, 308h; void *
0x180010eda  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180010edf  jmp     short loc_180010EE6
0x180010ee1  mov     [rsp+5D8h+var_590], r15b
0x180010ee6  mov     edx, [rsp+5D8h+var_588]
0x180010eea  lea     rcx, [rsp+5D8h+Src]
0x180010ef2  call    ?SetCurrentTurn@ProvAgent@@QEAAXW4ProvisioningTurn@Provisioning@Management@Windows@@@Z; ProvAgent::SetCurrentTurn(Windows::Management::Provisioning::ProvisioningTurn)
0x180010ef7  xor     edx, edx; dwCoInit
0x180010ef9  xor     ecx, ecx; pvReserved
0x180010efb  call    cs:__imp_CoInitializeEx
0x180010f01  mov     rcx, [rsp+5D8h]; this
0x180010f09  test    eax, eax
0x180010f0b  js      loc_1800116D9
0x180010f11  mov     [rsp+5D8h+var_55B], r15b
0x180010f16  mov     rcx, [rsp+5D8h+var_580]
0x180010f1b  test    rcx, rcx
0x180010f1e  jz      short loc_180010F32
0x180010f20  mov     [rsp+5D8h+var_580], r14
0x180010f25  mov     rax, [rcx]
0x180010f28  mov     rax, [rax+10h]
0x180010f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f31  nop
0x180010f32  lea     rax, [rsp+5D8h+var_580]
0x180010f37  mov     [rsp+5D8h+ppv], rax; int
0x180010f3c  lea     r9, _GUID_7b967ffd_bc01_4a23_aedd_055f4002710f; riid
0x180010f43  mov     r8d, r15d; dwClsContext
0x180010f46  xor     edx, edx; pUnkOuter
0x180010f48  lea     rcx, _GUID_fb647f50_2192_49e0_a68f_5775434058c7; rclsid
0x180010f4f  call    cs:__imp_CoCreateInstance
0x180010f55  mov     rcx, [rsp+5D8h]; this
0x180010f5d  test    eax, eax
0x180010f5f  js      loc_1800116EE
0x180010f65  mov     rcx, [rsp+5D8h+var_580]
0x180010f6a  mov     rax, [rcx]
0x180010f6d  mov     r8, [rax+20h]
0x180010f71  cmp     qword ptr [r13+28h], 8
0x180010f76  jb      short loc_180010F7E
0x180010f78  mov     rdx, [r13+10h]
0x180010f7c  jmp     short loc_180010F82
0x180010f7e  lea     rdx, [r13+10h]
0x180010f82  mov     rax, r8
0x180010f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8a  cmp     [rsp+5D8h+var_588], r15d
0x180010f8f  jnz     short loc_180010F9F
0x180010f91  call    ?InUpgrade@ProvAgent@@SA_NXZ; ProvAgent::InUpgrade(void)
0x180010f96  test    al, al
0x180010f98  jz      short loc_180010F9F
0x180010f9a  call    ?UpgradeClearSettingsGroups@@YAXXZ; UpgradeClearSettingsGroups(void)
0x180010f9f  mov     rcx, r13; this
0x180010fa2  call    ?CheckFirstRun@ProvOperations@@AEAAJXZ; ProvOperations::CheckFirstRun(void)
0x180010fa7  mov     rcx, [rsp+5D8h]; this
0x180010faf  test    eax, eax
0x180010fb1  jns     short loc_180010FC0
0x180010fb3  mov     r9d, eax; char *
0x180010fb6  mov     edx, 31Eh; void *
0x180010fbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010fc0  mov     [rsp+5D8h+var_58F], r14b
0x180010fc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl(void)'::`2'::impl
0x180010fcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(void)
0x180010fd1  test    al, al
0x180010fd3  jz      short loc_180010FE6
0x180010fd5  cmp     [rsp+5D8h+var_570], r14d
0x180010fda  jz      short loc_180010FF9
0x180010fdc  mov     rcx, r13; this
0x180010fdf  call    ?CleanupOOBEProvisioningLogs@ProvOperations@@QEAAXXZ; ProvOperations::CleanupOOBEProvisioningLogs(void)
0x180010fe4  jmp     short loc_180010FF9
0x180010fe6  cmp     [rsp+5D8h+var_570], r14d
0x180010feb  jnz     short loc_180010FF9
0x180010fed  lea     rcx, aMdmdiagnostics; "MdmDiagnosticsCleanup"
0x180010ff4  call    ?EnableTask@@YAXPEBG@Z; EnableTask(ushort const *)
0x180010ff9  mov     r8d, [rsp+5D8h+var_570]
0x180010ffe  xor     edx, edx
0x180011000  lea     rcx, aDeviceprovisio; "DeviceProvisioning"
0x180011007  call    cs:__imp_?SetupAutoLog@@YAJPEBG0H@Z; SetupAutoLog(ushort const *,ushort const *,int)
0x18001100d  test    eax, eax
0x18001100f  js      short loc_180011027
0x180011011  lea     rcx, aDeviceprovisio; "DeviceProvisioning"
0x180011018  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x18001101e  test    eax, eax
0x180011020  js      short loc_180011027
0x180011022  mov     [rsp+5D8h+var_58F], r15b
0x180011027  lea     rdi, [rsp+5D8h+var_58F]
0x18001102c  mov     [rsp+5D8h+var_4F0], rdi
0x180011034  mov     [rsp+5D8h+var_4E8], r15b
0x18001103c  mov     ebx, 20Ah
0x180011041  mov     r8d, ebx; Size
0x180011044  xor     edx, edx; Val
0x180011046  lea     rcx, [rsp+5D8h+var_248]; void *
0x18001104e  call    memset_0
0x180011053  mov     [rsp+5D8h+var_598], ebx
0x180011057  lea     r8, [rsp+5D8h+var_598]; unsigned int *
0x18001105c  lea     rdx, [rsp+5D8h+var_248]; unsigned __int8 *
0x180011064  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x180011069  mov     rcx, [rsp+5D8h]; this
0x180011071  test    eax, eax
0x180011073  js      loc_180011703
0x180011079  lea     rdx, [rsp+5D8h+Destination]; Destination
0x180011081  mov     rcx, [r13+38h]; this
0x180011085  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x18001108a  mov     edx, [rsp+5D8h+var_588]
0x18001108e  lea     rcx, [rsp+5D8h+var_550]
0x180011096  call    ?GetContexts@ProvAgent@@SA?AV?$vector@UProvContext@@V?$allocator@UProvContext@@@std@@@std@@W4ProvisioningTurn@Provisioning@Management@Windows@@@Z; ProvAgent::GetContexts(Windows::Management::Provisioning::ProvisioningTurn)
0x18001109b  nop
0x18001109c  mov     rcx, qword ptr [rsp+5D8h+var_550]
0x1800110a4  mov     rbx, rcx
0x1800110a7  mov     rsi, qword ptr [rsp+5D8h+var_550+8]
0x1800110af  cmp     rbx, rsi
0x1800110b2  jz      loc_18001139C
0x1800110b8  cmp     qword ptr [r13+28h], 8
0x1800110bd  jb      short loc_1800110C5
0x1800110bf  mov     rax, [r13+10h]
0x1800110c3  jmp     short loc_1800110C9
0x1800110c5  lea     rax, [r13+10h]
0x1800110c9  mov     qword ptr [rsp+5D8h+pvarg], rax
0x1800110d1  mov     eax, [rbx+0Ch]
0x1800110d4  mov     [rsp+5D8h+var_598], eax
0x1800110d8  mov     eax, [rbx+4]
0x1800110db  mov     [rsp+5D8h+var_568], eax
0x1800110df  mov     eax, [rbx]
0x1800110e1  mov     dword ptr [rsp+5D8h+pv], eax
0x1800110e5  lea     r9, [rbx+8]
0x1800110e9  lea     rcx, [rsp+5D8h+Destination]
0x1800110f1  mov     [rsp+5D8h+var_5A8], rcx
0x1800110f6  lea     rcx, [rsp+5D8h+pvarg]
0x1800110fe  mov     [rsp+5D8h+var_5B0], rcx
0x180011103  lea     rcx, [rsp+5D8h+var_598]
0x180011108  mov     [rsp+5D8h+ppv], rcx; int
0x18001110d  lea     r8, [rsp+5D8h+var_568]
  ... truncated ...
```
