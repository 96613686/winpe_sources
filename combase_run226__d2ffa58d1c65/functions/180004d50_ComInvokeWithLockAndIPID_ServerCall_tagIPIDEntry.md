# ComInvokeWithLockAndIPID(ServerCall *,tagIPIDEntry *)

- ea: `0x180004d50`
- end: `0x18000617f`
- name: `?ComInvokeWithLockAndIPID@@YAJPEAVServerCall@@PEAUtagIPIDEntry@@@Z`
- size: `5167`
- prototype: `HRESULT __fastcall(ServerCall *pServerCall, tagIPIDEntry *pIPIDEntry)`
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019240`
- `0x1800907c0`

## callees

- `0x180003964`
- `0x1800039a0`
- `0x180004d50`
- `0x180006250`
- `0x180006390`
- `0x180006534`
- `0x18000712c`
- `0x18000833c`
- `0x18000b408`
- `0x18001d124`
- `0x180023e4c`
- `0x180036038`
- `0x18003a630`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x18003cf8c`
- `0x180047aa8`
- `0x180076a4c`
- `0x1800798e4`
- `0x180079994`
- `0x1800844b0`
- `0x1800865f4`
- `0x180093140`
- `0x1800c4dbc`
- `0x1800c9668`
- `0x1800cc0e0`
- `0x18013f4c8`
- `0x1801471d0`
- `0x180183380`
- `0x180187418`
- `0x1801999b0`
- `0x18019a080`
- `0x18019a654`
- `0x1801af8a8`
- `0x1801b2480`
- `0x1801b3f94`
- `0x1801ce150`
- `0x1802135dd`
- `0x180255010`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180005c36`
- `RPCRT4!RpcRevertToSelfEx` at `0x180005c36`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800057af`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800057af`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18000578b`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18000578b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005165`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180244f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180244f15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000515d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000515d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180244def`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180244def`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005c5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005f1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005c5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005f1f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800059ab`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800059ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005012`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005bc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005012`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005bc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000503f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000521e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005be8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000503f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000521e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005be8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005d73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800060d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005d73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800060d7`

## string_xrefs

- `0x1800051a7`: `onecore\com\combase\coll\pgalloc.cxx`
- `0x180005c70`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180005d4a`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180006016`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180004fb5`: `onecore\com\combase\dcomrem\marshal.hxx`
- `0x180005ad3`: `ComInvokeWithLockAndIPID`
- `0x180005de5`: `ComInvokeWithLockAndIPID`
- `0x180005b09`: `Sending auto-retry response to Winrt async call (%u calls already nested)`
- `0x180005fd5`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18000613b`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x180004f5c`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180005afe`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180005dec`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180005ea7`: `onecore\com\combase\dcomrem\chock.cxx`

## pseudocode

```c
__int64 __fastcall ComInvokeWithLockAndIPID(ServerCall *pServerCall, IMetaDataImport2 *pIPIDEntry)
{
  ServerCall_vtbl *v2; // rax
  IMetaDataImport2 *ptr; // r15
  ServerCall *v4; // r14
  CMessageCall *v5; // rax
  CMessageCall *v6; // rbx
  CCtxConnectionManager *v7; // r13
  IMetaDataImport2_vtbl *v8; // r12
  char *ReservedForOle; // rdi
  HRESULT (__fastcall *GetScopeProps)(IMetaDataImport *, wchar_t *, unsigned int, unsigned int *, _GUID *); // rsi
  HRESULT (__fastcall *EnumTypeDefs)(IMetaDataImport *, void **, unsigned int *, unsigned int, unsigned int *); // rsi
  _DWORD *v12; // r14
  int v13; // esi
  __int64 v14; // rdx
  const char *v15; // r9
  _DWORD *v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  char v19; // r15
  int v20; // eax
  _BYTE *v21; // rcx
  tagPageEntry *pNext; // r14
  HRESULT (__fastcall *v24)(IMetaDataImport *, void **, unsigned int *, unsigned int, unsigned int *); // rsi
  __int64 v25; // rsi
  IMetaDataImport2_vtbl *v26; // rcx
  HRESULT v27; // eax
  int AutoRetryResponseMessage; // r12d
  IUnknown *v29; // rsi
  CStdMarshal *v30; // r15
  signed __int32 v31; // esi
  unsigned int v32; // eax
  CStdMarshal *v33; // rcx
  signed __int32 v34; // esi
  IMetaDataImport2_vtbl *v35; // rcx
  void *m_ptr; // rsi
  DWORD LastError; // edi
  unsigned int PendingDisconnectType; // esi
  COleStaticMutexSem *pLock; // r15
  bool v41; // zf
  __int64 lockOrder; // rcx
  IMetaDataImport2 *v43; // rdx
  int v44; // eax
  unsigned int size; // r15d
  tagPageEntry *reserved1; // rcx
  unsigned int dwDestCtx; // eax
  int v48; // eax
  _QWORD *v49; // rcx
  int v50; // eax
  unsigned int dataRepresentation; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  IMetaDataImport2 *v55; // rax
  __int64 v56; // rcx
  _QWORD *p_size; // rcx
  IMetaDataImport2 *v58; // r8
  const WireExtentArray *orpcThis; // rax
  const SHookList *v60; // rsi
  unsigned int v61; // edx
  unsigned int *v62; // r15
  size_t v63; // r8
  unsigned __int64 v64; // rax
  void *v65; // rsp
  __int64 v66; // r15
  unsigned int v67; // r13d
  __int64 v68; // rcx
  void *v69; // r8
  __int64 v70; // r9
  unsigned int v71; // eax
  const WireLocalThis *localThis; // r15
  unsigned int sizeOfLocalThis; // esi
  HRESULT v74; // eax
  unsigned int dwClientThread; // r8d
  unsigned int requestContainerPassthroughDataSize; // edx
  void *v77; // rcx
  int v78; // eax
  void *requestStubData; // rax
  ServerCall *v80; // rsi
  IMetaDataImport2 *v81; // rcx
  __int64 v82; // rcx
  unsigned int v83; // eax
  unsigned int v84; // eax
  const WireLocalThis *v85; // rax
  unsigned __int64 *astaOxids; // r12
  unsigned int v87; // eax
  unsigned int dwFlags; // r8d
  int v89; // edx
  int v90; // r9d
  _DWORD *v91; // rcx
  int v92; // esi
  _DWORD *v93; // rcx
  int v94; // eax
  HRESULT (__fastcall *InvokeInApartment)(ServerCall *, tagIPIDEntry *); // rax
  HRESULT v96; // eax
  _DWORD *v97; // rdx
  MarshaledHandleStorage *v98; // rcx
  HRESULT (__fastcall *v99)(IMetaDataImport *, void **, unsigned int *, unsigned int, unsigned int *); // rsi
  _QWORD *v100; // rcx
  bool v101; // r15
  void *v102; // rsi
  int v103; // ecx
  _DWORD *v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rdx
  _GUID v107; // xmm0
  ServerCall *v108; // rsi
  ServerCall_vtbl *v109; // rax
  RPC_STATUS v110; // eax
  void *v111; // rdx
  bool v112; // cf
  _DWORD *v113; // rsi
  int v114; // edi
  __int64 v115; // rax
  const WireExtentArray *v116; // r15
  char *v117; // rax
  __int64 v118; // rax
  __int64 v119; // rdx
  void *hRpc; // rcx
  int v121; // eax
  CMessageCall *v122; // rax
  DWORD CurrentThreadId; // r15d
  unsigned __int16 v124; // si
  const _GUID *v125; // rax
  int v126; // eax
  __int64 v127; // r15
  tagPageEntry *v128; // r15
  const WireExtent *aExtent; // [rsp+40h] [rbp+0h] BYREF
  unsigned int dwLocalClientPID; // [rsp+48h] [rbp+8h] BYREF
  Microsoft::WRL::ComPtr<IMetaDataImport2> v131; // [rsp+50h] [rbp+10h] BYREF
  unsigned int v132; // [rsp+58h] [rbp+18h]
  ServerCall *v133; // [rsp+60h] [rbp+20h]
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy> pPrimaryUnknown; // [rsp+68h] [rbp+28h] BYREF
  const WireContainerThis *passthroughData; // [rsp+70h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<IMetaDataImport2> v136; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v137; // [rsp+80h] [rbp+40h]
  IMetaDataImport2_vtbl *v138; // [rsp+88h] [rbp+48h]
  const WireExtentArray *v139; // [rsp+90h] [rbp+50h]
  IMetaDataImport2_vtbl *v140; // [rsp+98h] [rbp+58h]
  _GUID v141; // [rsp+A0h] [rbp+60h] BYREF
  _GUID moidForTracing; // [rsp+B0h] [rbp+70h] BYREF
  CCtxCall ctxCall; // [rsp+C0h] [rbp+80h] BYREF
  void *retaddr; // [rsp+278h] [rbp+238h]

  v2 = pServerCall->__vftable;
  ptr = pIPIDEntry;
  v136.ptr_ = pIPIDEntry;
  v4 = pServerCall;
  v133 = pServerCall;
  v5 = v2->GetTransportCall(pServerCall);
  v6 = v5;
  if ( v5 )
    v5->AddRef(v5);
  v7 = 0;
  v8 = ptr[11].__vftable;
  v138 = v8;
  passthroughData = 0;
  ReservedForOle = (char *)NtCurrentTeb()->ReservedForOle;
  GetScopeProps = v8->GetScopeProps;
  if ( !GetScopeProps )
  {
LABEL_4:
    v140 = ptr[6].__vftable;
    _InterlockedIncrement((volatile signed __int32 *)&v140->GetClassLayout);
    EnumTypeDefs = v8->EnumTypeDefs;
    (*(void (__fastcall **)(__int64))(*((_QWORD *)EnumTypeDefs + 1) + 8LL))((__int64)EnumTypeDefs + 8);
    _InterlockedIncrement((volatile signed __int32 *)EnumTypeDefs + 16);
    if ( !--gIPIDLock._cLocks && gIPIDLock._lockOrder != Highest )
    {
      v12 = NtCurrentTeb()->ReservedForOle;
      if ( v12 )
      {
        v13 = 1 << gIPIDLock._lockOrder;
        if ( ((1 << gIPIDLock._lockOrder) & v12[144]) == 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs((unsigned __int8)gIPIDLock._lockOrder);
        v12[144] &= ~v13;
      }
      v4 = v133;
    }
    LeaveCriticalSection(&gIPIDLock._cs);
    v16 = NtCurrentTeb()->ReservedForOle;
    if ( !v16 || (v17 = v16[5], (v17 & 0x800) != 0) || (v17 & 0x80u) == 0 || (v17 & 0x400000) != 0 )
    {
      ++*((_DWORD *)ReservedForOle + 12);
      pNext = 0;
      v24 = v138->EnumTypeDefs;
      goto LABEL_26;
    }
    v18 = *((_QWORD *)ReservedForOle + 16);
    v19 = 0;
    v20 = *(_DWORD *)(v18 + 8);
    if ( v20 )
    {
      if ( v20 != 4 )
      {
LABEL_23:
        if ( FeatureDevelopmentProperties::Query(EnableRemoteAsyncSTAReentrancyGuard, (bool *)v14) )
        {
          v118 = *((_QWORD *)ReservedForOle + 16);
          v119 = *(_QWORD *)(v118 + 384);
          if ( *(_DWORD *)(v118 + 8) )
            v119 += 232;
          if ( *(_DWORD *)(v119 + 4) >= 8u && v4->IsWinrtAsyncCall(v4) )
          {
            v19 = 1;
            if ( gfEnableTracing )
            {
              if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              {
                v105 = *((_QWORD *)ReservedForOle + 16);
                v106 = *(_QWORD *)(v105 + 384);
                if ( *(_DWORD *)(v105 + 8) )
                  v106 += 232;
                ComTraceMessage(
                  -1,
                  "onecore\\com\\combase\\dcomrem\\channelb.cxx",
                  "ComInvokeWithLockAndIPID",
                  1965,
                  VERBOSE,
                  L"Sending auto-retry response to Winrt async call (%u calls already nested)",
                  *(_DWORD *)(v106 + 4));
                ++*((_DWORD *)ReservedForOle + 12);
                pNext = 0;
                v24 = v138->EnumTypeDefs;
                goto LABEL_157;
              }
            }
          }
        }
        ++*((_DWORD *)ReservedForOle + 12);
        pNext = 0;
        v24 = v138->EnumTypeDefs;
        if ( v19 )
        {
LABEL_157:
          v107 = *(_GUID *)((char *)v24 + 376);
          v108 = v133;
          moidForTracing = v107;
          v133->OnSendingAutoRetryResponse(v133);
          v109 = v133->__vftable;
          LOBYTE(aExtent) = 0;
          if ( !v109->IsMachineLocal(v133) || v133->IsFromRpcss(v133, (bool *)&aExtent) < 0 || (_BYTE)aExtent )
          {
            AutoRetryResponseMessage = -2147418111;
          }
          else
          {
            v122 = v108->GetTransportCall(v108);
            AutoRetryResponseMessage = CMessageCall::MakeAutoRetryResponseMessage(v122, &moidForTracing);
            if ( AutoRetryResponseMessage >= 0 && v108->IsProcessLocal(v108) )
            {
              CurrentThreadId = GetCurrentThreadId();
              v124 = v108->GetProcNum(v108);
              v125 = v133->GetTargetInterface(v133, &v141);
              OriginateErrorForStaWithReentrancyGuardTimeout(v125, v124, CurrentThreadId);
              v131.ptr_ = 0;
              pPrimaryUnknown.m_ptr = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v131);
              if ( RoGetMatchingRestrictedErrorInfo(-2147417846, (IRestrictedErrorInfo **)&v131) < 0 )
              {
                v108 = v133;
              }
              else
              {
                v126 = Microsoft::WRL::ComPtr<IRestrictedErrorInfo>::As<IErrorInfo>(
                         (Microsoft::WRL::ComPtr<IRestrictedErrorInfo> *)&v131,
                         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IErrorInfo> >)&pPrimaryUnknown);
                v108 = v133;
                if ( v126 >= 0 )
                {
                  v127 = (__int64)v133->GetTransportCall(v133);
                  passthroughData = (const WireContainerThis *)pPrimaryUnknown.m_ptr;
                  if ( *(IUnknown **)(v127 + 408) != pPrimaryUnknown.m_ptr )
                  {
                    v136.ptr_ = (IMetaDataImport2 *)pPrimaryUnknown.m_ptr;
                    Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::InternalAddRef(&v136);
                    v136.ptr_ = *(IMetaDataImport2 **)(v127 + 408);
                    *(_QWORD *)(v127 + 408) = passthroughData;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v136);
                  }
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&pPrimaryUnknown);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v131);
            }
            v108->Finalize(v108);
          }
LABEL_32:
          v30 = (CStdMarshal *)((char *)v138->EnumTypeDefs + 8);
          v31 = _InterlockedExchangeAdd((volatile signed __int32 *)v138->EnumTypeDefs + 16, 0xFFFFFFFF);
          v132 = 0;
          COleStaticMutexSem::Request(&gIPIDLock, "onecore\\com\\combase\\dcomrem\\marshal.hxx", 0x370u, v15);
          v32 = CStdMarshal::GetFlags(v30) & 2;
          LODWORD(v131.ptr_) = v32;
          v34 = v31 - 1;
          if ( v34 || !v32 )
          {
            COleStaticMutexSem::Release(&gIPIDLock);
            if ( v34 || !LODWORD(v131.ptr_) )
            {
              v30->Release(v30);
LABEL_35:
              if ( v7 )
              {
                if ( v7->_mutex.m_fCsInitialized == 1 )
                  EnterCriticalSection(&v7->_mutex.m_cs);
                --v7->_cObjRefs;
                ++v7->_decrementCounts[0];
                if ( v7->_disconnecting && !v7->_cObjRefs )
                  SetEvent(v7->_hdisconnectEvent);
                if ( v7->_mutex.m_fCsInitialized == 1 )
                  LeaveCriticalSection(&v7->_mutex.m_cs);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v7->_cRefs, 0xFFFFFFFF) == 1 )
                {
                  CCtxConnectionManager::~CCtxConnectionManager(v7);
                  HeapFree(g_hHeap, 0, v7);
                }
              }
              v35 = v140;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v140->GetClassLayout, 0xFFFFFFFF) == 1 )
              {
                if ( BYTE1(v35->FindMethod) )
                {
                  v121 = (int)v35->GetScopeProps;
                  if ( (v121 & 0x1000000) != 0 || (v121 & 0x2000000) != 0 )
                  {
                    v35 = (IMetaDataImport2_vtbl *)v35->GetMethodSemantics;
                    if ( v35 )
                      SetEvent(v35);
                  }
                }
              }
              --*((_DWORD *)ReservedForOle + 12);
              if ( pNext )
                ((void (__fastcall *)(tagPageEntry *))pNext->pNext[1].pNext)(pNext);
              if ( (v6->gap8[12] & 0x24) == 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v35);
              if ( (v6->gap8[12] & 0x20) != 0 )
              {
                m_ptr = v6->_processLocalRequestBuffer.m_ptr;
                if ( m_ptr )
                {
                  LastError = GetLastError();
                  HeapFree(g_hHeap, 0, m_ptr);
                  SetLastError(LastError);
                }
                v6->_processLocalRequestBuffer.m_ptr = 0;
              }
              v6->_orpcThis = 0;
              v6->_sizeOfOrpcThis = 0;
              v6->_containerThis = 0;
              v6->_sizeOfContainerThis = 0;
              v6->_localThis = 0;
              v6->_sizeOfLocalThis = 0;
              v6->_requestStubData = 0;
              v6->_sizeOfRequestStubData = 0;
              v6->_clientLocalThisFlags = 0;
              v6->_clientWinrtAsyncRequestBlock = 0;
              v6->Release(v6);
              return (unsigned int)AutoRetryResponseMessage;
            }
            PendingDisconnectType = v132;
          }
          else
          {
            PendingDisconnectType = CStdMarshal::GetPendingDisconnectType(v33);
            COleStaticMutexSem::Release(&gIPIDLock);
          }
          CStdMarshal::DisconnectAndRelease(v30, PendingDisconnectType);
          goto LABEL_35;
        }
        ptr = v136.ptr_;
