# CSyncClientCall::SendReceive2(tagRPCOLEMESSAGE *,ulong *)

- ea: `0x1800bdc30`
- end: `0x1800befe1`
- name: `?SendReceive2@CSyncClientCall@@UEAAJPEAUtagRPCOLEMESSAGE@@PEAK@Z`
- size: `5041`
- prototype: `HRESULT __fastcall(CSyncClientCall *this, tagRPCOLEMESSAGE *pMessage, unsigned int *pstatus)`
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800cbba0`

## callees

- `0x180003d84`
- `0x180006710`
- `0x18000712c`
- `0x18000833c`
- `0x18000b408`
- `0x180012e50`
- `0x1800188a0`
- `0x180019100`
- `0x18001f124`
- `0x180038a30`
- `0x18003a8bc`
- `0x1800472a0`
- `0x180056ce0`
- `0x180058e20`
- `0x18005a880`
- `0x180065188`
- `0x1800678f0`
- `0x18006c1d0`
- `0x1800789c0`
- `0x1800865f4`
- `0x1800874e0`
- `0x1800880f8`
- `0x18008e230`
- `0x18009f724`
- `0x1800a3f50`
- `0x1800bdc30`
- `0x1800c1034`
- `0x1800c3b50`
- `0x1800cd798`
- `0x1800ed9ec`
- `0x1800fe35c`
- `0x180106d58`
- `0x180158334`
- `0x180165c44`
- `0x1801688d4`
- `0x18017791c`
- `0x180179024`
- `0x180186018`
- `0x18018abe4`
- `0x18018db98`
- `0x1801999b0`
- `0x18019b278`
- `0x1801c9df0`
- `0x1801fdb10`
- `0x1802135dd`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `RPCRT4!RpcErrorEndEnumeration` at `0x1800bea82`
- `RPCRT4!RpcErrorEndEnumeration` at `0x1800bea82`
- `RPCRT4!I_RpcAsyncSetHandle` at `0x1800be1db`
- `RPCRT4!I_RpcAsyncSetHandle` at `0x1800be1db`
- `RPCRT4!RpcErrorStartEnumeration` at `0x1800be8e2`
- `RPCRT4!RpcErrorStartEnumeration` at `0x1800be8e2`
- `RPCRT4!RpcErrorGetNextRecord` at `0x1800be91f`
- `RPCRT4!RpcErrorGetNextRecord` at `0x1800be91f`
- `ntdll!RtlApplicationVerifierStop` at `0x1800bdd17`
- `ntdll!RtlApplicationVerifierStop` at `0x1800bdd17`
- `ntdll!EtwEventActivityIdControl` at `0x1800be199`
- `ntdll!EtwEventActivityIdControl` at `0x1800be1af`
- `ntdll!EtwEventActivityIdControl` at `0x1800be3a9`
- `ntdll!EtwEventActivityIdControl` at `0x1800be199`
- `ntdll!EtwEventActivityIdControl` at `0x1800be1af`
- `ntdll!EtwEventActivityIdControl` at `0x1800be3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bde7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bdee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800be885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bde7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bdee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800be885`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800be49e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800be4dd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800be49e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800be4dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800bdeaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be53e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800bdeaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800be53e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800be4b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800be4b9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!AllowSetForegroundWindow` at `0x1800be0c6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!AllowSetForegroundWindow` at `0x1800be0c6`

## string_xrefs

- `0x1800beba2`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x1800be7c0`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800bec37`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800becbf`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800bee03`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800bee4b`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800be35c`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800befcf`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800be97d`: `onecore\com\combase\callheaders\networkcallheaders.cpp`
- `0x1800be9d9`: `onecore\com\combase\callheaders\networkcallheaders.cpp`
- `0x1800bdce3`: `A lock is being held across a COM call (examine current stack)`

## pseudocode

