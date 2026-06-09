# CheckAccess(void *,ulong,TransportLocality,int,void *)

- ea: `0x180165ef0`
- end: `0x1801672ad`
- name: `?CheckAccess@@YAJPEAXKW4TransportLocality@@H0@Z`
- size: `5053`
- prototype: `__int64 __fastcall(wchar_t *hRpc, unsigned int dwAuthnLevel, TransportLocality locality, int fCheckIAccessControl, _GUID *Interface)`
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800312b0`
- `0x1800ddd30`
- `0x18012b030`

## callees

- `0x180006250`
- `0x180006410`
- `0x18000712c`
- `0x18000833c`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x1800472a0`
- `0x18005cc10`
- `0x18005df80`
- `0x1800865f4`
- `0x1800fd6b0`
- `0x180152f44`
- `0x18015682c`
- `0x180165ef0`
- `0x18017101c`
- `0x180179024`
- `0x1801999b0`
- `0x1801b2330`
- `0x1801b2480`
- `0x1801b2550`
- `0x1801dcf2c`
- `0x180209ca4`
- `0x1802135dd`
- `0x180255010`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x1801660db`
- `RPCRT4!RpcStringBindingParseW` at `0x1801660db`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180166061`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180166061`
- `RPCRT4!RpcStringFreeW` at `0x180166099`
- `RPCRT4!RpcStringFreeW` at `0x180166117`
- `RPCRT4!RpcStringFreeW` at `0x18016612f`
- `RPCRT4!RpcStringFreeW` at `0x180166146`
- `RPCRT4!RpcStringFreeW` at `0x1801661d3`
- `RPCRT4!RpcStringFreeW` at `0x1801661ea`
- `RPCRT4!RpcStringFreeW` at `0x18016625b`
- `RPCRT4!RpcStringFreeW` at `0x1801664a1`
- `RPCRT4!RpcStringFreeW` at `0x1801664e1`
- `RPCRT4!RpcStringFreeW` at `0x180166099`
- `RPCRT4!RpcStringFreeW` at `0x180166117`
- `RPCRT4!RpcStringFreeW` at `0x18016612f`
- `RPCRT4!RpcStringFreeW` at `0x180166146`
- `RPCRT4!RpcStringFreeW` at `0x1801661d3`
- `RPCRT4!RpcStringFreeW` at `0x1801661ea`
- `RPCRT4!RpcStringFreeW` at `0x18016625b`
- `RPCRT4!RpcStringFreeW` at `0x1801664a1`
- `RPCRT4!RpcStringFreeW` at `0x1801664e1`
- `RPCRT4!I_RpcBindingInqCurrentModifiedId` at `0x180166799`
- `RPCRT4!I_RpcBindingInqCurrentModifiedId` at `0x180166799`
- `RPCRT4!UuidFromStringW` at `0x180166223`
- `RPCRT4!UuidFromStringW` at `0x180166223`
- `RPCRT4!RpcBindingServerFromClient` at `0x180166014`
- `RPCRT4!RpcBindingServerFromClient` at `0x180166014`
- `RPCRT4!RpcBindingFree` at `0x18016615d`
- `RPCRT4!RpcBindingFree` at `0x180166201`
- `RPCRT4!RpcBindingFree` at `0x18016615d`
- `RPCRT4!RpcBindingFree` at `0x180166201`
- `ntdll!EtwEventWriteTransfer` at `0x1801665f1`
- `ntdll!EtwEventWriteTransfer` at `0x18016721c`
- `ntdll!EtwEventWriteTransfer` at `0x1801665f1`
- `ntdll!EtwEventWriteTransfer` at `0x18016721c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801663c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801663c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180167258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180167258`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180166b4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180166c95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180167243`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180166b4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180166c95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180167243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180166b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180166c7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016722c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180166b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180166c7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016722c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801662d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180166425`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801662d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180166425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180166d66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180166e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180166d66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180166e40`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1801663b6`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1801663b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180166875`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180166a08`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180166875`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180166a08`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180166a9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180166bcb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18016700a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801670f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180166a9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180166bcb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18016700a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801670f7`

## string_xrefs

