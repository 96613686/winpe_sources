# ThreadInvokeWorker(_RPC_MESSAGE *,bool &,CAsyncCall * &,bool &,bool &,tagIPIDEntry * &,ObjectLibrary::ReferencedPtr<ServerCall> &)

- ea: `0x180019690`
- end: `0x18001ae8a`
- name: `?ThreadInvokeWorker@@YAJPEAU_RPC_MESSAGE@@AEA_NAEAPEAVCAsyncCall@@11AEAPEAUtagIPIDEntry@@AEAV?$ReferencedPtr@VServerCall@@@ObjectLibrary@@@Z`
- size: `6138`
- prototype: `HRESULT __fastcall(_RPC_MESSAGE *pMessage, bool *fFakeAsync, CAsyncCall **pCall, bool *serverCancelationNotificationUnsubscribeNeeded, bool *invokeOnThisThread, tagIPIDEntry **pIPIDEntry, ObjectLibrary::ReferencedPtr<ServerCall> *spServerCall)`
- caller_count: `1`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019240`

## callees

- `0x1800034c4`
- `0x180003964`
- `0x180006250`
- `0x180006390`
- `0x180006710`
- `0x18000712c`
- `0x180007200`
- `0x1800074b0`
- `0x1800075c0`
- `0x1800076c0`
- `0x1800157dc`
- `0x1800158a0`
- `0x180015918`
- `0x180019100`
- `0x180019690`
- `0x180039560`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x1800472a0`
- `0x18005a880`
- `0x18005daf0`
- `0x18005df48`
- `0x180063660`
- `0x1800655d8`
- `0x18006ed00`
- `0x18006ef24`
- `0x180082eac`
- `0x180083228`
- `0x1800865f4`
- `0x1800874e0`
- `0x18008db2c`
- `0x18009ad9c`
- `0x18009b790`
- `0x18009b8ac`
- `0x18009b950`
- `0x18009bc84`
- `0x18009c17c`
- `0x1800c0a80`
- `0x1800c1a9c`
- `0x1800c8710`
- `0x1800dd2f0`
- `0x1800ea4fc`
- `0x18012e390`
- `0x180134f60`
- `0x18014ebe8`
- `0x180155ae0`
- `0x18016e704`
- `0x18016ebfc`
- `0x1801894ec`
- `0x1801999b0`

## import_xrefs

- `RPCRT4!RpcBindingInqObject` at `0x180019786`
- `RPCRT4!RpcBindingInqObject` at `0x180019786`
- `RPCRT4!I_RpcAsyncSetHandle` at `0x18001ab37`
- `RPCRT4!I_RpcAsyncSetHandle` at `0x18001ab37`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800197ff`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800197ff`
- `ntdll!EtwEventActivityIdControl` at `0x18001aca6`
- `ntdll!EtwEventActivityIdControl` at `0x18001aca6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ed6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a16f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ed6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a16f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a902`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001a3a3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001a3a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800199f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800199f3`

## string_xrefs

- `0x18001975c`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180019797`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180019810`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180019888`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x1800198db`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18001a956`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18001aa88`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18001ad91`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18001ae11`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180019eae`: `onecore\com\combase\proxy\winrtasyncproxy\winrtasyncproxy.cpp`
- `0x180019f51`: `onecore\com\combase\proxy\winrtasyncproxy\winrtasyncproxy.cpp`
- `0x18001a02e`: `onecore\com\combase\proxy\winrtasyncproxy\winrtasyncproxy.cpp`
- `0x18001ac5b`: `onecore\com\combase\dcomrem\call.cxx`
- `0x18001ad85`: `ThreadInvokeWorker`
- `0x18001adfc`: `ThreadInvokeWorker`
- `0x180019b9a`: `onecore\com\combase\featuredevelopmentproperties\lib\featuredevelopmentproperties.cpp`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __fastcall ThreadInvokeWorker(
        _RPC_MESSAGE *pMessage,
        bool *fFakeAsync,
        ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall> > > > > > **pCall,
        bool *serverCancelationNotificationUnsubscribeNeeded,
        bool *invokeOnThisThread,
        tagIPIDEntry **pIPIDEntry,
        ObjectLibrary::ReferencedPtr<ServerCall> *spServerCall)
{
  volatile bool v7; // di
  HRESULT v10; // eax
  HRESULT v11; // ebx
  void *Handle; // rcx
  RPC_STATUS v14; // eax
  int v15; // esi
  unsigned int flags; // eax
  unsigned int v17; // edx
  bool v18; // r15
  tagCOMVERSION v19; // r14d
  const WireContainerThis *v20; // rcx
  GUID passthroughTraceActivity; // xmm7
  _GUID callId; // xmm6
  char *RpcInterfaceInformation; // rbx
  _DWORD *v24; // rax
  volatile bool cachedValue; // bl
  FeatureDevelopmentProperties::ReadFromRegistryResult v26; // eax
  const FeatureDevelopmentProperties::<unnamed_type_g_boolPropertyDefaultOverrideRecords> *v27; // rdx
  char v28; // dl
  wchar_t *v29; // rax
  wchar_t *v30; // rax
  ArrayOfGuids *ptr; // rdi
  _GUID *guids; // rbx
  ArrayOfGuids *v33; // rsi
  bool enableCallTracing; // bl
  CallIdAndTracingInformation *v35; // rax
  _GUID v36; // xmm0
  ComCallTraceActivity *v37; // rdi
  ComCallTraceActivity *v38; // rax
  unsigned int v39; // edx
  const void *v40; // r8
  unsigned int v41; // r9d
  unsigned int v42; // r10d
  unsigned int v43; // r11d
  __int16 ProcNum; // ax
  __int16 v45; // si
  const _RPC_SERVER_INTERFACE *ServerInterfaceInformation; // rax
  _GUID SyntaxGUID; // xmm0
  ObjectLibrary::ReferencedPtr<WinrtAsyncProxyMethodInfo> *v48; // rcx
  WinrtAsyncProxyMethodInfo *v49; // rbx
  int v50; // esi
  WinrtAsyncProxyCall *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdi
  HRESULT v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rsi
  bool v57; // zf
  ServerCall *v58; // rbx
  ObjectLibrary::ReferencedPtr<ServerCall> *v59; // rsi
  __int64 v60; // rbx
  int v61; // eax
  __int64 v62; // rcx
  int v63; // ebx
  ObjectLibrary::Details::MixinBase<ComCallTraceActivity,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> *v64; // rcx
  unsigned __int16 MajorVersion; // dx
  __int64 v66; // rcx
  CONTAINER_EXTENT_ARRAY *v67; // r15
  ArrayOfGuids *v68; // rsi
  unsigned __int64 v69; // rsi
  char *v70; // rax
  const CMessageCall::ServerSideOfOutofprocCallType *v71; // rdx
  char *v72; // rsi
  _RTL_WORK_ON_BEHALF_TICKET v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  const void *v76; // rdi
  unsigned __int64 v77; // rdi
  char *v78; // rax
  char *v79; // rdi
  int v80; // r9d
  int v81; // r11d
  _GUID v82; // xmm0
  __int64 v83; // rcx
  bool v84; // al
  ComCallTraceActivity *v85; // rax
  unsigned int v86; // eax
  void (__fastcall ***v87)(_QWORD); // r10
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  ObjectLibrary::ReferencedPtr<ServerCall> *v98; // rsi
  ServerCall **v99; // r14
  const char *v100; // r9
  bool v101; // si
  tagIPIDEntry **v102; // r15
  unsigned int v103; // edx
  unsigned __int64 v104; // rax
  tagIPIDEntry *EntryPtr; // rax
  tagIPIDEntry *v106; // rdi
  OXIDEntry *pOXIDEntry; // rsi
  CRIFTable *v108; // rcx
  __int64 v109; // r8
  const char *v110; // r9
  __int64 v111; // rcx
  _DWORD *v112; // r8
  __int64 v113; // rcx
  unsigned int dwFlags; // eax
  ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall> > > > > > *v115; // rdi
  int v116; // r10d
  __int64 v117; // rax
  const WireLocalThis **v118; // [rsp+30h] [rbp-F0h]
  _GUID *v119; // [rsp+38h] [rbp-E8h]
  _GUID *v120; // [rsp+48h] [rbp-D8h]
  const WireThis **v121; // [rsp+50h] [rbp-D0h]
  bool whichProperty; // [rsp+A0h] [rbp-80h] BYREF
  tagCOMVERSION dcomVersion; // [rsp+A8h] [rbp-78h] BYREF
  unsigned __int16 MinorVersion; // [rsp+B0h] [rbp-70h]
  __int64 v125; // [rsp+B8h] [rbp-68h] BYREF
  ObjectLibrary::ReferencedPtr<ArrayOfGuids> result; // [rsp+C0h] [rbp-60h] BYREF
  volatile unsigned __int16 sequenceNumberWhenCached; // [rsp+C8h] [rbp-58h] BYREF
  unsigned int sizeOfStubData; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int sizeOfLocalThis; // [rsp+D8h] [rbp-48h] BYREF
  unsigned int sizeOfOrpcThis; // [rsp+E0h] [rbp-40h] BYREF
  const void *stubData; // [rsp+E8h] [rbp-38h] BYREF
  unsigned int sizeOfContainerThis; // [rsp+F0h] [rbp-30h] BYREF
  unsigned int clientPid; // [rsp+F8h] [rbp-28h] BYREF
  const WireContainerThis *containerThis; // [rsp+100h] [rbp-20h] BYREF
  const WireThis *orpcThis; // [rsp+108h] [rbp-18h] BYREF
  ComCallTraceActivity *marshalContext; // [rsp+110h] [rbp-10h] BYREF
  const WireLocalThis *localThis; // [rsp+118h] [rbp-8h] BYREF
  unsigned int dwClientThread; // [rsp+120h] [rbp+0h]
  _RTL_WORK_ON_BEHALF_TICKET first; // [rsp+128h] [rbp+8h] BYREF
  wil::unique_struct<CONTAINERVERSION,void (__cdecl*)(CONTAINERVERSION *),&ClearContainerVersion,std::nullptr_t,0> containerVersion; // [rsp+130h] [rbp+10h] BYREF
  ObjectLibrary::ReferencedPtr<ServerCall> *v141; // [rsp+148h] [rbp+28h]
  _GUID incomingCallId; // [rsp+150h] [rbp+30h] BYREF
  bool *v143; // [rsp+160h] [rbp+40h]
  tagIPIDEntry **v144; // [rsp+168h] [rbp+48h]
  bool *v145; // [rsp+170h] [rbp+50h]
  bool *v146; // [rsp+178h] [rbp+58h]
  _GUID ipid; // [rsp+180h] [rbp+60h] BYREF
  CallIdAndTracingInformation callIdAndTracingInformation; // [rsp+190h] [rbp+70h] BYREF
  CallIdAndTracingInformation Buf2; // [rsp+1B0h] [rbp+90h] BYREF
  _BYTE destObject[50]; // [rsp+1D0h] [rbp+B0h] OVERLAPPED BYREF
  _BYTE v151[30]; // [rsp+202h] [rbp+E2h] BYREF
  _GUID incomingPassthroughTraceActivity; // [rsp+220h] [rbp+100h] BYREF
  _GUID Buf1; // [rsp+230h] [rbp+110h] BYREF
  CWinrtAsyncServerCallChannel callChannelCallbacks; // [rsp+240h] [rbp+120h] BYREF
  void *retaddr; // [rsp+348h] [rbp+228h]

  v7 = 0;
  v141 = spServerCall;
  v146 = invokeOnThisThread;
  v144 = pIPIDEntry;
  v143 = serverCancelationNotificationUnsubscribeNeeded;
  v145 = fFakeAsync;
  LODWORD(marshalContext) = 0;
  orpcThis = 0;
  sizeOfOrpcThis = 0;
  containerThis = 0;
  sizeOfContainerThis = 0;
  localThis = 0;
  sizeOfLocalThis = 0;
  stubData = 0;
  sizeOfStubData = 0;
  v10 = ProcessIncomingRequestRpcMessage(
          pMessage,
          (unsigned int *)&marshalContext,
          &orpcThis,
          &sizeOfOrpcThis,
          &containerThis,
          &sizeOfContainerThis,
          &localThis,
          &sizeOfLocalThis,
          &stubData,
          &sizeOfStubData);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x19A9u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v10);
    return v11;
  }
  Handle = pMessage->Handle;
  ipid = 0;
  v14 = RpcBindingInqObject(Handle, &ipid);
  if ( v14 )
    return wil::details::in1diag3::Return_Win32(retaddr, 0x19ADu, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v14);
  v15 = (int)marshalContext;
  dcomVersion = (tagCOMVERSION)5;
  MinorVersion = 7;
  clientPid = 0;
  first = 0;
  *(_QWORD *)&containerVersion.version = 3;
  containerVersion.capabilityFlags = 0;
  containerVersion.extensions = 0;
  if ( !(_DWORD)marshalContext )
  {
    if ( I_RpcBindingInqLocalClientPID(0, &clientPid) )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x19B7u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", -2147417856);
      return -2147417856;
    }
    flags = orpcThis->part1.flags;
    v17 = flags >> 6;
    v18 = (flags & 0x20) != 0;
    LOBYTE(v17) = (flags & 0x40) != 0;
    LODWORD(v125) = v17;
    if ( (flags & 4) != 0 )
      v19 = (tagCOMVERSION)2;
    else
      v19 = (tagCOMVERSION)(flags & 2 | 1);
