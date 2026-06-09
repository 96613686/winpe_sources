# CRIFTable::RegisterServerInterface(_GUID const &,IRpcStubBuffer *)

- ea: `0x18013830c`
- end: `0x180138e6d`
- name: `?RegisterServerInterface@CRIFTable@@QEAAJAEBU_GUID@@PEAUIRpcStubBuffer@@@Z`
- size: `2913`
- prototype: `HRESULT __fastcall(CRIFTable *this, const _GUID *iidOriginal, IRpcStubBuffer *stubOriginal)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180096ebc`

## callees

- `0x180006250`
- `0x180006390`
- `0x18000712c`
- `0x180022f94`
- `0x18002f1b0`
- `0x18003a8bc`
- `0x180063660`
- `0x1800865b8`
- `0x180087534`
- `0x18008db2c`
- `0x1800a08d0`
- `0x1800aa7ac`
- `0x1800cb3a0`
- `0x1800ea5f8`
- `0x18011b4d0`
- `0x18013830c`
- `0x1801462a8`
- `0x18014d5f4`
- `0x18014ebe8`
- `0x18015b904`
- `0x18017504c`
- `0x1801999b0`
- `0x1802135dd`
- `0x180255010`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x1801387dd`
- `RPCRT4!RpcServerRegisterIf3` at `0x1801387dd`
- `RPCRT4!RpcServerUnregisterIf` at `0x180138d28`
- `RPCRT4!RpcServerUnregisterIf` at `0x180138d28`
- `ntdll!RtlWakeAllConditionVariable` at `0x180138e0c`
- `ntdll!RtlWakeAllConditionVariable` at `0x180138e0c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1801385e6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1801385e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801385c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801385c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1801385da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1801385da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013864c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013864c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138aa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138bc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138dbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138aa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138bc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180138dbf`

## string_xrefs

- `0x18013837d`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013838c`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013840e`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013841e`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013850e`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013858d`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x18013894d`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138974`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138a29`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138a76`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138ad7`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138b2a`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138b92`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138be3`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138bfd`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138c5f`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138d8f`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138dcb`: `onecore\com\combase\dcomrem\riftbl.cxx`
- `0x180138515`: `Rewaiting on registration of IID %ls, attempt #%d`
- `0x1801383f2`: `RegisterServerInterface called during RIFTable cleanup`
- `0x180138b99`: `NdrCreateServerInterfaceFromStub %ls failed: %!WINERROR!`
- `0x180138c47`: `%ls already registered`
- `0x1801385d3`: `WARNING: ole32.dll has timed out on a condition variable, which may indicate deadlock.\nIf the issue you are debugging is unrelated to this wait, condition variable timeouts can be disabled for the duration of this function with the following debugger command:\ned ole32!g_fDisableConditionVariableTimeouts 1\n`

## pseudocode