- `0x180165fe3`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180166500`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1801666c7`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180166769`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180166c46`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180166cb5`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180166d8f`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18016729b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18016616a`: `onecore\com\combase\common\core\activateonhost.cpp`
- `0x180166234`: `onecore\com\combase\common\core\activateonhost.cpp`
- `0x180166444`: `onecore\com\combase\common\core\activateonhost.cpp`
- `0x18016646a`: `onecore\com\combase\common\core\activateonhost.cpp`
- `0x180166480`: `onecore\com\combase\common\core\activateonhost.cpp`
- `0x18016602a`: `onecore\com\combase\ih\RpcUtilities.hpp`
- `0x180166077`: `onecore\com\combase\ih\RpcUtilities.hpp`
- `0x1801660f5`: `onecore\com\combase\ih\RpcUtilities.hpp`
- `0x180165fd1`: `CheckAccess`
- `0x1801666bd`: `CheckAccess`
- `0x180166748`: `CheckAccess`
- `0x18016682c`: `CheckAccess`
- `0x1801669c9`: `CheckAccess`
- `0x180166c3c`: `CheckAccess`
- `0x180166f49`: `CheckAccess`
- `0x180166c5b`: `iid:%ws Local:%!bool! SID:%ws`
- `0x180166b18`: `iid:%ws Local:%!bool! SID:%ws %!WINERROR!`
- `0x18016707e`: `iid:%ws Local:%d SID:%ws %!WINERROR!`
- `0x180166363`: `onecore\com\combase\common\core\containersynchronization.cpp`

## pseudocode

```c
__int64 __fastcall CheckAccess(
        wchar_t *hRpc,
        unsigned int dwAuthnLevel,
        TransportLocality locality,
        int fCheckIAccessControl,
        _GUID *Interface)
{
  TransportLocality v6; // esi
  __int64 result; // rax
  unsigned int v8; // r13d
  bool v9; // r14
  RPC_STATUS v10; // eax
  unsigned int v11; // ebx
  RPC_BINDING_HANDLE *p_Binding; // rcx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  __int64 v15; // rdx
  HRESULT v16; // edi
  unsigned __int16 *v17; // rsi
  int v18; // ebx
  RPC_STATUS v19; // eax
  const _WNF_STATE_NAME *v20; // rcx
  unsigned int v21; // r8d
  void (__fastcall ***v22)(_QWORD, __int64); // rbx
  unsigned int v23; // edx
  LSTATUS ValueW; // eax
  __int32 v25; // eax
  void *TokenForRpcClient; // r14
  int v27; // eax
  const char *v28; // rcx
  TraceLevel v29; // r9d
  int v30; // r10d
  _LUID ModifiedId; // rcx
  BOOL TokenInformation; // r12d
  int v33; // r15d
  int v34; // eax
  int v35; // edi
  int v36; // ebx
  int v37; // ebx
  int v38; // eax
  const char *v39; // rcx
  TraceLevel v40; // r9d
  const char *v41; // r9
  void *v42; // rax
  void *v43; // rbx
  wchar_t *v44; // rsi
  const char *v45; // rdx
  const char *v46; // rcx
  TraceLevel v47; // r9d
  const char *v48; // r9
  void *UserSid; // rax
  void *v50; // rbx
  RPC_WSTR v51; // rsi
  _LUID v52; // rbx
  __int64 v53; // rax
  int v54; // edx
  bool v55; // zf
  unsigned int v56; // eax
  _DWORD *ReservedForOle; // rsi
  int v58; // ebx
  _LUID v59; // rbx
  __int64 v60; // rax
  int v61; // edx
  unsigned int v62; // eax
  _DWORD *v63; // rsi
  int v64; // ebx
  unsigned int v65; // r15d
  tagEventLogSD v66; // r13d
  TransportLocality v67; // r12d
  LPWSTR v68; // rsi
  TraceLevel v69; // r9d
  _GUID *v70; // r13
  void *v71; // rax
  void *v72; // r15
  const char *v73; // rdx
  const char *v74; // rcx
  TraceLevel v75; // r9d
  wchar_t *v76; // r10
  RPC_WSTR v77; // rcx
  __int64 v78; // rax
  unsigned int v79; // eax
  const wchar_t *level; // [rsp+20h] [rbp-E0h]
  const wchar_t *levela; // [rsp+20h] [rbp-E0h]
  int line[2]; // [rsp+38h] [rbp-C8h]
  int __formal; // [rsp+40h] [rbp-C0h]
  tagEventLogSD hsClassIdentifier; // [rsp+48h] [rbp-B8h]
  int fAccess; // [rsp+50h] [rbp-B0h] BYREF
  __int32 pvData; // [rsp+54h] [rbp-ACh] BYREF
  TransportLocality v87; // [rsp+58h] [rbp-A8h]
  RPC_WSTR Protseq; // [rsp+60h] [rbp-A0h] BYREF
  DWORD CompareAddress[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v90; // [rsp+70h] [rbp-90h] BYREF
  unsigned int lSize; // [rsp+74h] [rbp-8Ch] BYREF
  int v92; // [rsp+78h] [rbp-88h] BYREF
  _LUID luidMod; // [rsp+80h] [rbp-80h] BYREF
  _GUID *hToken; // [rsp+88h] [rbp-78h]
  LPWSTR StringSid; // [rsp+90h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+98h] [rbp-68h] BYREF
  RPC_WSTR StringBinding; // [rsp+A0h] [rbp-60h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+A8h] [rbp-58h] BYREF
  RPC_WSTR v99; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v100; // [rsp+B8h] [rbp-48h]
  RPC_BINDING_HANDLE v101; // [rsp+C0h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+C8h] [rbp-38h] BYREF
  RPC_BINDING_HANDLE v103; // [rsp+D0h] [rbp-30h] BYREF
  RPC_WSTR v104; // [rsp+D8h] [rbp-28h] BYREF
  RPC_WSTR v105; // [rsp+E0h] [rbp-20h] BYREF
  RPC_WSTR v106; // [rsp+E8h] [rbp-18h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+F0h] [rbp-10h] BYREF
  RPC_WSTR v108; // [rsp+F8h] [rbp-8h] BYREF
  RPC_WSTR v109; // [rsp+100h] [rbp+0h] BYREF
  RPC_BINDING_HANDLE v110; // [rsp+108h] [rbp+8h] BYREF
  RPC_WSTR v111; // [rsp+110h] [rbp+10h] BYREF
  RPC_WSTR v112; // [rsp+118h] [rbp+18h] BYREF
  _BYTE sz[80]; // [rsp+120h] [rbp+20h] BYREF
  wistd::function<void __cdecl(void)> subscriptionState; // [rsp+170h] [rbp+70h] BYREF
  UUID Uuid; // [rsp+1F0h] [rbp+F0h] BYREF
  _TOKEN_STATISTICS sTokenStatistics; // [rsp+200h] [rbp+100h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  StringSid = hRpc;
  v92 = fCheckIAccessControl;
  v87 = locality;
  hToken = Interface;
  fAccess = 0;
  v6 = locality;
  lSize = 56;
  luidMod = 0;
  memset(&sTokenStatistics, 0, sizeof(sTokenStatistics));
  if ( locality == Local )
  {
    v8 = 2;
    goto LABEL_86;
  }
  if ( locality == Container )
  {
    ServerBinding = 0;
    v9 = 0;
    v10 = RpcBindingServerFromClient(hRpc, &ServerBinding);
    v11 = v10;
    if ( v10 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, 0x6Du, "onecore\\com\\combase\\ih\\RpcUtilities.hpp", v10);
      if ( !ServerBinding )
      {
LABEL_27:
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                0x32u,
                "onecore\\com\\combase\\common\\core\\activateonhost.cpp",
                v11);
LABEL_71:
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(retaddr, 0x952u, "onecore\\com\\combase\\dcomrem\\security.cxx", v16);
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 > 2
            && (Tlgg_hCombaseTraceLoggingProviderProv.KeywordAny & 0x400000000000LL) != 0
            && (Tlgg_hCombaseTraceLoggingProviderProv.KeywordAll & 0x400000000000LL) == Tlgg_hCombaseTraceLoggingProviderProv.KeywordAll )
          {
            CompareAddress[0] = v16;
            *(_QWORD *)&sz[32] = CompareAddress;
            HIDWORD(v99) = *(unsigned __int16 *)&tlgEvent_14._tlgLevel;
            wcscpy((wchar_t *)sz, (const wchar_t *)&Tlgg_hCombaseTraceLoggingProviderProv.ProviderMetadataPtr);
            *(_QWORD *)&sz[48] = Interface;
            *(_QWORD *)&sz[56] = 16;
            *(_QWORD *)&sz[40] = 4;
            LODWORD(v99) = 184549376;
            v100 = 0x400000000000LL;
            *(_DWORD *)&sz[8] = *Tlgg_hCombaseTraceLoggingProviderProv.ProviderMetadataPtr;
            *(_QWORD *)&sz[16] = &tlgEvent_14._tlgEvtMetaSize;
            *(_DWORD *)&sz[12] = 2;
            *(_QWORD *)&sz[24] = 0x10000005ELL;
            v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(Tlgg_hCombaseTraceLoggingProviderProv.RegHandle, &v99, 0, 0, 4, sz);
            return 2147942405LL;
          }
          return 2147942405LL;
        }
        if ( v9 )
          return 0;
        v8 = 32;
        if ( CheckContainerAuthentication(hRpc, v15) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_79;
      }
      v101 = ServerBinding;
      p_Binding = &v101;
LABEL_26:
      RpcBindingFree(p_Binding);
      goto LABEL_27;
    }
    StringBinding = 0;
    v13 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
    v11 = v13;
    if ( v13 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, 0x74u, "onecore\\com\\combase\\ih\\RpcUtilities.hpp", v13);
      if ( StringBinding )
      {
        String = StringBinding;
        RpcStringFreeW(&String);
      }
      if ( !ServerBinding )
        goto LABEL_27;
      v103 = ServerBinding;
      p_Binding = &v103;
      goto LABEL_26;
    }
    NetworkAddr = 0;
    Protseq = 0;
    v14 = RpcStringBindingParseW(StringBinding, 0, &Protseq, &NetworkAddr, 0, 0);
    v11 = v14;
    if ( v14 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, 0x7Cu, "onecore\\com\\combase\\ih\\RpcUtilities.hpp", v14);
      if ( NetworkAddr )
      {
        v104 = NetworkAddr;
        RpcStringFreeW(&v104);
      }
      if ( Protseq )
      {
        v105 = Protseq;
        RpcStringFreeW(&v105);
      }
      if ( StringBinding )
      {
        v106 = StringBinding;
        RpcStringFreeW(&v106);
      }
      if ( !ServerBinding )
        goto LABEL_27;
      Binding = ServerBinding;
      p_Binding = &Binding;
      goto LABEL_26;
    }
    v17 = NetworkAddr;
    v15 = -1;
    NetworkAddr = 0;
    do
    {
      v18 = String1[v15 + 1] - Protseq[v15 + 1];
      if ( v18 )
        break;
      v15 += 2;
      if ( v15 == 15 )
        break;
      v18 = String1[v15] - Protseq[v15];
    }
    while ( !v18 );
    if ( Protseq )
    {
      v108 = Protseq;
      RpcStringFreeW(&v108);
    }
    if ( StringBinding )
    {
      v109 = StringBinding;
      RpcStringFreeW(&v109);
    }
    if ( ServerBinding )
    {
      v110 = ServerBinding;
      RpcBindingFree(&v110);
    }
    if ( !v18 )
    {
      Uuid = 0;
      v19 = UuidFromStringW(v17, &Uuid);
      if ( v19 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                0x37u,
                "onecore\\com\\combase\\common\\core\\activateonhost.cpp",
                v19);
        if ( v17 )
        {
          v111 = v17;
          RpcStringFreeW(&v111);
        }
LABEL_70:
        v6 = v87;
        goto LABEL_71;
      }
      if ( !memcmp_0(&Uuid, &HV_GUID_PARENT, 0x10u) )
      {
        if ( !ActivateOnHost::s_initialized._Storage._Value )
        {
          pvData = 0;
          CompareAddress[0] = 4;
          if ( (RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\Containers",
                  L"FirstBootExperienceEnabled",
                  0x10u,
                  0,
                  &pvData,
                  CompareAddress)
             || !pvData)
            && ContainerSynchronization::ShouldWaitForRestore() )
          {
            pvData = 0;
            subscriptionState.__buf_.__align = (unsigned __int64)wistd::__function::__func__lambda_3d150f8d20dbfcb587a427312ad80f8f__void___cdecl_void__::_vftable_;
            *(_QWORD *)CompareAddress = 0;
            *(_QWORD *)&subscriptionState.__buf_.__data[8] = &pvData;
            subscriptionState.__f_ = (wistd::__function::__base<void __cdecl(void)> *)&subscriptionState.__buf_;
            v22 = 0;
            if ( wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(
                   v20,
                   &subscriptionState,
                   v21,
                   (wil::details::wnf_subscription_state<wil::details::empty_wnf_state> **)CompareAddress) >= 0 )
              v22 = *(void (__fastcall ****)(_QWORD, __int64))CompareAddress;
            if ( subscriptionState.__f_ )
              ((void (*)(void))subscriptionState.__f_->destroy)();
            if ( !v22 )
            {
              v16 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                0x3Du,
                "onecore\\com\\combase\\common\\core\\containersynchronization.cpp",
                -2147024882);
              v23 = 85;
              goto LABEL_62;
            }
            while ( !_InterlockedExchange(&pvData, 0) )
            {
              CompareAddress[0] = 0;
              if ( !WaitOnAddress(&pvData, CompareAddress, 4u, 0xFFFFFFFF) )
              {
                if ( GetLastError() != 1460 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    0xDBFu,
                    "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
                break;
              }
            }
            (**v22)(v22, 1);
          }
          v90 = 0;
          CompareAddress[0] = 4;
          ValueW = RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"SOFTWARE\\Microsoft\\OLE",
                     L"ActivateOnHostFlags",
                     0x10u,
                     0,
                     &v90,
                     CompareAddress);
          if ( ValueW == 2 )
          {
            v25 = 0;
            v90 = 0;
          }
          else
          {
            if ( ValueW )
            {
              v16 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      0x7Cu,
                      "onecore\\com\\combase\\common\\core\\activateonhost.cpp",
                      ValueW);
              if ( v16 < 0 )
              {
                v23 = 89;
LABEL_62:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  v23,
                  "onecore\\com\\combase\\common\\core\\activateonhost.cpp",
                  v16);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0x3Cu,
                  "onecore\\com\\combase\\common\\core\\activateonhost.cpp",
                  v16);
                if ( v17 )
                {
                  v112 = v17;
                  RpcStringFreeW(&v112);
                }
                goto LABEL_70;
              }
            }
            v25 = v90;
          }
          _InterlockedExchange((volatile __int32 *)&ActivateOnHost::s_machineActivateOnHostFlags, v25);
          ActivateOnHost::s_initialized._Storage._Value = 1;
        }
        v9 = ActivateOnHost::s_machineActivateOnHostFlags._Storage._Value != 0;
      }
    }
    if ( v17 )
    {
      v99 = v17;
      RpcStringFreeW(&v99);
    }
    v16 = 0;
    goto LABEL_70;
  }
  if ( locality != Network )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
    {
      ComTraceMessage(
        -1,
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CheckAccess",
        2415,
        ERRORS,
        L"Unexpected TransportLocality:%d",
        locality);
      return 2147942405LL;
    }
    return 2147942405LL;
  }
  v8 = 4;