```c
__int64 __fastcall CSyncClientCall::SendReceive2(
        CSyncClientCall *this,
        tagRPCOLEMESSAGE *pMessage,
        unsigned int *pstatus)
{
  __int64 v4; // rbx
  unsigned int cbBuffer; // edi
  int v6; // eax
  bool v7; // zf
  IErrorInfo *ReservedForOle; // rax
  HRESULT v9; // eax
  BOOL v10; // r12d
  tagIPIDEntry *pServerIPIDEntry; // rax
  GUID *p_ipid; // rax
  OXIDEntry *pServerOXIDEntry; // rax
  GUID *p_moxid; // rax
  unsigned int dwPid; // ebx
  tagRPCOLEMESSAGE *v16; // rdi
  _DWORD *v17; // rsi
  DWORD TickCount; // eax
  OXIDEntry *v19; // rcx
  unsigned int v20; // r13d
  int v21; // eax
  OXIDEntry *v22; // rcx
  unsigned int v23; // ebx
  _DWORD *v24; // rdx
  HRESULT v25; // eax
  HRESULT (__fastcall *DispatchCrossApartmentCall)(tagRPCOLEMESSAGE *, OXIDEntry *, CSyncClientCall *); // r9
  int v27; // r15d
  __int64 dwFlags; // rcx
  __int64 v29; // rax
  int v30; // eax
  OXIDEntry *v31; // rax
  _BYTE *v32; // rdi
  int v33; // eax
  int v34; // r13d
  int v35; // eax
  char v36; // cl
  int v37; // r10d
  unsigned int *v38; // rbx
  const ThreadTypeSpecificRoutines *v39; // rax
  unsigned __int64 v40; // rbx
  HRESULT v41; // eax
  void (__fastcall *v42)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  unsigned int v43; // edi
  int v44; // ebx
  const _GUID *v45; // r8
  __int64 v46; // rax
  OXIDEntry *v47; // rcx
  const WireThat *v48; // rdi
  unsigned int v49; // r12d
  __int64 v50; // rbx
  __int64 v51; // rcx
  unsigned int *v52; // rsi
  CStdIdentity *pStdId; // rbx
  void **v55; // rax
  _GUID *v56; // rdi
  IErrorInfo *ptr; // rsi
  unsigned int v58; // ebx
  unsigned __int64 OIDForTracing; // rax
  const _EVENT_DESCRIPTOR *v60; // rdx
  _MCGEN_TRACE_CONTEXT *v61; // rcx
  IErrorInfo *v62; // rcx
  unsigned int v63; // ebx
  unsigned int *v64; // r8
  unsigned int v65; // eax
  int *v66; // rax
  RPC_STATUS started; // eax
  __int64 v68; // rax
  int v69; // r8d
  int v70; // ecx
  char *AnsiString; // rbx
  unsigned int v72; // eax
  HRESULT v73; // eax
  char v74; // r13
  int v75; // ebx
  tagRPCOLEMESSAGE *v76; // rcx
  __int64 v77; // r8
  unsigned int v78; // ecx
  __int64 v79; // rdi
  __int64 v80; // rcx
  __int64 v81; // rcx
  unsigned int v82; // ebx
  const WireLocalThat *v83; // rdx
  HRESULT v84; // eax
  unsigned int v85; // edx
  __int64 v86; // rcx
  __int64 v87; // rcx
  IErrorInfo *v88; // rbx
  HRESULT v89; // eax
  IErrorInfo *v90; // rcx
  unsigned int v91; // ebx
  void *v92; // rax
  void *v93; // rdi
  _DWORD *v94; // rdx
  CStdIdentity *v95; // rbx
  bool v96; // di
  unsigned __int64 v97; // rax
  tagRPCOLEMESSAGE *v98; // rcx
  __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // rbx
  __int64 v102; // rcx
  unsigned int v103; // edi
  const WireContainerThat *v104; // rbx
  HRESULT ErrorInfoFromContainerThat; // eax
  HRESULT v106; // eax
  IErrorInfo *v107; // r8
  Microsoft::WRL::ComPtr<IErrorInfo> *v108; // rcx
  unsigned int *v109; // rcx
  void *v110; // rcx
  CStdIdentity *v111; // rcx
  PVOID Value3; // [rsp+30h] [rbp-D0h]
  PCSTR Description4; // [rsp+48h] [rbp-B8h]
  unsigned int size; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::WRL::ComPtr<IErrorInfo> errorInfo; // [rsp+68h] [rbp-98h] BYREF
  char v116; // [rsp+70h] [rbp-90h]
  unsigned int passthroughDataSize; // [rsp+74h] [rbp-8Ch] BYREF
  const WireContainerThat *passthroughData; // [rsp+78h] [rbp-88h] BYREF
  tagRPCOLEMESSAGE *v119; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *pulStatus; // [rsp+88h] [rbp-78h] BYREF
  ErrorObjectCreator errorObjectCreator; // [rsp+90h] [rbp-70h] BYREF
  BOOL v122; // [rsp+98h] [rbp-68h]
  int v123; // [rsp+9Ch] [rbp-64h]
  unsigned int v124; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v125; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int dwTid; // [rsp+B0h] [rbp-50h] BYREF
  tagRPC_ERROR_ENUM_HANDLE EnumHandle; // [rsp+B8h] [rbp-48h] BYREF
  _GUID Buf1; // [rsp+D0h] [rbp-30h] BYREF
  GUID v129; // [rsp+E0h] [rbp-20h] BYREF
  char v130; // [rsp+F0h] [rbp-10h]
  _GUID iid; // [rsp+F8h] [rbp-8h] BYREF
  tagRPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+110h] [rbp+10h] BYREF
  wchar_t sz[17]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v134; // [rsp+1D2h] [rbp+D2h]
  _BYTE v135[30]; // [rsp+1E2h] [rbp+E2h] BYREF
  wchar_t v136[17]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v137; // [rsp+222h] [rbp+122h]
  _BYTE v138[30]; // [rsp+232h] [rbp+132h] BYREF
  _BYTE v139[80]; // [rsp+250h] [rbp+150h] BYREF
  ErrorObjectCreator *p_errorObjectCreator; // [rsp+2A0h] [rbp+1A0h]
  __int64 v141; // [rsp+2A8h] [rbp+1A8h]
  const WireContainerThat **p_passthroughData; // [rsp+2B0h] [rbp+1B0h]
  __int64 v143; // [rsp+2B8h] [rbp+1B8h]
  _GUID *p_Buf1; // [rsp+2C0h] [rbp+1C0h]
  __int64 v145; // [rsp+2C8h] [rbp+1C8h]
  unsigned __int64 RpcValues[5]; // [rsp+2D0h] [rbp+1D0h] BYREF
  void *retaddr; // [rsp+338h] [rbp+238h]

  pulStatus = pstatus;
  v119 = pMessage;
  passthroughDataSize = 0;
  v122 = 0;
  v123 = 0;
  memset(&ErrorInfo, 0, sizeof(ErrorInfo));
  memset(&EnumHandle, 0, sizeof(EnumHandle));
  if ( ComVerifierSettings::s_singleton._pSettingsState
    && ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyLocks
    && ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierIsCurrentThreadHoldingLocks() )
  {
    Description4 = ::Description4;
    HIDWORD(Value3) = 0;
    if ( gMockApplicationVerifierStop )
      ((void (__fastcall *)(__int64, const char *, _QWORD))gMockApplicationVerifierStop)(
        268436496,
        "A lock is being held across a COM call (examine current stack)",
        0);
    else
      RtlApplicationVerifierStop(
        0x10000410u,
        "A lock is being held across a COM call (examine current stack)",
        0,
        ::Description4,
        0,
        ::Description4,
        0,
        ::Description4,
        0,
        ::Description4);
  }
  v4 = *(_QWORD *)this->gapC0;
  cbBuffer = v119->cbBuffer;
  if ( (*(_BYTE *)(v4 + 20) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( cbBuffer > *(_DWORD *)(v4 + 528) )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x313u, "onecore\\com\\combase\\dcomrem\\call.cxx");
  v6 = *(_DWORD *)(v4 + 480) + *(_DWORD *)(v4 + 496) + *(_DWORD *)(v4 + 512);
  *(_DWORD *)(v4 + 528) = cbBuffer;
  v7 = g_hEventLogger == 0;
  *(_DWORD *)(v4 + 168) = cbBuffer + v6;
  iid = *(_GUID *)(*(_QWORD *)this->gapC0 + 120LL);
  if ( v7 )
    goto LABEL_24;
  ReservedForOle = (IErrorInfo *)NtCurrentTeb()->ReservedForOle;
  errorInfo.ptr_ = ReservedForOle;
  if ( !ReservedForOle )
  {
    if ( COleTls::TLSAllocData((COleTls *)&errorInfo) < 0 )
    {
LABEL_24:
      v10 = 0;
      goto LABEL_25;
    }
    ReservedForOle = errorInfo.ptr_;
  }
  if ( (HIDWORD(ReservedForOle[2].__vftable) & 0x410) != 0 || !g_pEventFire )
    goto LABEL_24;
  v9 = g_pEventFire->IsActive(g_pEventFire);
  v10 = v9 == 0;
  if ( !v9 )
  {
    pServerIPIDEntry = this->_pServerIPIDEntry;
    if ( pServerIPIDEntry )
      p_ipid = &pServerIPIDEntry->ipid;
    else
      p_ipid = &GUID_NULL;
    RpcValues[0] = (unsigned __int64)p_ipid;
    pServerOXIDEntry = this->_pServerOXIDEntry;
    if ( pServerOXIDEntry )
      p_moxid = &pServerOXIDEntry->_moxid;
    else
      p_moxid = &GUID_NULL;
    RpcValues[1] = (unsigned __int64)p_moxid;
    RpcValues[2] = (unsigned __int64)&v119;
    RpcValues[3] = (unsigned __int64)&iid;
    RpcValues[4] = *(unsigned __int16 *)(*(_QWORD *)this->gapC0 + 140LL);
    LogEventClientCall(RpcValues);
  }
LABEL_25:
  dwPid = this->_pServerOXIDEntry->_info.dwPid;
  if ( dwPid == GetCurrentProcessId() )
    *(_DWORD *)(*(_QWORD *)this->gapC0 + 216LL) |= 0x1000u;
  v16 = v119;
  passthroughData = (const WireContainerThat *)v119;
  v17 = NtCurrentTeb()->ReservedForOle;
  TickCount = GetTickCount();
  v19 = this->_pServerOXIDEntry;
  v20 = v17[105];
  v125 = TickCount;
  v21 = v17[106];
  v17[105] = v19->_info.dwPid;
  v17[106] = 0;
  v22 = this->_pServerOXIDEntry;
  v124 = v20;
  LODWORD(errorInfo.ptr_) = v21;
  v23 = v22->_info.dwPid;
  if ( v23 != GetCurrentProcessId() )
  {
    dwFlags = this->_pServerOXIDEntry->_info.dwFlags;
    if ( (dwFlags & 1) != 0 && (dwFlags & 0xC800000) != 0 )
    {
      v29 = *(_QWORD *)this->gapC0;
      dwFlags = *(unsigned __int16 *)(v29 + 140);
      Buf1 = *(_GUID *)(v29 + 120);
      if ( (_WORD)dwFlags == 11 )
      {
        v30 = memcmp_0(&Buf1, &IID_IOleObject, 0x10u);
        dwFlags = v30 == 0;
        if ( v30 )
          goto LABEL_55;
      }
      else if ( (_WORD)dwFlags != 7 || memcmp_0(&Buf1, &IID_IAdviseSink, 0x10u) )
      {
        goto LABEL_55;
      }
      if ( IsInSendMessageExPresent() )
        AllowSetForegroundWindow(this->_pServerOXIDEntry->_info.dwPid);
    }
LABEL_55:
    v31 = this->_pServerOXIDEntry;
    if ( (v31->_info.dwFlags & 0xC800000) != 0 )
      v17[106] = v31->_info.dwTid;
    v32 = *(_BYTE **)this->gapC0;
    v7 = (v32[20] & 0x24) == 0;
    Buf1 = this->_pStdId->m_moid;
    if ( !v7 )
      MicrosoftTelemetryAssertTriggeredNoArgs(dwFlags);
    v27 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v32 + 56LL))(v32);
    if ( v27 < 0 )
    {
LABEL_88:
      CMessageCall::ClientFreeRequestMessage((CMessageCall *)v32);
      *(_QWORD *)passthroughData->part1.unassignedPassthroughGuid_1.Data4 = 0;
LABEL_89:
      v20 = v124;
      goto LABEL_90;
    }
    v33 = *((_DWORD *)v32 + 5);
    v34 = 0;
    if ( (v33 & 0x200) == 0 )
    {
      errorObjectCreator.__vftable = 0;
      QueryUnbiasedInterruptTime((PULONGLONG)&errorObjectCreator);
      v40 = (unsigned __int64)errorObjectCreator.__vftable / 0x2710;
      *(_QWORD *)&sz[12] = GetTickCount64();
      v41 = CMessageCall::RpcSendRequestReceiveResponse((CMessageCall *)v32, &Buf1);
      errorObjectCreator.__vftable = 0;
      v27 = v41;
      QueryUnbiasedInterruptTime((PULONGLONG)&errorObjectCreator);
      OutgoingCallDiagnosis::RecordDurationOfCall((unsigned __int64)errorObjectCreator.__vftable / 0x2710 - v40);
      *(_QWORD *)passthroughData->part1.unassignedPassthroughGuid_1.Data4 = 0;
      goto LABEL_85;
    }
    if ( (v33 & 4) != 0 )
    {
      size = *((_DWORD *)v32 + 208);
      *((_DWORD *)v32 + 208) = size | 0x20000000;
      CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)&v32[**((int **)v32 + 1) + 8]);
    }
    v130 = 0;
    v129 = GUID_NULL;
    if ( memcmp_0(v32 + 272, &GUID_NULL, 0x10u) && !(unsigned int)EtwEventActivityIdControl(1, &v129) )
    {
      v35 = EtwEventActivityIdControl(2, v32 + 272);
      v36 = v130;
      if ( !v35 )
        v36 = 1;
      v130 = v36;
    }
    v27 = I_RpcAsyncSetHandle((PRPC_MESSAGE)(v32 + 144), (PRPC_ASYNC_STATE)(v32 + 680));
    if ( v27 )
    {
      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
        && (!gfEnableTracing || (WPP_GLOBAL_Control->ReserveSpace[28] & 1) == 0) )
      {
        goto LABEL_76;
      }
    }
    else if ( !gfEnableTracing || (WPP_GLOBAL_Control->ReserveSpace[28] & 8) == 0 )
    {
LABEL_76:
      if ( v130 )
        EtwEventActivityIdControl(2, &v129);
      if ( v27 )
      {
        v34 = 1;
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v32 + 166);
        *((_DWORD *)v32 + 54) |= 0x800000u;
        v38 = (unsigned int *)(v32 + 836);
        size = *((_DWORD *)v32 + 209);
        *((_DWORD *)v32 + 209) = 1;
        CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)&v32[**((int **)v32 + 1) + 8]);
        v27 = CAsyncCall::RpcSendRequest((CAsyncCall *)v32, &Buf1);
        *(_QWORD *)passthroughData->part1.unassignedPassthroughGuid_1.Data4 = 0;
        if ( v27 >= 0 )
        {
          v39 = ThreadTypeSpecific();
          v39->WaitForCall(this, WaitingForReply, 0xFFFFFFFF);
          v27 = CAsyncCall::RpcReceiveResponse((CAsyncCall *)v32, &Buf1);
LABEL_86:
          if ( v27 >= 0 || !v34 )
            goto LABEL_89;
          goto LABEL_88;
        }
        size = *v38;
        *v38 = 3;
        CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)((char *)v38 + **((int **)v32 + 1) - 828));
        ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall,>>>>>>::Release((ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall> > > > > > *)v32);
      }
LABEL_85:
      (*(void (__fastcall **)(_BYTE *, _QWORD))(*(_QWORD *)v32 + 32LL))(v32, (unsigned int)v27);
      goto LABEL_86;
    }
    wcscpy(sz, L"Guid unavailable");
    memset(v135, 0, sizeof(v135));
    v134 = 0;
    wStringFromGUID2((const _GUID *)(v32 + 28), sz, 40);
    wcscpy(v136, L"Guid unavailable");
    memset(v138, 0, sizeof(v138));
    v137 = 0;
    wStringFromGUID2(&Buf1, v136, 40);
    wcscpy((wchar_t *)v139, L"Guid unavailable");
    memset(&v139[34], 0, 46);
    wStringFromGUID2((const _GUID *)(v32 + 120), (wchar_t *)v139, 40);
    LODWORD(Description4) = v37;
    ComTraceWinError(
      v27,
      "onecore\\com\\combase\\dcomrem\\call.cxx",
      "CAsyncCall::CallI_RpcAsyncSetHandle",
      4289,
      L"I_RpcAsyncSetHandle for call object %p (iid:%ws MOID:%ws ipid:%ws method:%d): %!WINERROR!",
      v32,
      v139,
      v136,
      sz,
      Description4,
      v27);
    goto LABEL_76;
  }
  *(_QWORD *)(*(_QWORD *)this->gapC0 + 200LL) = 0;
  v24 = NtCurrentTeb()->ReservedForOle;
  if ( !v24 || (v24[5] & 0x1180) == 0 || (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x820) == 0x820 )
  {
    if ( !g_cMTAInits && (!v24 || (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x820) != 0x820) )
    {
      v25 = g_UninitializedThreadRoutines.DispatchCrossApartmentCall(v16, this->_pServerOXIDEntry, this);
      goto LABEL_45;
    }
    goto LABEL_43;
  }
  if ( (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x1000) != 0 )
  {
LABEL_43:
    DispatchCrossApartmentCall = g_DispatchOrImplicitMTAThreadRoutines.DispatchCrossApartmentCall;
    goto LABEL_44;
  }
  if ( (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x40400080) != 0x80 )
  {
    if ( (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x40400080) == 0x400080 )
    {
      v25 = g_ApplicationSTAThreadRoutines.DispatchCrossApartmentCall(v16, this->_pServerOXIDEntry, this);
      goto LABEL_45;
    }
    DispatchCrossApartmentCall = g_ExplicitMTAThreadRoutines.DispatchCrossApartmentCall;
    if ( (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x40400080) == 0x40000080 )
      DispatchCrossApartmentCall = g_BridgeSTAThreadRoutines.DispatchCrossApartmentCall;
LABEL_44:
    v25 = DispatchCrossApartmentCall(v16, this->_pServerOXIDEntry, this);
    goto LABEL_45;
  }
  v25 = g_ClassicSTAThreadRoutines.DispatchCrossApartmentCall(v16, this->_pServerOXIDEntry, this);
LABEL_45:
  v27 = v25;
LABEL_90:
  v43 = GetTickCount() - v125;
  if ( v43 > 0xC8 )
  {
    v44 = (v17[5] >> 19) & 1;
    Buf1 = *(_GUID *)(*(_QWORD *)this->gapC0 + 120LL);
    McGenEventRegister_EtwEventRegister(
      &S_olemsg_COM,
      v42,
      &S_olemsg_COM_Context,
      &S_olemsg_COM_Context.RegistrationHandle);
    if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 2) != 0 )
    {
      v46 = *(_QWORD *)this->gapC0;
      size = v27;
      v124 = v43;
      v125 = v44;
      LODWORD(passthroughData) = *(unsigned __int16 *)(v46 + 140);
      v47 = this->_pServerOXIDEntry;
      *(_QWORD *)&v139[24] = 4;
      *(_QWORD *)&v139[40] = 4;
      *(_QWORD *)&v139[56] = 4;
      LODWORD(errorObjectCreator.__vftable) = v47->_info.dwPid;
      dwTid = v47->_info.dwTid;
      *(_QWORD *)&v139[16] = &v125;
      *(_QWORD *)&v139[32] = &v124;
      *(_QWORD *)&v139[48] = &size;
      *(_QWORD *)&v139[64] = &dwTid;
      p_errorObjectCreator = &errorObjectCreator;
      p_passthroughData = &passthroughData;
      p_Buf1 = &Buf1;
      *(_QWORD *)&v139[72] = 4;
      v141 = 4;
      v143 = 4;
      v145 = 16;
      McGenEventWrite_EtwEventWriteTransfer(
        &S_olemsg_COM_Context,
        &ComCallDelayEvent,
        v45,
        8u,
        (_EVENT_DATA_DESCRIPTOR *)v139);
    }
  }
  v17[106] = errorInfo.ptr_;
  v17[105] = v20;
  if ( v10 )
    LogEventClientReturn(RpcValues);
  v48 = 0;
  v49 = 0;
  v116 = 0;
  if ( v27 )
  {
    if ( v27 == -2147467211 )
    {
      v116 = 1;
      if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        LODWORD(Value3) = -2147467211;
        ComTraceMessage(
          -2147467211,
          "onecore\\com\\combase\\dcomrem\\channelb.cxx",
          "CSyncClientCall::SendReceive2",
          5365,
          VERBOSE,
          L"Transforming result from %!HRESULT! to RPC_E_DISCONNECTED",
          Value3);
      }
      v27 = -2147417848;
    }
    else if ( v27 == -2147417848 && (*((_BYTE *)this + 272) & 4) != 0 )
    {
      pStdId = this->_pStdId;
      errorInfo.ptr_ = 0;
      v55 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IMarshalingStream>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationCatalogContext> >)&errorInfo);
      CStdIdentity::QueryInterface(pStdId, &GUID_00000000_0000_0000_c000_000000000046, v55);
      if ( (Microsoft_Windows_COM_RundownInstrumentationEnableBits[0] & 1) != 0 )
      {
        v56 = &this->_pServerIPIDEntry->ipid;
        ptr = errorInfo.ptr_;
        v58 = v119->iMethod & 0x7FFF;
        OIDForTracing = CStdIdentity::GetOIDForTracing(this->_pStdId);
        McTemplateU0xjqjp_EtwEventWriteTransfer(v61, v60, OIDForTracing, &iid, v58, v56, ptr);
        v48 = 0;
      }
      v62 = errorInfo.ptr_;
      if ( errorInfo.ptr_ )
      {
        errorInfo.ptr_ = 0;
        v62->Release(v62);
      }
    }
    v63 = this->_pServerOXIDEntry->_info.dwPid;
    if ( v63 == GetCurrentProcessId() )
    {
      v64 = (unsigned int *)(*(_QWORD *)this->gapC0 + 20LL);
      v65 = *v64;
      if ( (*v64 & 0x40000000) != 0 )
      {
        LODWORD(errorInfo.ptr_) = *v64;
        passthroughDataSize = v27;
        *v64 = v65 & 0xBFFFFFFF;
        v27 = 0;
        v66 = *(int **)(v64 - 3);
        v123 = 1;
        CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)((char *)v64 + *v66 - 12));
      }
      goto LABEL_134;
    }
    started = RpcErrorStartEnumeration(&EnumHandle);
    v122 = started == 0;
    if ( started )
    {
      v122 = 0;
LABEL_134:
      v52 = pulStatus;
      goto LABEL_135;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            ErrorInfo.Version = 1;
            ErrorInfo.Flags = 0;
            ErrorInfo.NumberOfParameters = 4;
            if ( RpcErrorGetNextRecord(&EnumHandle, 0, &ErrorInfo) )
              goto LABEL_134;
          }
          while ( ErrorInfo.GeneratingComponent != 11
               || ErrorInfo.NumberOfParameters != 1
               || ErrorInfo.Parameters[0].ParameterType != eeptBinary );
          v68 = *(_QWORD *)this->gapC0;
          v69 = ErrorInfo.Parameters[0].u.BVal.Size;
          passthroughDataSize = v27;
          v27 = 0;
          v123 = 1;
          v70 = *(_DWORD *)(v68 + 152) & 0xF0;
          v49 = 0;
          if ( (unsigned int)ErrorInfo.Parameters[0].u.BVal.Size >= 8 )
            break;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0xC3u,
            "onecore\\com\\combase\\callheaders\\networkcallheaders.cpp",
            -2147417839,
            "Buffer too small");
        }
        AnsiString = ErrorInfo.Parameters[0].u.AnsiString;
        if ( v70 != 16 )
          *(_DWORD *)ErrorInfo.Parameters[0].u.AnsiString = _byteswap_ulong(*(_DWORD *)ErrorInfo.Parameters[0].u.AnsiString);
        v72 = 0;
        size = 0;
        if ( *((_DWORD *)AnsiString + 1) )
          break;
LABEL_132:
        v49 = v72 + 8;
        v48 = (const WireThat *)AnsiString;
      }
      v73 = ProcessIncomingOrpcExtentArray<0>(v69 - 8, (WireExtentArray *)(AnsiString + 8), v70 != 16, &size);
      if ( v73 >= 0 )
      {
        v72 = size;
        goto LABEL_132;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xCBu,
        "onecore\\com\\combase\\callheaders\\networkcallheaders.cpp",
        v73);
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this->gapC0 + 56LL) + 48LL))(*(_QWORD *)this->gapC0 + 56LL) != 5 )
  {
    v50 = *(_QWORD *)this->gapC0;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v50 + 56) + 48LL))(v50 + 56) == 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v51);
    v49 = *(_DWORD *)(v50 + 560);
    v48 = *(const WireThat **)(v50 + 552);
  }
  v52 = pulStatus;
  v27 = ClientCallRetryContext::CalculateRetryStatus(
          (*((_DWORD *)NtCurrentTeb()->ReservedForOle + 5) & 0x40400080) == 128,
          *(ResponseMessageType *)(*(_QWORD *)this->gapC0 + 432LL),
          pulStatus);
  if ( v27 < 0 )
  {
    if ( this->_sourceOfHResult == Unknown )
      this->_sourceOfHResult = ServerSideChannelCallControl;
  }
  else if ( *v52 == -2147352577 )
  {
    return 2147614719LL;
  }
LABEL_135:
  v74 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this->gapC0 + 56LL) + 48LL))(*(_QWORD *)this->gapC0 + 56LL) != 5 )
  {
    v75 = v27;
    v27 = ClientNotify(v49, v48, *(_DWORD *)(*(_QWORD *)this->gapC0 + 152LL), v27, *(CMessageCall **)this->gapC0, 0);
    if ( v27 && !v75 && this->_sourceOfHResult == Unknown )
      this->_sourceOfHResult = ServerSideChannelGeneric;
    if ( v122 )
      RpcErrorEndEnumeration(&EnumHandle);
    if ( v123 )
    {
      if ( v27 )
        goto LABEL_178;
      v27 = passthroughDataSize;
    }
    if ( !v27 )
    {
      v76 = v119;
      v77 = *(_QWORD *)this->gapC0;
      if ( v119 != (tagRPCOLEMESSAGE *)-24LL )
      {
        v119->cbBuffer = *(_DWORD *)(v77 + 608);
        v76 = v119;
      }
      v76->Buffer = *(void **)(v77 + 600);
      v119->dataRepresentation = *(_DWORD *)(*(_QWORD *)this->gapC0 + 152LL);
      v78 = this->_pServerOXIDEntry->_info.dwFlags;
      if ( (v78 & 1) != 0 || (v78 & 4) != 0 )
      {
        v79 = *(_QWORD *)this->gapC0;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v79 + 56) + 48LL))(v79 + 56) == 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v80);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v79 + 56) + 48LL))(v79 + 56) == 5 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v81);
        v82 = *(_DWORD *)(v79 + 576);
        v83 = *(const WireLocalThat **)(v79 + 568);
        errorInfo.ptr_ = 0;
        passthroughDataSize = 0;
        passthroughData = 0;
        size = 0;
        v84 = ValidateAndCalculateSizeOfIncomingLocalThat(
                v82,
                v83,
                &size,
                (const WireContainerExtent **)&errorInfo,
                &passthroughDataSize,
                &passthroughData);
        if ( v84 < 0 )
        {
          v85 = 803;
LABEL_158:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            v85,
            "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
            v84);
          MicrosoftTelemetryAssertTriggeredNoArgs(v86);
          RoOriginateError(-2147417839, 0);
          v27 = -2147417839;
          if ( OXIDEntry::IsInLocalProcess(this->_pServerOXIDEntry) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v87);
          CMessageCall::ClientFreeResponseMessage(*(CMessageCall **)this->gapC0);
          v74 = 1;
          v119->Buffer = 0;
          goto LABEL_172;
        }
        if ( size != v82 )
        {
          v85 = 805;
          v84 = -2147417839;
          goto LABEL_158;
        }
        v88 = errorInfo.ptr_;
        if ( errorInfo.ptr_ )
        {
          errorInfo.ptr_ = 0;
          errorObjectCreator.__vftable = (ErrorObjectCreator_vtbl *)ErrorObjectCreator::`vftable';
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&errorInfo);
          v89 = CreateErrorInfoFromContainerErrorInformationExtent(
                  (const CONTAINER_EXTENT *)((char *)&v88->__vftable + 4),
                  &errorObjectCreator,
                  &errorInfo.ptr_);
          if ( v89 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, 0x1589u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v89);
          CoSetErrorInfo(0, errorInfo.ptr_);
          v90 = errorInfo.ptr_;
          if ( errorInfo.ptr_ )
          {
            errorInfo.ptr_ = 0;
            v90->Release(v90);
          }
        }
        v91 = passthroughDataSize;
        if ( passthroughDataSize )
        {
          v92 = MIDL_user_allocate(passthroughDataSize);
          v93 = v92;
          if ( v92 )
          {
            memcpy_0(v92, passthroughData, v91);
            v94 = NtCurrentTeb()->ReservedForOle;
            v94[142] = v91;
            *((_QWORD *)v94 + 70) = v93;
          }
          else
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              0x159Du,
              "onecore\\com\\combase\\dcomrem\\channelb.cxx",
              -2147024882);
          }
          v52 = pulStatus;
        }
      }
      v27 = *v52;
      goto LABEL_172;
    }