```c
__int64 __fastcall CRIFTable::RegisterServerInterface(
        CRIFTable *this,
        const _GUID *iidOriginal,
        IRpcStubBuffer *stubOriginal,
        const char *a4)
{
  int v4; // r13d
  ServerCall *v7; // rax
  int v8; // ebx
  int v9; // esi
  int v10; // r15d
  unsigned int Data1; // r12d
  HRESULT ServerInterfaceFromStub; // ebx
  SHashChain *v13; // rax
  const char *v14; // rdx
  unsigned int v15; // r8d
  SHashChain *v16; // rsi
  CRIFTable *pNext_high; // rcx
  _GUID v19; // xmm0
  unsigned int v20; // r15d
  CRIFTable::tagRIFEntry *v21; // rdi
  unsigned int v22; // r14d
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  _RPC_SERVER_INTERFACE *v25; // rax
  const char *v26; // r9
  const char *v27; // r9
  int v28; // edx
  int v29; // r9d
  char v30; // r10
  int v31; // ecx
  const _GUID *v32; // r8
  struct _TEB *v33; // rax
  __int64 v34; // r9
  _DWORD *ReservedForOle; // rcx
  _DWORD *v36; // rcx
  _GUID iidBase; // xmm0
  IRpcStubBuffer *v38; // rcx
  CRIFTable::tagRIFEntry *v39; // rbx
  SHashChain *pNext; // rax
  SHashChain *v41; // r15
  IRpcStubBuffer *m_ptr; // r14
  wchar_t *v43; // rax
  wchar_t *v44; // rbx
  const wchar_t *v45; // rax
  CRIFTable *v46; // rcx
  CRIFTable::tagRIFEntry *v47; // rax
  ServerCall *v48; // rax
  wchar_t *v49; // rax
  unsigned int v50; // r8d
  wchar_t *v51; // rax
  wchar_t *v52; // rax
  ServerCall *v53; // rax
  CRIFTable::tagRIFEntry *pSrvBase; // rdx
  char v55; // r14
  SHashChain *pPrev; // r12
  SHashChain *v57; // rdi
  _DWORD *v58; // rcx
  RPC_STATUS v59; // r15d
  _DWORD *v60; // rdx
  wchar_t *v61; // rax
  const char *v62; // r9
  unsigned int format; // [rsp+20h] [rbp-E0h]
  CRIFTable::tagRIFEntry *pRIFEntryAdd; // [rsp+40h] [rbp-C0h] BYREF
  wil::com_ptr_t<IRpcStubBuffer,wil::err_returncode_policy> stubCurrent; // [rsp+48h] [rbp-B8h] BYREF
  CRIFTable::tagRIFEntry *v66; // [rsp+50h] [rbp-B0h]
  _GUID iidCurrent; // [rsp+58h] [rbp-A8h] BYREF
  _GUID clsidDummy; // [rsp+68h] [rbp-98h] BYREF
  GuidString v69; // [rsp+80h] [rbp-80h] BYREF
  GuidString v70; // [rsp+D0h] [rbp-30h] BYREF
  void *retaddr; // [rsp+178h] [rbp+78h]

  v4 = 0;
  if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    GuidString::GuidString(&v70, iidOriginal);
    ComTraceMessageT<void *>(
      "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
      "CRIFTable::RegisterServerInterface",
      676,
      INFO,
      (wchar_t *)L"Registering server IID %ls",
      v7);
  }
  v8 = *(_DWORD *)&iidOriginal->Data4[4];
  v9 = *(_DWORD *)iidOriginal->Data4;
  v10 = *(_DWORD *)&iidOriginal->Data2;
  Data1 = iidOriginal->Data1;
  COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", 0x2ABu, a4);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper>::GetImpl'::`2'::impl)
    && CRIFTable::m_cleaningUp )
  {
    COleStaticMutexSem::Release(&CRIFTable::_mxs);
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
        "CRIFTable::RegisterServerInterface",
        694,
        ERRORS,
        L"RegisterServerInterface called during RIFTable cleanup");
    ServerInterfaceFromStub = -2147418113;
    wil::details::in1diag3::Return_Hr(retaddr, 0x2B7u, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", -2147418113);
  }
  else
  {
    v13 = CHashTable::Lookup(&CRIFTable::_HashTbl, (v8 + v9 + Data1 + v10) % 0x17, iidOriginal);
    v16 = v13;
    pNext_high = (CRIFTable *)HIDWORD(v13[8].pNext);
    if ( (_DWORD)pNext_high == 2 )
    {
      CRIFTable::AddRefRegisteredServerInterfaceHelper(pNext_high, (CRIFTable::tagRIFEntry *)v13);
      COleStaticMutexSem::Release(&CRIFTable::_mxs);
      return 0;
    }
    v19 = *iidOriginal;
    v20 = 0;
    stubCurrent.m_ptr = stubOriginal;
    ServerInterfaceFromStub = 0;
    iidCurrent = v19;
    if ( stubOriginal )
      stubOriginal->AddRef(stubOriginal);
    v21 = (CRIFTable::tagRIFEntry *)v16;
    v66 = 0;
    while ( 1 )
    {
      ++v21->cSrvRefs;
      v22 = 0;
      while ( v21->srvRegistrationState == PENDING_REGISTRATION )
      {
        if ( v20 > 1
          && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
           || gfEnableTracing && IsWppLevelEnabled((TraceLevel)(Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 + 1))) )
        {
          GuidString::GuidString(&v70, &iidCurrent);
          ComTraceMessageT<unsigned __int64,unsigned long>(
            "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
            "CRIFTable::RegisterServerInterface",
            773,
            WARNING,
            L"Rewaiting on registration of IID %ls, attempt #%d",
            v23,
            v20);
        }
        if ( COleStaticMutexSem::YieldUntilWoken(
               (COleStaticMutexSem *)pNext_high,
               v14,
               v15,
               &v21->ConditionSrvInterface,
               format) )
        {
          v22 = 0;
          ++v20;
        }
        else
        {
          ++v22;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
            || gfEnableTracing && IsWppLevelEnabled((TraceLevel)(Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 + 1)) )
          {
            GuidString::GuidString(&v70, &iidCurrent);
            ComTraceMessageT<unsigned __int64,unsigned long>(
              "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
              "CRIFTable::RegisterServerInterface",
              791,
              WARNING,
              L"Timed out waiting on registration of IID %ls, timeout #%d",
              v24,
              v22);
          }
          if ( !g_fDisableConditionVariableTimeouts && v22 > 1 )
          {
            if ( !IsDebuggerPresent() )
              goto LABEL_82;
            if ( !v4 )
            {
              OutputDebugStringA(
                "WARNING: ole32.dll has timed out on a condition variable, which may indicate deadlock.\n"
                "If the issue you are debugging is unrelated to this wait, condition variable timeouts can be disabled fo"
                "r the duration of this function with the following debugger command:\n"
                "ed ole32!g_fDisableConditionVariableTimeouts 1\n");
              v4 = 1;
            }
            DebugBreak();
            if ( v22 > 3 )
            {
LABEL_82:
              v66 = v21;
              ServerInterfaceFromStub = -2147023436;
              if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
              {
                GuidString::GuidString(&v69, &iidCurrent);
                ComTraceMessageT<void *>(
                  "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
                  "CRIFTable::RegisterServerInterface",
                  844,
                  ERRORS,
                  (wchar_t *)L"Timed out waiting for registration of %ws",
                  v48);
              }
              goto LABEL_114;
            }
          }
        }
      }
      v20 = 0;
      if ( v21->srvRegistrationState == FULLY_REGISTERED )
      {
        if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        {
          GuidString::GuidString(&v69, &iidCurrent);
          ComTraceMessageT<void *>(
            "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
            "CRIFTable::RegisterServerInterface",
            850,
            VERBOSE,
            (wchar_t *)L"%ls already registered",
            v53);
        }
        pSrvBase = v21->pSrvBase;
        if ( pSrvBase )
          CRIFTable::AddRefRegisteredServerInterfaceHelper(pNext_high, pSrvBase);
LABEL_114:
        v55 = 0;
        if ( ServerInterfaceFromStub < 0 )
          goto LABEL_120;
        goto LABEL_115;
      }
      if ( v21->srvRegistrationState )
        MicrosoftTelemetryAssertTriggeredNoArgs(pNext_high);
      v21->srvRegistrationState = PENDING_REGISTRATION;
      COleStaticMutexSem::Release(&CRIFTable::_mxs);
      v25 = (_RPC_SERVER_INTERFACE *)HeapAlloc(g_hHeap, 0, 0x60u);
      v21->pSrvInterface = v25;
      if ( !v25 )
      {
        ServerInterfaceFromStub = -2147024882;
        COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", 0x376u, v26);
        goto LABEL_118;
      }
      *v25 = gServerIf;
      v21->pSrvInterface->InterfaceId.SyntaxGUID = iidCurrent;
      ServerInterfaceFromStub = NdrCreateServerInterfaceFromStub(stubCurrent.m_ptr, v21->pSrvInterface);
      if ( ServerInterfaceFromStub )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          GuidString::GuidString(&v69, &iidCurrent);
          ComTraceMessageT<unsigned short *,long>(
            "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
            "CRIFTable::RegisterServerInterface",
            896,
            ERRORS,
            L"NdrCreateServerInterfaceFromStub %ls failed: %!WINERROR!",
            v52,
            ServerInterfaceFromStub);
        }
        HeapFree(g_hHeap, 0, v21->pSrvInterface);
        v21->pSrvInterface = 0;
        if ( ServerInterfaceFromStub > 0 )
          ServerInterfaceFromStub = (unsigned __int16)ServerInterfaceFromStub | 0x80070000;
        v50 = 901;