LABEL_86:
  if ( (unsigned int)gAuthnLevel > 1 && dwAuthnLevel < (unsigned int)gAuthnLevel )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
    {
      ComTraceMessage(
        -1,
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CheckAccess",
        2438,
        ERRORS,
        L"AuthnLevel from RPC:%d My AuthnLevel:%d",
        dwAuthnLevel,
        (_DWORD)gAuthnLevel);
      return 2147942405LL;
    }
    return 2147942405LL;
  }
  if ( locality == Local )
  {
    v27 = I_RpcBindingInqCurrentModifiedId(hRpc, &luidMod);
    if ( !v27 )
    {
      ModifiedId = luidMod;
      TokenForRpcClient = 0;
      TokenInformation = 1;
      goto LABEL_102;
    }
    if ( v27 != 1765
      && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
       || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0) )
    {
      wcscpy((wchar_t *)sz, L"Guid unavailable");
      memset(&sz[34], 0, 46);
      wStringFromGUID2(Interface, (wchar_t *)sz, 40);
      ComTraceMessageT<unsigned short *,bool,long>(v28, "CheckAccess", 2458, v29, level, (wchar_t *)sz, 1, v30);
    }
  }
LABEL_79:
  TokenForRpcClient = GetTokenForRpcClient(hRpc, v6);
  if ( !TokenForRpcClient )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
    {
      wcscpy((wchar_t *)sz, L"Guid unavailable");
      memset(&sz[34], 0, 46);
      wStringFromGUID2(Interface, (wchar_t *)sz, 40);
      line[0] = v6 == Local;
      ComTraceMessage(
        5,
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CheckAccess",
        2478,
        ERRORS,
        L"iid:%ws Local:%!bool! %!WINERROR!",
        sz,
        *(_QWORD *)line,
        5);
      return 2147942405LL;
    }
    return 2147942405LL;
  }
  TokenInformation = GetTokenInformation(TokenForRpcClient, TokenStatistics, &sTokenStatistics, lSize, &lSize);
  if ( !TokenInformation )
  {
    v33 = 0;
LABEL_134:
    if ( v6 != Container )
    {
      if ( !(unsigned int)CallAccessCheck(TokenForRpcClient, gSecDescRestrictions, v8, &fAccess) )
      {
        UserSid = GetUserSid(TokenForRpcClient);
        v50 = UserSid;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
          || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
        {
          Protseq = 0;
          ConvertSidToStringSidW(UserSid, &Protseq);
          v51 = (RPC_WSTR)&pszValueToSet;
          if ( Protseq )
            v51 = Protseq;
          wcscpy((wchar_t *)sz, L"Guid unavailable");
          memset(&sz[34], 0, 46);
          wStringFromGUID2(hToken, (wchar_t *)sz, 40);
          line[0] = v87 == Local;
          ComTraceMessage(
            -1,
            "onecore\\com\\combase\\dcomrem\\security.cxx",
            "CheckAccess",
            2580,
            ERRORS,
            L"iid:%ws Local:%!bool! SID:%ws",
            sz,
            *(_QWORD *)line,
            v51);
          if ( Protseq )
            LocalFree(Protseq);
        }
        if ( v50 )
          HeapFree(g_hHeap, 0, v50);
LABEL_145:
        v35 = fAccess;
        goto $Cleanup_12;
      }
      v35 = fAccess;
      if ( TokenInformation )
      {
        v52 = luidMod;
        COleStaticMutexSem::Request(
          &gSecurityLockRestrictions,
          "onecore\\com\\combase\\dcomrem\\security.cxx",
          0x189u,
          v48);
        v53 = gMostRecentRestrictionsIndex + 1;
        gMostRecentRestrictionsIndex = v53;
        if ( (unsigned int)v53 < 5 )
        {
          v54 = v53;
        }
        else
        {
          v53 = 0;
          gMostRecentRestrictionsIndex = 0;
          v54 = 0;
        }
        gRestrictionsCache[v53].fAccess = v35;
        v55 = gSecurityLockRestrictions._cLocks == 1;
        v56 = gSecurityLockRestrictions._cLocks - 1;
        gRestrictionsCache[v54].lClient = v52;
        gSecurityLockRestrictions._cLocks = v56;
        if ( v55 && gSecurityLockRestrictions._lockOrder != Highest )
        {
          ReservedForOle = NtCurrentTeb()->ReservedForOle;
          if ( ReservedForOle )
          {
            v58 = 1 << gSecurityLockRestrictions._lockOrder;
            if ( ((1 << gSecurityLockRestrictions._lockOrder) & ReservedForOle[144]) == 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            ReservedForOle[144] &= ~v58;
          }
        }
        LeaveCriticalSection(&gSecurityLockRestrictions._cs);
      }
      if ( !v35 )
      {
        v37 = 1;
        goto LABEL_178;
      }
    }
    goto LABEL_121;
  }
  ModifiedId = sTokenStatistics.ModifiedId;
  luidMod = sTokenStatistics.ModifiedId;
LABEL_102:
  v33 = 0;
  v34 = CacheAccessCheck(
          ModifiedId,
          &fAccess,
          gRestrictionsCache,
          &gMostRecentRestrictionsIndex,
          &gSecurityLockRestrictions);
  v35 = fAccess;
  v36 = v34;
  if ( v34 && !fAccess )
  {
    v37 = 1;
LABEL_178:
    v65 = 18211;
    goto LABEL_179;
  }
  if ( gSecDesc )
  {
    v38 = CacheAccessCheck(
            luidMod,
            &fAccess,
            gPermissionsCache,
            &gMostRecentPermissionsIndex,
            &gSecurityLockPermissions);
    v35 = fAccess;
    v33 = v38;
    if ( v38 )
    {
      if ( !fAccess )
      {
        v37 = 1;
        goto LABEL_178;
      }
    }
  }
  if ( v36 && (v33 || !gSecDesc) )
  {
$AccessChecksDone:
    v37 = 0;
    if ( !v35 )
      goto LABEL_178;
    goto $Cleanup_12;
  }
  if ( !TokenForRpcClient )
  {
    TokenForRpcClient = GetTokenForRpcClient(StringSid, v6);
    if ( !TokenForRpcClient )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
        || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
      {
        wcscpy((wchar_t *)sz, L"Guid unavailable");
        memset(&sz[34], 0, 46);
        wStringFromGUID2(hToken, (wchar_t *)sz, 40);
        ComTraceMessageT<unsigned short *,bool,long>(
          v39,
          "CheckAccess",
          2552,
          v40,
          levela,
          (wchar_t *)sz,
          v6 == Local,
          5);
      }
      goto LABEL_214;
    }
    TokenInformation = GetTokenInformation(TokenForRpcClient, TokenStatistics, &sTokenStatistics, lSize, &lSize);
    if ( TokenInformation )
      luidMod = sTokenStatistics.ModifiedId;
  }
  if ( !v36 )
    goto LABEL_134;
