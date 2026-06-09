# _RoGetActivationFactory

- ea: `0x180009ab0`
- end: `0x18000a86b`
- name: `_RoGetActivationFactory`
- size: `3515`
- prototype: `HRESULT __fastcall(HSTRING__ *activatableClassId, unsigned __int64 userContext, const _GUID *iid, void **factory)`
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800095d0`
- `0x180159240`

## callees

- `0x180006250`
- `0x18000712c`
- `0x180009ab0`
- `0x18000be10`
- `0x180016970`
- `0x180017018`
- `0x180017120`
- `0x180037f30`
- `0x180038028`
- `0x18003a8bc`
- `0x18003cf8c`
- `0x18003eaa0`
- `0x18003f240`
- `0x1800421e0`
- `0x1800436b0`
- `0x1800450a0`
- `0x1800521b8`
- `0x180053178`
- `0x180055270`
- `0x180056ce0`
- `0x18006c7b8`
- `0x180079c5c`
- `0x1800865f4`
- `0x180086f14`
- `0x180086f50`
- `0x1800c1034`
- `0x1800d0e28`
- `0x1801066c4`
- `0x1801718f4`
- `0x180171d4c`
- `0x1801999b0`
- `0x1801d28a8`
- `0x1801d2bcc`
- `0x180255010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009c08`
- `ntdll!RtlNtStatusToDosError` at `0x180009c97`
- `ntdll!RtlNtStatusToDosError` at `0x180009c08`
- `ntdll!RtlNtStatusToDosError` at `0x180009c97`
- `ntdll!RtlLoadString` at `0x180009c00`
- `ntdll!RtlLoadString` at `0x180009c8f`
- `ntdll!RtlLoadString` at `0x180009c00`
- `ntdll!RtlLoadString` at `0x180009c8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009af9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009af9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d72`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000a2aa`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000a2aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a344`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a344`

## string_xrefs

- `0x180009fe1`: `onecore\com\combase\winrtbase\winrtbase.cpp`
- `0x18000a84a`: `onecore\com\combase\winrtbase\winrtbase.cpp`
- `0x180009e3e`: `onecore\com\combase\catalog\catalog.cxx`
- `0x18000a1ff`: `onecore\com\combase\objact\objact.cxx`
- `0x18000a2bb`: `onecore\com\combase\objact\objact.cxx`
- `0x18000a380`: `onecore\com\combase\objact\objact.cxx`
- `0x180009cd5`: `onecore\com\combase\objact\dllhost.cxx`
- `0x18000a387`: `Access denied: Activatable class: %ws User sid: %ws`

## pseudocode