LABEL_21:
    v20 = containerThis;
    goto LABEL_22;
  }
  v18 = 0;
  LOBYTE(v125) = 0;
  if ( (_DWORD)marshalContext != 5 )
  {
    if ( !gEnableNetworkDCOM )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x19C5u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", -2147418111);
      FreeContainerExtentArray(0);
      return -2147418111;
    }
    dcomVersion = orpcThis->part1.version;
    if ( (orpcThis->part1.flags & 4) != 0 )
      v19 = (tagCOMVERSION)2;
    else
      v19 = (tagCOMVERSION)(orpcThis->part1.flags & 2 | 1);
    MinorVersion = dcomVersion.MinorVersion;
    dcomVersion = (tagCOMVERSION)dcomVersion.MajorVersion;
    goto LABEL_21;
  }
  if ( !gEnableContainerDCOM )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x19BEu, "onecore\\com\\combase\\dcomrem\\channelb.cxx", -2147418111);
    ClearContainerVersion(&containerVersion);
    return -2147418111;
  }
  v20 = containerThis;
  v19 = (tagCOMVERSION)1;
  containerVersion.version = containerThis->part1.version;
  containerVersion.capabilityFlags = containerThis->part1.capabilityFlags;
LABEL_22:
  passthroughTraceActivity = GUID_NULL;
  callId = GUID_NULL;
  incomingPassthroughTraceActivity = GUID_NULL;
  incomingCallId = GUID_NULL;
  if ( localThis )
  {
    passthroughTraceActivity = localThis->part1.passthroughTraceActivity;
    dwClientThread = localThis->part1.dwClientThread;
    callId = localThis->part1.callId;
LABEL_26:
    incomingCallId = callId;
    incomingPassthroughTraceActivity = passthroughTraceActivity;
    goto LABEL_27;
  }
  dwClientThread = 0;
  if ( v20 )
  {
    passthroughTraceActivity = v20->part1.passthroughTraceActivity;
    callId = v20->part1.callId;
    goto LABEL_26;
  }
LABEL_27:
  RpcInterfaceInformation = (char *)pMessage->RpcInterfaceInformation;
  if ( RpcInterfaceInformation )
  {
    v24 = (_DWORD *)*((_QWORD *)RpcInterfaceInformation + 6);
    if ( !v24 || *v24 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20);
  }
  Buf1 = *(_GUID *)(RpcInterfaceInformation + 4);
  if ( pMessage->ProcNum == g_testInjectedDelayForIncomingOutofprocCall_procnum
    && !memcmp_0(&Buf1, &g_testInjectedDelayForIncomingOutofprocCall_iid, 0x10u) )
  {
    Sleep(g_testInjectedDelayForIncomingOutofprocCall_delayInMs);
  }
  if ( (Microsoft_Windows_COM_PerfEnableBits[0] & 8) == 0 )
    goto LABEL_65;
  sequenceNumberWhenCached = FeatureDevelopmentProperties::g_aBoolPropertyStates[7].sequenceNumberWhenCached;
  if ( FeatureDevelopmentProperties::g_aBoolPropertyStates[7].sequenceNumberWhenCached )
  {
    cachedValue = FeatureDevelopmentProperties::g_aBoolPropertyStates[7].cachedValue;
    goto LABEL_56;
  }
  *(_QWORD *)&Buf2.callId.Data1 = FeatureDevelopmentProperties::g_aBoolPropertyDescriptors[7].pszPropertyName;
  LODWORD(result.ptr_) = 0;
  *(_QWORD *)Buf2.callId.Data4 = &result;
  whichProperty = 0;
  v26 = FeatureDevelopmentProperties::ForEachPropertyScopeUntilFound__lambda_aaa27e8e7b83daf88975ce93ba96d2b7___(
          PropertyDescriptorFlags_ExcludeUserHive|PropertyDescriptorFlags_AllScopes,
          (unsigned __int16 *)&sequenceNumberWhenCached,
          (FeatureDevelopmentProperties::ReadUInt32FromRegistry::__l2::<lambda_aaa27e8e7b83daf88975ce93ba96d2b7> *)&Buf2);
  if ( v26 )
  {
    if ( v26 == CacheIsCurrent )
    {
      cachedValue = FeatureDevelopmentProperties::g_aBoolPropertyStates[7].cachedValue;
      goto LABEL_56;
    }
    if ( FeatureDevelopmentProperties::GetDefaultOverride<enum FeatureDevelopmentProperties::BoolProperty,FeatureDevelopmentProperties::_unnamed_type_g_boolPropertyDefaultOverrideRecords_,2>(
           EnableCallTracing,
           (const FeatureDevelopmentProperties::<unnamed_type_g_boolPropertyDefaultOverrideRecords> (*)[2])v27,
           &whichProperty) )
    {
      v7 = 1;
      if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
      {
        cachedValue = whichProperty;
        v30 = (wchar_t *)L"true";
        if ( !whichProperty )
          v30 = (wchar_t *)L"false";
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          "onecore\\com\\combase\\featuredevelopmentproperties\\lib\\featuredevelopmentproperties.cpp",
          "FeatureDevelopmentProperties::Query",
          985,
          INFO,
          L"Property %S was set to %S via an override for this process",
          FeatureDevelopmentProperties::g_aBoolPropertyDescriptors[7].pszPropertyName,
          v30);
      }
      else
      {
        cachedValue = whichProperty;
      }
    }
    else
    {
      cachedValue = 1;
      if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          "onecore\\com\\combase\\featuredevelopmentproperties\\lib\\featuredevelopmentproperties.cpp",
          "FeatureDevelopmentProperties::Query",
          993,
          VERBOSE,
          L"Property %S defaulted to %S",
          FeatureDevelopmentProperties::g_aBoolPropertyDescriptors[7].pszPropertyName,
          (wchar_t *)L"true");
    }
  }
  else
  {
    cachedValue = LODWORD(result.ptr_) != 0;
    v7 = 1;
    if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
    {
      v29 = (wchar_t *)L"true";
      if ( !v28 )
        v29 = (wchar_t *)L"false";
      ComTraceMessageT<unsigned short const *,unsigned short *>(
        "onecore\\com\\combase\\featuredevelopmentproperties\\lib\\featuredevelopmentproperties.cpp",
        "FeatureDevelopmentProperties::Query",
        975,
        INFO,
        L"Property %S was explicitly set to %S",
        FeatureDevelopmentProperties::g_aBoolPropertyDescriptors[7].pszPropertyName,
        v29);
    }
  }
  FeatureDevelopmentProperties::g_aBoolPropertyStates[7].cachedValue = cachedValue;
  FeatureDevelopmentProperties::g_aBoolPropertyStates[7].valueWasExplicit = v7;
  FeatureDevelopmentProperties::g_aBoolPropertyStates[7].sequenceNumberWhenCached = sequenceNumberWhenCached;