LABEL_107:
        COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", v50, v27);
        goto LABEL_114;
      }
      v21->pSrvInterface->DispatchTable = &gDispatchTable;
      if ( memcmp_0(&iidCurrent, &IID_IWinRTInprocActivator, 0x10u) )
      {
        if ( gEnableNetworkDCOM || gEnableContainerDCOM )
        {
          if ( gAnonymousAccessAllowed || gfLogCallFailure || gEnableContainerDCOM && !gIncomingContainerAuthnSvc )
          {
            v28 = 83;
            v29 = 115;
          }
          else
          {
            v28 = 75;
            v29 = 107;
          }
        }
        else
        {
          v28 = ServerInterfaceFromStub + 107;
          v29 = ServerInterfaceFromStub + 107;
        }
        v30 = 0;
        v31 = 0;
        while ( 1 )
        {
          v32 = gLocalOnlyIIDs[v31];
          if ( *(_QWORD *)&iidCurrent.Data1 == *(_QWORD *)&v32->Data1
            && *(_QWORD *)iidCurrent.Data4 == *(_QWORD *)v32->Data4 )
          {
            break;
          }
          if ( (unsigned int)++v31 >= 5 )
            goto LABEL_56;
        }
        v30 = 1;
LABEL_56:
        v33 = NtCurrentTeb();
        if ( !v30 )
          v29 = v28;
        v34 = v21->rpcInterfaceFlags | v29;
        ReservedForOle = v33->ReservedForOle;
        if ( ReservedForOle )
          ++ReservedForOle[112];
        ServerInterfaceFromStub = RpcServerRegisterIf3(
                                    v21->pSrvInterface,
                                    0,
                                    0,
                                    v34,
                                    1234,
                                    -1,
                                    ORPCInterfaceSecCallback,
                                    gLrpcSecurityDescriptor);
        v36 = NtCurrentTeb()->ReservedForOle;
        if ( v36 )
          --v36[112];
        if ( ServerInterfaceFromStub )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            GuidString::GuidString(&v69, &iidCurrent);
            ComTraceMessageT<unsigned short *,long>(
              "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
              "CRIFTable::RegisterServerInterface",
              956,
              ERRORS,
              L"RpcServerRegisterIf2 %ws failed: %!WINERROR!",
              v49,
              ServerInterfaceFromStub);
          }
          HeapFree(g_hHeap, 0, v21->pSrvInterface);
          v21->pSrvInterface = 0;
          if ( ServerInterfaceFromStub > 0 )
            ServerInterfaceFromStub = (unsigned __int16)ServerInterfaceFromStub | 0x80070000;
          v50 = 961;
          goto LABEL_107;
        }
      }
      if ( SLOBYTE(v21->dwFlags) >= 0 )
      {
        pRIFEntryAdd = 0;
        ServerInterfaceFromStub = NdrGetBaseInterfaceFromStub(
                                    stubCurrent.m_ptr,
                                    (IRpcStubBuffer **)&pRIFEntryAdd,
                                    &iidCurrent);
        m_ptr = stubCurrent.m_ptr;
        stubCurrent.m_ptr = (IRpcStubBuffer *)pRIFEntryAdd;
        if ( pRIFEntryAdd )
          ((void (__fastcall *)(CRIFTable::tagRIFEntry *))pRIFEntryAdd->HashNode.chain.pNext->pPrev)(pRIFEntryAdd);
        if ( m_ptr )
          m_ptr->Release(m_ptr);
      }
      else if ( *(_QWORD *)&v21->iidBase.Data1 == *(_QWORD *)&IID_IUnknown.Data1
             && *(_QWORD *)v21->iidBase.Data4 == *(_QWORD *)IID_IUnknown.Data4 )
      {
        ServerInterfaceFromStub = 1;
      }
      else
      {
        iidBase = v21->iidBase;
        pRIFEntryAdd = 0;
        iidCurrent = iidBase;
        ServerInterfaceFromStub = GetPSFactory(&v21->iidBase, (IPSFactoryBuffer **)&pRIFEntryAdd);
        if ( ServerInterfaceFromStub >= 0 )
        {
          v38 = stubCurrent.m_ptr;
          v39 = pRIFEntryAdd;
          pNext = pRIFEntryAdd->HashNode.chain.pNext;
          stubCurrent.m_ptr = 0;
          v41 = pNext[2].pNext;
          if ( v38 )
            v38->Release(v38);
          ServerInterfaceFromStub = ((__int64 (__fastcall *)(CRIFTable::tagRIFEntry *, _GUID *, _QWORD, wil::com_ptr_t<IRpcStubBuffer,wil::err_returncode_policy> *))v41)(
                                      v39,
                                      &v21->iidBase,
                                      0,
                                      &stubCurrent);
          v20 = 0;
        }
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&pRIFEntryAdd);
      }
      if ( ServerInterfaceFromStub )
        break;
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      {
        GuidString::GuidString(&v70, &iidCurrent);
        v44 = v43;
        GuidString::GuidString(&v69, &v21->HashNode.key);
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
          "CRIFTable::RegisterServerInterface",
          1053,
          VERBOSE,
          L"IID %ls --> base IID %ls",
          v45,
          v44);
      }
      COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", 0x421u, v27);
      pRIFEntryAdd = 0;
      clsidDummy = 0;
      ServerInterfaceFromStub = CRIFTable::GetPSClsidHelper(v46, &iidCurrent, 0, &clsidDummy, &pRIFEntryAdd);
      if ( ServerInterfaceFromStub < 0 )
        goto LABEL_118;
      v47 = pRIFEntryAdd;
      v21->pSrvBase = pRIFEntryAdd;
      v21 = v47;
    }
    if ( ServerInterfaceFromStub != 1 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        GuidString::GuidString(&v69, &iidCurrent);
        ComTraceMessageT<unsigned short *,long>(
          "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
          "CRIFTable::RegisterServerInterface",
          1088,
          ERRORS,
          L"NdrGetBaseInterfaceFromStub %ls failed: %!HRESULT!",
          v51,
          ServerInterfaceFromStub);
      }
      v50 = 1089;
      goto LABEL_107;
    }
    ServerInterfaceFromStub = 0;
    COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", 0x43Au, v27);