```c
__int64 __fastcall RoGetActivationFactory(
        HSTRING__ *activatableClassId,
        unsigned __int64 userContext,
        _GUID *iid,
        IUnknown **factory)
{
  tagSOleTlsData *ReservedForOle; // rax
  DWORD CurrentThreadId; // eax
  tagSOleTlsData *v9; // rax
  DWORD v10; // eax
  NTSTATUS v11; // eax
  signed int v12; // eax
  bool v13; // sf
  HRESULT ActivationFactory; // edi
  NTSTATUS v16; // eax
  signed int v17; // eax
  bool v18; // sf
  _DWORD *v19; // r14
  int v20; // ebx
  __int64 v21; // rax
  int v22; // edx
  _WORD *v23; // rcx
  _WORD *v24; // r8
  IComCatalog *v25; // rcx
  unsigned int v26; // edx
  int v27; // edx
  Windows::Foundation::ActivationType v28; // r14d
  TrustLevel trustLevel; // edi
  Windows::Foundation::ActivateAsUser activateAsUser; // r15d
  HRESULT v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  const _GUID *v34; // r8
  _GUID *v35; // r15
  const _GUID *v36; // r8
  const _EVENT_DESCRIPTOR *v37; // rdx
  const _GUID *v38; // r8
  IWinRTRuntimeClassInfo *v39; // r14
  ProcessToken *v40; // rcx
  const wchar_t *v41; // r15
  HRESULT SelfSid; // eax
  wchar_t *v43; // r12
  IWinRTRuntimeClassInfo v44; // rax
  HRESULT (__fastcall *GetActivatableClassId)(IWinRTRuntimeClassInfo *, HSTRING__ **); // rbx
  wchar_t *v46; // rcx
  const wchar_t *v47; // rax
  bool IsEnabled; // al
  int WinRTInprocClass; // eax
  wchar_t *v50; // rbx
  __int64 v51; // rcx
  IWinRTRuntimeClassInfo v52; // rax
  unsigned __int64 v53; // rdx
  unsigned __int8 v54; // cl
  wil::details::static_lazy<ComTrace> *v55; // rcx
  ComTrace *v56; // rcx
  signed int v57; // edi
  IWinRTRuntimeClassInfo v58; // rax
  unsigned __int64 v59; // rdx
  unsigned __int8 v60; // cl
  wil::details::static_lazy<ComTrace> *v61; // rcx
  ComTrace *v62; // rcx
  wchar_t *v63; // rbx
  unsigned int v64; // edx
  const _GUID *v65; // r8
  _QWORD *pShimData; // rcx
  void (__fastcall *v67)(PSECURITY_DESCRIPTOR, GUID *, _QWORD, _GUID *, IUnknown **); // r14
  IWinRTRuntimeClassInfo *v68; // rbx
  IWinRTRuntimeClassInfo_vtbl *v69; // rax
  int v70; // ebx
  HRESULT (__fastcall *GetServerInfo)(IWinRTRuntimeClassInfo *, IWinRTServerInfo **); // rax
  int sharedUsagePropertyPresent; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *message; // [rsp+68h] [rbp-98h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-90h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+78h] [rbp-88h] BYREF
  IWinRTRuntimeClassInfo *pRuntimeClassInfo; // [rsp+80h] [rbp-80h] BYREF
  _GUID *v77; // [rsp+88h] [rbp-78h]
  void *ppvObj; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  unsigned int dwActivationType; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int dwTrustLevel; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int dwActivateAsUser; // [rsp+A8h] [rbp-58h] BYREF
  int activateInBrokerForMediumILContainer; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int dwRegistrationScope; // [rsp+B0h] [rbp-50h] BYREF
  int activateInSharedBroker; // [rsp+B4h] [rbp-4Ch] BYREF
  HSTRING__ *desktopApplicationPath; // [rsp+B8h] [rbp-48h] BYREF
  tagMULTI_QI OneQI; // [rsp+C0h] [rbp-40h] BYREF
  Windows::Internal::StringReference strSharedUsageServerPropertyValue; // [rsp+D8h] [rbp-28h] BYREF
  Windows::Internal::StringReference strSharedUsageServerPropertyName; // [rsp+F8h] [rbp-8h] BYREF
  _EVENT_DATA_DESCRIPTOR Context; // [rsp+118h] [rbp+18h] BYREF
  void *retaddr; // [rsp+188h] [rbp+88h]

  v77 = iid;
  *factory = 0;
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  if ( !ReservedForOle )
  {
    CurrentThreadId = GetCurrentThreadId();
    ReservedForOle = TLSPreallocateData(CurrentThreadId);
    if ( !ReservedForOle )
    {
LABEL_166:
      wil::details::in1diag3::Return_Hr(retaddr, 0x413u, "onecore\\com\\combase\\winrtbase\\winrtbase.cpp", -2147221008);
      return 2147746288LL;
    }
    NtCurrentTeb()->ReservedForOle = ReservedForOle;
    ReservedForOle->ppTlsSlot = &NtCurrentTeb()->ReservedForOle;
  }
  if ( !g_cMTAInits && !ReservedForOle->cComInits && !IsThreadInNTA() )
    goto LABEL_166;
  v9 = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  if ( !v9 )
  {
    v10 = GetCurrentThreadId();
    v9 = TLSPreallocateData(v10);
    if ( !v9 )
      return (unsigned int)-2147024882;
    NtCurrentTeb()->ReservedForOle = v9;
    v9->ppTlsSlot = &NtCurrentTeb()->ReservedForOle;
  }
  if ( (v9->dwFlags & 0x800000) == 0 )
  {
    if ( (gMTHost._dwType & 0x100) != 0 )
    {
      message = 0;
      LOWORD(sharedUsagePropertyPresent) = 0;
      ActivationFactory = -2146959352;
      v16 = RtlLoadString(&_ImageBase, 5405, 0, 0, &message, &sharedUsagePropertyPresent, 0, 0);
      v17 = RtlNtStatusToDosError(v16);
      v18 = v17 < 0;
      if ( v17 > 0 )
        v18 = 1;
      if ( v18 )
        RoOriginateError(-2146959352, 0);
      else
        RoOriginateErrorW(-2146959352, (unsigned __int16)sharedUsagePropertyPresent, message);
    }
    else
    {
      COleStaticMutexSem::Request(
        &gMTHost._mxs,
        "onecore\\com\\combase\\objact\\dllhost.cxx",
        0x2A5u,
        (const char *)factory);
      if ( (gMTHost._dwType & 0x40) != 0 )
      {
        ActivationFactory = 0;
      }
      else
      {
        ActivationFactory = IncrementMTAUsageHelper(0, 0);
        if ( ActivationFactory >= 0 )
        {
          gMTHost._dwType |= 0x40u;
          _InterlockedIncrement((volatile signed __int32 *)&gcActivationHostThreadInits);
          g_fMTAHostUsageFlags |= 1u;
        }
      }
      if ( !--gMTHost._mxs._cLocks && gMTHost._mxs._lockOrder != Highest )
      {
        v19 = NtCurrentTeb()->ReservedForOle;
        if ( v19 )
        {
          v20 = 1 << gMTHost._mxs._lockOrder;
          if ( ((1 << gMTHost._mxs._lockOrder) & v19[144]) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs((unsigned __int8)gMTHost._mxs._lockOrder);
          v19[144] &= ~v20;
        }
      }
      LeaveCriticalSection(&gMTHost._mxs._cs);
    }
    if ( ActivationFactory >= 0 )
    {
      pRuntimeClassInfo = 0;
      if ( !activatableClassId )
        goto LABEL_161;
      v21 = *((unsigned int *)activatableClassId + 1);
      if ( (_DWORD)v21 )
      {
        v22 = *(_DWORD *)activatableClassId;
        if ( (*(_DWORD *)activatableClassId & 0x10) == 0 )
        {
          v23 = (_WORD *)*((_QWORD *)activatableClassId + 2);
          v24 = &v23[v21];
          if ( v23 >= v24 )
          {
LABEL_41:
            v22 |= 0x10u;
          }
          else
          {
            while ( *v23 )
            {
              if ( ++v23 >= v24 )
                goto LABEL_41;
            }
            v22 |= 0x18u;
          }
          *(_DWORD *)activatableClassId = v22;
        }
        if ( (v22 & 8) != 0 )
          goto LABEL_161;
      }
      if ( (unsigned int)(*((_DWORD *)activatableClassId + 1) - 1) > 0xFF )
      {
LABEL_161:
        ActivationFactory = -2147024809;
        goto LABEL_162;
      }
      v25 = gpCatalog;
      *(_QWORD *)PrivilegeSetLength = 0;
      if ( !gpCatalog )
      {
        ppvObj = 0;
        ActivationFactory = CComCatalog::InitializeCatalogIfNecessary(&s_catalogObject);
        if ( ActivationFactory < 0 )
        {
          v26 = 189;
LABEL_51:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            v26,
            "onecore\\com\\combase\\catalog\\catalog.cxx",
            ActivationFactory);
LABEL_64:
          if ( ActivationFactory >= 0 )
          {
            dwActivationType = 0;
            pRuntimeClassInfo->GetActivationType(pRuntimeClassInfo, &dwActivationType);
            v28 = dwActivationType;
            dwTrustLevel = 0;
            pRuntimeClassInfo->GetTrustLevel(pRuntimeClassInfo, &dwTrustLevel);
            trustLevel = dwTrustLevel;
            dwRegistrationScope = 0;
            pRuntimeClassInfo->GetRegistrationScope(pRuntimeClassInfo, &dwRegistrationScope);
            dwActivateAsUser = 0;
            pRuntimeClassInfo->GetActivateAsUser(pRuntimeClassInfo, &dwActivateAsUser);
            activateAsUser = dwActivateAsUser;
            activateInBrokerForMediumILContainer = 0;
            v31 = pRuntimeClassInfo->GetActivateInBrokerForMediumILContainer(
                    pRuntimeClassInfo,
                    &activateInBrokerForMediumILContainer);
            v32 = v31;
            if ( v31 < 0 )
            {
              wil::details::in1diag3::Return_Hr(retaddr, 0x440u, "onecore\\com\\combase\\winrtbase\\winrtbase.cpp", v31);
              return v32;
            }
            v33 = 0;
            sharedUsagePropertyPresent = 0;
            desktopApplicationPath = 0;
            ActivationFactory = DetermineActivationActionForRequest(
                                  activatableClassId,
                                  v28,
                                  (Windows::Foundation::RegistrationScope)dwRegistrationScope,
                                  userContext,
                                  activateAsUser,
                                  trustLevel,
                                  activateInBrokerForMediumILContainer,
                                  (ActivationAction *)&sharedUsagePropertyPresent,
                                  &desktopApplicationPath);
            if ( ActivationFactory >= 0 )
            {
              activateInSharedBroker = 0;
              if ( sharedUsagePropertyPresent )
              {
                switch ( sharedUsagePropertyPresent )
                {
                  case 1:
                    pRuntimeClassInfo->GetActivateInSharedBroker(pRuntimeClassInfo, &activateInSharedBroker);
                    if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                      McGenEventWrite_EtwEventWriteTransfer(
                        &COM_PERFORMANCE_PROVIDER_Context,
                        &WinRT_BrokeredGetActivationFactory_Start,
                        v38,
                        1u,
                        &Context);
                    v35 = v77;
                    ActivationFactory = RuntimeBrokerActivation(
                                          activatableClassId,
                                          1,
                                          userContext,
                                          activateInSharedBroker != 0,
                                          v77,
                                          (void **)factory);
                    if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                    {
                      v37 = &WinRT_BrokeredGetActivationFactory_Stop;
                      goto LABEL_146;
                    }
                    break;
                  case 2:
                    if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                      McGenEventWrite_EtwEventWriteTransfer(
                        &COM_PERFORMANCE_PROVIDER_Context,
                        &WinRT_DesktopBrokeredGetActivationFactory_Start,
                        v34,
                        1u,
                        &Context);
                    v35 = v77;
                    ActivationFactory = DesktopBrokeredGetActivationFactory(
                                          activatableClassId,
                                          desktopApplicationPath,
                                          v77,
                                          (void **)factory);
                    WindowsDeleteString(desktopApplicationPath);
                    if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                    {
                      v37 = &WinRT_DesktopBrokeredGetActivationFactory_Stop;
LABEL_146:
                      McGenEventWrite_EtwEventWriteTransfer(&COM_PERFORMANCE_PROVIDER_Context, v37, v36, 1u, &Context);
                    }
                    break;
                  case 3:
                    ActivationFactory = -2147024891;
                    goto LABEL_162;
                  default:
                    v35 = v77;
                    goto LABEL_150;
                }
LABEL_147:
                if ( ActivationFactory < 0 )
                  goto LABEL_162;
LABEL_150:
                pShimData = NtCurrentPeb()->pShimData;
                if ( pShimData )
                {
                  v67 = (void (__fastcall *)(PSECURITY_DESCRIPTOR, GUID *, _QWORD, _GUID *, IUnknown **))pShimData[558];
                  if ( v67 )
                  {
                    v68 = pRuntimeClassInfo;
                    pSecurityDescriptor = 0;
                    GrantedAccess = 0;
                    if ( pRuntimeClassInfo->GetActivationType(pRuntimeClassInfo, &GrantedAccess) >= 0 )
                    {
                      v69 = v68->__vftable;
                      if ( !GrantedAccess )
                      {
                        v70 = v69->GetDllPath(v68, (wchar_t **)&pSecurityDescriptor);
                        goto LABEL_158;
                      }
                      GetServerInfo = v69->GetServerInfo;
                      message = 0;
                      if ( GetServerInfo(v68, (IWinRTServerInfo **)&message) >= 0 && message )
                      {
                        v70 = (*(__int64 (__fastcall **)(wchar_t *, PSECURITY_DESCRIPTOR *))(*(_QWORD *)message + 48LL))(
                                message,
                                &pSecurityDescriptor);
                        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)message + 16LL))(message);
LABEL_158:
                        if ( v70 >= 0 )
                          v67(pSecurityDescriptor, &GUID_NULL, *((_QWORD *)activatableClassId + 2), v35, factory);
                      }
                    }
                  }
                }
                LogWinRTActivation(activatableClassId);
                ApiTelemetryLogger::LogApiCall(*((const wchar_t **)activatableClassId + 2));
                goto LABEL_162;
              }
              if ( v28 )
              {
                *(_QWORD *)&strSharedUsageServerPropertyName._header.Reserved.Reserved2[16] = L"Usage";
                strSharedUsageServerPropertyName._hstring = (HSTRING__ *)&strSharedUsageServerPropertyName._header;
                LOBYTE(sharedUsagePropertyPresent) = 0;
                *(_QWORD *)&Context.Size = 0;
                *(_QWORD *)&strSharedUsageServerPropertyValue._header.Reserved.Reserved2[16] = L"Shared";
                *(_OWORD *)&strSharedUsageServerPropertyName._header.Reserved.Reserved1 = 0x500000001uLL;
                strSharedUsageServerPropertyValue._hstring = (HSTRING__ *)&strSharedUsageServerPropertyValue._header;
                Context.Ptr = 0x600000001LL;
                *(_OWORD *)&strSharedUsageServerPropertyValue._header.Reserved.Reserved1 = 0x600000001uLL;
                if ( IsStringPropertyValuePresentInServerRegistration(
                       activatableClassId,
                       0,
                       &strSharedUsageServerPropertyName,
                       &strSharedUsageServerPropertyValue,
                       (bool *)&sharedUsagePropertyPresent) >= 0
                  && (_BYTE)sharedUsagePropertyPresent )
                {
                  v33 = 0x100000;
                }
                if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                  McGenEventWrite_EtwEventWriteTransfer(
                    &COM_PERFORMANCE_PROVIDER_Context,
                    &WinRT_OutOfProc_GetActivationFactory_Start,
                    v65,
                    1u,
                    &Context);
                v35 = v77;
                OneQI.pIID = v77;
                *(_QWORD *)&OneQI.hr = 0;
                OneQI.pItf = 0;
                ActivationFactory = WinRTGetActivationFactoryOfOutofprocClass(
                                      pRuntimeClassInfo,
                                      v64,
                                      v33,
                                      userContext,
                                      &OneQI);
                *factory = OneQI.pItf;
                if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                {
                  v37 = &WinRT_OutOfProc_GetActivationFactory_End;
                  goto LABEL_146;
                }
                goto LABEL_147;
              }
              if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) != 0 )
                McGenEventWrite_EtwEventWriteTransfer(
                  &COM_PERFORMANCE_PROVIDER_Context,
                  &WinRT_Inproc_GetActivationFactory_Start,
                  v34,
                  1u,
                  &Context);
              v39 = pRuntimeClassInfo;
              pSecurityDescriptor = 0;
              pRuntimeClassInfo->GetPermissions(pRuntimeClassInfo, &pSecurityDescriptor);
              v41 = g_WindowsEmptyStringInternal;
              if ( pSecurityDescriptor )
              {
                message = 0;
                SelfSid = ProcessToken::GetSelfSid(v40, (void **)&message);
                ActivationFactory = SelfSid;
                if ( SelfSid < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    0xA3u,
                    "onecore\\com\\combase\\objact\\objact.cxx",
                    SelfSid);
                  goto LABEL_87;
                }
                v43 = message;
                OneQI.pItf = 0;
                OneQI.hr = 0;
                OneQI.pIID = (const _GUID *)1;
                PrivilegeSetLength[0] = 20;
                Context = 0;
                GrantedAccess = 0;
                sharedUsagePropertyPresent = 0;
                if ( AccessCheckByType(
                       pSecurityDescriptor,
                       message,
                       (HANDLE)0xFFFFFFFFFFFFFFFCLL,
                       8u,
                       0,
                       0,
                       (PGENERIC_MAPPING)&Context,
                       (PPRIVILEGE_SET)&OneQI,
                       PrivilegeSetLength,
                       &GrantedAccess,
                       &sharedUsagePropertyPresent) )
                {
                  if ( sharedUsagePropertyPresent )
                  {
                    ActivationFactory = 0;
                  }
                  else
                  {
                    v44.__vftable = v39->__vftable;
                    ppvObj = 0;
                    ActivationFactory = -2147024891;
                    GetActivatableClassId = v44.GetActivatableClassId;
                    WindowsDeleteString(0);
                    ppvObj = 0;
                    GetActivatableClassId(v39, (HSTRING__ **)&ppvObj);
                    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
                    {
                      message = 0;
                      ConvertSidToStringSidW(v43, &message);
                      v46 = (wchar_t *)&pszValueToSet;
                      if ( message )
                        v46 = message;
                      if ( ppvObj )
                        v47 = (const wchar_t *)*((_QWORD *)ppvObj + 2);
                      else
                        v47 = g_WindowsEmptyStringInternal;
                      ComTraceMessage(
                        -1,
                        "onecore\\com\\combase\\objact\\objact.cxx",
                        "CheckActivationPermissions",
                        193,
                        ERRORS,
                        L"Access denied: Activatable class: %ws User sid: %ws",
                        v47,
                        v46);
                      if ( message )
                        LocalFree(message);
                    }
                    if ( ppvObj && (*(_BYTE *)ppvObj & 1) == 0 )
                      STRING_OPAQUE::Release((STRING_OPAQUE *)ppvObj);
                  }
                }
                else
                {
                  ActivationFactory = wil::details::in1diag3::Return_GetLastError(
                                        retaddr,
                                        0xB6u,
                                        "onecore\\com\\combase\\objact\\objact.cxx");
                }
                if ( ActivationFactory < 0 )
                  goto LABEL_87;
              }
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableActivationOfWinRTBothClassesInNA>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EnableActivationOfWinRTBothClassesInNA>::GetImpl'::`2'::impl);
              LOBYTE(sharedUsagePropertyPresent) = 0;
              if ( !IsEnabled )
              {
                PrivilegeSetLength[0] = 0;
                if ( (CClassCache::_dwFlags & 1) == 0 )
                  CClassCache::Init();
                message = 0;
                ActivationFactory = CClassCache::GetOrLoadWinRTInprocClass(
                                      v39,
                                      (IActivationFactory **)&message,
                                      (bool *)&sharedUsagePropertyPresent,
                                      (BothClassInNAExclusionReason *)PrivilegeSetLength);
                if ( ActivationFactory >= 0 )
                {
                  v63 = message;
                  v35 = v77;
                  ActivationFactory = (**(__int64 (__fastcall ***)(wchar_t *, _GUID *, IUnknown **))message)(
                                        message,
                                        v77,
                                        factory);
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v63 + 16LL))(v63);
                  goto LABEL_88;
                }
