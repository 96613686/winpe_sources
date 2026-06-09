# StartNetworkProfilesTelemetryRpc(void)

- ea: `0x18012146c`
- end: `0x18012170c`
- name: `?StartNetworkProfilesTelemetryRpc@@YAJXZ`
- size: `672`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800bba00`

## callees

- `0x180013748`
- `0x180048608`
- `0x18004faf4`
- `0x18005085c`
- `0x1800704dc`
- `0x1800a1724`
- `0x1800a88a0`
- `0x18012146c`
- `0x1801298a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012161e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012161e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801215e5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801215e5`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1801214e8`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1801214e8`
- `RPCRT4!RpcEpRegisterW` at `0x1801215b4`
- `RPCRT4!RpcEpRegisterW` at `0x1801215b4`
- `RPCRT4!RpcServerInqBindings` at `0x180121588`
- `RPCRT4!RpcServerInqBindings` at `0x180121588`
- `RPCRT4!RpcServerRegisterIf3` at `0x180121564`
- `RPCRT4!RpcServerRegisterIf3` at `0x180121564`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180121517`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180121517`
- `RPCRT4!RpcServerUseProtseqW` at `0x1801214a7`
- `RPCRT4!RpcServerUseProtseqW` at `0x1801214a7`

## string_xrefs

- `0x180121692`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`
- `0x1801216a7`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`
- `0x1801216bc`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`
- `0x1801216d0`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`
- `0x1801216e5`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`
- `0x1801216f9`: `onecore\net\netprofiles\service\src\telemetryrpc\lib\telemetryrpc.cpp`

## pseudocode