LABEL_56:
  if ( !cachedValue )
  {
LABEL_65:
    enableCallTracing = 0;
    goto LABEL_66;
  }
  RegistryGuidList::Get(&g_callTracingIidsList, &result);
  ptr = result.ptr_;
  if ( !result.ptr_ )
  {
LABEL_72:
    enableCallTracing = 1;
    goto LABEL_66;
  }
  if ( !result.ptr_->_count )
  {
    ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(result.ptr_);
    goto LABEL_72;
  }
  guids = (_GUID *)result.ptr_->_guids;
  v33 = (ArrayOfGuids *)&result.ptr_->_guids[result.ptr_->_count];
  if ( (ArrayOfGuids *)result.ptr_->_guids == v33 )
  {
LABEL_62:
    if ( ptr )
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(ptr);
    v15 = (int)marshalContext;
    goto LABEL_65;
  }
  while ( 1 )
  {
    Buf2.callId = *guids;
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    if ( ++guids == (_GUID *)v33 )
      goto LABEL_62;
  }
  if ( ptr )
    ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(ptr);
  v15 = (int)marshalContext;
  enableCallTracing = 1;
LABEL_66:
  *(_DWORD *)(&callIdAndTracingInformation.enableCallTracing + 1) = 0;
  *(_WORD *)(&callIdAndTracingInformation.enableCallTracing + 5) = 0;
  *(&callIdAndTracingInformation.enableCallTracing + 7) = 0;
  callIdAndTracingInformation.callId = 0;
  callIdAndTracingInformation.callTraceActivity.ptr_ = 0;
  if ( !memcmp_0(&incomingCallId, &GUID_NULL, 0x10u) )
  {
    v35 = MakeCallIdAndTracingInformation(&Buf2, enableCallTracing);
    v36 = v35->callId;
    callIdAndTracingInformation.enableCallTracing = v35->enableCallTracing;
    callIdAndTracingInformation.callId = v36;
    ObjectLibrary::ReferencedPtr<ComCallTraceActivity>::operator=(
      &callIdAndTracingInformation.callTraceActivity,
      &v35->callTraceActivity);
    ObjectLibrary::ReferencedPtr<ComCallTraceActivity>::InternalRelease(&Buf2.callTraceActivity);
    v37 = callIdAndTracingInformation.callTraceActivity.ptr_;
    enableCallTracing = callIdAndTracingInformation.enableCallTracing;
    callId = callIdAndTracingInformation.callId;
  }
  else
  {
    callIdAndTracingInformation.enableCallTracing = enableCallTracing;
    callIdAndTracingInformation.callId = callId;
    v38 = (ComCallTraceActivity *)HeapAlloc(g_hHeap, 0, 0x18u);
    v37 = v38;
    if ( v38 )
    {
      v38->_cReferences = 1;
      v38->_guidActivity = callId;
      v38->_createdFromExisting = 1;
    }
    else
    {
      v37 = 0;
    }
    callIdAndTracingInformation.callTraceActivity.ptr_ = v37;
  }
  if ( v18 )
  {
    ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IServerCallChannel,>>::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<IServerCallChannel,>>(&callChannelCallbacks);
    ProcNum = pMessage->ProcNum;
    callChannelCallbacks.__vftable = (CWinrtAsyncServerCallChannel_vtbl *)CWinrtAsyncServerCallChannel::`vftable';
    callChannelCallbacks._callIdAndTracingInformation.callId = callId;
    callChannelCallbacks._procNum = ProcNum & 0x7FFF;
    callChannelCallbacks._callIdAndTracingInformation.enableCallTracing = enableCallTracing;
    callChannelCallbacks._callIdAndTracingInformation.callTraceActivity.ptr_ = v37;
    callChannelCallbacks._iid = Buf1;
    callChannelCallbacks._passthroughTraceActivity = passthroughTraceActivity;
    if ( v37 )
      _InterlockedIncrement((volatile signed __int32 *)v37);
    v45 = pMessage->ProcNum & 0x7FFF;
    callChannelCallbacks._orpcThis = orpcThis;
    callChannelCallbacks._localThis = localThis;
    callChannelCallbacks._clientPid = v43;
    callChannelCallbacks._sizeOfOrpcThis = v42;
    callChannelCallbacks._sizeOfLocalThis = v41;
    callChannelCallbacks._requestStubData = v40;
    callChannelCallbacks._sizeOfRequestStubData = v39;
    whichProperty = 0;
    ServerInterfaceInformation = GetServerInterfaceInformation(pMessage);
    *(_WORD *)&Buf2.enableCallTracing = v45;
    LODWORD(result.ptr_) = 0;
    *(_WORD *)&destObject[32] = v45;
    SyntaxGUID = ServerInterfaceInformation->InterfaceId.SyntaxGUID;
    whichProperty = 1;
    *(_QWORD *)destObject = &callChannelCallbacks;
    *(_GUID *)&destObject[16] = SyntaxGUID;
    *(_QWORD *)&destObject[8] = &whichProperty;
    *(_QWORD *)&destObject[40] = &result;
    Buf2.callId = SyntaxGUID;
    ObjectLibrary::Details::ContainerOf_MruCacheImplementationLayer_ObjectLibrary::Details::MruCacheImplementationOptions_WinrtAsyncProxyMethodInfo_10__WinrtAsyncProxyMethodInfoCache_ObjectLibrary::Details::ContainerOf_LockingLayer_WinrtAsyncProxyMethodInfoCache_ObjectLibrary::Details::ContainerOf_ReferencesToElementsLayer_ObjectLibrary::Details::ReferencesToElementsOptions_WinrtAsyncProxyMethodInfo_0__WinrtAsyncProxyMethodInfoCache_ObjectLibrary::Details::MixinBase_WinrtAsyncProxyMethodInfoCache_ObjectLibrary::Details::Mixins_NilBaseForwarderLayer_______::FindOrCreate_std::pair__GUID_unsigned_short___lambda_9da0acafa7ae07318b6774c8ba517608___(
      v48,
      (const std::pair<_GUID,unsigned short> *)&stubData,
      (FindOrCreateMethodInfo::__l2::<lambda_9da0acafa7ae07318b6774c8ba517608> *)&Buf2);
    v49 = (WinrtAsyncProxyMethodInfo *)stubData;
    if ( stubData || (v50 = (int)result.ptr_, v49 = 0, SLODWORD(result.ptr_) >= 0) )
    {
      v51 = (WinrtAsyncProxyCall *)HeapAlloc(g_hHeap, 0, 0xB0u);
      if ( v51 && (WinrtAsyncProxyCall::WinrtAsyncProxyCall(v51, v49, 0), (v53 = v52) != 0) )
      {
        NdrOleIdentifyTransferSyntax(pMessage->TransferSyntax, (WhichTransferSyntax *)(v52 + 100));
        v125 = 0;
        v54 = callChannelCallbacks.CreateWinrtAsyncServerCall(
                &callChannelCallbacks,
                v49,
                pMessage,
                (IWinrtAsyncProxyCall *)(v53 + 48),
                (IStubCall *)(v53 + 64),
                (IWinrtAsyncServerCall **)&v125);
        v50 = v54;
        if ( v54 >= 0 )
        {
          v56 = v125;
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          if ( v49 )
            ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<WinrtAsyncProxyMethodInfoCache,WinrtAsyncProxyMethodInfo,ObjectLibrary::ContainerKind::MruCache<10>,0>,WinrtAsyncProxyMethodInfo,ObjectLibrary::ForwardedBases<WinrtAsyncOperationInfo const,>>>>>::Release(v49);
          v57 = v56 == 0;
          v58 = (ServerCall *)(v56 - 312);
          v59 = v141;
          if ( v57 )
            v58 = 0;
          if ( v141->ptr_ )
            (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v141->ptr_->gap10 + 16LL))(v141->ptr_->gap10);
          v59->ptr_ = v58;
          v60 = (__int64)v58->GetTransportCall(v58);
          v61 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 16LL))(v60, v60);
          v62 = 0;
          if ( !v61 )
            v62 = v60;
          *pCall = (ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall> > > > > > *)v62;
          _InterlockedIncrement((volatile signed __int32 *)(v62 + 664));
          v50 = 0;
          v63 = 0;
          goto LABEL_102;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0xA01u,
          "onecore\\com\\combase\\proxy\\winrtasyncproxy\\winrtasyncproxy.cpp",
          v54);
        v55 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      else
      {
        v50 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x9FBu,
          "onecore\\com\\combase\\proxy\\winrtasyncproxy\\winrtasyncproxy.cpp",
          -2147024882);
      }
      if ( v49 )
        ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<WinrtAsyncProxyMethodInfo,ObjectLibrary::ContainedBy<ObjectLibrary::ContainmentSpecification<WinrtAsyncProxyMethodInfoCache,WinrtAsyncProxyMethodInfo,ObjectLibrary::ContainerKind::MruCache<10>,0>,WinrtAsyncProxyMethodInfo,ObjectLibrary::ForwardedBases<WinrtAsyncOperationInfo const,>>>>>::Release(v49);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x9F4u,
        "onecore\\com\\combase\\proxy\\winrtasyncproxy\\winrtasyncproxy.cpp",
        (HRESULT)result.ptr_);
    }
    v63 = v50;
LABEL_102:
    v64 = callChannelCallbacks._callIdAndTracingInformation.callTraceActivity.ptr_;
    if ( callChannelCallbacks._callIdAndTracingInformation.callTraceActivity.ptr_ )
    {
      callChannelCallbacks._callIdAndTracingInformation.callTraceActivity.ptr_ = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v64, 0xFFFFFFFF) == 1 )
      {
        *(_DWORD *)&v64->ObjectLibrary::Details::Mixins_NilBaseForwarderLayer = -568426787;
        ObjectLibrary::Details::MixinBase<ComCallTraceActivity,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>::CallDeleteThisAsSelf<0>(v64);
      }
    }
    goto LABEL_138;
  }
  MajorVersion = dcomVersion.MajorVersion;
  v66 = MinorVersion;
  v67 = 0;
  *(_QWORD *)destObject = CDestObject::`vftable';
  v63 = 0;
  *(_DWORD *)&destObject[16] = containerVersion.version;
  *(_DWORD *)&destObject[20] = first.ThreadId;
  *(_QWORD *)&destObject[24] = containerVersion.capabilityFlags;
  *(_DWORD *)&destObject[8] = v15;
  *(_WORD *)&destObject[12] = dcomVersion.MajorVersion;
  *(_WORD *)&destObject[14] = MinorVersion;
  *(_QWORD *)&destObject[32] = 0;
  memset(&containerVersion, 0, sizeof(containerVersion));
  if ( dcomVersion.MajorVersion != 5 || !MinorVersion )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(MinorVersion);
    v66 = MinorVersion;
    MajorVersion = dcomVersion.MajorVersion;
  }
  if ( v15 != 2 && (MajorVersion != 5 || (_WORD)v66 != 7) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v66);
  result.ptr_ = (ArrayOfGuids *)ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<CMessageCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue._Storage._Value._value;
  if ( ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<CMessageCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue._Storage._Value._value == -1 )
  {
    first = 0;
    _InterlockedExchange64(
      (volatile __int64 *)&ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<CMessageCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue,
      0);
    v68 = 0;
  }
  else
  {
    v68 = result.ptr_;
  }
  v69 = ((unsigned __int64)&v68->_count + 7) & 0xFFFFFFFFFFFFFFF0uLL;
  if ( v69 < 0xFFFFFFFFFFFFFC70uLL && (v70 = (char *)HeapAlloc(g_hHeap, 0, v69 + 912)) != 0 && (v72 = &v70[v69]) != 0 )
  {
    LODWORD(result.ptr_) = sizeOfStubData;
    marshalContext = v37;
    sizeOfStubData = 4;
    *(_QWORD *)&incomingCallId.Data1 = pMessage;
    v73 = *(_RTL_WORK_ON_BEHALF_TICKET *)NtCurrentTeb()->WorkingOnBehalfTicket;
    *((_QWORD *)v72 + 1) = &CAsyncCall::`vbtable';
    first = v73;
    dcomVersion = v19;
    *((_QWORD *)v72 + 113) = ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<ObjectLibrary::InheritBaseAllocator,0,ObjectLibrary::Details::Nil>,WinRT::Metadata::Marshaling::MetadataUnknown,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<0>,WinRT::Metadata::Marshaling::MetadataUnknown,ObjectLibrary::ForwardedBases<WinRT::Metadata::Marshaling::MetadataType,>>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
    ObjectLibrary::Details::AddGeneralTypeIdentity<CAsyncCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CAsyncCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>,ObjectLibrary::ForwardedBases<CMessageCall,>>::AddTypeIdLayerHelper<ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CAsyncCall,CClientCall>,CMessageCall,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil>>>>>::AddGeneralTypeIdentity<CAsyncCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CAsyncCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>,ObjectLibrary::ForwardedBases<CMessageCall,>>::AddTypeIdLayerHelper<ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CAsyncCall,CClientCall>,CMessageCall,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil>>>>>(
      (ObjectLibrary::Details::AddGeneralTypeIdentity<CAsyncCall,ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CAsyncCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall> >,ObjectLibrary::ForwardedBases<CMessageCall> >::AddTypeIdLayerHelper<ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall> >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CAsyncCall,CClientCall>,CMessageCall,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil> > > > > *)v72,
      v71,
      (tagCALLCATEGORY *)&dcomVersion,
      (const tagRPCOLEMESSAGE **)&incomingCallId,
      &sizeOfStubData,
      &ipid,
      (CDestObject *)destObject,
      &incomingPassthroughTraceActivity,
      &marshalContext,
      &callIdAndTracingInformation.callId,
      &orpcThis,
      &sizeOfOrpcThis,
      &containerThis,
      &sizeOfContainerThis,
      &localThis,
      &sizeOfLocalThis,
      &stubData,
      (unsigned int *)&result,
      &first);
    *(_QWORD *)v72 = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<65>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>::`vftable'{for `ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil>>'};
    *(_QWORD *)&v72[*(int *)(*((_QWORD *)v72 + 1) + 4LL) + 8] = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<65>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,CAsyncCall,ObjectLibrary::ForwardedBases<CMessageCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
    v74 = *(int *)(*((_QWORD *)v72 + 1) + 4LL);
    *(_DWORD *)&v72[v74 + 4] = v74 - 672;
    *(_QWORD *)v72 = CAsyncCall::`vftable'{for `ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil>>'};
    *(_QWORD *)&v72[*(int *)(*((_QWORD *)v72 + 1) + 4LL) + 8] = CAsyncCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
    v75 = *(int *)(*((_QWORD *)v72 + 1) + 4LL);
    *(_DWORD *)&v72[v75 + 4] = v75 - 896;
    *((_QWORD *)v72 + 84) = 0;
    *(_OWORD *)(v72 + 680) = 0;
    *(_OWORD *)(v72 + 696) = 0;
    *(_OWORD *)(v72 + 712) = 0;
    *(_OWORD *)(v72 + 728) = 0;
    *(_OWORD *)(v72 + 744) = 0;
    *(_OWORD *)(v72 + 760) = 0;
    *(_OWORD *)(v72 + 776) = 0;
    *((_QWORD *)v72 + 99) = 0;
    *((_DWORD *)v72 + 200) = -2147417835;
    v72[804] = 0;
    *((_DWORD *)v72 + 202) = 0;
    *((_QWORD *)v72 + 102) = 0;
    *((_QWORD *)v72 + 103) = 0;
    *((_QWORD *)v72 + 104) = 0;
    *((_QWORD *)v72 + 105) = 0;
    *((_QWORD *)v72 + 107) = 0;
    *((_QWORD *)v72 + 106) = CachedCallEvent::`vftable';
    *((_DWORD *)v72 + 216) = 1;
    InitializeSRWLock((PSRWLOCK)v72 + 109);
    *((_DWORD *)v72 + 54) |= 0x8000u;
    *((_DWORD *)v72 + 220) = 0;
    *((_QWORD *)v72 + 111) = 0;
    CAsyncCall::InitializeRpcAsyncState((CAsyncCall *)v72);
    *pCall = (ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall> > > > > > *)v72;
    stubData = (const void *)ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<ServerCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue._Storage._Value._value;
    if ( ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<ServerCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue._Storage._Value._value == -1 )
    {
      *(_QWORD *)&incomingCallId.Data1 = 0;
      _InterlockedExchange64(
        (volatile __int64 *)&ObjectLibrary::AlmostStaticConstantValue<unsigned __int64,&protected: static unsigned __int64 ObjectLibrary::Details::MixinBase<ServerCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::CallGetAllocationHeaderSizeIfExists<0>(void),ObjectLibrary::SentinelValue<unsigned __int64,-1>>::s_cachedValue,
        0);
      v76 = 0;
    }
    else
    {
      v76 = stubData;
    }
    v77 = ((unsigned __int64)v76 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v77 < 0xFFFFFFFFFFFFFE88uLL && (v78 = (char *)HeapAlloc(g_hHeap, 0, v77 + 376)) != 0 && (v79 = &v78[v77]) != 0 )
    {
      *((_QWORD *)v79 + 1) = &SyncServerCall::`vbtable'{for `CBaseCall'};
      *((_QWORD *)v79 + 3) = CCtxCall::`vbtable';
      *((_QWORD *)v79 + 46) = ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<ObjectLibrary::InheritBaseAllocator,0,ObjectLibrary::Details::Nil>,WinRT::Metadata::Marshaling::MetadataUnknown,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<0>,WinRT::Metadata::Marshaling::MetadataUnknown,ObjectLibrary::ForwardedBases<WinRT::Metadata::Marshaling::MetadataType,>>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      _InterlockedExchangeAdd((volatile signed __int32 *)&CBaseCall::s_uCurrentCallTraceId, 1u);
      ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::DebuggingOptions<0>,ObjectLibrary::ObjectNoAssociations>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::DebuggingOptions<0>,ObjectLibrary::ObjectNoAssociations>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>((ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::DebuggingOptions<0>,ObjectLibrary::ObjectNoAssociations>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall> > *)v79);
      v82 = incomingPassthroughTraceActivity;
      *(_QWORD *)v79 = ServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ServerCall'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = ServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v83 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      v84 = callIdAndTracingInformation.enableCallTracing;
      *(_DWORD *)&v79[v83 + 4] = v83 - 312;
      *((_QWORD *)v79 + 6) = 0;
      *(_GUID *)(v79 + 56) = v82;
      v79[88] = v84;
      v85 = callIdAndTracingInformation.callTraceActivity.ptr_;
      *(_GUID *)(v79 + 72) = callIdAndTracingInformation.callId;
      *((_QWORD *)v79 + 12) = v85;
      if ( v85 )
        _InterlockedIncrement((volatile signed __int32 *)v85);
      v86 = dwClientThread;
      *((_QWORD *)v79 + 13) = 0;
      *((_OWORD *)v79 + 7) = 0;
      *((_QWORD *)v79 + 16) = 0;
      *((_QWORD *)v79 + 17) = 0;
      *((_DWORD *)v79 + 38) = v86;
      *((_DWORD *)v79 + 36) = v80;
      *((_DWORD *)v79 + 37) = v81;
      *((_QWORD *)v79 + 20) = 0;
      *((_QWORD *)v79 + 21) = 0;
      *((_QWORD *)v79 + 22) = CRpcCall::`vftable'{for `ICall'};
      *((_QWORD *)v79 + 23) = CRpcCall::`vftable'{for `IRpcCall'};
      *((_QWORD *)v79 + 24) = CRpcCall::`vftable'{for `ICallInfo'};
      *((_DWORD *)v79 + 50) = 1;
      *((_QWORD *)v79 + 26) = 0;
      *((_QWORD *)v79 + 27) = 0;
      *((_QWORD *)v79 + 30) = v79 + 256;
      *((_QWORD *)v79 + 31) = 0;
      *((GUID *)v79 + 14) = GUID_NULL;
      *((_DWORD *)v79 + 64) = 0;
      v79[264] &= 0xF8u;
      MarshalByValueSerializationData::MarshalByValueSerializationData((MarshalByValueSerializationData *)(v79 + 272));
      v79[304] = 0;
      *(_QWORD *)v79 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ServerCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v88 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v88 + 4] = v88 - 320;
      *(_QWORD *)v79 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ServerCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v89 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v89 + 4] = v89 - 320;
      *(_QWORD *)v79 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,ServerCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,ServerCall,ObjectLibrary::ForwardedBases<CBaseCall,IMessageParam,IServerCall>>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v90 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v90 + 4] = v90 - 320;
      *(_QWORD *)v79 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = StandardComServerCall::`vftable'{for `IServerTransportCallEvents'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = StandardComServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v91 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v91 + 4] = v91 - 336;
      *((_QWORD *)v79 + 40) = v87;
      if ( v87 )
        (**v87)(v87);
      v79[332] &= 0xFCu;
      *(_QWORD *)v79 = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<4>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,StandardComServerCall,ObjectLibrary::ForwardedBases<ServerCall,IServerTransportCallEvents>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = StandardComServerCall::`vftable'{for `IServerTransportCallEvents'};
      v92 = *((_QWORD *)v79 + 1);
      *((_DWORD *)v79 + 82) = 0;
      *(_QWORD *)&v79[*(int *)(v92 + 4) + 8] = StandardComServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v93 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v93 + 4] = v93 - 336;
      *(_QWORD *)v79 = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<1>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<1>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `IServerTransportCallEvents'};
      v94 = *((_QWORD *)v79 + 1);
      *((_DWORD *)v79 + 84) = 1;
      *(_QWORD *)&v79[*(int *)(v94 + 4) + 8] = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<1>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v95 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v95 + 4] = v95 - 344;
      *(_QWORD *)v79 = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<1>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `IServerTransportCallEvents'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v96 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v96 + 4] = v96 - 344;
      *(_QWORD *)v79 = SyncServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeIdHelper<ObjectLibrary::OneOf<CCtxCall,CSyncClientCall,AsyncComClientCall,WinrtAsyncClientCall,SyncServerCall,AsyncComServerCall,WinrtAsyncServerCall>,CBaseCall,ObjectLibrary::Details::MixinBase<CBaseCall,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>'};
      *((_QWORD *)v79 + 2) = ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<1>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `ObjectLibrary::Details::MixinBase<IMessageParam,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<ObjectLibrary::IComReferenceCounting,>>>'};
      *((_QWORD *)v79 + 5) = SyncServerCall::`vftable'{for `ServerCall'};
      *((_QWORD *)v79 + 39) = ObjectLibrary::Object<ObjectLibrary::ObjectOptions<ObjectLibrary::ComReferenceCountingOptions<1>,ObjectLibrary::ObjectNoAllocation,ObjectLibrary::ObjectNoPolymorphism,ObjectLibrary::ObjectNoDebugging,ObjectLibrary::ObjectNoAssociations>,SyncServerCall,ObjectLibrary::ForwardedBases<StandardComServerCall,>>::`vftable'{for `IServerTransportCallEvents'};
      *(_QWORD *)&v79[*(int *)(*((_QWORD *)v79 + 1) + 4LL) + 8] = SyncServerCall::`vftable'{for `ObjectLibrary::Details::PolymorphicTypeBase'};
      v97 = *(int *)(*((_QWORD *)v79 + 1) + 4LL);
      *(_DWORD *)&v79[v97 + 4] = v97 - 360;
      v79[344] = v125 & 0xFD | v79[344] & 0xFC;
      *((_QWORD *)v79 + 44) = SyncStubCall::`vftable';
    }
    else
    {
      v79 = 0;
    }
    v98 = v141;
    if ( v141->ptr_ )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v141->ptr_->gap10 + 16LL))(v141->ptr_->gap10);
    v67 = *(CONTAINER_EXTENT_ARRAY **)&destObject[32];
    v98->ptr_ = (ServerCall *)v79;
    v50 = -2147024882;
    if ( v79 )
      v50 = 0;
  }
  else
  {
    *pCall = 0;
    v50 = -2147024882;
  }
  if ( v67 )
  {
    ClearContainerExtentArray(v67);
    HeapFree(g_hHeap, 0, v67);
  }
LABEL_138:
  if ( v50 >= 0 )
  {
    v99 = (ServerCall **)v141;
    (*pCall)->_hRpc = pMessage->Handle;
    if ( !(*v99)->ServerShouldUseCancelationNotification(*v99) )
    {
LABEL_142:
      COleStaticMutexSem::Request(&gIPIDLock, "onecore\\com\\combase\\dcomrem\\channelb.cxx", 0x1A46u, v100);
      v101 = 0;
      v102 = v144;
      v103 = ipid.Data1 & 0xFFFF03FF;
      v104 = (unsigned __int64)(ipid.Data1 & 0xFFFF03FF) >> 16;
      *v144 = 0;
      if ( v104 < CIPIDTable::_palloc._pgalloc._cPages
        && (unsigned __int16)v103 < CIPIDTable::_palloc._pgalloc._cEntriesPerPage )
      {
        EntryPtr = (tagIPIDEntry *)CPageAllocator::GetEntryPtr(&CIPIDTable::_palloc, v103);
        v106 = EntryPtr;
        if ( EntryPtr )
        {
          if ( (tagIPIDEntry::GetFlags(EntryPtr) & 0x80u) == 0 )
          {
            if ( tagIPIDEntry::IsConnected(v106) )
            {
              if ( v106->ipid.Data1 == ipid.Data1
                && *(_DWORD *)&v106->ipid.Data2 == *(_DWORD *)&ipid.Data2
                && *(_DWORD *)v106->ipid.Data4 == *(_DWORD *)ipid.Data4
                && *(_DWORD *)&v106->ipid.Data4[4] == *(_DWORD *)&ipid.Data4[4] )
              {
                if ( !v106->pChnl || v106->pOXIDEntry->_stopped._Storage._Value )
                {
                  v63 = -2147417848;
                  if ( !v106->pStub )
                    v63 = -2147467262;
                }
                else
                {
                  *v102 = v106;
                  pOXIDEntry = v106->pOXIDEntry;
                  OXIDEntry::IncRefCnt(pOXIDEntry);
                  v63 = CRIFTable::TryAddRefServerInterface(v108, &Buf1, v109, v110);
                  if ( v63 >= 0 )
                  {
                    v112 = &(*pCall)->gap8[12];
                    LODWORD(v125) = *v112;
                    *v112 = v125 | 1;
                    CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)((char *)v112 + **(int **)(v112 - 3) - 12));
                    goto LABEL_159;
                  }
                  if ( v63 == -2147467231 )
                  {
                    if ( (*v99)->IsWinrtAsyncCall(*v99) )
                      MicrosoftTelemetryAssertTriggeredNoArgs(v113);
LABEL_159:
                    dwFlags = pOXIDEntry->_info.dwFlags;
                    if ( (dwFlags & 0x1000000) != 0 || (dwFlags & 0x2000000) != 0 )
                    {
                      *v146 = 1;
                      CallIdAndTracingInformation::~CallIdAndTracingInformation(&callIdAndTracingInformation);
                      ClearContainerVersion(&containerVersion);
                      return 0;
                    }
                    COleStaticMutexSem::Release(&gIPIDLock);
                    v115 = *pCall;
                    if ( ((*pCall)->gap8[12] & 4) != 0 )
                    {
                      LODWORD(v125) = v115[1].message.dataRepresentation;
                      v115[1].message.dataRepresentation = v125 | 0x20000000;
                      CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)((char *)&v115[1].message.dataRepresentation + **(int **)v115->gap8 - 824));
                    }
                    PushTraceActivity::PushTraceActivity((PushTraceActivity *)&Buf2, &v115->_callId);
                    v63 = I_RpcAsyncSetHandle(pMessage, (PRPC_ASYNC_STATE)&v115[1]);
                    if ( v63 )
                    {
                      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                        && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
                      {
                        goto LABEL_171;
                      }
                    }
                    else if ( !gfEnableTracing || (WPP_GLOBAL_Control->ReserveSpace[28] & 8) == 0 )
                    {
LABEL_171:
                      if ( Buf2.enableCallTracing )
                        EtwEventActivityIdControl(2, &Buf2);
                      if ( v63 )
                      {
                        if ( v63 > 0 )
                          v63 = (unsigned __int16)v63 | 0x80070000;
                      }
                      else
                      {
                        *v145 = 1;
                        *v143 = 0;
                        v63 = OXIDEntry::PostCall(pOXIDEntry, *v99, 0);
                        if ( !v63 )
                        {
                          ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CAsyncCall,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CAsyncCall,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CAsyncCall,ObjectLibrary::Details::MixinBase<CAsyncCall,ObjectLibrary::Details::Mixins_BaseForwarderLayer<ObjectLibrary::ForwardedBases<CMessageCall,>>>>>>::Release(*pCall);
                          *pCall = 0;
                          OXIDEntry::DecRefCnt(pOXIDEntry);
                          goto LABEL_197;
                        }
                      }
                      OXIDEntry::DecRefCnt(pOXIDEntry);
                      goto LABEL_197;
                    }
                    *(_OWORD *)destObject = *(_OWORD *)L"Guid unavailable";
                    *(_OWORD *)&destObject[16] = *(_OWORD *)L"vailable";
                    memset(v151, 0, sizeof(v151));
                    memset(&destObject[32], 0, 18);
                    wStringFromGUID2(&v115->_ipid, (wchar_t *)destObject, 40);
                    *(_OWORD *)&callChannelCallbacks.__vftable = *(_OWORD *)L"Guid unavailable";
                    memset(&callChannelCallbacks._passthroughTraceActivity.Data2, 0, 48);
                    *(_OWORD *)&callChannelCallbacks._iid.Data2 = *(_OWORD *)L"vailable";
                    wStringFromGUID2(&v115->_iidWire, (wchar_t *)&callChannelCallbacks, 40);
                    LODWORD(v121) = v63;
                    LODWORD(v120) = v116;
                    ComTraceWinError(
                      v63,
                      "onecore\\com\\combase\\dcomrem\\call.cxx",
                      "CAsyncCall::CallI_RpcAsyncSetHandle",
                      4309,
                      L"I_RpcAsyncSetHandle for call object %p with explicit pRpcMessage %p (iid:%ws ipid:%ws method:%d): %!WINERROR!",
                      v115,
                      pMessage,
                      &callChannelCallbacks,
                      destObject,
                      v120,
                      v121);
                    goto LABEL_171;
                  }
                  MicrosoftTelemetryAssertTriggeredNoArgs(v111);
                  wil::details::in1diag3::Log_Hr(retaddr, 0x1A93u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v63);
                }
LABEL_186:
                if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
                {
                  GuidString::GuidString((GuidString *)destObject, &ipid);
                  LODWORD(v119) = v63;
                  ComTraceMessage(
                    v63,
                    "onecore\\com\\combase\\dcomrem\\channelb.cxx",
                    "ThreadInvokeWorker",
                    6813,
                    ERRORS,
                    L"LookupFromIPIDTables failed: IPID:%ws %!HRESULT!",
                    v117,
                    v119);
                }
                if ( CMessageCall::IsMachineLocal(*pCall) && CIPIDTable::IsIPIDRunDown(&ipid, *v102) )
                {
                  if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
                  {
                    LODWORD(v118) = v63;
                    ComTraceMessage(
                      v63,
                      "onecore\\com\\combase\\dcomrem\\channelb.cxx",
                      "ThreadInvokeWorker",
                      6819,
                      VERBOSE,
                      L"Transforming result from %!HRESULT! to CO_E_PREMATURE_STUB_RUNDOWN",
                      v118);
                  }
                  v63 = -2147467211;
                }
                COleStaticMutexSem::Release(&gIPIDLock);
                goto LABEL_197;
              }
            }
            else
            {
              v101 = v106->pStub == 0;
            }
          }
        }
      }
      v63 = -2147417848;
      if ( v101 )
        v63 = -2147467262;
      goto LABEL_186;
    }
    v63 = CAsyncCall::ServerSubscribeForCancelationNotification((CAsyncCall *)*pCall);
    if ( v63 >= 0 )
    {
      *v143 = 1;
      goto LABEL_142;
    }
  }
LABEL_197:
  CallIdAndTracingInformation::~CallIdAndTracingInformation(&callIdAndTracingInformation);
  ClearContainerVersion(&containerVersion);
  return v63;
}

```