LABEL_87:
                v35 = v77;
LABEL_88:
                if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 1) == 0 )
                  goto LABEL_147;
                v37 = &WinRT_Inproc_GetActivationFactory_End;
                goto LABEL_146;
              }
              GrantedAccess = 0;
              if ( (CClassCache::_dwFlags & 1) == 0 )
                CClassCache::Init();
              message = 0;
              WinRTInprocClass = CClassCache::GetOrLoadWinRTInprocClass(
                                   v39,
                                   (IActivationFactory **)&message,
                                   (bool *)&sharedUsagePropertyPresent,
                                   (BothClassInNAExclusionReason *)&GrantedAccess);
              v50 = message;
              ActivationFactory = WinRTInprocClass;
              if ( WinRTInprocClass < 0 )
              {
                v35 = v77;
LABEL_133:
                if ( v50 )
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v50 + 16LL))(v50);
                goto LABEL_88;
              }
              v51 = 0;
              *(_QWORD *)PrivilegeSetLength = 0;
              if ( (_BYTE)sharedUsagePropertyPresent )
              {
                if ( (**(int (__fastcall ***)(wchar_t *, GUID *, DWORD *))message)(
                       message,
                       &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90,
                       PrivilegeSetLength) < 0 )
                {
                  v52.__vftable = v39->__vftable;
                  message = 0;
                  v52.GetActivatableClassId(v39, (HSTRING__ **)&message);
                  if ( message )
                    v41 = (const wchar_t *)*((_QWORD *)message + 2);
                  if ( ComTrace::IsEnabled(v54, v53) )
                  {
                    wil::details::static_lazy<ComTrace>::get(
                      v55,
                      _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
                    ComTrace::ActivatedNonAgileFactoryOfBothClassInNA_(v56, v41);
                  }
                  goto LABEL_128;
                }
                v51 = *(_QWORD *)PrivilegeSetLength;
              }
              v57 = GrantedAccess;
              if ( !GrantedAccess )
                goto LABEL_130;
              *(_QWORD *)PrivilegeSetLength = 0;
              if ( v51 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              if ( (**(int (__fastcall ***)(wchar_t *, GUID *, DWORD *))v50)(
                     v50,
                     &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90,
                     PrivilegeSetLength) < 0
                || v57 == 1 )
              {
                goto LABEL_130;
              }
              v58.__vftable = v39->__vftable;
              message = 0;
              v58.GetActivatableClassId(v39, (HSTRING__ **)&message);
              if ( message )
                v41 = (const wchar_t *)*((_QWORD *)message + 2);
              if ( ComTrace::IsEnabled(v60, v59) )
              {
                wil::details::static_lazy<ComTrace>::get(
                  v61,
                  _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
                ComTrace::ExcludedActivationOfBothClassWithAgileFactoryInNA_(
                  v62,
                  v41,
                  (BothClassInNAExclusionReason)v57);
              }
LABEL_128:
              if ( message )
                WindowsDeleteString((HSTRING)message);
LABEL_130:
              v35 = v77;
              ActivationFactory = (**(__int64 (__fastcall ***)(wchar_t *, _GUID *, IUnknown **))v50)(v50, v77, factory);
              if ( *(_QWORD *)PrivilegeSetLength )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)PrivilegeSetLength + 16LL))(*(_QWORD *)PrivilegeSetLength);
              goto LABEL_133;
            }
          }