LABEL_121:
  if ( !gSecDesc || v33 )
  {
    if ( !v92 || !gAccessControl )
    {
      v35 = 1;
      goto $Cleanup_12;
    }
    v35 = CheckAccessControl() == 0;
    goto $AccessChecksDone;
  }
  if ( !(unsigned int)CallAccessCheck(TokenForRpcClient, (_SECURITY_DESCRIPTOR *)gSecDesc, v8, &fAccess) )
  {
    v42 = GetUserSid(TokenForRpcClient);
    v43 = v42;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
    {
      Protseq = 0;
      ConvertSidToStringSidW(v42, &Protseq);
      v44 = (wchar_t *)&pszValueToSet;
      if ( Protseq )
        v44 = Protseq;
      wcscpy((wchar_t *)sz, L"Guid unavailable");
      memset(&sz[34], 0, 46);
      wStringFromGUID2(hToken, (wchar_t *)sz, 40);
      ComTraceMessageT<unsigned short *,bool,unsigned short *,long>(
        v46,
        v45,
        2615,
        v47,
        L"iid:%ws Local:%!bool! SID:%ws %!WINERROR!",
        (wchar_t *)sz,
        v87 == Local,
        v44,
        __formal);
      if ( Protseq )
        LocalFree(Protseq);
    }
    if ( v43 )
    {
      HeapFree(g_hHeap, 0, v43);
      v35 = fAccess;
      goto $Cleanup_12;
    }
    goto LABEL_145;
  }
  v35 = fAccess;
  if ( TokenInformation )
  {
    v59 = luidMod;
    COleStaticMutexSem::Request(&gSecurityLockPermissions, "onecore\\com\\combase\\dcomrem\\security.cxx", 0x189u, v41);
    v60 = gMostRecentPermissionsIndex + 1;
    gMostRecentPermissionsIndex = v60;
    if ( (unsigned int)v60 < 5 )
    {
      v61 = v60;
    }
    else
    {
      v60 = 0;
      gMostRecentPermissionsIndex = 0;
      v61 = 0;
    }
    gPermissionsCache[v60].fAccess = v35;
    v55 = gSecurityLockPermissions._cLocks == 1;
    v62 = gSecurityLockPermissions._cLocks - 1;
    gPermissionsCache[v61].lClient = v59;
    gSecurityLockPermissions._cLocks = v62;
    if ( v55 && gSecurityLockPermissions._lockOrder != Highest )
    {
      v63 = NtCurrentTeb()->ReservedForOle;
      if ( v63 )
      {
        v64 = 1 << gSecurityLockPermissions._lockOrder;
        if ( ((1 << gSecurityLockPermissions._lockOrder) & v63[144]) == 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v63[144] &= ~v64;
      }
    }
    LeaveCriticalSection(&gSecurityLockPermissions._cs);
  }
  if ( !v35 )
  {
    v37 = 1;
    if ( genumAccessSD != EventLog_SERVERACCESSPERMISSIONSPROG )
    {
      v65 = 18209;
      v66 = genumAccessSD;
      goto LABEL_180;
    }
    v65 = 18210;
LABEL_179:
    v66 = EventLog_DONTCARE;
LABEL_180:
    v67 = v87;
    v68 = StringSid;
    if ( !TokenForRpcClient )
    {
      TokenForRpcClient = GetTokenForRpcClient(StringSid, v87);
      if ( !TokenForRpcClient )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
          || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
        {
          wcscpy((wchar_t *)sz, L"Guid unavailable");
          memset(&sz[34], 0, 46);
          wStringFromGUID2(hToken, (wchar_t *)sz, 40);
          ComTraceMessageT<unsigned short *,bool,long>(
            sz,
            "CheckAccess",
            2669,
            v69,
            levela,
            (wchar_t *)sz,
            v67 == Local,
            5);
        }
        return 2147942405LL;
      }
    }
    if ( v37 && gfLogCallFailure )
    {
      hsClassIdentifier = v66;
      v70 = hToken;
      LogAccessFailed(
        v68,
        0,
        0,
        &g_AppId,
        hToken,
        v65,
        TokenForRpcClient,
        v67 != Local,
        EventLog_ModeDontCare,
        hsClassIdentifier);
    }
    else
    {
      v70 = hToken;
    }
    v71 = GetUserSid(TokenForRpcClient);
    v72 = v71;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
      || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
    {
      StringSid = 0;
      ConvertSidToStringSidW(v71, &StringSid);
      wcscpy((wchar_t *)sz, L"Guid unavailable");
      memset(&sz[34], 0, 46);
      wStringFromGUID2(v70, (wchar_t *)sz, 40);
      ComTraceMessageT<unsigned short *,bool,unsigned short *,long>(
        v74,
        v73,
        2683,
        v75,
        L"iid:%ws Local:%d SID:%ws %!WINERROR!",
        (wchar_t *)sz,
        v67 == Local,
        v76,
        __formal);
      if ( StringSid )
        LocalFree(StringSid);
    }
    if ( v67 == Container
      && Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 > 2
      && (Tlgg_hCombaseTraceLoggingProviderProv.KeywordAny & 0x400000000000LL) != 0
      && (Tlgg_hCombaseTraceLoggingProviderProv.KeywordAll & 0x400000000000LL) == Tlgg_hCombaseTraceLoggingProviderProv.KeywordAll )
    {
      Protseq = 0;
      ConvertSidToStringSidW(v72, &Protseq);
      v77 = (RPC_WSTR)&pszValueToSet;
      v92 = -2147024891;
      if ( Protseq )
        v77 = Protseq;
      if ( v77 )
      {
        v78 = -1;
        do
          v55 = v77[++v78] == 0;
        while ( !v55 );
        v79 = 2 * v78 + 2;
      }
      else
      {
        v77 = (RPC_WSTR)&pszValueToSet;
        v79 = 2;
      }
      *(_QWORD *)&subscriptionState.__buf_.__data[80] = v79;
      *(_QWORD *)&subscriptionState.__buf_.__data[72] = v77;
      *(_QWORD *)&subscriptionState.__buf_.__data[56] = &g_AppId;
      *(_QWORD *)&subscriptionState.__buf_.__data[24] = &v92;
      HIDWORD(v99) = *(unsigned __int16 *)&tlgEvent_15._tlgLevel;
      *(_QWORD *)&subscriptionState.gap0 = Tlgg_hCombaseTraceLoggingProviderProv.ProviderMetadataPtr;
      *(_QWORD *)&subscriptionState.__buf_.__data[64] = 16;
      *(_QWORD *)&subscriptionState.__buf_.__data[40] = v70;
      *(_QWORD *)&subscriptionState.__buf_.__data[48] = 16;
      *(_QWORD *)&subscriptionState.__buf_.__data[32] = 4;
      LODWORD(v99) = 184549376;
      v100 = 0x400000000000LL;
      subscriptionState.__buf_.__align = (unsigned __int16)*Tlgg_hCombaseTraceLoggingProviderProv.ProviderMetadataPtr
                                       | 0x200000000LL;
      *(_QWORD *)&subscriptionState.__buf_.__data[8] = &tlgEvent_15._tlgEvtMetaSize;
      *(_QWORD *)&subscriptionState.__buf_.__data[16] = 0x100000052LL;
      CompareAddress[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(Tlgg_hCombaseTraceLoggingProviderProv.RegHandle, &v99, 0, 0, 6, &subscriptionState);
      if ( Protseq )
        LocalFree(Protseq);
    }
    if ( v72 )
      HeapFree(g_hHeap, 0, v72);
  }
$Cleanup_12:
  if ( TokenForRpcClient )
    CloseHandle(TokenForRpcClient);
LABEL_214:
  result = 0;
  if ( !v35 )
    return 2147942405LL;
  return result;
}