```c
__int64 __fastcall StartNetworkProfilesTelemetryRpc(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v8; // rcx
  const char *v9; // r9
  __int64 result; // rax
  unsigned int v11; // [rsp+20h] [rbp-68h]
  RPC_WSTR *p_ServerPrincName; // [rsp+40h] [rbp-48h] BYREF
  RPC_WSTR PrincName; // [rsp+48h] [rbp-40h] BYREF
  char v14; // [rsp+50h] [rbp-38h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+58h] [rbp-30h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+60h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)dword_1801BD288 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      byte_18019800B);
  v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  try
  {
    if ( v1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v1,
        v11);
    ServerPrincName = 0;
    p_ServerPrincName = &ServerPrincName;
    PrincName = 0;
    v14 = 1;
    v2 = RpcServerInqDefaultPrincNameW(0xAu, &PrincName);
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v2,
        v11);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_ServerPrincName);
    v3 = RpcServerRegisterAuthInfoW(ServerPrincName, 0xAu, 0, 0);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v3,
        v11);
    v4 = RpcServerRegisterIf3(qword_1801548E0, 0, 0, 41);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v4,
        0x4D2u);
    BindingVector = 0;
    v5 = RpcServerInqBindings(&BindingVector);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v5,
        0x4D2u);
    v6 = RpcEpRegisterW(qword_1801548E0, BindingVector, 0, (RPC_WSTR)L"NetworkProfiles Telemetry RPC Interface");
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
        (const char *)v6,
        0x4D2u);
    TlgRegisterAggregateProviderEx(&dword_1801BDDA0);
    ThreadpoolTimer = CreateThreadpoolTimer(PeriodicTimerCallback, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &g_periodicTimer,
      ThreadpoolTimer);
    pftDueTime = (struct _FILETIME)-108000000000LL;
    SetThreadpoolTimer(g_periodicTimer, &pftDueTime, 0xA4CB80u, 0);
    if ( !g_periodicTimer && (unsigned int)dword_1801BD288 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v8,
        qword_180197EB0);
    if ( (unsigned int)dword_1801BD288 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v8,
        byte_180197F03);
    wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(&BindingVector);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ServerPrincName);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6F,
                           (unsigned int)"onecore\\net\\netprofiles\\service\\src\\telemetryrpc\\lib\\telemetryrpc.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18012146c  sub     rsp, 88h
0x180121473  mov     rax, cs:__security_cookie
0x18012147a  xor     rax, rsp
0x18012147d  mov     [rsp+88h+var_18], rax
0x180121482  mov     eax, cs:dword_1801BD288
0x180121488  cmp     eax, 5
0x18012148b  jbe     short loc_180121499
0x18012148d  lea     rdx, byte_18019800B
0x180121494  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180121499  xor     r8d, r8d; SecurityDescriptor
0x18012149c  lea     edx, [r8+0Ah]; MaxCalls
0x1801214a0  mov     rcx, cs:off_18014BD30; Protseq
0x1801214a7  call    cs:__imp_RpcServerUseProtseqW
0x1801214ad  mov     rcx, [rsp+88h]; this
0x1801214b5  test    eax, eax
0x1801214b7  jnz     loc_18012168F
0x1801214bd  mov     [rsp+88h+ServerPrincName], 0
0x1801214c6  lea     rax, [rsp+88h+ServerPrincName]
0x1801214cb  mov     [rsp+88h+var_48], rax
0x1801214d0  mov     [rsp+88h+PrincName], 0
0x1801214d9  mov     [rsp+88h+var_38], 1
0x1801214de  lea     rdx, [rsp+88h+PrincName]; PrincName
0x1801214e3  mov     ecx, 0Ah; AuthnSvc
0x1801214e8  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x1801214ee  mov     rcx, [rsp+88h]; this
0x1801214f6  test    eax, eax
0x1801214f8  jnz     loc_1801216A4
0x1801214fe  lea     rcx, [rsp+88h+var_48]
0x180121503  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180121508  xor     r9d, r9d; Arg
0x18012150b  xor     r8d, r8d; GetKeyFn
0x18012150e  lea     edx, [r9+0Ah]; AuthnSvc
0x180121512  mov     rcx, [rsp+88h+ServerPrincName]; ServerPrincName
0x180121517  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18012151d  mov     rcx, [rsp+88h]; this
0x180121525  test    eax, eax
0x180121527  jnz     loc_1801216B9
0x18012152d  mov     [rsp+88h+var_50], 0
0x180121536  lea     rax, ?TelemetryRpcSecurityCallBack@@YAJPEAX0@Z; TelemetryRpcSecurityCallBack(void *,void *)
0x18012153d  mov     [rsp+88h+var_58], rax
0x180121542  mov     [rsp+88h+var_60], 0
0x18012154a  mov     [rsp+88h+var_68], 4D2h; unsigned int
0x180121552  mov     r9d, 29h ; ')'
0x180121558  xor     r8d, r8d
0x18012155b  xor     edx, edx
0x18012155d  mov     rcx, cs:IfSpec
0x180121564  call    cs:__imp_RpcServerRegisterIf3
0x18012156a  mov     rcx, [rsp+88h]; this
0x180121572  test    eax, eax
0x180121574  jnz     loc_1801216CD
0x18012157a  mov     [rsp+88h+BindingVector], 0
0x180121583  lea     rcx, [rsp+88h+BindingVector]; BindingVector
0x180121588  call    cs:__imp_RpcServerInqBindings
0x18012158e  mov     rcx, [rsp+88h]; this
0x180121596  test    eax, eax
0x180121598  jnz     loc_1801216E2
0x18012159e  lea     r9, aNetworkprofile_0; "NetworkProfiles Telemetry RPC Interface"
0x1801215a5  xor     r8d, r8d; UuidVector
0x1801215a8  mov     rdx, [rsp+88h+BindingVector]; BindingVector
0x1801215ad  lea     rcx, qword_1801548E0; IfSpec
0x1801215b4  call    cs:__imp_RpcEpRegisterW
0x1801215ba  mov     rcx, [rsp+88h]; this
0x1801215c2  test    eax, eax
0x1801215c4  jnz     loc_1801216F6
0x1801215ca  xor     r9d, r9d
0x1801215cd  lea     rcx, dword_1801BDDA0; CallbackContext
0x1801215d4  call    TlgRegisterAggregateProviderEx
0x1801215d9  xor     r8d, r8d; pcbe
0x1801215dc  xor     edx, edx; pv
0x1801215de  lea     rcx, ?PeriodicTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801215e5  call    cs:__imp_CreateThreadpoolTimer
0x1801215eb  mov     rdx, rax
0x1801215ee  lea     rcx, ?g_periodicTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> g_periodicTimer
0x1801215f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801215fa  mov     rax, 0FFFFFFE6DAB2C800h
0x180121604  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], rax
0x180121609  xor     r9d, r9d; msWindowLength
0x18012160c  mov     r8d, 0A4CB80h; msPeriod
0x180121612  lea     rdx, [rsp+88h+pftDueTime]; pftDueTime
0x180121617  mov     rcx, cs:?g_periodicTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18012161e  call    cs:__imp_SetThreadpoolTimer
0x180121624  cmp     cs:?g_periodicTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> g_periodicTimer
0x18012162c  jnz     short loc_180121645
0x18012162e  mov     eax, cs:dword_1801BD288
0x180121634  cmp     eax, 5
0x180121637  jbe     short loc_180121645
0x180121639  lea     rdx, qword_180197EB0
0x180121640  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180121645  mov     eax, cs:dword_1801BD288
0x18012164b  cmp     eax, 5
0x18012164e  jbe     short loc_18012165D
0x180121650  lea     rdx, byte_180197F03
0x180121657  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18012165c  nop
0x18012165d  lea     rcx, [rsp+88h+BindingVector]
0x180121662  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x180121667  nop
0x180121668  lea     rcx, [rsp+88h+ServerPrincName]
0x18012166d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180121672  xor     eax, eax
0x180121674  jmp     short loc_18012167A
0x180121676  mov     eax, dword ptr [rsp+88h+BindingVector]
0x18012167a  mov     rcx, [rsp+88h+var_18]
0x18012167f  xor     rcx, rsp; StackCookie
0x180121682  call    __security_check_cookie
0x180121687  add     rsp, 88h
0x18012168e  retn
0x18012168f  mov     r9d, eax; char *
0x180121692  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x180121699  mov     edx, 45h ; 'E'; void *
0x18012169e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801216a4  mov     r9d, eax; char *
0x1801216a7  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x1801216ae  mov     edx, 49h ; 'I'; void *
0x1801216b3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801216b9  mov     r9d, eax; char *
0x1801216bc  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x1801216c3  mov     edx, 4Ah ; 'J'; void *
0x1801216c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801216cd  mov     r9d, eax; char *
0x1801216d0  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x1801216d7  mov     edx, 56h ; 'V'; void *
0x1801216dc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801216e2  mov     r9d, eax; char *
0x1801216e5  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x1801216ec  mov     edx, 59h ; 'Y'; void *
0x1801216f1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801216f6  mov     r9d, eax; char *
0x1801216f9  lea     r8, aOnecoreNetNetp_46; "onecore\\net\\netprofiles\\service\\src"...
0x180121700  mov     edx, 5Dh ; ']'; void *
0x180121705  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