LABEL_162:
          if ( pRuntimeClassInfo )
          {
            pRuntimeClassInfo->Release(pRuntimeClassInfo);
            return (unsigned int)ActivationFactory;
          }
          return (unsigned int)ActivationFactory;
        }
        ActivationFactory = CComCatalog::QueryInterface(&s_catalogObject, &IID_IComCatalog, &ppvObj);
        if ( ActivationFactory < 0 )
        {
          v26 = 190;
          goto LABEL_51;
        }
        if ( !ppvObj )
        {
          ActivationFactory = -2147024882;
          goto LABEL_64;
        }
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&gpCatalog, (signed __int64)ppvObj, 0) )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObj + 16LL))(ppvObj);
        v25 = gpCatalog;
      }
      ActivationFactory = v25->QueryInterface(
                            v25,
                            &GUID_22de7513_3849_4767_847d_c66aebc88040,
                            (void **)PrivilegeSetLength);
      if ( ActivationFactory >= 0 )
      {
        if ( g_processToken._userHiveOkState )
        {
          v27 = g_processToken._userHiveOkState == UserHiveIsOk;
        }
        else
        {
          sharedUsagePropertyPresent = 0;
          IsUserHiveOK((void *)0xFFFFFFFFFFFFFFFCLL, &sharedUsagePropertyPresent);
          if ( sharedUsagePropertyPresent )
          {
            g_processToken._userHiveOkState = UserHiveIsOk;
            v27 = 1;
          }
          else
          {
            g_processToken._userHiveOkState = UserHiveIsNotOk;
            v27 = 0;
          }
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, GUID *, IWinRTRuntimeClassInfo **, _QWORD))(**(_QWORD **)PrivilegeSetLength + 24LL))(
                              *(_QWORD *)PrivilegeSetLength,
                              (unsigned int)((v27 << 23) + 0x400000),
                              0,
                              *((_QWORD *)activatableClassId + 2),
                              0,
                              0,
                              &GUID_3ca31250_4cd0_42ef_a711_2f5686e69e07,
                              &pRuntimeClassInfo,
                              0);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)PrivilegeSetLength + 16LL))(*(_QWORD *)PrivilegeSetLength);
      }
      goto LABEL_64;
    }
    return (unsigned int)ActivationFactory;
  }
  message = 0;
  LOWORD(sharedUsagePropertyPresent) = 0;
  v11 = RtlLoadString(&_ImageBase, 5404, 0, 0, &message, &sharedUsagePropertyPresent, 0, 0);
  v12 = RtlNtStatusToDosError(v11);
  v13 = v12 < 0;
  if ( v12 > 0 )
    v13 = 1;
  if ( v13 )
    RoOriginateError(-2147418113, 0);
  else
    RoOriginateErrorW(-2147418113, (unsigned __int16)sharedUsagePropertyPresent, message);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180009ab0  push    rbp