```

## disassembly

```asm
0x180165ef0  mov     [rsp-8+arg_18], rbx
0x180165ef5  push    rbp
0x180165ef6  push    rsi
0x180165ef7  push    rdi
0x180165ef8  push    r12
0x180165efa  push    r13
0x180165efc  push    r14
0x180165efe  push    r15
0x180165f00  lea     rbp, [rsp-140h]
0x180165f08  sub     rsp, 240h
0x180165f0f  mov     rax, cs:__security_cookie
0x180165f16  xor     rax, rsp
0x180165f19  mov     [rbp+170h+var_38], rax
0x180165f20  mov     r12, [rbp+170h+rguid]
0x180165f27  lea     rbx, ?gSecurityLockRestrictions@@3VCOleStaticMutexSem@@A; COleStaticMutexSem gSecurityLockRestrictions
0x180165f2e  xor     r13d, r13d
0x180165f31  mov     [rbp+170h+StringSid], hRpc
0x180165f35  xorps   xmm0, xmm0
0x180165f38  mov     [rsp+270h+var_1F8], fCheckIAccessControl
0x180165f3d  xor     eax, eax
0x180165f3f  mov     [rsp+270h+var_218], locality
0x180165f44  mov     [rbp+170h+hToken], r12
0x180165f48  mov     r15, hRpc
0x180165f4b  mov     [rsp+270h+fAccess], r13d
0x180165f50  mov     esi, locality
0x180165f53  mov     qword ptr [rbp+170h+sTokenStatistics.ModifiedId.LowPart], rax
0x180165f5a  mov     ecx, locality
0x180165f5d  mov     [rsp+270h+lSize], 38h ; '8'
0x180165f65  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180165f6c  mov     qword ptr [rbp+170h+luidMod.LowPart], r13
0x180165f70  movups  xmmword ptr [rbp+170h+sTokenStatistics.TokenId.LowPart], xmm0
0x180165f77  movups  xmmword ptr [rbp+170h+sTokenStatistics.ExpirationTime], xmm0
0x180165f7e  movups  xmmword ptr [rbp+170h+sTokenStatistics.DynamicCharged], xmm0
0x180165f85  test    locality, locality
0x180165f88  jz      loc_180166706
0x180165f8e  sub     ecx, 1
0x180165f91  jz      short loc_180166006
0x180165f93  cmp     ecx, 1
0x180165f96  jz      short loc_180165FFB
0x180165f98  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180165f9e  test    eax, eax
0x180165fa0  jnz     short loc_180165FC0
0x180165fa2  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180165fa9  jz      loc_180166F65
0x180165faf  mov     rax, cs:WPP_GLOBAL_Control
0x180165fb6  test    byte ptr [rax+1Ch], 1
0x180165fba  jz      loc_180166F65
0x180165fc0  mov     dword ptr [rsp+270h+pcbData], locality
0x180165fc5  lea     rax, aUnexpectedTran; "Unexpected TransportLocality:%d"
0x180165fcc  mov     [rsp+270h+format], rax; format
0x180165fd1  lea     r8, aCheckaccess; "CheckAccess"
0x180165fd8  mov     fCheckIAccessControl, 96Fh; line
0x180165fde  mov     [rsp+270h+level], r13d; level
0x180165fe3  lea     rdx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180165fea  mov     ecx, edi; hr
0x180165fec  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180165ff1  mov     eax, 80070005h
0x180165ff6  jmp     loc_18016726A
0x180165ffb  mov     r13d, 4
0x180166001  jmp     loc_18016670C
0x180166006  lea     rdx, [rbp+170h+ServerBinding]; ServerBinding
0x18016600a  mov     [rbp+170h+ServerBinding], r13
0x18016600e  mov     hRpc, r15; ClientBinding
0x180166011  xor     r14b, r14b
0x180166014  call    cs:__imp_RpcBindingServerFromClient
0x18016601a  mov     hRpc, [rbp+178h]; callerReturnAddress
0x180166021  mov     ebx, eax
0x180166023  test    eax, eax
0x180166025  jz      short loc_180166055
0x180166027  mov     fCheckIAccessControl, eax; err
0x18016602a  lea     r8, aOnecoreComComb_186; "onecore\\com\\combase\\ih\\RpcUtilities"...
0x180166031  mov     dwAuthnLevel, 6Dh ; 'm'; lineNumber
0x180166036  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18016603b  mov     hRpc, [rbp+170h+ServerBinding]
0x18016603f  test    hRpc, hRpc
0x180166042  jz      loc_180166163
0x180166048  mov     [rbp+170h+var_1B0], hRpc
0x18016604c  lea     hRpc, [rbp+170h+var_1B0]
0x180166050  jmp     loc_18016615D
0x180166055  mov     hRpc, [rbp+170h+ServerBinding]; Binding
0x180166059  lea     rdx, [rbp+170h+StringBinding]; StringBinding
0x18016605d  mov     [rbp+170h+StringBinding], r13
0x180166061  call    cs:__imp_RpcBindingToStringBindingW
0x180166067  mov     hRpc, [rbp+178h]; callerReturnAddress
0x18016606e  mov     ebx, eax
0x180166070  test    eax, eax
0x180166072  jz      short loc_1801660B9
0x180166074  mov     fCheckIAccessControl, eax; err
0x180166077  lea     r8, aOnecoreComComb_186; "onecore\\com\\combase\\ih\\RpcUtilities"...
0x18016607e  mov     dwAuthnLevel, 74h ; 't'; lineNumber
0x180166083  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180166088  mov     rax, [rbp+170h+StringBinding]
0x18016608c  test    rax, rax
0x18016608f  jz      short loc_18016609F
0x180166091  lea     hRpc, [rbp+170h+String]; String
0x180166095  mov     [rbp+170h+String], rax
0x180166099  call    cs:__imp_RpcStringFreeW
0x18016609f  mov     rax, [rbp+170h+ServerBinding]
0x1801660a3  test    rax, rax
0x1801660a6  jz      loc_180166163
0x1801660ac  mov     [rbp+170h+var_1A0], rax
0x1801660b0  lea     hRpc, [rbp+170h+var_1A0]
0x1801660b4  jmp     loc_18016615D
0x1801660b9  mov     hRpc, [rbp+170h+StringBinding]; StringBinding
0x1801660bd  lea     r9, [rbp+170h+NetworkAddr]; NetworkAddr
0x1801660c1  mov     [rsp+270h+format], r13; NetworkOptions
0x1801660c6  lea     r8, [rsp+270h+Protseq]; Protseq
0x1801660cb  xor     dwAuthnLevel, dwAuthnLevel; ObjUuid
0x1801660cd  mov     qword ptr [rsp+270h+level], r13; Endpoint
0x1801660d2  mov     [rbp+170h+NetworkAddr], r13
0x1801660d6  mov     [rsp+270h+Protseq], r13
0x1801660db  call    cs:__imp_RpcStringBindingParseW
0x1801660e1  mov     hRpc, [rbp+178h]; callerReturnAddress
0x1801660e8  mov     ebx, eax
0x1801660ea  test    eax, eax
0x1801660ec  jz      loc_180166185
0x1801660f2  mov     fCheckIAccessControl, eax; err
0x1801660f5  lea     r8, aOnecoreComComb_186; "onecore\\com\\combase\\ih\\RpcUtilities"...
0x1801660fc  mov     dwAuthnLevel, 7Ch ; '|'; lineNumber
0x180166101  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180166106  mov     rax, [rbp+170h+NetworkAddr]
0x18016610a  test    rax, rax
0x18016610d  jz      short loc_18016611D
0x18016610f  lea     hRpc, [rbp+170h+var_198]; String
0x180166113  mov     [rbp+170h+var_198], rax
0x180166117  call    cs:__imp_RpcStringFreeW
0x18016611d  mov     rax, [rsp+270h+Protseq]
0x180166122  test    rax, rax
0x180166125  jz      short loc_180166135
0x180166127  lea     hRpc, [rbp+170h+var_190]; String
0x18016612b  mov     [rbp+170h+var_190], rax
0x18016612f  call    cs:__imp_RpcStringFreeW
0x180166135  mov     rax, [rbp+170h+StringBinding]
0x180166139  test    rax, rax
0x18016613c  jz      short loc_18016614C
0x18016613e  lea     hRpc, [rbp+170h+var_188]; String
0x180166142  mov     [rbp+170h+var_188], rax
0x180166146  call    cs:__imp_RpcStringFreeW
0x18016614c  mov     rax, [rbp+170h+ServerBinding]
0x180166150  test    rax, rax
0x180166153  jz      short loc_180166163
0x180166155  mov     [rbp+170h+Binding], rax
0x180166159  lea     hRpc, [rbp+170h+Binding]; Binding
0x18016615d  call    cs:__imp_RpcBindingFree
0x180166163  mov     hRpc, [rbp+178h]; callerReturnAddress
0x18016616a  lea     r8, aOnecoreComComb_122; "onecore\\com\\combase\\common\\core\\ac"...
0x180166171  mov     fCheckIAccessControl, ebx; err
0x180166174  mov     dwAuthnLevel, 32h ; '2'; lineNumber
0x180166179  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18016617e  mov     edi, eax
0x180166180  jmp     loc_1801664EE
0x180166185  mov     rsi, [rbp+170h+NetworkAddr]
0x180166189  lea     r8, String1; "ncacn_hvsocket"
0x180166190  mov     rax, [rsp+270h+Protseq]
0x180166195  mov     rdx, rdi
0x180166198  mov     [rbp+170h+NetworkAddr], r13
0x18016619c  nop     dword ptr [rax+00h]
0x1801661a0  movzx   ebx, word ptr [r8+rdx*2+2]
0x1801661a6  movzx   ecx, word ptr [rax+rdx*2+2]
0x1801661ab  sub     ebx, ecx
0x1801661ad  jnz     short loc_1801661C6
0x1801661af  add     rdx, 2
0x1801661b3  cmp     rdx, 0Fh
0x1801661b7  jz      short loc_1801661C6
0x1801661b9  movzx   ebx, word ptr [r8+rdx*2]
0x1801661be  movzx   ecx, word ptr [rax+rdx*2]
0x1801661c2  sub     ebx, ecx
0x1801661c4  jz      short loc_1801661A0
0x1801661c6  test    rax, rax
0x1801661c9  jz      short loc_1801661D9
0x1801661cb  lea     hRpc, [rbp+170h+var_178]; String
0x1801661cf  mov     [rbp+170h+var_178], rax
0x1801661d3  call    cs:__imp_RpcStringFreeW
0x1801661d9  mov     rax, [rbp+170h+StringBinding]
0x1801661dd  test    rax, rax
0x1801661e0  jz      short loc_1801661F0
0x1801661e2  lea     hRpc, [rbp+170h+var_170]; String
0x1801661e6  mov     [rbp+170h+var_170], rax
0x1801661ea  call    cs:__imp_RpcStringFreeW
0x1801661f0  mov     rax, [rbp+170h+ServerBinding]
0x1801661f4  test    rax, rax
0x1801661f7  jz      short loc_180166207
0x1801661f9  lea     hRpc, [rbp+170h+var_168]; Binding
0x1801661fd  mov     [rbp+170h+var_168], rax
0x180166201  call    cs:__imp_RpcBindingFree
0x180166207  test    ebx, ebx
0x180166209  jnz     loc_1801664D4
0x18016620f  xorps   xmm0, xmm0
0x180166212  lea     rdx, [rbp+170h+Uuid]; Uuid
0x180166219  mov     hRpc, rsi; StringUuid
0x18016621c  movups  xmmword ptr [rbp+170h+Uuid.Data1], xmm0
0x180166223  call    cs:__imp_UuidFromStringW
0x180166229  test    eax, eax
0x18016622b  jz      short loc_180166266
0x18016622d  mov     hRpc, [rbp+178h]; callerReturnAddress
0x180166234  lea     r8, aOnecoreComComb_122; "onecore\\com\\combase\\common\\core\\ac"...
0x18016623b  mov     fCheckIAccessControl, eax; err
0x18016623e  mov     dwAuthnLevel, 37h ; '7'; lineNumber
0x180166243  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180166248  mov     edi, eax
0x18016624a  test    rsi, rsi
0x18016624d  jz      loc_1801664EA
0x180166253  lea     hRpc, [rbp+170h+var_160]; String
0x180166257  mov     [rbp+170h+var_160], rsi
0x18016625b  call    cs:__imp_RpcStringFreeW
0x180166261  jmp     loc_1801664EA
0x180166266  mov     locality, 10h; Size
0x18016626c  lea     rdx, HV_GUID_PARENT; Buf2
0x180166273  lea     hRpc, [rbp+170h+Uuid]; Buf1
0x18016627a  call    memcmp_0
0x18016627f  test    eax, eax
0x180166281  jnz     loc_1801664D4
0x180166287  movzx   eax, cs:?s_initialized@ActivateOnHost@@0U?$atomic@_N@std@@A._Storage._Value; std::atomic<bool> ActivateOnHost::s_initialized ...
0x18016628e  nop
0x18016628f  test    al, al
0x180166291  jnz     loc_1801664BE
0x180166297  lea     rax, [rsp+270h+CompareAddress]
0x18016629c  mov     [rsp+270h+pvData], r13d
0x1801662a1  mov     [rsp+270h+pcbData], rax; pcbData
0x1801662a6  lea     r8, aFirstbootexper; "FirstBootExperienceEnabled"
0x1801662ad  lea     rax, [rsp+270h+pvData]
0x1801662b2  mov     [rsp+270h+CompareAddress], 4
0x1801662ba  mov     [rsp+270h+format], rax; pvData
0x1801662bf  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Con"...
0x1801662c6  mov     fCheckIAccessControl, 10h; dwFlags
0x1801662cc  mov     qword ptr [rsp+270h+level], r13; pdwType
0x1801662d1  mov     hRpc, 0FFFFFFFF80000002h; hkey
0x1801662d8  call    cs:__imp_RegGetValueW
0x1801662de  test    eax, eax
0x1801662e0  jnz     short loc_1801662ED
0x1801662e2  cmp     [rsp+270h+pvData], r13d
0x1801662e7  jnz     loc_1801663E4
0x1801662ed  call    ?ShouldWaitForRestore@ContainerSynchronization@@CA_NXZ; ContainerSynchronization::ShouldWaitForRestore(void)
0x1801662f2  test    al, al
0x1801662f4  jz      loc_1801663E4
0x1801662fa  lea     rax, wistd____function____func__lambda_3d150f8d20dbfcb587a427312ad80f8f__void___cdecl_void_____vftable_
0x180166301  mov     [rsp+270h+pvData], r13d
0x180166306  mov     qword ptr [rbp+170h+subscriptionState.__buf_], rax
0x18016630a  lea     r9, [rsp+270h+CompareAddress]; callback
0x18016630f  lea     rax, [rsp+270h+pvData]
0x180166314  mov     qword ptr [rsp+270h+CompareAddress], r13
0x180166319  mov     qword ptr [rbp+170h+subscriptionState.__buf_+8], rax
0x180166320  lea     rdx, [rbp+170h+subscriptionState]; subscriptionState
0x180166324  lea     rax, [rbp+170h+subscriptionState.__buf_]
0x180166328  mov     [rbp+170h+subscriptionState.__f_], rax
0x18016632f  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x180166334  mov     hRpc, [rbp+170h+subscriptionState.__f_]
0x18016633b  test    eax, eax
0x18016633d  mov     rbx, r13
0x180166340  cmovns  rbx, qword ptr [rsp+270h+CompareAddress]
0x180166346  test    hRpc, hRpc
0x180166349  jz      short loc_180166357
0x18016634b  mov     rax, [hRpc]
0x18016634e  mov     rax, [rax+18h]
0x180166352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166357  test    rbx, rbx
0x18016635a  jnz     short loc_180166390
0x18016635c  mov     hRpc, [rbp+178h]; callerReturnAddress
0x180166363  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\common\\core\\co"...
0x18016636a  mov     edi, 8007000Eh
0x18016636f  mov     dwAuthnLevel, 3Dh ; '='; lineNumber
0x180166374  mov     fCheckIAccessControl, edi; hr
0x180166377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016637c  mov     dwAuthnLevel, 55h ; 'U'
0x180166381  jmp     loc_180166463
0x180166390  mov     eax, r13d
0x180166393  xchg    eax, [rsp+270h+pvData]
0x180166397  test    eax, eax
0x180166399  jnz     short loc_1801663D1
0x18016639b  mov     fCheckIAccessControl, 0FFFFFFFFh; dwMilliseconds
0x1801663a1  mov     [rsp+270h+CompareAddress], r13d
0x1801663a6  mov     locality, 4; AddressSize
0x1801663ac  lea     rdx, [rsp+270h+CompareAddress]; CompareAddress
0x1801663b1  lea     hRpc, [rsp+270h+pvData]; Address
0x1801663b6  call    cs:__imp_WaitOnAddress
0x1801663bc  test    eax, eax
0x1801663be  jnz     short loc_180166390
0x1801663c0  call    cs:__imp_GetLastError
0x1801663c6  cmp     eax, 5B4h
0x1801663cb  jnz     loc_180167294
0x1801663d1  mov     rax, [rbx]
0x1801663d4  mov     dwAuthnLevel, 1
0x1801663d9  mov     hRpc, rbx
0x1801663dc  mov     rax, [rax]
0x1801663df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801663e4  lea     rax, [rsp+270h+CompareAddress]
0x1801663e9  mov     [rsp+270h+var_200], r13d
0x1801663ee  mov     [rsp+270h+pcbData], rax; pcbData
0x1801663f3  lea     r8, aActivateonhost; "ActivateOnHostFlags"
0x1801663fa  lea     rax, [rsp+270h+var_200]
0x1801663ff  mov     [rsp+270h+CompareAddress], 4
0x180166407  mov     [rsp+270h+format], rax; pvData
0x18016640c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\OLE"
0x180166413  mov     fCheckIAccessControl, 10h; dwFlags
0x180166419  mov     qword ptr [rsp+270h+level], r13; pdwType
0x18016641e  mov     hRpc, 0FFFFFFFF80000002h; hkey
0x180166425  call    cs:__imp_RegGetValueW
0x18016642b  cmp     eax, 2
0x18016642e  jnz     short loc_180166439
0x180166430  mov     eax, r13d
  ... truncated ...
```