LABEL_178:
    v74 = 1;
    goto LABEL_172;
  }
  if ( v27 >= 0 )
  {
    v101 = *(_QWORD *)this->gapC0;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v101 + 56) + 48LL))(v101 + 56) != 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v102);
    v103 = *(_DWORD *)(v101 + 592);
    v104 = *(const WireContainerThat **)(v101 + 584);
    passthroughData = (const WireContainerThat *)ErrorObjectCreator::`vftable';
    pulStatus = 0;
    ErrorInfoFromContainerThat = CreateErrorInfoFromContainerThat(
                                   v103,
                                   v104,
                                   (ICreateErrorObjectFromProperties *)&passthroughData,
                                   (IErrorInfo **)&pulStatus);
    if ( ErrorInfoFromContainerThat < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        0x15CFu,
        "onecore\\com\\combase\\dcomrem\\channelb.cxx",
        ErrorInfoFromContainerThat);
    CoSetErrorInfo(0, (IErrorInfo *)pulStatus);
    errorInfo.ptr_ = 0;
    size = 0;
    v106 = CopyPassthroughDataFromContainerThat(
             v103,
             v104,
             (wistd::unique_ptr<WireContainerThat,wil::function_deleter<void (__cdecl*)(void *),&MIDL_user_free> > *)&errorInfo,
             &size);
    if ( v106 >= 0 )
    {
      v107 = 0;
      v108 = (Microsoft::WRL::ComPtr<IErrorInfo> *)NtCurrentTeb()->ReservedForOle;
      LODWORD(v108[71].ptr_) = size;
      v108[70].ptr_ = errorInfo.ptr_;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(retaddr, 0x15D5u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v106);
      v107 = errorInfo.ptr_;
    }
    if ( v107 )
      HeapFree(g_hHeap, 0, v107);
    v109 = pulStatus;
    if ( pulStatus )
    {
      pulStatus = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v109 + 16LL))(v109);
    }
  }
LABEL_172:
  if ( v116 )
  {
    v95 = this->_pStdId;
    v96 = (*((_BYTE *)this + 272) & 4) != 0;
    v97 = CStdIdentity::GetOIDForTracing(v95);
    InstrumentPrematureStubRundownFailure(
      &iid,
      v119->iMethod & 0x7FFF,
      &this->_pServerIPIDEntry->ipid,
      v97,
      v96,
      v27,
      v95,
      0,
      0);
  }
  if ( v27 )
  {
    v100 = *v52;
  }
  else
  {
    v98 = v119;
    v99 = *(_QWORD *)this->gapC0;
    if ( v119 != (tagRPCOLEMESSAGE *)-24LL )
    {
      v119->cbBuffer = *(_DWORD *)(v99 + 608);
      v98 = v119;
    }
    v98->Buffer = *(void **)(v99 + 600);
    v119->dataRepresentation = *(_DWORD *)(*(_QWORD *)this->gapC0 + 152LL);
    v27 = *v52;
    v100 = *v52;
  }
  if ( !v74 )
    goto LABEL_201;
  if ( v27 == -2147417851 )
  {
    v100 = *(unsigned int *)(*(_QWORD *)this->gapC0 + 448LL);
    *v52 = v100;
  }
  else if ( v27 )
  {
    v100 = (unsigned int)v27;
    *v52 = v27;
    v27 = -2147417852;
    goto LABEL_196;
  }
  if ( (_DWORD)v100 )
  {
LABEL_196:
    if ( (_DWORD)v100 == -2147418105
      || (_DWORD)v100 == -2147418094
      || (_DWORD)v100 == -2147417848
      || (_DWORD)v100 == -2147023174 )
    {
      CStdIdentity::SetConnectionStatus(this->_pStdId, v100);
    }
  }
LABEL_201:
  if ( !v27
    && ((unsigned __int8 (__fastcall *)(CSyncClientCall *, __int64))this->NeedsUnmarshalingTlsMitigation)(this, v100) )
  {
    this->_pushTlsMitigation._currentMitigation = UnmarshalingWithInprocOutParameterMitigation;
    v110 = NtCurrentTeb()->ReservedForOle;
    this->_pushTlsMitigation._savedMitigation = *((_DWORD *)v110 + 123);
    *((_DWORD *)v110 + 123) = 6;
  }
  if ( !*v52 )
  {
    v111 = this->_pStdId;
    if ( v111->m_ConnStatus )
      CStdIdentity::SetConnectionStatus(v111, 0);
  }
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1800bdc30  push    rbp
0x1800bdc32  push    rbx
0x1800bdc33  push    rdi
0x1800bdc34  push    r14
0x1800bdc36  push    r15
0x1800bdc38  lea     rbp, [rsp-210h]
0x1800bdc40  sub     rsp, 310h
0x1800bdc47  mov     rax, cs:__security_cookie
0x1800bdc4e  xor     rax, rsp
0x1800bdc51  mov     [rbp+230h+var_38], rax
0x1800bdc58  xorps   xmm0, xmm0
0x1800bdc5b  mov     [rbp+230h+pulStatus], pstatus
0x1800bdc5f  xor     eax, eax
0x1800bdc61  mov     [rbp+230h+var_2B0], pMessage
0x1800bdc65  xor     r15d, r15d
0x1800bdc68  mov     qword ptr [rbp+230h+ErrorInfo.Parameters.u+50h], rax
0x1800bdc6f  mov     [rbp+230h+EnumHandle.Head], rax
0x1800bdc73  mov     r14, this
0x1800bdc76  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x1800bdc7d  mov     [rsp+330h+passthroughDataSize], r15d
0x1800bdc82  mov     [rbp+230h+var_298], r15d
0x1800bdc86  mov     [rbp+230h+var_294], r15d
0x1800bdc8a  movups  xmmword ptr [rbp+230h+ErrorInfo.Version], xmm0
0x1800bdc8e  movups  xmmword ptr [rbp+230h+ErrorInfo.ProcessID], xmm0
0x1800bdc92  movups  xmmword ptr [rbp+230h+ErrorInfo.u+0Ch], xmm0
0x1800bdc96  movups  xmmword ptr [rbp+230h+ErrorInfo.NumberOfParameters], xmm0
0x1800bdc9a  movups  xmmword ptr [rbp+230h+ErrorInfo.Parameters.u], xmm0
0x1800bdc9e  movups  xmmword ptr [rbp+230h+ErrorInfo.Parameters.ParameterType+18h], xmm0
0x1800bdca2  movups  xmmword ptr [rbp+230h+ErrorInfo.Parameters.u+20h], xmm0
0x1800bdca6  movups  xmmword ptr [rbp+230h+ErrorInfo.Parameters.u+30h], xmm0
0x1800bdcad  movups  xmmword ptr [rbp+230h+ErrorInfo.Parameters.ParameterType+48h], xmm0
0x1800bdcb4  movups  xmmword ptr [rbp+230h+EnumHandle.Signature], xmm0
0x1800bdcb8  test    rax, rax
0x1800bdcbb  jz      short loc_1800BDD1D
0x1800bdcbd  cmp     [rax+3], r15b
0x1800bdcc1  jz      short loc_1800BDD1D
0x1800bdcc3  mov     rax, [rax+30h]
0x1800bdcc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdccc  test    eax, eax
0x1800bdcce  jz      short loc_1800BDD1D
0x1800bdcd0  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x1800bdcd7  lea     r9, Description4; Description1
0x1800bdcde  mov     [rsp+330h+Description4], r9; Description4
0x1800bdce3  lea     pMessage, aALockIsBeingHe; "A lock is being held across a COM call "...
0x1800bdcea  mov     [rsp+330h+Value4], r15; Value4
0x1800bdcef  xor     r8d, r8d; Value1
0x1800bdcf2  mov     [rsp+330h+Description3], r9; Description3
0x1800bdcf7  mov     ecx, 10000410h; Code
0x1800bdcfc  mov     [rsp+330h+Value3], r15; Value3
0x1800bdd01  mov     [rsp+330h+Description2], r9; Description2
0x1800bdd06  mov     [rsp+330h+Value2], r15; Value2
0x1800bdd0b  test    rax, rax
0x1800bdd0e  jz      short loc_1800BDD17
0x1800bdd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd15  jmp     short loc_1800BDD1D
0x1800bdd17  call    cs:__imp_RtlApplicationVerifierStop
0x1800bdd1d  mov     rbx, [r14+0C0h]
0x1800bdd24  mov     rax, [rbp+230h+var_2B0]
0x1800bdd28  test    byte ptr [rbx+14h], 4
0x1800bdd2c  mov     edi, [rax+18h]
0x1800bdd2f  jz      short loc_1800BDD36
0x1800bdd31  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!IsServerSideOfOutofprocCall()")
0x1800bdd36  cmp     edi, [rbx+210h]
0x1800bdd3c  ja      loc_1800BEFC8
0x1800bdd42  mov     eax, [rbx+200h]
0x1800bdd48  add     eax, [rbx+1F0h]
0x1800bdd4e  add     eax, [rbx+1E0h]
0x1800bdd54  mov     [rbx+210h], edi
0x1800bdd5a  add     eax, edi
0x1800bdd5c  cmp     cs:g_hEventLogger, r15
0x1800bdd63  mov     [rbx+0A8h], eax
0x1800bdd69  lea     rbx, GUID_NULL
0x1800bdd70  mov     rax, [r14+0C0h]
0x1800bdd77  mov     [rsp+330h+arg_18], rsi
0x1800bdd7f  mov     [rsp+330h+var_28], r12
0x1800bdd87  mov     [rsp+330h+var_30], r13
0x1800bdd8f  movups  xmm0, xmmword ptr [rax+78h]
0x1800bdd93  movups  xmmword ptr [rbp+230h+iid.Data1], xmm0
0x1800bdd97  jz      loc_1800BDE71
0x1800bdd9d  mov     rax, gs:30h
0x1800bdda6  mov     rax, [rax+1758h]
0x1800bddad  mov     [rsp+330h+errorInfo.ptr_], rax
0x1800bddb2  test    rax, rax
0x1800bddb5  jnz     short loc_1800BDDCE
0x1800bddb7  lea     this, [rsp+330h+errorInfo]; this
0x1800bddbc  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x1800bddc1  test    eax, eax
0x1800bddc3  js      loc_1800BDE71
0x1800bddc9  mov     rax, [rsp+330h+errorInfo.ptr_]
0x1800bddce  test    dword ptr [rax+14h], 410h
0x1800bddd5  jnz     loc_1800BDE71
0x1800bdddb  mov     this, cs:g_pEventFire
0x1800bdde2  test    this, this
0x1800bdde5  jz      loc_1800BDE71
0x1800bddeb  mov     rax, [this]
0x1800bddee  mov     rax, [rax+28h]
0x1800bddf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bddf7  test    eax, eax
0x1800bddf9  mov     r12d, r15d
0x1800bddfc  setz    r12b
0x1800bde00  test    eax, eax
0x1800bde02  jnz     short loc_1800BDE74
0x1800bde04  mov     rax, [r14+50h]
0x1800bde08  test    rax, rax
0x1800bde0b  jz      short loc_1800BDE13
0x1800bde0d  add     rax, 38h ; '8'
0x1800bde11  jmp     short loc_1800BDE16
0x1800bde13  mov     rax, rbx
0x1800bde16  mov     [rbp+230h+RpcValues], rax
0x1800bde1d  mov     rax, [r14+40h]
0x1800bde21  test    rax, rax
0x1800bde24  jz      short loc_1800BDE2E
0x1800bde26  add     rax, 0C8h
0x1800bde2c  jmp     short loc_1800BDE31
0x1800bde2e  mov     rax, rbx
0x1800bde31  mov     [rbp+230h+RpcValues+8], rax
0x1800bde38  lea     rax, [rbp+230h+var_2B0]
0x1800bde3c  mov     [rbp+230h+RpcValues+10h], rax
0x1800bde43  lea     rax, [rbp+230h+iid]
0x1800bde47  mov     [rbp+230h+RpcValues+18h], rax
0x1800bde4e  mov     rax, [r14+0C0h]
0x1800bde55  movzx   ecx, word ptr [rax+8Ch]
0x1800bde5c  mov     [rbp+230h+RpcValues+20h], this
0x1800bde63  lea     this, [rbp+230h+RpcValues]; RpcValues
0x1800bde6a  call    ?LogEventClientCall@@YAXPEA_K@Z; LogEventClientCall(unsigned __int64 *)
0x1800bde6f  jmp     short loc_1800BDE74
0x1800bde71  mov     r12d, r15d
0x1800bde74  mov     rax, [r14+40h]
0x1800bde78  mov     ebx, [rax+1Ch]
0x1800bde7b  call    cs:__imp_GetCurrentProcessId
0x1800bde81  cmp     ebx, eax
0x1800bde83  jnz     short loc_1800BDE96
0x1800bde85  mov     rax, [r14+0C0h]
0x1800bde8c  or      dword ptr [rax+0D8h], 1000h
0x1800bde96  mov     rax, gs:30h
0x1800bde9f  mov     rdi, [rbp+230h+var_2B0]
0x1800bdea3  mov     [rsp+330h+passthroughData], rdi
0x1800bdea8  mov     rsi, [rax+1758h]
0x1800bdeaf  call    cs:__imp_GetTickCount
0x1800bdeb5  mov     this, [r14+40h]
0x1800bdeb9  mov     r13d, [rsi+1A4h]
0x1800bdec0  mov     [rbp+230h+var_288], eax
0x1800bdec3  mov     eax, [rsi+1A8h]
0x1800bdec9  mov     edx, [this+1Ch]
0x1800bdecc  mov     [rsi+1A4h], edx
0x1800bded2  mov     [rsi+1A8h], r15d
0x1800bded9  mov     this, [r14+40h]
0x1800bdedd  mov     [rbp+230h+var_290], r13d
0x1800bdee1  mov     dword ptr [rsp+330h+errorInfo.ptr_], eax
0x1800bdee5  mov     ebx, [this+1Ch]
0x1800bdee8  call    cs:__imp_GetCurrentProcessId
0x1800bdeee  cmp     ebx, eax
0x1800bdef0  jnz     loc_1800BE042
0x1800bdef6  mov     rax, [r14+0C0h]
0x1800bdefd  mov     [rax+0C8h], r15
0x1800bdf04  mov     rax, gs:30h
0x1800bdf0d  mov     pMessage, [rax+1758h]
0x1800bdf14  test    pMessage, pMessage
0x1800bdf17  jz      loc_1800BDFEB
0x1800bdf1d  test    dword ptr [pMessage+14h], 1180h
0x1800bdf24  jz      loc_1800BDFEB
0x1800bdf2a  mov     rax, gs:30h
0x1800bdf33  mov     this, [rax+1758h]
0x1800bdf3a  mov     eax, [this+14h]
0x1800bdf3d  and     eax, 820h
0x1800bdf42  cmp     eax, 820h
0x1800bdf47  jz      loc_1800BDFEB
0x1800bdf4d  mov     rax, gs:30h
0x1800bdf56  mov     this, [rax+1758h]
0x1800bdf5d  test    dword ptr [this+14h], 1000h
0x1800bdf64  jnz     loc_1800BE021
0x1800bdf6a  mov     rax, gs:30h
0x1800bdf73  mov     this, [rax+1758h]
0x1800bdf7a  mov     eax, [this+14h]
0x1800bdf7d  and     eax, 40400080h
0x1800bdf82  cmp     eax, 80h
0x1800bdf87  jnz     short loc_1800BDF95
0x1800bdf89  mov     r9, cs:g_ClassicSTAThreadRoutines.DispatchCrossApartmentCall
0x1800bdf90  jmp     loc_1800BE028
0x1800bdf95  mov     rax, gs:30h
0x1800bdf9e  mov     this, [rax+1758h]
0x1800bdfa5  mov     eax, [this+14h]
0x1800bdfa8  and     eax, 40400080h
0x1800bdfad  cmp     eax, 400080h
0x1800bdfb2  jnz     short loc_1800BDFBD
0x1800bdfb4  mov     r9, cs:g_ApplicationSTAThreadRoutines.DispatchCrossApartmentCall
0x1800bdfbb  jmp     short loc_1800BE028
0x1800bdfbd  mov     rax, gs:30h
0x1800bdfc6  mov     r9, cs:g_ExplicitMTAThreadRoutines.DispatchCrossApartmentCall
0x1800bdfcd  mov     this, [rax+1758h]
0x1800bdfd4  mov     eax, [this+14h]
0x1800bdfd7  and     eax, 40400080h
0x1800bdfdc  cmp     eax, 40000080h
0x1800bdfe1  cmovz   r9, cs:g_BridgeSTAThreadRoutines.DispatchCrossApartmentCall
0x1800bdfe9  jmp     short loc_1800BE028
0x1800bdfeb  cmp     cs:g_cMTAInits, r15d
0x1800bdff2  ja      short loc_1800BE021
0x1800bdff4  test    pMessage, pMessage
0x1800bdff7  jz      short loc_1800BE018
0x1800bdff9  mov     rax, gs:30h
0x1800be002  mov     this, [rax+1758h]
0x1800be009  mov     eax, [this+14h]
0x1800be00c  and     eax, 820h
0x1800be011  cmp     eax, 820h
0x1800be016  jz      short loc_1800BE021
0x1800be018  mov     r9, cs:g_UninitializedThreadRoutines.DispatchCrossApartmentCall
0x1800be01f  jmp     short loc_1800BE028
0x1800be021  mov     r9, cs:g_DispatchOrImplicitMTAThreadRoutines.DispatchCrossApartmentCall
0x1800be028  mov     pMessage, [r14+40h]
0x1800be02c  mov     pstatus, r14
0x1800be02f  mov     this, rdi
0x1800be032  mov     rax, r9
0x1800be035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be03a  mov     r15d, eax
0x1800be03d  jmp     loc_1800BE53E
0x1800be042  mov     rax, [r14+40h]
0x1800be046  mov     ecx, [rax+50h]
0x1800be049  test    cl, 1
0x1800be04c  jz      short loc_1800BE0CC
0x1800be04e  test    ecx, 0C800000h
0x1800be054  jz      short loc_1800BE0CC
0x1800be056  mov     rax, [r14+0C0h]
0x1800be05d  movups  xmm0, xmmword ptr [rax+78h]
0x1800be061  movzx   ecx, word ptr [rax+8Ch]
0x1800be068  movups  [rbp+230h+Buf1], xmm0
0x1800be06c  cmp     cx, 0Bh
0x1800be070  jnz     short loc_1800BE096
0x1800be072  mov     r8d, 10h; Size
0x1800be078  lea     pMessage, IID_IOleObject; Buf2
0x1800be07f  lea     this, [rbp+230h+Buf1]; Buf1
0x1800be083  call    memcmp_0
0x1800be088  test    eax, eax
0x1800be08a  mov     ecx, r15d
0x1800be08d  setz    cl
0x1800be090  test    ecx, ecx
0x1800be092  jz      short loc_1800BE0CC
0x1800be094  jmp     short loc_1800BE0B6
0x1800be096  cmp     cx, 7
0x1800be09a  jnz     short loc_1800BE0CC
0x1800be09c  mov     r8d, 10h; Size
0x1800be0a2  lea     pMessage, IID_IAdviseSink; Buf2
0x1800be0a9  lea     this, [rbp+230h+Buf1]; Buf1
0x1800be0ad  call    memcmp_0
0x1800be0b2  test    eax, eax
0x1800be0b4  jnz     short loc_1800BE0CC
0x1800be0b6  call    IsInSendMessageExPresent
0x1800be0bb  test    al, al
0x1800be0bd  jz      short loc_1800BE0CC
0x1800be0bf  mov     this, [r14+40h]
0x1800be0c3  mov     ecx, [this+1Ch]; dwProcessId
0x1800be0c6  call    cs:__imp_AllowSetForegroundWindow
0x1800be0cc  mov     rax, [r14+40h]
0x1800be0d0  test    dword ptr [rax+50h], 0C800000h
0x1800be0d7  jz      short loc_1800BE0E2
0x1800be0d9  mov     eax, [rax+18h]
0x1800be0dc  mov     [rsi+1A8h], eax
0x1800be0e2  mov     rax, [r14+48h]
0x1800be0e6  mov     rdi, [r14+0C0h]
0x1800be0ed  movups  xmm0, xmmword ptr [rax+178h]
0x1800be0f4  test    byte ptr [rdi+14h], 24h
0x1800be0f8  movups  [rbp+230h+Buf1], xmm0
0x1800be0fc  jz      short loc_1800BE103
0x1800be0fe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pCall->IsClientSideOfOutofprocCall()")
0x1800be103  mov     rax, [rdi]
0x1800be106  mov     this, rdi
0x1800be109  mov     rax, [rax+38h]
0x1800be10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be112  mov     r15d, eax
0x1800be115  test    eax, eax
0x1800be117  js      loc_1800BE525
0x1800be11d  mov     eax, [rdi+14h]
0x1800be120  xor     r13d, r13d
0x1800be123  bt      eax, 9
0x1800be127  jnb     loc_1800BE496
0x1800be12d  test    al, 4
0x1800be12f  jz      short loc_1800BE164
0x1800be131  lea     pstatus, [rdi+340h]
0x1800be138  mov     eax, [pstatus]
0x1800be13b  lea     pMessage, [rsp+330h+size]
0x1800be140  mov     [rsp+330h+size], eax
0x1800be144  bts     eax, 1Dh
0x1800be148  mov     [pstatus], eax
0x1800be14b  mov     rax, [pstatus-338h]
0x1800be152  movsxd  this, dword ptr [rax]
0x1800be155  add     this, 0FFFFFFFFFFFFFCC8h
0x1800be15c  add     this, pstatus; this
0x1800be15f  call    ?DestroyOptionalRanking@?$RankingType@VEffectiveClsctxRanking@CPackagedComCatalog@@@EntryLookup@CPackagedComCatalog@@UEBAXAEAUOptionalRankingGeneric@23@@Z; CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking(CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &)
0x1800be164  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800be16b  mov     r8d, 10h; Size
0x1800be171  mov     [rbp+230h+var_240], r13b
0x1800be175  lea     pMessage, GUID_NULL; Buf2
0x1800be17c  lea     this, [rdi+110h]; Buf1
0x1800be183  movups  [rbp+230h+var_250], xmm0
0x1800be187  call    memcmp_0
0x1800be18c  test    eax, eax
0x1800be18e  jz      short loc_1800BE1C8
0x1800be190  lea     pMessage, [rbp+230h+var_250]
0x1800be194  mov     ecx, 1
0x1800be199  call    cs:__imp_EtwEventActivityIdControl
0x1800be19f  test    eax, eax
  ... truncated ...
```