0x180009ab2  push    rbx
0x180009ab3  push    rsi
0x180009ab4  push    r12
0x180009ab6  push    r13
0x180009ab8  lea     rbp, [rsp-60h]
0x180009abd  sub     rsp, 160h
0x180009ac4  mov     rax, cs:__security_cookie
0x180009acb  xor     rax, rsp
0x180009ace  mov     [rbp+80h+var_50], rax
0x180009ad2  xor     ebx, ebx
0x180009ad4  mov     [rbp+80h+var_F8], iid
0x180009ad8  mov     [factory], rbx
0x180009adb  mov     r13, factory
0x180009ade  mov     rax, gs:30h
0x180009ae7  mov     r12, userContext
0x180009aea  mov     rsi, activatableClassId
0x180009aed  mov     rax, [rax+1758h]
0x180009af4  test    rax, rax
0x180009af7  jnz     short loc_180009B33
0x180009af9  call    cs:__imp_GetCurrentThreadId
0x180009aff  mov     ecx, eax; dwThreadId
0x180009b01  call    ?TLSPreallocateData@@YAPEAUtagSOleTlsData@@K@Z; TLSPreallocateData(ulong)
0x180009b06  test    rax, rax
0x180009b09  jz      loc_18000A843
0x180009b0f  mov     activatableClassId, gs:30h
0x180009b18  mov     [activatableClassId+1758h], rax
0x180009b1f  mov     activatableClassId, gs:30h
0x180009b28  add     activatableClassId, 1758h
0x180009b2f  mov     [rax+20h], activatableClassId
0x180009b33  cmp     cs:g_cMTAInits, ebx
0x180009b39  ja      short loc_180009B4D
0x180009b3b  cmp     [rax+28h], ebx
0x180009b3e  jnz     short loc_180009B4D
0x180009b40  call    ?IsThreadInNTA@@YAHXZ; IsThreadInNTA(void)
0x180009b45  test    eax, eax
0x180009b47  jz      loc_18000A843
0x180009b4d  mov     rax, gs:30h
0x180009b56  mov     [rsp+180h+var_28], rdi
0x180009b5e  mov     [rsp+180h+var_30], r14
0x180009b66  mov     [rsp+180h+var_38], r15
0x180009b6e  mov     rax, [rax+1758h]
0x180009b75  test    rax, rax
0x180009b78  jnz     short loc_180009BB4
0x180009b7a  call    cs:__imp_GetCurrentThreadId
0x180009b80  mov     ecx, eax; dwThreadId
0x180009b82  call    ?TLSPreallocateData@@YAPEAUtagSOleTlsData@@K@Z; TLSPreallocateData(ulong)
0x180009b87  test    rax, rax
0x180009b8a  jz      loc_18000A837
0x180009b90  mov     activatableClassId, gs:30h
0x180009b99  mov     [activatableClassId+1758h], rax
0x180009ba0  mov     activatableClassId, gs:30h
0x180009ba9  add     activatableClassId, 1758h
0x180009bb0  mov     [rax+20h], activatableClassId
0x180009bb4  test    dword ptr [rax+14h], 800000h
0x180009bbb  jz      loc_180009C44
0x180009bc1  mov     [rsp+180h+pAction], rbx
0x180009bc6  lea     rax, [rsp+180h+sharedUsagePropertyPresent]
0x180009bcb  mov     [rsp+180h+GenericMapping], rbx
0x180009bd0  lea     activatableClassId, __ImageBase
0x180009bd7  mov     qword ptr [rsp+180h+trustLevel], rax
0x180009bdc  mov     edx, 151Ch
0x180009be1  lea     rax, [rsp+180h+message]
0x180009be6  mov     [rsp+180h+message], rbx
0x180009beb  xor     r9d, r9d
0x180009bee  mov     qword ptr [rsp+180h+activateAsUser], rax
0x180009bf3  xor     r8d, r8d
0x180009bf6  mov     word ptr [rsp+180h+sharedUsagePropertyPresent], bx
0x180009bfb  mov     edi, 8000FFFFh
0x180009c00  call    cs:__imp_RtlLoadString
0x180009c06  mov     ecx, eax; Status
0x180009c08  call    cs:__imp_RtlNtStatusToDosError
0x180009c0e  test    eax, eax
0x180009c10  jle     short loc_180009C1C
0x180009c12  movzx   eax, ax
0x180009c15  or      eax, 80070000h
0x180009c1a  test    eax, eax
0x180009c1c  mov     ecx, edi; error
0x180009c1e  js      short loc_180009C36
0x180009c20  movzx   edx, word ptr [rsp+180h+sharedUsagePropertyPresent]; cchMax
0x180009c25  mov     iid, [rsp+180h+message]; message
0x180009c2a  call    RoOriginateErrorW
0x180009c2f  mov     eax, edi
0x180009c31  jmp     loc_180009FF7
0x180009c36  xor     edx, edx; message
0x180009c38  call    RoOriginateError
0x180009c3d  mov     eax, edi
0x180009c3f  jmp     loc_180009FF7
0x180009c44  test    cs:?gMTHost@@3VCDllHost@@A._dwType, 100h; CDllHost gMTHost ...
0x180009c4e  jz      short loc_180009CCF
0x180009c50  mov     [rsp+180h+pAction], rbx
0x180009c55  lea     rax, [rsp+180h+sharedUsagePropertyPresent]
0x180009c5a  mov     [rsp+180h+GenericMapping], rbx
0x180009c5f  lea     activatableClassId, __ImageBase
0x180009c66  mov     qword ptr [rsp+180h+trustLevel], rax
0x180009c6b  mov     edx, 151Dh
0x180009c70  lea     rax, [rsp+180h+message]
0x180009c75  mov     [rsp+180h+message], rbx
0x180009c7a  xor     r9d, r9d
0x180009c7d  mov     qword ptr [rsp+180h+activateAsUser], rax
0x180009c82  xor     r8d, r8d
0x180009c85  mov     word ptr [rsp+180h+sharedUsagePropertyPresent], bx
0x180009c8a  mov     edi, 80080008h
0x180009c8f  call    cs:__imp_RtlLoadString
0x180009c95  mov     ecx, eax; Status
0x180009c97  call    cs:__imp_RtlNtStatusToDosError
0x180009c9d  test    eax, eax
0x180009c9f  jle     short loc_180009CAB
0x180009ca1  movzx   eax, ax
0x180009ca4  or      eax, 80070000h
0x180009ca9  test    eax, eax
0x180009cab  mov     ecx, edi; error
0x180009cad  js      short loc_180009CC3
0x180009caf  movzx   edx, word ptr [rsp+180h+sharedUsagePropertyPresent]; cchMax
0x180009cb4  mov     iid, [rsp+180h+message]; message
0x180009cb9  call    RoOriginateErrorW
0x180009cbe  jmp     loc_180009D78
0x180009cc3  xor     edx, edx; message
0x180009cc5  call    RoOriginateError
0x180009cca  jmp     loc_180009D78
0x180009ccf  mov     r8d, 2A5h; dwLine
0x180009cd5  lea     userContext, aOnecoreComComb_161; "onecore\\com\\combase\\objact\\dllhost."...
0x180009cdc  lea     activatableClassId, ?gMTHost@@3VCDllHost@@A._mxs; this
0x180009ce3  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180009ce8  test    byte ptr cs:?gMTHost@@3VCDllHost@@A._dwType, 40h; CDllHost gMTHost ...
0x180009cef  jz      short loc_180009CF5
0x180009cf1  mov     edi, ebx
0x180009cf3  jmp     short loc_180009D19
0x180009cf5  xor     edx, edx; ppMtaUsageIncrementor
0x180009cf7  xor     ecx, ecx; bFailIfNotInitialized
0x180009cf9  call    ?IncrementMTAUsageHelper@@YAJ_NPEAPEAU_MTA_USAGE_INCREMENTOR@@@Z; IncrementMTAUsageHelper(bool,_MTA_USAGE_INCREMENTOR * *)
0x180009cfe  mov     edi, eax
0x180009d00  test    eax, eax
0x180009d02  js      short loc_180009D19
0x180009d04  or      cs:?gMTHost@@3VCDllHost@@A._dwType, 40h; CDllHost gMTHost ...
0x180009d0b  lock inc cs:?gcActivationHostThreadInits@@3KA; ulong gcActivationHostThreadInits
0x180009d12  or      cs:?g_fMTAHostUsageFlags@@3W4MTA_HOST_USAGE_FLAGS@@A, 1; MTA_HOST_USAGE_FLAGS g_fMTAHostUsageFlags
0x180009d19  mov     eax, cs:?gMTHost@@3VCDllHost@@A._mxs._cLocks; CDllHost gMTHost ...
0x180009d1f  add     eax, 0FFFFFFFFh
0x180009d22  mov     cs:?gMTHost@@3VCDllHost@@A._mxs._cLocks, eax; CDllHost gMTHost ...
0x180009d28  jnz     short loc_180009D6B
0x180009d2a  movzx   ecx, cs:?gMTHost@@3VCDllHost@@A._mxs._lockOrder; CDllHost gMTHost ...
0x180009d31  cmp     cl, 13h
0x180009d34  jz      short loc_180009D6B
0x180009d36  mov     rax, gs:30h
0x180009d3f  mov     r14, [rax+1758h]
0x180009d46  test    r14, r14
0x180009d49  jz      short loc_180009D6B
0x180009d4b  mov     ebx, 1
0x180009d50  shl     ebx, cl
0x180009d52  test    [r14+240h], ebx
0x180009d59  jnz     short loc_180009D60
0x180009d5b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x180009d60  not     ebx
0x180009d62  and     [r14+240h], ebx
0x180009d69  xor     ebx, ebx
0x180009d6b  lea     activatableClassId, ?gMTHost@@3VCDllHost@@A._mxs._cs; lpCriticalSection
0x180009d72  call    cs:__imp_LeaveCriticalSection
0x180009d78  test    edi, edi
0x180009d7a  js      loc_18000A83C
0x180009d80  mov     [rbp+80h+pRuntimeClassInfo], rbx
0x180009d84  test    rsi, rsi
0x180009d87  jz      loc_18000A816
0x180009d8d  mov     eax, [rsi+4]
0x180009d90  test    eax, eax
0x180009d92  jz      short loc_180009DCE
0x180009d94  mov     edx, [rsi]
0x180009d96  test    dl, 10h
0x180009d99  jnz     short loc_180009DBC
0x180009d9b  mov     activatableClassId, [rsi+10h]
0x180009d9f  lea     iid, [activatableClassId+rax*2]
0x180009da3  cmp     activatableClassId, iid
0x180009da6  jnb     short loc_180009DB7
0x180009da8  cmp     word ptr [activatableClassId], 0
0x180009dac  jz      short loc_180009E10
0x180009dae  add     activatableClassId, 2
0x180009db2  cmp     activatableClassId, iid
0x180009db5  jb      short loc_180009DA8
0x180009db7  or      edx, 10h
0x180009dba  mov     [rsi], edx
0x180009dbc  test    dl, 8
0x180009dbf  jnz     loc_18000A816
0x180009dc5  test    rsi, rsi
0x180009dc8  jz      loc_18000A816
0x180009dce  mov     eax, [rsi+4]
0x180009dd1  dec     eax
0x180009dd3  cmp     eax, 0FFh
0x180009dd8  ja      loc_18000A816
0x180009dde  mov     activatableClassId, cs:?gpCatalog@@3PEAUIComCatalog@@EA; IComCatalog * gpCatalog
0x180009de5  mov     qword ptr [rsp+180h+PrivilegeSetLength], rbx
0x180009dea  test    activatableClassId, activatableClassId
0x180009ded  jnz     loc_180009E89
0x180009df3  lea     activatableClassId, s_catalogObject; this
0x180009dfa  mov     [rbp+80h+ppvObj], rbx
0x180009dfe  call    ?InitializeCatalogIfNecessary@CComCatalog@@QEAAJXZ; CComCatalog::InitializeCatalogIfNecessary(void)
0x180009e03  mov     edi, eax
0x180009e05  test    eax, eax
0x180009e07  jns     short loc_180009E15
0x180009e09  mov     edx, 0BDh
0x180009e0e  jmp     short loc_180009E37
0x180009e10  or      edx, 18h
0x180009e13  jmp     short loc_180009DBA
0x180009e15  lea     iid, [rbp+80h+ppvObj]; ppvObj
0x180009e19  lea     userContext, IID_IComCatalog; riid
0x180009e20  lea     activatableClassId, s_catalogObject; this
0x180009e27  call    ?QueryInterface@CComCatalog@@UEAAJAEBU_GUID@@PEAPEAX@Z; CComCatalog::QueryInterface(_GUID const &,void * *)
0x180009e2c  mov     edi, eax
0x180009e2e  test    eax, eax
0x180009e30  jns     short loc_180009E52
0x180009e32  mov     edx, 0BEh; lineNumber
0x180009e37  mov     activatableClassId, [rbp+88h]; callerReturnAddress
0x180009e3e  lea     iid, aOnecoreComComb_111; "onecore\\com\\combase\\catalog\\catalog"...
0x180009e45  mov     r9d, edi; hr
0x180009e48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e4d  jmp     loc_180009F4E
0x180009e52  mov     activatableClassId, [rbp+80h+ppvObj]
0x180009e56  test    activatableClassId, activatableClassId
0x180009e59  jnz     short loc_180009E65
0x180009e5b  mov     edi, 8007000Eh
0x180009e60  jmp     loc_180009F4E
0x180009e65  xor     eax, eax
0x180009e67  lock cmpxchg cs:?gpCatalog@@3PEAUIComCatalog@@EA, activatableClassId; IComCatalog * gpCatalog
0x180009e70  jz      short loc_180009E82
0x180009e72  mov     activatableClassId, [rbp+80h+ppvObj]
0x180009e76  mov     rax, [activatableClassId]
0x180009e79  mov     rax, [rax+10h]
0x180009e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e82  mov     activatableClassId, cs:?gpCatalog@@3PEAUIComCatalog@@EA; IComCatalog * gpCatalog
0x180009e89  mov     rax, [activatableClassId]
0x180009e8c  lea     iid, [rsp+180h+PrivilegeSetLength]
0x180009e91  lea     userContext, _GUID_22de7513_3849_4767_847d_c66aebc88040
0x180009e98  mov     rax, [rax]
0x180009e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea0  mov     edi, eax
0x180009ea2  test    eax, eax
0x180009ea4  js      loc_180009F4E
0x180009eaa  mov     eax, cs:?g_processToken@@3VProcessToken@@A._userHiveOkState; ProcessToken g_processToken ...
0x180009eb0  test    eax, eax
0x180009eb2  jz      short loc_180009EBE
0x180009eb4  cmp     eax, 1
0x180009eb7  mov     edx, ebx
0x180009eb9  setz    dl
0x180009ebc  jmp     short loc_180009EF7
0x180009ebe  lea     userContext, [rsp+180h+sharedUsagePropertyPresent]; fOK
0x180009ec3  mov     [rsp+180h+sharedUsagePropertyPresent], ebx
0x180009ec7  mov     activatableClassId, 0FFFFFFFFFFFFFFFCh; hToken
0x180009ece  call    IsUserHiveOK
0x180009ed3  cmp     [rsp+180h+sharedUsagePropertyPresent], 0
0x180009ed8  jz      short loc_180009EEB
0x180009eda  mov     cs:?g_processToken@@3VProcessToken@@A._userHiveOkState, 1; ProcessToken g_processToken ...
0x180009ee4  mov     edx, 1
0x180009ee9  jmp     short loc_180009EF7
0x180009eeb  mov     cs:?g_processToken@@3VProcessToken@@A._userHiveOkState, 2; ProcessToken g_processToken ...
0x180009ef5  mov     edx, ebx
0x180009ef7  mov     activatableClassId, qword ptr [rsp+180h+PrivilegeSetLength]
0x180009efc  lea     iid, [rbp+80h+pRuntimeClassInfo]
0x180009f00  mov     factory, [rsi+10h]
0x180009f04  mov     [rsp+180h+pDesktopApplicationPath], rbx
0x180009f09  mov     [rsp+180h+pAction], iid
0x180009f0e  lea     iid, _GUID_3ca31250_4cd0_42ef_a711_2f5686e69e07
0x180009f15  mov     rax, [activatableClassId]
0x180009f18  mov     [rsp+180h+GenericMapping], iid
0x180009f1d  xor     r8d, r8d
0x180009f20  shl     edx, 17h
0x180009f23  add     edx, 400000h
0x180009f29  mov     [rsp+180h+trustLevel], ebx
0x180009f2d  mov     rax, [rax+18h]
0x180009f31  mov     qword ptr [rsp+180h+activateAsUser], rbx
0x180009f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3b  mov     activatableClassId, qword ptr [rsp+180h+PrivilegeSetLength]
0x180009f40  mov     edi, eax
0x180009f42  mov     rax, [activatableClassId]
0x180009f45  mov     rax, [rax+10h]
0x180009f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f4e  test    edi, edi
0x180009f50  js      loc_18000A81B
0x180009f56  mov     activatableClassId, [rbp+80h+pRuntimeClassInfo]
0x180009f5a  lea     userContext, [rbp+80h+dwActivationType]
0x180009f5e  mov     [rbp+80h+dwActivationType], ebx
0x180009f61  mov     rax, [activatableClassId]
0x180009f64  mov     rax, [rax+20h]
0x180009f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f6d  mov     activatableClassId, [rbp+80h+pRuntimeClassInfo]
0x180009f71  lea     userContext, [rbp+80h+dwTrustLevel]
0x180009f75  mov     r14d, [rbp+80h+dwActivationType]
0x180009f79  mov     [rbp+80h+dwTrustLevel], ebx
0x180009f7c  mov     rax, [activatableClassId]
0x180009f7f  mov     rax, [rax+40h]
0x180009f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f88  mov     activatableClassId, [rbp+80h+pRuntimeClassInfo]
0x180009f8c  lea     userContext, [rbp+80h+dwRegistrationScope]
0x180009f90  mov     edi, [rbp+80h+dwTrustLevel]
0x180009f93  mov     [rbp+80h+dwRegistrationScope], ebx
0x180009f96  mov     rax, [activatableClassId]
0x180009f99  mov     rax, [rax+48h]
0x180009f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa2  mov     activatableClassId, [rbp+80h+pRuntimeClassInfo]
0x180009fa6  lea     userContext, [rbp+80h+dwActivateAsUser]
0x180009faa  mov     [rbp+80h+dwActivateAsUser], ebx
0x180009fad  mov     rax, [activatableClassId]
  ... truncated ...
```