## disassembly

```asm
0x180019690  push    rbp
0x180019692  push    rbx
0x180019693  push    rdi
0x180019694  push    r12
0x180019696  push    r13
0x180019698  lea     rbp, [rsp-200h]
0x1800196a0  sub     rsp, 320h
0x1800196a7  mov     rax, cs:__security_cookie
0x1800196ae  xor     rax, rsp
0x1800196b1  mov     [rbp+220h+var_70], rax
0x1800196b8  mov     rax, [rbp+220h+arg_30]
0x1800196bf  xor     edi, edi
0x1800196c1  mov     [rbp+220h+var_1F8], rax
0x1800196c5  mov     r13, pCall
0x1800196c8  mov     rax, [rbp+220h+arg_20]
0x1800196cf  lea     pCall, [rbp+220h+orpcThis]; orpcThis
0x1800196d3  mov     [rbp+220h+var_1C8], rax
0x1800196d7  mov     r12, pMessage
0x1800196da  mov     rax, [rbp+220h+arg_28]
0x1800196e1  mov     [rbp+220h+var_1D8], rax
0x1800196e5  lea     rax, [rbp+220h+sizeOfStubData]
0x1800196e9  mov     [rsp+340h+var_2F8], rax; sizeOfStubData
0x1800196ee  lea     rax, [rbp+220h+stubData]
0x1800196f2  mov     [rsp+340h+var_300], rax; stubData
0x1800196f7  lea     rax, [rbp+220h+sizeOfLocalThis]
0x1800196fb  mov     [rsp+340h+var_308], rax; sizeOfLocalThis
0x180019700  lea     rax, [rbp+220h+localThis]
0x180019704  mov     [rsp+340h+var_310], rax; localThis
0x180019709  lea     rax, [rbp+220h+sizeOfContainerThis]
0x18001970d  mov     [rsp+340h+var_318], rax; sizeOfContainerThis
0x180019712  lea     rax, [rbp+220h+containerThis]
0x180019716  mov     [rbp+220h+var_1E0], serverCancelationNotificationUnsubscribeNeeded
0x18001971a  lea     serverCancelationNotificationUnsubscribeNeeded, [rbp+220h+sizeOfOrpcThis]; sizeOfOrpcThis
0x18001971e  mov     [rbp+220h+var_1D0], fFakeAsync
0x180019722  lea     fFakeAsync, [rbp+220h+marshalContext]; marshalContext
0x180019726  mov     qword ptr [rsp+340h+level], rax; containerThis
0x18001972b  mov     dword ptr [rbp+220h+marshalContext], edi
0x18001972e  mov     [rbp+220h+orpcThis], rdi
0x180019732  mov     [rbp+220h+sizeOfOrpcThis], edi
0x180019735  mov     [rbp+220h+containerThis], rdi
0x180019739  mov     [rbp+220h+sizeOfContainerThis], edi
0x18001973c  mov     [rbp+220h+localThis], rdi
0x180019740  mov     [rbp+220h+sizeOfLocalThis], edi
0x180019743  mov     [rbp+220h+stubData], rdi
0x180019747  mov     [rbp+220h+sizeOfStubData], edi
0x18001974a  call    ?ProcessIncomingRequestRpcMessage@@YAJPEBU_RPC_MESSAGE@@PEAKPEAPEBUWireThis@@1PEAPEBUWireContainerThis@@1PEAPEBUWireLocalThis@@1PEAPEBX1@Z; ProcessIncomingRequestRpcMessage(_RPC_MESSAGE const *,ulong *,WireThis const * *,ulong *,WireContainerThis const * *,ulong *,WireLocalThis const * *,ulong *,void const * *,ulong *)
0x18001974f  mov     ebx, eax
0x180019751  test    eax, eax
0x180019753  jns     short loc_180019777
0x180019755  mov     pMessage, [rbp+228h]; callerReturnAddress
0x18001975c  lea     pCall, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180019763  mov     r9d, eax; hr
0x180019766  mov     edx, 19A9h; lineNumber
0x18001976b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019770  mov     eax, ebx
0x180019772  jmp     loc_18001AE6C
0x180019777  mov     pMessage, [r12]; Binding
0x18001977b  lea     fFakeAsync, [rbp+220h+ipid]; ObjectUuid
0x18001977f  xorps   xmm0, xmm0
0x180019782  movups  xmmword ptr [rbp+220h+ipid.Data1], xmm0
0x180019786  call    cs:__imp_RpcBindingInqObject
0x18001978c  test    eax, eax
0x18001978e  jz      short loc_1800197B0
0x180019790  mov     pMessage, [rbp+228h]; callerReturnAddress
0x180019797  lea     pCall, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x18001979e  mov     r9d, eax; err
0x1800197a1  mov     edx, 19ADh; lineNumber
0x1800197a6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800197ab  jmp     loc_18001AE6C
0x1800197b0  mov     eax, 5
0x1800197b5  mov     [rsp+340h+var_28], rsi
0x1800197bd  mov     esi, dword ptr [rbp+220h+marshalContext]
0x1800197c0  mov     dword ptr [rbp+220h+dcomVersion.MajorVersion], eax
0x1800197c3  mov     eax, 7
0x1800197c8  mov     [rbp+220h+var_290], ax
0x1800197cc  xor     eax, eax
0x1800197ce  mov     [rsp+340h+var_30], r14
0x1800197d6  mov     [rsp+340h+var_38], r15
0x1800197de  mov     [rbp+220h+clientPid], edi
0x1800197e1  mov     qword ptr [rbp+220h+var_218.ThreadId], rax
0x1800197e5  mov     qword ptr [rbp+220h+containerVersion.version], 3
0x1800197ed  mov     [rbp+220h+containerVersion.capabilityFlags], rdi
0x1800197f1  mov     [rbp+220h+containerVersion.extensions], rdi
0x1800197f5  test    esi, esi
0x1800197f7  jnz     short loc_18001986E
0x1800197f9  lea     fFakeAsync, [rbp+220h+clientPid]; Pid
0x1800197fd  xor     ecx, ecx; Binding
0x1800197ff  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180019805  test    eax, eax
0x180019807  jz      short loc_180019831
0x180019809  mov     pMessage, [rbp+228h]; callerReturnAddress
0x180019810  lea     pCall, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180019817  mov     r9d, 80010100h; hr
0x18001981d  mov     edx, 19B7h; lineNumber
0x180019822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019827  mov     eax, 80010100h
0x18001982c  jmp     loc_18001AE54
0x180019831  mov     rax, [rbp+220h+orpcThis]
0x180019835  mov     eax, [rax+4]
0x180019838  mov     r15d, eax
0x18001983b  shr     r15d, 5
0x18001983f  mov     edx, eax
0x180019841  shr     edx, 6
0x180019844  and     r15b, 1
0x180019848  and     dl, 1
0x18001984b  mov     dword ptr [rbp+220h+var_288], edx
0x18001984e  test    al, 4
0x180019850  jz      short loc_18001985D
0x180019852  mov     r14d, 2
0x180019858  jmp     loc_180019936
0x18001985d  movzx   r14d, al
0x180019861  and     r14d, 2
0x180019865  or      r14d, 1
0x180019869  jmp     loc_180019936
0x18001986e  xor     r15b, r15b
0x180019871  mov     byte ptr [rbp+220h+var_288], al
0x180019874  cmp     esi, 5
0x180019877  jnz     short loc_1800198CC
0x180019879  cmp     cs:?gEnableContainerDCOM@@3HA, eax; int gEnableContainerDCOM
0x18001987f  jnz     short loc_1800198B2
0x180019881  mov     pMessage, [rbp+228h]; callerReturnAddress
0x180019888  lea     pCall, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x18001988f  mov     r9d, 80010001h; hr
0x180019895  mov     edx, 19BEh; lineNumber
0x18001989a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001989f  lea     pMessage, [rbp+220h+containerVersion]; containerVersion
0x1800198a3  call    ?ClearContainerVersion@@YAXPEAUCONTAINERVERSION@@@Z; ClearContainerVersion(CONTAINERVERSION *)
0x1800198a8  mov     eax, 80010001h
0x1800198ad  jmp     loc_18001AE54
0x1800198b2  mov     pMessage, [rbp+220h+containerThis]
0x1800198b6  mov     r14d, 1
0x1800198bc  mov     eax, [pMessage+4]
0x1800198bf  mov     [rbp+220h+containerVersion.version], eax
0x1800198c2  mov     rax, [pMessage+8]
0x1800198c6  mov     [rbp+220h+containerVersion.capabilityFlags], rax
0x1800198ca  jmp     short loc_18001993A
0x1800198cc  cmp     cs:?gEnableNetworkDCOM@@3HA, eax; int gEnableNetworkDCOM
0x1800198d2  jnz     short loc_180019903
0x1800198d4  mov     pMessage, [rbp+228h]; callerReturnAddress
0x1800198db  lea     pCall, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x1800198e2  mov     r9d, 80010001h; hr
0x1800198e8  mov     edx, 19C5h; lineNumber
0x1800198ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198f2  xor     ecx, ecx; array
0x1800198f4  call    ?FreeContainerExtentArray@@YAXPEAUCONTAINER_EXTENT_ARRAY@@@Z; FreeContainerExtentArray(CONTAINER_EXTENT_ARRAY *)
0x1800198f9  mov     eax, 80010001h
0x1800198fe  jmp     loc_18001AE54
0x180019903  mov     pMessage, [rbp+220h+orpcThis]
0x180019907  mov     eax, [pMessage]
0x180019909  mov     dword ptr [rbp+220h+dcomVersion.MajorVersion], eax
0x18001990c  mov     eax, [pMessage+4]
0x18001990f  test    al, 4
0x180019911  jz      short loc_18001991B
0x180019913  mov     r14d, 2
0x180019919  jmp     short loc_180019927
0x18001991b  movzx   r14d, al
0x18001991f  and     r14d, 2
0x180019923  or      r14d, 1
0x180019927  movzx   eax, [rbp+220h+dcomVersion.MinorVersion]
0x18001992b  mov     [rbp+220h+var_290], ax
0x18001992f  movzx   eax, [rbp+220h+dcomVersion.MajorVersion]
0x180019933  mov     dword ptr [rbp+220h+dcomVersion.MajorVersion], eax
0x180019936  mov     pMessage, [rbp+220h+containerThis]
0x18001993a  mov     rax, [rbp+220h+localThis]
0x18001993e  movaps  [rsp+340h+var_50], xmm6
0x180019946  movaps  [rsp+340h+var_60], xmm7
0x18001994e  movups  xmm7, xmmword ptr cs:GUID_NULL.Data1
0x180019955  movups  xmm6, xmm7
0x180019958  movups  xmmword ptr [rbp+220h+incomingPassthroughTraceActivity.Data1], xmm7
0x18001995f  movups  xmmword ptr [rbp+220h+incomingCallId.Data1], xmm7
0x180019963  test    rax, rax
0x180019966  jz      short loc_180019978
0x180019968  mov     edx, [rax+4]
0x18001996b  movups  xmm7, xmmword ptr [rax+8]
0x18001996f  mov     [rbp+220h+var_220], edx
0x180019972  movups  xmm6, xmmword ptr [rax+18h]
0x180019976  jmp     short loc_180019988
0x180019978  mov     [rbp+220h+var_220], edi
0x18001997b  test    pMessage, pMessage
0x18001997e  jz      short loc_180019993
0x180019980  movups  xmm7, xmmword ptr [pMessage+38h]
0x180019984  movups  xmm6, xmmword ptr [pMessage+58h]
0x180019988  movups  xmmword ptr [rbp+220h+incomingCallId.Data1], xmm6
0x18001998c  movups  xmmword ptr [rbp+220h+incomingPassthroughTraceActivity.Data1], xmm7
0x180019993  mov     rbx, [r12+28h]
0x180019998  test    rbx, rbx
0x18001999b  jz      short loc_1800199B7
0x18001999d  mov     rax, [rbx+30h]
0x1800199a1  test    rax, rax
0x1800199a4  jnz     short loc_1800199AD
0x1800199a6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "interfaceInformation->DispatchTable")
0x1800199ab  jmp     short loc_1800199B7
0x1800199ad  cmp     dword ptr [rax], 1
0x1800199b0  jz      short loc_1800199B7
0x1800199b2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "interfaceInformation->DispatchTable->DispatchTableCount == 1")
0x1800199b7  movups  xmm0, xmmword ptr [rbx+4]
0x1800199bb  movzx   eax, cs:g_testInjectedDelayForIncomingOutofprocCall_procnum
0x1800199c2  movups  [rbp+220h+Buf1], xmm0
0x1800199c9  cmp     [r12+1Ch], eax
0x1800199ce  jnz     short loc_1800199F9
0x1800199d0  mov     r8d, 10h; Size
0x1800199d6  lea     fFakeAsync, g_testInjectedDelayForIncomingOutofprocCall_iid; Buf2
0x1800199dd  lea     pMessage, [rbp+220h+Buf1]; Buf1
0x1800199e4  call    memcmp_0
0x1800199e9  test    eax, eax
0x1800199eb  jnz     short loc_1800199F9
0x1800199ed  mov     ecx, cs:g_testInjectedDelayForIncomingOutofprocCall_delayInMs; dwMilliseconds
0x1800199f3  call    cs:__imp_Sleep
0x1800199f9  test    byte ptr cs:Microsoft_Windows_COM_PerfEnableBits, 8
0x180019a00  jz      loc_180019C54
0x180019a06  movzx   eax, cs:FeatureDevelopmentProperties__g_aBoolPropertyStates.sequenceNumberWhenCached+1Ch
0x180019a0d  mov     [rbp+220h+var_278], ax
0x180019a11  test    ax, ax
0x180019a14  jz      short loc_180019A22
0x180019a16  movzx   ebx, cs:FeatureDevelopmentProperties__g_aBoolPropertyStates.cachedValue+1Ch
0x180019a1d  jmp     loc_180019BC1
0x180019a22  mov     rax, cs:?g_aBoolPropertyDescriptors@FeatureDevelopmentProperties@@3QBUBoolPropertyDescriptor@1@B.pszPropertyName+70h; FeatureDevelopmentProperties::BoolPropertyDescriptor const near * const FeatureDevelopmentProperties::g_aBoolPropertyDescriptors ...
0x180019a29  lea     pCall, [rbp+220h+Buf2]
0x180019a30  mov     qword ptr [rbp+220h+Buf2], rax
0x180019a37  lea     fFakeAsync, [rbp+220h+var_278]
0x180019a3b  lea     rax, [rbp+220h+result]
0x180019a3f  mov     dword ptr [rbp+220h+result.ptr_], edi
0x180019a42  xor     bl, bl
0x180019a44  mov     qword ptr [rbp+220h+Buf2+8], rax
0x180019a4b  mov     ecx, 100Fh
0x180019a50  mov     [rbp+220h+whichProperty], bl
0x180019a53  call    FeatureDevelopmentProperties__ForEachPropertyScopeUntilFound__lambda_aaa27e8e7b83daf88975ce93ba96d2b7___
0x180019a58  test    eax, eax
0x180019a5a  jnz     short loc_180019AC9
0x180019a5c  cmp     dword ptr [rbp+220h+result.ptr_], edi
0x180019a5f  jz      short loc_180019A68
0x180019a61  mov     bl, 1
0x180019a63  movzx   edx, bl
0x180019a66  jmp     short loc_180019A6A
0x180019a68  xor     dl, dl
0x180019a6a  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180019a71  mov     dil, 1
0x180019a74  jz      loc_180019BA6
0x180019a7a  mov     ecx, 2; level
0x180019a7f  call    IsWppLevelEnabled
0x180019a84  test    al, al
0x180019a86  jz      loc_180019BA6
0x180019a8c  test    dl, dl
0x180019a8e  lea     pMessage, aFalse; "false"
0x180019a95  lea     rax, aTrue; "true"
0x180019a9c  mov     r9d, 2
0x180019aa2  cmovz   rax, pMessage
0x180019aa6  mov     r8d, 3CFh
0x180019aac  mov     [rsp+340h+var_310], rax
0x180019ab1  mov     rax, cs:?g_aBoolPropertyDescriptors@FeatureDevelopmentProperties@@3QBUBoolPropertyDescriptor@1@B.pszPropertyName+70h; FeatureDevelopmentProperties::BoolPropertyDescriptor const near * const FeatureDevelopmentProperties::g_aBoolPropertyDescriptors ...
0x180019ab8  mov     [rsp+340h+var_318], rax
0x180019abd  lea     rax, aPropertySWasEx_0; "Property %S was explicitly set to %S"
0x180019ac4  jmp     loc_180019B8E
0x180019ac9  cmp     eax, 2
0x180019acc  jnz     short loc_180019ADA
0x180019ace  movzx   ebx, cs:FeatureDevelopmentProperties__g_aBoolPropertyStates.cachedValue+1Ch
0x180019ad5  jmp     loc_180019BC1
0x180019ada  lea     pCall, [rbp+220h+whichProperty]; whichProperty
0x180019ade  mov     ecx, 7; whichProperty
0x180019ae3  call    ??$GetDefaultOverride@W4BoolProperty@FeatureDevelopmentProperties@@U_unnamed_type_g_boolPropertyDefaultOverrideRecords_@2@$01@FeatureDevelopmentProperties@@YA_NW4BoolProperty@0@AEAY01$$CBU_unnamed_type_g_boolPropertyDefaultOverrideRecords_@0@PEA_N@Z; FeatureDevelopmentProperties::GetDefaultOverride<FeatureDevelopmentProperties::BoolProperty,FeatureDevelopmentProperties::_unnamed_type_g_boolPropertyDefaultOverrideRecords_,2>(FeatureDevelopmentProperties::BoolProperty,FeatureDevelopmentProperties::_unnamed_type_g_boolPropertyDefaultOverrideRecords_ const (&)[2],bool *)
0x180019ae8  test    al, al
0x180019aea  jz      short loc_180019B4A
0x180019aec  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180019af3  mov     dil, 1
0x180019af6  jz      short loc_180019B44
0x180019af8  mov     ecx, 2; level
0x180019afd  call    IsWppLevelEnabled
0x180019b02  test    al, al
0x180019b04  jz      short loc_180019B44
0x180019b06  movzx   ebx, [rbp+220h+whichProperty]
0x180019b0a  lea     rax, aTrue; "true"
0x180019b11  test    bl, bl
0x180019b13  lea     pMessage, aFalse; "false"
0x180019b1a  mov     r9d, 2
0x180019b20  mov     r8d, 3D9h
0x180019b26  cmovz   rax, pMessage
0x180019b2a  mov     [rsp+340h+var_310], rax
0x180019b2f  mov     rax, cs:?g_aBoolPropertyDescriptors@FeatureDevelopmentProperties@@3QBUBoolPropertyDescriptor@1@B.pszPropertyName+70h; FeatureDevelopmentProperties::BoolPropertyDescriptor const near * const FeatureDevelopmentProperties::g_aBoolPropertyDescriptors ...
0x180019b36  mov     [rsp+340h+var_318], rax
0x180019b3b  lea     rax, aPropertySWasSe; "Property %S was set to %S via an overri"...
0x180019b42  jmp     short loc_180019B8E
0x180019b44  movzx   ebx, [rbp+220h+whichProperty]
0x180019b48  jmp     short loc_180019BA6
0x180019b4a  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180019b51  mov     bl, 1
0x180019b53  jz      short loc_180019BA6
0x180019b55  mov     ecx, 3; level
0x180019b5a  call    IsWppLevelEnabled
0x180019b5f  test    al, al
0x180019b61  jz      short loc_180019BA6
0x180019b63  lea     rax, aTrue; "true"
0x180019b6a  mov     r9d, 3; level
0x180019b70  mov     [rsp+340h+var_310], rax; <args_1>
0x180019b75  mov     r8d, 3E1h; line
0x180019b7b  mov     rax, cs:?g_aBoolPropertyDescriptors@FeatureDevelopmentProperties@@3QBUBoolPropertyDescriptor@1@B.pszPropertyName+70h; FeatureDevelopmentProperties::BoolPropertyDescriptor const near * const FeatureDevelopmentProperties::g_aBoolPropertyDescriptors ...
0x180019b82  mov     [rsp+340h+var_318], rax; <args_0>
0x180019b87  lea     rax, aPropertySDefau_0; "Property %S defaulted to %S"
0x180019b8e  lea     fFakeAsync, aFeaturedevelop_0; "FeatureDevelopmentProperties::Query"
0x180019b95  mov     qword ptr [rsp+340h+level], rax; format
0x180019b9a  lea     pMessage, aOnecoreComComb_20; "onecore\\com\\combase\\featuredevelopme"...
  ... truncated ...
```