LABEL_115:
    if ( (v21->dwFlags & 0x10) == 0
      && (*(_QWORD *)&v21->HashNode.key.Data1 != *(_QWORD *)&IID_IInspectable.Data1
       || *(_QWORD *)v21->HashNode.key.Data4 != *(_QWORD *)IID_IInspectable.Data4) )
    {
LABEL_118:
      v55 = 0;
      goto LABEL_120;
    }
    v55 = 1;
LABEL_120:
    while ( v16 != (SHashChain *)v66 )
    {
      if ( HIDWORD(v16[8].pNext) != 2 )
      {
        if ( HIDWORD(v16[8].pNext) != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs(pNext_high);
        pPrev = v16[6].pPrev;
        if ( ServerInterfaceFromStub < 0 )
        {
          v57 = v16[9].pNext;
          v16[9].pNext = 0;
          v16[6].pPrev = 0;
          if ( v57 )
          {
            COleStaticMutexSem::Release(&CRIFTable::_mxs);
            v58 = NtCurrentTeb()->ReservedForOle;
            if ( v58 )
              ++v58[112];
            v59 = RpcServerUnregisterIf(v57, 0, 0);
            v60 = NtCurrentTeb()->ReservedForOle;
            if ( v60 )
              --v60[112];
            if ( v59
              && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING)) )
            {
              GuidString::GuidString(&v69, (const _GUID *)((char *)&v57->pNext + 4));
              ComTraceMessageT<unsigned short *,long>(
                "onecore\\com\\combase\\dcomrem\\riftbl.cxx",
                "CRIFTable::RegisterServerInterface",
                1198,
                WARNING,
                L"RpcUnregisterServerIf %ws failed: %!WINERROR!",
                v61,
                v59);
            }
            HeapFree(g_hHeap, 0, v57);
            COleStaticMutexSem::Request(&CRIFTable::_mxs, "onecore\\com\\combase\\dcomrem\\riftbl.cxx", 0x4B3u, v62);
          }
          --LODWORD(v16[8].pNext);
        }
        LODWORD(v16[4].pNext) |= 8u;
        if ( v55 )
          LODWORD(v16[4].pNext) |= 0x10u;
        HIDWORD(v16[8].pNext) = ((ServerInterfaceFromStub >> 31) & 0xFFFFFFFE) + 2;
        RtlWakeAllConditionVariable(&v16[8].pPrev);
        v16 = pPrev;
        if ( pPrev )
          continue;
      }
      goto LABEL_142;
    }
    --LODWORD(v16[8].pNext);