LABEL_26:
        v25 = *((_QWORD *)v24 + 20);
        if ( v25 )
        {
          v29 = *(IUnknown **)(v25 + 48);
        }
        else
        {
          v26 = ptr[4].__vftable;
          pPrimaryUnknown.m_ptr = 0;
          v27 = (*(__int64 (__fastcall **)(IMetaDataImport2_vtbl *, GUID *, wil::com_ptr_t<IUnknown,wil::err_returncode_policy> *))v26->QueryInterface)(
                  v26,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  &pPrimaryUnknown);
          AutoRetryResponseMessage = v27;
          if ( v27 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, 0x7CCu, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v27);
          v29 = pPrimaryUnknown.m_ptr;
          if ( pPrimaryUnknown.m_ptr )
            pPrimaryUnknown.m_ptr->Release(pPrimaryUnknown.m_ptr);
          if ( AutoRetryResponseMessage < 0 )
            goto LABEL_32;
        }
        pLock = CServerSecurity::_palloc._pgalloc._pLock;
        if ( CServerSecurity::_palloc._pgalloc._pLock )
          COleStaticMutexSem::Request(
            CServerSecurity::_palloc._pgalloc._pLock,
            "onecore\\com\\combase\\coll\\pgalloc.cxx",
            0x7Cu,
            v15);
        pNext = CServerSecurity::_palloc._pgalloc._ListHead.pNext;
        pPrimaryUnknown.m_ptr = (IUnknown *)CServerSecurity::_palloc._pgalloc._ListHead.pNext;
        if ( CServerSecurity::_palloc._pgalloc._ListHead.pNext )
          CServerSecurity::_palloc._pgalloc._ListHead.pNext = CServerSecurity::_palloc._pgalloc._ListHead.pNext->pNext;
        if ( pLock )
        {
          v41 = pLock->_cLocks-- == 1;
          if ( v41 )
          {
            lockOrder = (unsigned __int8)pLock->_lockOrder;
            if ( (_BYTE)lockOrder != 19 )
            {
              v43 = (IMetaDataImport2 *)NtCurrentTeb()->ReservedForOle;
              v131.ptr_ = v43;
              if ( v43 )
              {
                v44 = 1 << lockOrder;
                HIDWORD(aExtent) = 1 << lockOrder;
                if ( ((1 << lockOrder) & (__int64)v43[72].__vftable) == 0 )
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs(lockOrder);
                  v44 = HIDWORD(aExtent);
                  v43 = v131.ptr_;
                }
                LODWORD(v43[72].__vftable) &= ~v44;
              }
            }
          }
          LeaveCriticalSection(&pLock->_cs);
        }
        if ( pNext
          || (pPrimaryUnknown.m_ptr = (IUnknown *)CInternalPageAllocator::Grow(&CServerSecurity::_palloc._pgalloc),
              (pNext = (tagPageEntry *)pPrimaryUnknown.m_ptr) != 0) )
        {
          _InterlockedIncrement(&CServerSecurity::_palloc._pgalloc._cEntries);
          pNext->dwFlag = -1592734483;
          size = 0;
        }
        else
        {
          size = 0;
          pNext = 0;
          pPrimaryUnknown.m_ptr = 0;
        }
        if ( ComVerifierSettings::s_fPgAllocUseSystemHeap )
        {
          if ( !pNext )
            goto LABEL_217;
          if ( !CServerSecurity::_palloc._hHeap
            || (pNext[1].pNext = 0,
                (v128 = (tagPageEntry *)HeapAlloc(
                                          CServerSecurity::_palloc._hHeap,
                                          8u,
                                          CServerSecurity::_palloc._cbPerEntry)) == 0) )
          {
            CInternalPageAllocator::ReleaseEntry(&CServerSecurity::_palloc._pgalloc, pNext);
            goto LABEL_217;
          }
          LODWORD(v128->pNext) = CInternalPageAllocator::GetEntryIndex(&CServerSecurity::_palloc._pgalloc, pNext);
          HIDWORD(v128->pNext) = 322424845;
          pNext[1].pNext = v128;
          _InterlockedIncrement(&CServerSecurity::_palloc._lNumEntries);
          pNext = v128 + 1;
          size = 0;
          pPrimaryUnknown.m_ptr = (IUnknown *)pNext;
        }
        if ( pNext )
        {
          reserved1 = (tagPageEntry *)v6->message.reserved1;
          pNext->pNext = (tagPageEntry *)CServerSecurity::`vftable'{for `IServerSecurity'};
          *(_QWORD *)&pNext->dwFlag = CServerSecurity::`vftable'{for `ICancelMethodCalls'};
          pNext[1].pNext = (tagPageEntry *)CServerSecurity::`vftable'{for `IComDispatchInfo'};
          *(_QWORD *)&pNext[1].dwFlag = CServerSecurity::`vftable'{for `ICallingProcessInfo'};
          pNext[2].pNext = (tagPageEntry *)CServerSecurity::`vftable'{for `IIndirectCallTarget'};
          *(_QWORD *)&pNext[2].dwFlag = CServerSecurity::`vftable'{for `ICallLocalityInfo'};
          pNext[3].pNext = (tagPageEntry *)1;
          *(_QWORD *)&pNext[3].dwFlag = v6->_spHandle.ptr_;
          pNext[4].pNext = reserved1;
          *(_QWORD *)&pNext[4].dwFlag = 0;
          pNext[5].pNext = 0;
          *(_QWORD *)&pNext[5].dwFlag = v29;
          pNext[6].pNext = 0;
          if ( (v6->gap8[12] & 0x20) != 0 )
          {
            v48 = 0;
          }
          else
          {
            dwDestCtx = v6->_destObj._dwDestCtx;
            if ( dwDestCtx == 5 )
            {
              v48 = 2;
            }
            else
            {
              v41 = dwDestCtx == 2;
              v48 = 3;
              if ( !v41 )
                v48 = 1;
            }
          }
          pNext[6].dwFlag = v48;
          if ( (v6->gap8[12] & 0x20) != 0 )
            *(_QWORD *)&pNext[4].dwFlag = v6;
          v49 = NtCurrentTeb()->ReservedForOle;
          if ( (*((_DWORD *)v49 + 5) & 0x200) != 0 )
          {
            HIDWORD(pNext[3].pNext) |= 2u;
            pNext[5].pNext = (tagPageEntry *)v49[29];
            v49[29] = 0;
            *((_DWORD *)v49 + 5) &= ~0x200u;
          }
          *((_QWORD *)ReservedForOle + 17) = pNext;
          v50 = *(_DWORD *)&v6->gap8[12] & 0x20;
          v132 = v50;
          if ( gAccessControl && !v50 && CheckAccessControl() )
          {
            AutoRetryResponseMessage = -2147024891;
LABEL_144:
            v101 = v133->IsServerAsyncAbiModel(v133);
            v102 = NtCurrentTeb()->ReservedForOle;
            if ( v102 )
            {
              v103 = *((_DWORD *)v102 + 5);
              if ( (v103 & 0x200) != 0 )
              {
                *((_DWORD *)v102 + 5) = v103 & 0xFFFFFDFF;
                if ( pNext[6].dwFlag
                  && (BYTE4(pNext[3].pNext) & 4) == 0
                  && (v110 = RpcRevertToSelfEx(pNext[4].pNext)) != 0 )
                {
                  wil::details::in1diag3::Return_Win32(
                    retaddr,
                    0x118Eu,
                    "onecore\\com\\combase\\dcomrem\\security.cxx",
                    v110);
                }
                else
                {
                  HIDWORD(pNext[3].pNext) &= ~4u;
                  v111 = (void *)*((_QWORD *)v102 + 29);
                  if ( v111 )
                  {
                    if ( SetThreadToken(0, v111) )
                    {
                      CloseHandle(*((HANDLE *)v102 + 29));
                      *((_QWORD *)v102 + 29) = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        0x119Eu,
                        "onecore\\com\\combase\\dcomrem\\security.cxx");
                    }
                  }
                  else if ( !SetThreadToken(0, 0) )
                  {
                    wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      0x119Au,
                      "onecore\\com\\combase\\dcomrem\\security.cxx");
                  }
                }
              }
            }
            if ( !v101 )
            {
              HIDWORD(pNext[3].pNext) |= 1u;
              *(_QWORD *)&pNext[3].dwFlag = 0;
              pNext[4].pNext = 0;
            }
            if ( (BYTE4(pNext[3].pNext) & 2) != 0 )
            {
              v104 = NtCurrentTeb()->ReservedForOle;
              v104[5] |= 0x200u;
              *((_QWORD *)v104 + 29) = pNext[5].pNext;
              HIDWORD(pNext[3].pNext) &= ~2u;
              pNext[5].pNext = 0;
            }
            goto LABEL_32;
          }
          if ( ComVerifierSettings::s_singleton._pSettingsState )
          {
            if ( (v6->gap8[12] & 0x20) == 0 )
            {
              hRpc = v6->_hRpc;
              LOBYTE(aExtent) = 0;
              if ( IsRpcServerCallOnLocalTransport(hRpc, (bool *)&aExtent) >= 0 && !(_BYTE)aExtent )
                CoVrfCheckServerSecurityBlanket();
            }
          }
          *((_BYTE *)&ctxCall + 208) &= 0xFCu;
          *((_QWORD *)ReservedForOle + 7) = v133;
          *(_QWORD *)ctxCall.gap8 = CCtxCall::`vbtable';
          dataRepresentation = v6->message.dataRepresentation;
          ctxCall._passthroughTraceActivity = GUID_NULL;
          *(_QWORD *)&ctxCall.gap151[15] = CCtxCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
          *(_DWORD *)&ctxCall.gap151[11] = 0;
          *(_QWORD *)ctxCall.gap20 = 2;
          memset(
            &ctxCall.ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >
          + 1,
            0,
            20);
          ctxCall._dwDestCtx = -1;
          memset(&ctxCall._cItfs, 0, 36);
          ctxCall._pPS = 0;
          ctxCall._pContext = 0;
          ctxCall._dataRep = dataRepresentation;
          ctxCall._hrServer = 0;
          ctxCall._iMethod = 0;
          ctxCall._piid = 0;
          ctxCall._uCallTraceId = 0;
          ctxCall._savedErrorObject.error.ptr_ = 0;
          ctxCall._savedErrorObject.passthroughData.__ptr_.__value_ = 0;
          ctxCall._enableCallTracing = 0;
          memset(&ctxCall._pInBiasContainer, 0, 24);
          memset(&ctxCall._callTraceActivity, 0, 68);
          MarshalByValueSerializationData::MarshalByValueSerializationData(&ctxCall._marshalByValueSerializationData);
          ctxCall._clientSyncTraceStarted = 0;
          ctxCall.ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ObjectNoComReferenceCounting,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxCall,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::ObjectLibrary::Details::AddGeneralTypeIdentity<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> > >::ObjectLibrary::Details::AddGeneralTypeIdentityHelper<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >,0>::ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >::ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::CBaseCall::ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil>::ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> >::__vftable = (CCtxCall_vtbl *)CCtxCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
          *(_QWORD *)ctxCall.gap10 = CCtxCall::`vftable'{for `ICallFrameWalker'};
          ctxCall.ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ObjectNoComReferenceCounting,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxCall,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::ObjectLibrary::Details::AddGeneralTypeIdentity<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> > >::ObjectLibrary::Details::AddGeneralTypeIdentityHelper<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >,0>::ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >::ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::IServerCall::ObjectLibrary::IComReferenceCounting::__vftable = (IServerCall_vtbl *)CCtxCall::`vftable'{for `IServerCall'};
          dwLocalClientPID = 0;
          *(_QWORD *)&ctxCall.gap8[*(int *)(*(_QWORD *)ctxCall.gap8 + 4LL)] = v52;
          v53 = *(int *)(*(_QWORD *)ctxCall.gap8 + 4LL);
          *(_QWORD *)(v54 + 128) = &ctxCall;
          v55 = v136.ptr_;
          *(_DWORD *)((char *)&ctxCall.ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ObjectNoComReferenceCounting,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CCtxCall,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::ObjectLibrary::Details::AddGeneralTypeIdentity<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> > >::ObjectLibrary::Details::AddGeneralTypeIdentityHelper<CCtxCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >,0>::ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CCtxCall,ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::AddTypeIdLayerHelper<ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil> >::ObjectLibrary::Details::MixinBase<CCtxCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> > >::ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,ICallFrameWalker,IServerCall> >::CBaseCall::ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::Nil>::ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> >::__vftable
                    + v53
                    + 4) = v53 - 344;
          v6->_dwServerTid = (unsigned int)v55[6].CloseEnum;
          if ( v6->_destObj.GetDestCtx(&v6->_destObj) == 5 )
          {
            AutoRetryResponseMessage = CMessageCall::SetContainerPassthroughDataCopiedFromContainerThis(v6);
            dwClientThread = 0;
          }
          else
          {
            if ( v6->_destObj.GetDestCtx(&v6->_destObj) == 5 )
              MicrosoftTelemetryAssertTriggeredNoArgs(v56);
            p_size = ReservedForOle + 144;
            v58 = (IMetaDataImport2 *)*((_QWORD *)ReservedForOle + 18);
            HIDWORD(aExtent) = v6->_sizeOfOrpcThis;
            orpcThis = (const WireExtentArray *)v6->_orpcThis;
            *((_QWORD *)ReservedForOle + 18) = &ctxCall;
            v60 = gHookList.pNext;
            v61 = v6->message.dataRepresentation;
            v62 = &orpcThis->unique_flag[3];
            v139 = orpcThis;
            v131.ptr_ = v58;
            v137 = v61;
            if ( gHookList.pNext != &gHookList || *v62 )
            {
              if ( !gNumExtent )
              {
                *p_size = v58;
                AutoRetryResponseMessage = -2147417838;
                goto LABEL_143;
              }
              *(_QWORD *)&moidForTracing.Data1 = 0;
              v63 = 8LL * gNumExtent;
              if ( !is_mul_ok(gNumExtent, 8u) )
                v63 = -1;
              if ( !is_mul_ok(gNumExtent, 8u) )
                ObjectLibrary::Details::LogicalError(-2147024362, 0);
              v64 = 8LL * gNumExtent + 15;
              if ( v64 <= 8 * (unsigned __int64)gNumExtent )
                v64 = 0xFFFFFFFFFFFFFF0LL;
              v65 = alloca(v64 & 0xFFFFFFFFFFFFFFF0uLL);
              memset_0(&aExtent, 0, v63);
              if ( *v62 )
              {
                v116 = v139;
                v117 = (char *)ValidateAndParseExtentArray(
                                 v60,
                                 (const WireExtentArray *)&v139->unique_flag[4],
                                 HIDWORD(aExtent) - 32,
                                 gNumExtent,
                                 &aExtent);
                if ( v117 != (char *)v116 + HIDWORD(aExtent) )
                {
                  AutoRetryResponseMessage = -2147417838;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    0x263u,
                    "onecore\\com\\combase\\dcomrem\\chock.cxx",
                    -2147417838);
                  *((Microsoft::WRL::ComPtr<IMetaDataImport2> *)ReservedForOle + 18) = v131;
                  goto LABEL_143;
                }
              }
              v58 = v131.ptr_;
              v66 = 0;
              p_size = ReservedForOle + 144;
              v139 = (const WireExtentArray *)(ReservedForOle + 144);
              if ( v60 != &gHookList )
              {
                v67 = v137;
                do
                {
                  v68 = (__int64)*(&aExtent + v66);
                  v69 = (void *)(v68 + 24);
                  if ( v68 )
                  {
                    v70 = *(unsigned int *)(v68 + 20);
                  }
                  else
                  {
                    v69 = 0;
                    v70 = 0;
                  }
                  v60->pHook->ServerNotify(v60->pHook, &v60->uExtension, &v6->_iidWire, v70, v69, v67);
                  v60 = v60->pNext;
                  v66 = (unsigned int)(v66 + 1);
                }
                while ( v60 != &gHookList );
                pNext = (tagPageEntry *)pPrimaryUnknown.m_ptr;
                v7 = (CCtxConnectionManager *)passthroughData;
                p_size = &v139->size;
                v58 = v131.ptr_;
              }
            }
            size = 0;
            *p_size = v58;
            v71 = v6->_destObj._dwDestCtx;
            AutoRetryResponseMessage = 0;
            if ( v71 == 2 )
            {
              dwClientThread = dwLocalClientPID;
            }
            else
            {
              if ( v71 == 5 )
              {
                dwClientThread = dwLocalClientPID;
                goto LABEL_108;
              }
              localThis = v6->_localThis;
              sizeOfLocalThis = v6->_sizeOfLocalThis;
              dwLocalClientPID = 0;
              passthroughData = 0;
              HIDWORD(aExtent) = 0;
              v74 = ValidateAndCalculateSizeOfIncomingLocalThis(
                      sizeOfLocalThis,
                      localThis,
                      (unsigned int *)&aExtent + 1,
                      &dwLocalClientPID,
                      &passthroughData);
              AutoRetryResponseMessage = v74;
              if ( v74 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0x292u,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
                  v74);
                goto LABEL_143;
              }
              if ( HIDWORD(aExtent) != sizeOfLocalThis )
              {
                AutoRetryResponseMessage = -2147417839;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0x294u,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
                  -2147417839);
                goto LABEL_143;
              }
              v6->_requestContainerPassthroughDataSize = dwLocalClientPID;
              v6->_requestContainerPassthroughData = passthroughData;
              dwClientThread = localThis->part1.dwClientThread;
              size = 0;
              AutoRetryResponseMessage = 0;
            }
          }
          if ( AutoRetryResponseMessage < 0 )
          {
LABEL_143:
            CCtxCall::~CCtxCall(&ctxCall);
            goto LABEL_144;
          }