LABEL_142:
    if ( v4 )
      g_fDisableConditionVariableTimeouts = 1;
    COleStaticMutexSem::Release(&CRIFTable::_mxs);
    wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&stubCurrent);
  }
  return (unsigned int)ServerInterfaceFromStub;
}

```

## disassembly

```asm
0x18013830c  push    rbp
0x18013830e  push    rbx
0x18013830f  push    rsi
0x180138310  push    rdi
0x180138311  push    r12
0x180138313  push    r13
0x180138315  push    r14
0x180138317  push    r15
0x180138319  lea     rbp, [rsp-38h]
0x18013831e  sub     rsp, 138h
0x180138325  mov     rax, cs:__security_cookie
0x18013832c  xor     rax, rsp
0x18013832f  mov     [rbp+70h+var_50], rax
0x180138333  xor     r13d, r13d
0x180138336  mov     r14, stubOriginal
0x180138339  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180138340  mov     rdi, iidOriginal
0x180138343  jz      short loc_180138389
0x180138345  mov     rax, cs:WPP_GLOBAL_Control
0x18013834c  test    byte ptr [rax+1Ch], 4
0x180138350  jz      short loc_180138389
0x180138352  lea     rcx, [rbp+70h+var_A0]; this
0x180138356  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18013835b  mov     [rsp+170h+var_148], rax; <args_0>
0x180138360  lea     r9d, [r13+2]; level
0x180138364  lea     rax, aRegisteringSer; "Registering server IID %ls"
0x18013836b  mov     r8d, 2A4h; line
0x180138371  lea     iidOriginal, aCriftableRegis_1; "CRIFTable::RegisterServerInterface"
0x180138378  mov     [rsp+170h+format], rax; format
0x18013837d  lea     rcx, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138384  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x180138389  mov     ebx, [rdi+0Ch]
0x18013838c  lea     iidOriginal, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138393  mov     esi, [rdi+8]
0x180138396  lea     rcx, ?_mxs@CRIFTable@@0VCOleStaticMutexSem@@A; this
0x18013839d  mov     r15d, [rdi+4]
0x1801383a1  mov     r8d, 2ABh; dwLine
0x1801383a7  mov     r12d, [rdi]
0x1801383aa  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1801383af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper@@@details@3@XZ@4V453@A; __annotation("WILSTG:|59355008|Feature_FixUAFInReleaseServerInterfaceHelper|EnabledByDefault")
0x1801383b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixUAFInReleaseServerInterfaceHelper>::__private_IsEnabled(void)
0x1801383bb  test    al, al
0x1801383bd  jz      short loc_18013843C
0x1801383bf  cmp     cs:?m_cleaningUp@CRIFTable@@0_NA, r13b; bool CRIFTable::m_cleaningUp
0x1801383c6  jz      short loc_18013843C
0x1801383c8  lea     rcx, ?_mxs@CRIFTable@@0VCOleStaticMutexSem@@A; this
0x1801383cf  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x1801383d4  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801383da  test    eax, eax
0x1801383dc  jnz     short loc_1801383F2
0x1801383de  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1801383e5  jz      short loc_18013841A
0x1801383e7  xor     ecx, ecx; level
0x1801383e9  call    IsWppLevelEnabled
0x1801383ee  test    al, al
0x1801383f0  jz      short loc_18013841A
0x1801383f2  lea     rax, aRegisterserver; "RegisterServerInterface called during R"...
0x1801383f9  xor     r9d, r9d; level
0x1801383fc  mov     r8d, 2B6h; line
0x180138402  mov     [rsp+170h+format], rax; format
0x180138407  lea     iidOriginal, aCriftableRegis_1; "CRIFTable::RegisterServerInterface"
0x18013840e  lea     rcx, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138415  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18013841a  mov     rcx, [rbp+78h]; callerReturnAddress
0x18013841e  lea     stubOriginal, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138425  mov     ebx, 8000FFFFh
0x18013842a  mov     edx, 2B7h; lineNumber
0x18013842f  mov     r9d, ebx; hr
0x180138432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138437  jmp     loc_180138E4B
0x18013843c  lea     ecx, [r12+r15]
0x180138440  mov     eax, 0B21642C9h
0x180138445  add     ecx, esi
0x180138447  mov     stubOriginal, rdi; k
0x18013844a  add     ecx, ebx
0x18013844c  mul     ecx
0x18013844e  shr     edx, 4
0x180138451  imul    eax, edx, 17h
0x180138454  sub     ecx, eax
0x180138456  mov     edx, ecx; dwHash
0x180138458  lea     rcx, ?_HashTbl@CRIFTable@@0VCUUIDHashTable@@A; this
0x18013845f  call    ?Lookup@CHashTable@@IEAAPEAUSHashChain@@KPEBX@Z; CHashTable::Lookup(ulong,void const *)
0x180138464  mov     rsi, rax
0x180138467  mov     ecx, [rax+84h]; this
0x18013846d  cmp     ecx, 2
0x180138470  jnz     short loc_18013848D
0x180138472  mov     iidOriginal, rax; pRIFEntry
0x180138475  call    ?AddRefRegisteredServerInterfaceHelper@CRIFTable@@AEAAXPEAUtagRIFEntry@1@@Z; CRIFTable::AddRefRegisteredServerInterfaceHelper(CRIFTable::tagRIFEntry *)
0x18013847a  lea     rcx, ?_mxs@CRIFTable@@0VCOleStaticMutexSem@@A; this
0x180138481  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180138486  xor     eax, eax
0x180138488  jmp     loc_180138E4D
0x18013848d  movups  xmm0, xmmword ptr [rdi]
0x180138490  xor     r15d, r15d
0x180138493  mov     [rsp+170h+stubCurrent.m_ptr], r14
0x180138498  mov     ebx, r15d
0x18013849b  movdqu  xmmword ptr [rsp+170h+iidCurrent.Data1], xmm0
0x1801384a1  test    r14, r14
0x1801384a4  jz      short loc_1801384B5
0x1801384a6  mov     rax, [r14]
0x1801384a9  mov     rcx, r14
0x1801384ac  mov     rax, [rax+8]
0x1801384b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801384b5  mov     rdi, rsi
0x1801384b8  mov     [rsp+170h+var_120], r15
0x1801384bd  inc     dword ptr [rdi+80h]
0x1801384c3  xor     r14d, r14d
0x1801384c6  jmp     loc_1801385F6
0x1801384cb  cmp     r15d, 1
0x1801384cf  jbe     short loc_180138532
0x1801384d1  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801384d7  test    eax, eax
0x1801384d9  jnz     short loc_1801384EF
0x1801384db  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801384e1  jz      short loc_180138532
0x1801384e3  lea     ecx, [rax+1]; level
0x1801384e6  call    IsWppLevelEnabled
0x1801384eb  test    al, al
0x1801384ed  jz      short loc_180138532
0x1801384ef  lea     iidOriginal, [rsp+170h+iidCurrent]; guid
0x1801384f4  lea     rcx, [rbp+70h+var_A0]; this
0x1801384f8  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x1801384fd  mov     [rsp+170h+var_140], r15d; <args_1>
0x180138502  lea     iidOriginal, aCriftableRegis_1; "CRIFTable::RegisterServerInterface"
0x180138509  mov     [rsp+170h+var_148], rax; <args_0>
0x18013850e  lea     rcx, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138515  lea     rax, aRewaitingOnReg; "Rewaiting on registration of IID %ls, a"...
0x18013851c  mov     r9d, 1; level
0x180138522  mov     r8d, 305h; line
0x180138528  mov     [rsp+170h+format], rax; pConditionVariable
0x18013852d  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180138532  lea     r9, [rdi+88h]; dwLine
0x180138539  call    ?YieldUntilWoken@COleStaticMutexSem@@QEAAHPEBDKPEAVCOleConditionVariable@@K@Z; COleStaticMutexSem::YieldUntilWoken(char const *,ulong,COleConditionVariable *,ulong)
0x18013853e  test    eax, eax
0x180138540  jz      short loc_18013854D
0x180138542  xor     r14d, r14d
0x180138545  inc     r15d
0x180138548  jmp     loc_1801385F6
0x18013854d  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180138553  inc     r14d
0x180138556  test    eax, eax
0x180138558  jnz     short loc_18013856E
0x18013855a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180138560  jz      short loc_1801385B1
0x180138562  lea     ecx, [rax+1]; level
0x180138565  call    IsWppLevelEnabled
0x18013856a  test    al, al
0x18013856c  jz      short loc_1801385B1
0x18013856e  lea     iidOriginal, [rsp+170h+iidCurrent]; guid
0x180138573  lea     rcx, [rbp+70h+var_A0]; this
0x180138577  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18013857c  mov     [rsp+170h+var_140], r14d; <args_1>
0x180138581  lea     iidOriginal, aCriftableRegis_1; "CRIFTable::RegisterServerInterface"
0x180138588  mov     [rsp+170h+var_148], rax; <args_0>
0x18013858d  lea     rcx, aOnecoreComComb_62; "onecore\\com\\combase\\dcomrem\\riftbl."...
0x180138594  lea     rax, aTimedOutWaitin; "Timed out waiting on registration of II"...
0x18013859b  mov     r9d, 1; level
0x1801385a1  mov     r8d, 317h; line
0x1801385a7  mov     [rsp+170h+format], rax; format
0x1801385ac  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1801385b1  cmp     cs:?g_fDisableConditionVariableTimeouts@@3HA, 0; int g_fDisableConditionVariableTimeouts
0x1801385b8  jnz     short loc_1801385F6
0x1801385ba  cmp     r14d, 1
0x1801385be  jbe     short loc_1801385F6
0x1801385c0  call    cs:__imp_IsDebuggerPresent
0x1801385c6  test    eax, eax
0x1801385c8  jz      loc_1801389C7
0x1801385ce  test    r13d, r13d
0x1801385d1  jnz     short loc_1801385E6
0x1801385d3  lea     rcx, aWarningOle32Dl; "WARNING: ole32.dll has timed out on a c"...
0x1801385da  call    cs:__imp_OutputDebugStringA
0x1801385e0  mov     r13d, 1
0x1801385e6  call    cs:__imp_DebugBreak
0x1801385ec  cmp     r14d, 3
0x1801385f0  ja      loc_1801389C7
0x1801385f6  mov     eax, [rdi+84h]
0x1801385fc  cmp     eax, 1
0x1801385ff  jz      loc_1801384CB
0x180138605  mov     eax, [rdi+84h]
0x18013860b  xor     r15d, r15d
0x18013860e  cmp     eax, 2
0x180138611  jz      loc_180138C16
0x180138617  mov     eax, [rdi+84h]
0x18013861d  test    eax, eax
0x18013861f  jz      short loc_180138626
0x180138621  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pRIFEntryCurrent->srvRegistrationState == NOT_REGISTERED")
0x180138626  lea     r12, ?_mxs@CRIFTable@@0VCOleStaticMutexSem@@A; COleStaticMutexSem CRIFTable::_mxs
0x18013862d  mov     dword ptr [rdi+84h], 1
0x180138637  mov     rcx, r12; this
0x18013863a  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18013863f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180138646  xor     edx, edx; dwFlags
0x180138648  lea     r8d, [iidOriginal+60h]; dwBytes
0x18013864c  call    cs:__imp_HeapAlloc
0x180138652  mov     [rdi+90h], rax
0x180138659  test    rax, rax
0x18013865c  jz      loc_180138BF7
0x180138662  movaps  xmm0, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.Length; _RPC_SERVER_INTERFACE const gServerIf ...
0x180138669  movups  xmmword ptr [rax], xmm0
0x18013866c  movaps  xmm1, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.InterfaceId.SyntaxGUID.Data4+4; _RPC_SERVER_INTERFACE const gServerIf ...
0x180138673  movups  xmmword ptr [rax+10h], xmm1
0x180138677  movaps  xmm0, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.TransferSyntax.SyntaxGUID.Data4; _RPC_SERVER_INTERFACE const gServerIf ...
0x18013867e  movups  xmmword ptr [rax+20h], xmm0
0x180138682  movaps  xmm1, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.DispatchTable; _RPC_SERVER_INTERFACE const gServerIf ...
0x180138689  movups  xmmword ptr [rax+30h], xmm1
0x18013868d  movaps  xmm0, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.RpcProtseqEndpoint; _RPC_SERVER_INTERFACE const gServerIf ...
0x180138694  movups  xmmword ptr [rax+40h], xmm0
0x180138698  movaps  xmm1, xmmword ptr cs:?gServerIf@@3U_RPC_SERVER_INTERFACE@@B.InterpreterInfo; _RPC_SERVER_INTERFACE const gServerIf ...
0x18013869f  movups  xmmword ptr [rax+50h], xmm1
0x1801386a3  mov     rax, [rdi+90h]
0x1801386aa  movups  xmm0, xmmword ptr [rsp+170h+iidCurrent.Data1]
0x1801386af  movdqu  xmmword ptr [rax+4], xmm0
0x1801386b4  mov     iidOriginal, [rdi+90h]; pServerIf
0x1801386bb  mov     rcx, [rsp+170h+stubCurrent.m_ptr]; pStub
0x1801386c0  call    NdrCreateServerInterfaceFromStub
0x1801386c5  mov     ebx, eax
0x1801386c7  test    eax, eax
0x1801386c9  jnz     loc_180138B56
0x1801386cf  mov     rax, [rdi+90h]
0x1801386d6  lea     rcx, gDispatchTable
0x1801386dd  lea     r8d, [rbx+10h]; Size
0x1801386e1  lea     iidOriginal, IID_IWinRTInprocActivator; Buf2
0x1801386e8  mov     [rax+30h], rcx
0x1801386ec  lea     rcx, [rsp+170h+iidCurrent]; Buf1
0x1801386f1  call    memcmp_0
0x1801386f6  test    eax, eax
0x1801386f8  jz      loc_180138809
0x1801386fe  cmp     cs:?gEnableNetworkDCOM@@3HA, r15d; int gEnableNetworkDCOM
0x180138705  mov     eax, cs:?gEnableContainerDCOM@@3HA; int gEnableContainerDCOM
0x18013870b  jnz     short loc_18013871B
0x18013870d  test    eax, eax
0x18013870f  jnz     short loc_18013871B
0x180138711  lea     eax, [rbx+6Bh]
0x180138714  mov     edx, eax
0x180138716  mov     r9d, eax
0x180138719  jmp     short loc_18013874E
0x18013871b  cmp     cs:?gAnonymousAccessAllowed@@3HA, r15d; int gAnonymousAccessAllowed
0x180138722  jnz     short loc_180138745
0x180138724  cmp     cs:?gfLogCallFailure@@3HA, r15d; int gfLogCallFailure
0x18013872b  jnz     short loc_180138745
0x18013872d  test    eax, eax
0x18013872f  jz      short loc_18013873A
0x180138731  cmp     cs:?gIncomingContainerAuthnSvc@@3KA, r15d; ulong gIncomingContainerAuthnSvc
0x180138738  jz      short loc_180138745
0x18013873a  mov     edx, 4Bh ; 'K'
0x18013873f  lea     r9d, [iidOriginal+20h]
0x180138743  jmp     short loc_18013874E
0x180138745  mov     edx, 53h ; 'S'
0x18013874a  lea     r9d, [iidOriginal+20h]
0x18013874e  mov     r11, qword ptr [rsp+170h+iidCurrent.Data4]
0x180138753  mov     r10b, r15b
0x180138756  mov     rbx, qword ptr [rsp+170h+iidCurrent.Data1]
0x18013875b  mov     ecx, r15d
0x18013875e  mov     eax, ecx
0x180138760  lea     stubOriginal, gLocalOnlyIIDs
0x180138767  mov     stubOriginal, [stubOriginal+rax*8]
0x18013876b  cmp     rbx, [stubOriginal]
0x18013876e  jnz     short loc_180138776
0x180138770  cmp     r11, [stubOriginal+8]
0x180138774  jz      short loc_18013877F
0x180138776  inc     ecx
0x180138778  cmp     ecx, 5
0x18013877b  jb      short loc_18013875E
0x18013877d  jmp     short loc_180138782
0x18013877f  mov     r10b, 1
0x180138782  mov     rax, gs:30h
0x18013878b  test    r10b, r10b
0x18013878e  cmovz   r9d, edx
0x180138792  or      r9d, [rdi+50h]
0x180138796  mov     rcx, [rax+1758h]
0x18013879d  test    rcx, rcx
0x1801387a0  jz      short loc_1801387A8
0x1801387a2  inc     dword ptr [rcx+1C0h]
0x1801387a8  mov     rax, cs:?gLrpcSecurityDescriptor@@3PEAVCWorldSecurityDescriptor@@EA; CWorldSecurityDescriptor * gLrpcSecurityDescriptor
0x1801387af  or      r14d, 0FFFFFFFFh
0x1801387b3  mov     rcx, [rdi+90h]
0x1801387ba  xor     r8d, r8d
0x1801387bd  mov     [rsp+170h+var_138], rax
0x1801387c2  xor     edx, edx
0x1801387c4  lea     rax, ?ORPCInterfaceSecCallback@@YAJPEAX0@Z; ORPCInterfaceSecCallback(void *,void *)
0x1801387cb  mov     qword ptr [rsp+170h+var_140], rax
0x1801387d0  mov     dword ptr [rsp+170h+var_148], r14d
0x1801387d5  mov     dword ptr [rsp+170h+format], 4D2h
0x1801387dd  call    cs:__imp_RpcServerRegisterIf3
0x1801387e3  mov     ebx, eax
0x1801387e5  mov     rax, gs:30h
0x1801387ee  mov     rcx, [rax+1758h]
0x1801387f5  test    rcx, rcx
0x1801387f8  jz      short loc_180138801
0x1801387fa  add     [rcx+1C0h], r14d
0x180138801  test    ebx, ebx
0x180138803  jnz     loc_180138A3A
0x180138809  test    byte ptr [rdi+40h], 80h
0x18013880d  jz      loc_1801388AE
0x180138813  lea     r14, [rdi+54h]
0x180138817  mov     rax, [r14]
0x18013881a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180138821  jnz     short loc_18013883A
0x180138823  mov     rax, [r14+8]
0x180138827  cmp     rax, qword ptr cs:IID_IUnknown.Data4
  ... truncated ...
```