LABEL_108:
          v41 = v132 == 0;
          requestContainerPassthroughDataSize = v6->_requestContainerPassthroughDataSize;
          v77 = NtCurrentTeb()->ReservedForOle;
          v139 = (const WireExtentArray *)*((_QWORD *)v77 + 68);
          v137 = *((_DWORD *)v77 + 138);
          LODWORD(v131.ptr_) = *((_DWORD *)v77 + 139);
          *((_QWORD *)v77 + 68) = v6->_requestContainerPassthroughData;
          *((_QWORD *)v77 + 69) = requestContainerPassthroughDataSize;
          *((_DWORD *)ReservedForOle + 22) = dwClientThread;
          v78 = *((_DWORD *)ReservedForOle + 5);
          if ( v41 )
          {
            HIDWORD(aExtent) = 0;
            *((_DWORD *)ReservedForOle + 5) = v78 & 0xFFFFFFFE;
            if ( I_RpcBindingInqTransportType(v6->_hRpc, (unsigned int *)&aExtent + 1) || HIDWORD(aExtent) != 4 )
            {
              *((_DWORD *)ReservedForOle + 107) = 0;
            }
            else
            {
              dwLocalClientPID = 0;
              if ( !I_RpcBindingInqLocalClientPID(v6->_hRpc, &dwLocalClientPID) )
                *((_DWORD *)ReservedForOle + 107) = dwLocalClientPID;
            }
          }
          else
          {
            *((_DWORD *)ReservedForOle + 5) = v78 | 1;
            *((_DWORD *)ReservedForOle + 107) = HIDWORD(v140->CloseEnum);
          }
          if ( v6 != (CMessageCall *)-168LL )
            v6->message.cbBuffer = v6->_sizeOfRequestStubData;
          requestStubData = (void *)v6->_requestStubData;
          v6->message.iMethod &= ~0x8000u;
          v80 = v133;
          v81 = v136.ptr_;
          v6->message.Buffer = requestStubData;
          v80->Initialize(
            v80,
            (CStdIdentity *)v138->EnumTypeDefs,
            (bool)v138->EnumTypeRefs,
            (CObjectContext *)v138->GetScopeProps,
            (tagIPIDEntry *)v81);
          v6->message.reserved1 = v80;
          v82 = *(unsigned int *)&v6->gap8[12];
          if ( (v82 & 0x24) == 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v82);
            v82 = *(unsigned int *)&v6->gap8[12];
          }
          v83 = v6->_destObj._dwDestCtx;
          if ( v83 != 2 && v83 != 5 && (v6->_localThis->part1.dwFlags & 0x800) != 0 )
            v6->message.rpcFlags |= 0x80000000;
          if ( (v82 & 0x24) == 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v82);
            v82 = *(unsigned int *)&v6->gap8[12];
          }
          v84 = v6->_destObj._dwDestCtx;
          if ( v84 == 2 || v84 == 5 || (v85 = v6->_localThis, !v85->part1.unique_pTouchedAstaArray) )
          {
            astaOxids = 0;
          }
          else
          {
            size = v85->touchedAstas.size;
            astaOxids = v85->touchedAstas.astaOxids;
          }
          if ( (v82 & 0x24) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v82);
          v87 = v6->_destObj._dwDestCtx;
          if ( v87 == 2 || v87 == 5 )
          {
            v90 = 0;
          }
          else
          {
            dwFlags = v6->_localThis->part1.dwFlags;
            v89 = ((dwFlags & 0x4000) << 12) | 0x8000000;
            if ( (dwFlags & 0x8000) == 0 )
              v89 = (dwFlags & 0x4000) << 12;
            v90 = v89 | 0x10000000;
            if ( (dwFlags & 0x10000) == 0 )
              v90 = v89;
          }
          v91 = NtCurrentTeb()->ReservedForOle;
          v92 = v91[5];
          v132 = v91[129];
          *(_QWORD *)&v141.Data1 = *((_QWORD *)v91 + 65);
          v91[129] = size;
          *((_QWORD *)v91 + 65) = astaOxids;
          v91[5] = v90 | v92 & 0xE3FFFFFF;
          v93 = NtCurrentTeb()->ReservedForOle;
          if ( !v93 )
          {
            v96 = g_apartmentTypeSpecificRoutines[2].InvokeInApartment(v133, (tagIPIDEntry *)v136.ptr_);
            goto LABEL_140;
          }
          v94 = v93[5];
          if ( (v94 & 0x800) != 0 )
          {
            v96 = g_apartmentTypeSpecificRoutines[3].InvokeInApartment(v133, (tagIPIDEntry *)v136.ptr_);
          }
          else
          {
            if ( (v94 & 0x80u) != 0 )
            {
              if ( (v94 & 0x400000) != 0 )
              {
                v96 = g_apartmentTypeSpecificRoutines[1].InvokeInApartment(v133, (tagIPIDEntry *)v136.ptr_);
                goto LABEL_140;
              }
              v112 = (v94 & 0x40000000) != 0;
              InvokeInApartment = g_apartmentTypeSpecificRoutines[0].InvokeInApartment;
              if ( v112 )
                InvokeInApartment = g_apartmentTypeSpecificRoutines[4].InvokeInApartment;
            }
            else
            {
              InvokeInApartment = g_apartmentTypeSpecificRoutines[2].InvokeInApartment;
            }
            v96 = InvokeInApartment(v133, (tagIPIDEntry *)v136.ptr_);
          }
LABEL_140:
          AutoRetryResponseMessage = v96;
          v97 = NtCurrentTeb()->ReservedForOle;
          v97[129] = v132;
          *((_QWORD *)v97 + 65) = *(_QWORD *)&v141.Data1;
          v97[5] ^= (v92 ^ v97[5]) & 0x1C000000;
          v98 = v6->_marshaledHandles[0];
          if ( v98 )
          {
            MarshaledHandleStorage::`scalar deleting destructor'(v98, (unsigned int)v97);
            v6->_marshaledHandles[0] = 0;
          }
          passthroughData = 0;
          v99 = v138->EnumTypeDefs;
          QueryUnbiasedInterruptTime((PULONGLONG)&passthroughData);
          _InterlockedExchange64((volatile __int64 *)v99 + 30, (unsigned __int64)passthroughData / 0x2710);
          v100 = NtCurrentTeb()->ReservedForOle;
          v100[68] = v139;
          *((_DWORD *)v100 + 138) = v137;
          *((_DWORD *)v100 + 139) = v131.ptr_;
          goto LABEL_143;
        }
LABEL_217:
        AutoRetryResponseMessage = -2147024882;
        pNext = 0;
        goto LABEL_32;
      }
      LOBYTE(v14) = 0;
    }
    else
    {
      v14 = 1;
    }
    v21 = *(_BYTE **)(v18 + 384);
    if ( !(_BYTE)v14 )
      v21 += 232;
    if ( *v21
      || ReentrantSTAState::s_astaCallReentrancyGuardEnabledByDefault
      && ((v115 = *((_QWORD *)NtCurrentTeb()->ReservedForOle + 16), *(_DWORD *)(v115 + 8))
       || !*(_QWORD *)(*(_QWORD *)(v115 + 384) + 8LL)) )
    {
      if ( *((_DWORD *)ReservedForOle + 118) )
      {
        if ( !v4->_isLogicalThreadCallback )
        {
          v19 = 1;
          if ( gfEnableTracing )
          {
            if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              ComTraceMessage(
                -1,
                "onecore\\com\\combase\\dcomrem\\channelb.cxx",
                "ComInvokeWithLockAndIPID",
                1950,
                VERBOSE,
                L"Sending auto-retry response due to calls from ASTA on the stack");
          }
        }
      }
    }
    goto LABEL_23;
  }
  if ( (CObjectContext::GetFlags((CObjectContext *)v8->GetScopeProps) & 0x200) == 0 )
  {
    if ( !memcmp_0(&ptr[9], &IID_ILocalSystemActivator, 0x10u) )
    {
      v7 = (CCtxConnectionManager *)*((_QWORD *)GetScopeProps + 36);
      passthroughData = (const WireContainerThis *)v7;
      _InterlockedIncrement((volatile signed __int32 *)&v7->_cRefs);
      if ( v7->_mutex.m_fCsInitialized == 1 )
        EnterCriticalSection(&v7->_mutex.m_cs);
      ++v7->_cObjRefs;
      ++v7->_incrementCounts[0];
      if ( v7->_mutex.m_fCsInitialized == 1 )
        LeaveCriticalSection(&v7->_mutex.m_cs);
    }
    goto LABEL_4;
  }
  if ( !--gIPIDLock._cLocks && gIPIDLock._lockOrder != Highest )
  {
    v113 = NtCurrentTeb()->ReservedForOle;
    if ( v113 )
    {
      v114 = 1 << gIPIDLock._lockOrder;
      if ( ((1 << gIPIDLock._lockOrder) & v113[144]) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs((unsigned __int8)gIPIDLock._lockOrder);
      v113[144] &= ~v114;
    }
  }
  LeaveCriticalSection(&gIPIDLock._cs);
  if ( v6 )
    v6->Release(v6);
  return 2147549448LL;
}

```

## disassembly

```asm
0x180004d50  push    rbp
0x180004d52  push    rsi
0x180004d53  push    rdi
0x180004d54  push    r12
0x180004d56  push    r13
0x180004d58  push    r14
0x180004d5a  push    r15
0x180004d5c  sub     rsp, 240h
0x180004d63  lea     rbp, [rsp+40h]
0x180004d68  mov     [rbp+230h+arg_10], rbx
0x180004d6f  mov     rax, cs:__security_cookie
0x180004d76  xor     rax, rbp
0x180004d79  mov     [rbp+230h+var_40], rax
0x180004d80  mov     rax, [pServerCall]
0x180004d83  mov     r15, pIPIDEntry
0x180004d86  mov     [rbp+230h+var_1F8.ptr_], pIPIDEntry
0x180004d8a  mov     r14, pServerCall
0x180004d8d  mov     [rbp+230h+var_210], pServerCall
0x180004d91  mov     rax, [rax+0F0h]
0x180004d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9d  mov     rbx, rax
0x180004da0  test    rax, rax
0x180004da3  jz      short loc_180004DB3
0x180004da5  mov     rax, [rax]
0x180004da8  mov     pServerCall, rbx
0x180004dab  mov     rax, [rax]
0x180004dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db3  mov     rdi, gs:30h
0x180004dbc  xor     r13d, r13d
0x180004dbf  mov     r12, [r15+58h]
0x180004dc3  mov     [rbp+230h+var_1E8], r12
0x180004dc7  mov     [rbp+230h+passthroughData], r13
0x180004dcb  mov     rdi, [rdi+1758h]
0x180004dd2  mov     rsi, [r12+50h]
0x180004dd7  test    rsi, rsi
0x180004dda  jnz     loc_180005B7A
0x180004de0  mov     rax, [r15+30h]
0x180004de4  mov     [rbp+230h+var_1D8], rax
0x180004de8  lock inc dword ptr [rax+128h]
0x180004def  mov     rsi, [r12+30h]
0x180004df4  mov     rax, [rsi+8]
0x180004df8  lea     pServerCall, [rsi+8]
0x180004dfc  mov     rax, [rax+8]
0x180004e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e05  lock inc dword ptr [rsi+40h]
0x180004e09  mov     eax, cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._cLocks; COleStaticMutexSem gIPIDLock ...
0x180004e0f  mov     r12d, 1
0x180004e15  add     eax, 0FFFFFFFFh
0x180004e18  mov     cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._cLocks, eax; COleStaticMutexSem gIPIDLock ...
0x180004e1e  jnz     short loc_180004E64
0x180004e20  cmp     cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gIPIDLock ...
0x180004e27  jz      short loc_180004E64
0x180004e29  mov     rax, gs:30h
0x180004e32  mov     r14, [rax+1758h]
0x180004e39  test    r14, r14
0x180004e3c  jz      short loc_180004E60
0x180004e3e  movzx   ecx, cs:?gIPIDLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gIPIDLock ...
0x180004e45  mov     esi, r12d
0x180004e48  shl     esi, cl
0x180004e4a  test    [r14+240h], esi
0x180004e51  jz      loc_180005F15
0x180004e57  not     esi
0x180004e59  and     [r14+240h], esi
0x180004e60  mov     r14, [rbp+230h+var_210]
0x180004e64  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x180004e6b  call    cs:__imp_LeaveCriticalSection
0x180004e71  mov     rax, gs:30h
0x180004e7a  mov     rax, [rax+1758h]
0x180004e81  test    rax, rax
0x180004e84  jz      loc_180005F64
0x180004e8a  mov     eax, [rax+14h]
0x180004e8d  bt      eax, 0Bh
0x180004e91  jb      loc_180005F64
0x180004e97  test    al, al
0x180004e99  jns     loc_180005F64
0x180004e9f  bt      eax, 16h
0x180004ea3  jb      loc_180005F64
0x180004ea9  mov     pServerCall, [rdi+80h]
0x180004eb0  xor     r15b, r15b
0x180004eb3  mov     eax, [pServerCall+8]
0x180004eb6  test    eax, eax
0x180004eb8  jnz     loc_180006056
0x180004ebe  movzx   edx, r12b; whichProperty
0x180004ec2  mov     pServerCall, [pServerCall+180h]
0x180004ec9  test    dl, dl
0x180004ecb  lea     rax, [pServerCall+0E8h]
0x180004ed2  cmovz   pServerCall, rax
0x180004ed6  cmp     [pServerCall], r15b
0x180004ed9  jnz     loc_180005E39
0x180004edf  cmp     cs:?s_astaCallReentrancyGuardEnabledByDefault@ReentrantSTAState@@0_NA, r15b; bool ReentrantSTAState::s_astaCallReentrancyGuardEnabledByDefault
0x180004ee6  jnz     loc_180005E0A
0x180004eec  xor     al, al
0x180004eee  test    al, al
0x180004ef0  jnz     loc_180005D97
0x180004ef6  xor     ecx, ecx; whichProperty
0x180004ef8  call    ?Query@FeatureDevelopmentProperties@@YA_NW4BoolProperty@1@PEA_N@Z; FeatureDevelopmentProperties::Query(FeatureDevelopmentProperties::BoolProperty,bool *)
0x180004efd  test    al, al
0x180004eff  jnz     loc_180005F77
0x180004f05  inc     dword ptr [rdi+30h]
0x180004f08  xor     r14d, r14d
0x180004f0b  mov     rsi, [rbp+230h+var_1E8]
0x180004f0f  mov     rsi, [rsi+30h]
0x180004f13  test    r15b, r15b
0x180004f16  jnz     loc_180005B30
0x180004f1c  mov     r15, [rbp+230h+var_1F8.ptr_]
0x180004f20  mov     rsi, [rsi+0A0h]
0x180004f27  test    rsi, rsi
0x180004f2a  jnz     loc_180005191
0x180004f30  mov     pServerCall, [r15+20h]
0x180004f34  lea     r8, [rbp+230h+pPrimaryUnknown]
0x180004f38  mov     [rbp+230h+pPrimaryUnknown.m_ptr], rsi
0x180004f3c  lea     pIPIDEntry, _GUID_00000000_0000_0000_c000_000000000046
0x180004f43  mov     rax, [pServerCall]
0x180004f46  mov     rax, [rax]
0x180004f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4e  mov     r12d, eax
0x180004f51  test    eax, eax
0x180004f53  jns     short loc_180004F70
0x180004f55  mov     pServerCall, [rbp+238h]; callerReturnAddress
0x180004f5c  lea     r8, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180004f63  mov     r9d, eax; hr
0x180004f66  mov     edx, 7CCh; lineNumber
0x180004f6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004f70  mov     rsi, [rbp+230h+pPrimaryUnknown.m_ptr]
0x180004f74  test    rsi, rsi
0x180004f77  jz      short loc_180004F88
0x180004f79  mov     rax, [rsi]
0x180004f7c  mov     pServerCall, rsi
0x180004f7f  mov     rax, [rax+10h]
0x180004f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f88  test    r12d, r12d
0x180004f8b  jns     loc_1800060E2
0x180004f91  mov     rax, [rbp+230h+var_1E8]
0x180004f95  mov     esi, 0FFFFFFFFh
0x180004f9a  mov     r15, [rax+30h]
0x180004f9e  add     r15, 8
0x180004fa2  lock xadd [r15+38h], esi
0x180004fa8  mov     r8d, 370h; dwLine
0x180004fae  mov     [rbp+230h+var_218], 0
0x180004fb5  lea     pIPIDEntry, aOnecoreComComb_137; "onecore\\com\\combase\\dcomrem\\marshal"...
0x180004fbc  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A; this
0x180004fc3  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180004fc8  mov     pServerCall, r15; this
0x180004fcb  call    ?GetFlags@CStdMarshal@@IEBAKXZ; CStdMarshal::GetFlags(void)
0x180004fd0  and     eax, 2
0x180004fd3  mov     dword ptr [rbp+230h+var_220.ptr_], eax
0x180004fd6  sub     esi, 1
0x180004fd9  jz      loc_180005170
0x180004fdf  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A; this
0x180004fe6  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180004feb  test    esi, esi
0x180004fed  jz      loc_180005C0B
0x180004ff3  mov     rax, [r15]
0x180004ff6  mov     pServerCall, r15
0x180004ff9  mov     rax, [rax+10h]
0x180004ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005002  test    r13, r13
0x180005005  jz      short loc_180005059
0x180005007  cmp     dword ptr [r13+68h], 1
0x18000500c  jnz     short loc_180005018
0x18000500e  lea     pServerCall, [r13+40h]; lpCriticalSection
0x180005012  call    cs:__imp_EnterCriticalSection
0x180005018  mov     eax, [r13+30h]
0x18000501c  dec     eax
0x18000501e  mov     [r13+30h], eax
0x180005022  inc     dword ptr [r13+98h]
0x180005029  cmp     byte ptr [r13+34h], 0
0x18000502e  jnz     loc_180005D63
0x180005034  cmp     dword ptr [r13+68h], 1
0x180005039  jnz     short loc_180005045
0x18000503b  lea     pServerCall, [r13+40h]; lpCriticalSection
0x18000503f  call    cs:__imp_LeaveCriticalSection
0x180005045  mov     eax, 0FFFFFFFFh
0x18000504a  lock xadd [r13+70h], eax
0x180005050  cmp     eax, 1
0x180005053  jz      loc_180005D24
0x180005059  mov     pServerCall, [rbp+230h+var_1D8]
0x18000505d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005064  lock xadd [pServerCall+128h], eax
0x18000506c  cmp     eax, 1
0x18000506f  jnz     short loc_180005081
0x180005071  movzx   eax, byte ptr [pServerCall+0D9h]
0x180005078  nop
0x180005079  test    al, al
0x18000507b  jnz     loc_1800060B4
0x180005081  dec     dword ptr [rdi+30h]
0x180005084  test    r14, r14
0x180005087  jz      short loc_180005098
0x180005089  mov     rax, [r14]
0x18000508c  mov     pServerCall, r14
0x18000508f  mov     rax, [rax+10h]
0x180005093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005098  test    byte ptr [rbx+14h], 24h
0x18000509c  jz      loc_18000602C
0x1800050a2  test    byte ptr [rbx+14h], 20h
0x1800050a6  jz      loc_180005142
0x1800050ac  mov     rsi, [rbx+288h]
0x1800050b3  test    rsi, rsi
0x1800050b6  jnz     loc_180005149
0x1800050bc  xor     eax, eax
0x1800050be  mov     [rbx+288h], rax
0x1800050c5  mov     [rbx+1D8h], rax
0x1800050cc  mov     pServerCall, rbx
0x1800050cf  mov     [rbx+1E0h], eax
0x1800050d5  mov     [rbx+1E8h], rax
0x1800050dc  mov     [rbx+1F0h], eax
0x1800050e2  mov     [rbx+1F8h], rax
0x1800050e9  mov     [rbx+200h], eax
0x1800050ef  mov     [rbx+208h], rax
0x1800050f6  mov     [rbx+210h], eax
0x1800050fc  mov     [rbx+218h], rax
0x180005103  mov     [rbx+220h], rax
0x18000510a  mov     rax, [rbx]
0x18000510d  mov     rax, [rax+8]
0x180005111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005116  mov     eax, r12d
0x180005119  mov     pServerCall, [rbp+230h+var_40]
0x180005120  xor     pServerCall, rbp; StackCookie
0x180005123  call    __security_check_cookie
0x180005128  mov     rbx, [rbp+230h+arg_10]
0x18000512f  lea     rsp, [rbp+200h]
0x180005136  pop     r15
0x180005138  pop     r14
0x18000513a  pop     r13
0x18000513c  pop     r12
0x18000513e  pop     rdi
0x18000513f  pop     rsi
0x180005140  pop     rbp
0x180005141  retn
0x180005142  xor     eax, eax
0x180005144  jmp     loc_1800050C5
0x180005149  call    cs:__imp_GetLastError
0x18000514f  mov     pServerCall, cs:?g_hHeap@@3QEAXEA; hHeap
0x180005156  mov     r8, rsi; lpMem
0x180005159  xor     edx, edx; dwFlags
0x18000515b  mov     edi, eax
0x18000515d  call    cs:__imp_HeapFree
0x180005163  mov     ecx, edi; dwErrCode
0x180005165  call    cs:__imp_SetLastError
0x18000516b  jmp     loc_1800050BC
0x180005170  test    eax, eax
0x180005172  jz      loc_180004FDF
0x180005178  call    ?GetPendingDisconnectType@CStdMarshal@@AEAAKXZ; CStdMarshal::GetPendingDisconnectType(void)
0x18000517d  lea     pServerCall, ?gIPIDLock@@3VCOleStaticMutexSem@@A; this
0x180005184  mov     esi, eax
0x180005186  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18000518b  nop
0x18000518c  jmp     loc_180244F70
0x180005191  mov     rsi, [rsi+30h]
0x180005195  mov     r15, cs:?_palloc@CServerSecurity@@0VCPageAllocator@@A._pgalloc._pLock; CPageAllocator CServerSecurity::_palloc ...
0x18000519c  test    r15, r15
0x18000519f  jz      short loc_1800051B6
0x1800051a1  mov     r8d, 7Ch ; '|'; dwLine
0x1800051a7  lea     pIPIDEntry, aOnecoreComComb_114; "onecore\\com\\combase\\coll\\pgalloc.cx"...
0x1800051ae  mov     pServerCall, r15; this
0x1800051b1  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1800051b6  mov     r14, cs:?_palloc@CServerSecurity@@0VCPageAllocator@@A._pgalloc._ListHead.pNext; CPageAllocator CServerSecurity::_palloc ...
0x1800051bd  mov     [rbp+230h+pPrimaryUnknown.m_ptr], r14
0x1800051c1  test    r14, r14
0x1800051c4  jz      short loc_1800051D0
0x1800051c6  mov     rax, [r14]
0x1800051c9  mov     cs:?_palloc@CServerSecurity@@0VCPageAllocator@@A._pgalloc._ListHead.pNext, rax; CPageAllocator CServerSecurity::_palloc ...
0x1800051d0  test    r15, r15
0x1800051d3  jz      short loc_180005224
0x1800051d5  add     dword ptr [r15+4], 0FFFFFFFFh
0x1800051da  jnz     short loc_18000521A
0x1800051dc  movzx   ecx, byte ptr [r15]
0x1800051e0  cmp     cl, 13h
0x1800051e3  jz      short loc_18000521A
0x1800051e5  mov     rax, gs:30h
0x1800051ee  mov     pIPIDEntry, [rax+1758h]
0x1800051f5  mov     [rbp+230h+var_220.ptr_], pIPIDEntry
0x1800051f9  test    pIPIDEntry, pIPIDEntry
0x1800051fc  jz      short loc_18000521A
0x1800051fe  mov     eax, r12d
0x180005201  shl     eax, cl
0x180005203  mov     dword ptr [rbp+230h+aExtent+4], eax
0x180005206  test    [pIPIDEntry+240h], eax
0x18000520c  jz      loc_180005F53
0x180005212  not     eax
0x180005214  and     [pIPIDEntry+240h], eax
0x18000521a  lea     pServerCall, [r15+20h]; lpCriticalSection
0x18000521e  call    cs:__imp_LeaveCriticalSection
0x180005224  test    r14, r14
0x180005227  jz      loc_180005E42
0x18000522d  lock inc cs:?_palloc@CServerSecurity@@0VCPageAllocator@@A._pgalloc._cEntries; CPageAllocator CServerSecurity::_palloc ...
0x180005234  mov     dword ptr [r14+8], 0A110CCEDh
0x18000523c  xor     r15d, r15d
0x18000523f  cmp     cs:?s_fPgAllocUseSystemHeap@ComVerifierSettings@@0_NA, 0; bool ComVerifierSettings::s_fPgAllocUseSystemHeap
0x180005246  jnz     loc_180244EEB
0x18000524c  test    r14, r14
0x18000524f  jz      loc_180005FEE
0x180005255  mov     pServerCall, [rbx+90h]
0x18000525c  lea     rax, ??_7CServerSecurity@@6BIServerSecurity@@@; const CServerSecurity::`vftable'{for `IServerSecurity'}
0x180005263  mov     [r14], rax
0x180005266  lea     rax, ??_7CServerSecurity@@6BICancelMethodCalls@@@; const CServerSecurity::`vftable'{for `ICancelMethodCalls'}
0x18000526d  mov     [r14+8], rax
0x180005271  lea     rax, ??_7CServerSecurity@@6BIComDispatchInfo@@@; const CServerSecurity::`vftable'{for `IComDispatchInfo'}
0x180005278  mov     [r14+10h], rax
0x18000527c  lea     rax, ??_7CServerSecurity@@6BICallingProcessInfo@@@; const CServerSecurity::`vftable'{for `ICallingProcessInfo'}
  ... truncated ...
```
