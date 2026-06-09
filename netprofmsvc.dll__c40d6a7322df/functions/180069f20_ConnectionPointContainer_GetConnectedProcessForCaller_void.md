# ConnectionPointContainer::GetConnectedProcessForCaller(void)

- ea: `0x180069f20`
- end: `0x18006a115`
- name: `?GetConnectedProcessForCaller@ConnectionPointContainer@@QEAA?AV?$shared_ptr@VConnectedProcess@@@std@@XZ`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006a620`

## callees

- `0x180009990`
- `0x18000eab0`
- `0x180015608`
- `0x1800327c0`
- `0x180037100`
- `0x180047010`
- `0x180049cb0`
- `0x18004bda0`
- `0x18004c958`
- `0x180069f20`
- `0x1800a88a0`
- `0x18012a080`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a0ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a0ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069fba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069fba`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180069fd0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180069fd0`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180069f69`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180069f69`

## string_xrefs

- `0x18006a0ee`: `onecore\net\netprofiles\service\src\common\connectionpointcontainer.cpp`
- `0x18006a103`: `onecore\net\netprofiles\service\src\common\connectionpointcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ConnectionPointContainer::GetConnectedProcessForCaller(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, __int64, HANDLE *); // rbx
  int v7; // eax
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // r15d
  int v10; // ecx
  __int64 v11; // rbx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v18; // [rsp+20h] [rbp-60h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-40h] BYREF
  DWORD v21; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Process; // [rsp+58h] [rbp-28h] BYREF
  void *ppInterface; // [rsp+60h] [rbp-20h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v20[0] = a2;
  Process = 0;
  ppInterface = 0;
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  if ( v4 == -2147417833 )
  {
    CurrentProcess = GetCurrentProcess();
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &Process,
      CurrentProcess);
  }
  else
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpointcontainer.cpp",
        (const char *)(unsigned int)v4,
        v18);
    v5 = ppInterface;
    v6 = *(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &Process,
      0);
    v7 = v6(v5, 1052672, &Process);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpointcontainer.cpp",
        (const char *)(unsigned int)v7,
        v18);
  }
  ProcessId = GetProcessId(Process);
  v21 = ProcessId;
  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, a1 + 40);
  v11 = std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<ConnectedProcess>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>,0>>::_Find<unsigned long>(
          a1 + 104,
          &v21);
  if ( v11 == *(_QWORD *)(a1 + 104) )
  {
    v24 = 0;
    v20[0] = a1;
    std::make_shared<ConnectedProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,ConnectionPointContainer *>(
      &v24,
      &Process,
      v20);
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<ConnectedProcess>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>,0>>::_Emplace<unsigned long const &,std::shared_ptr<ConnectedProcess> &>(
      a1 + 104,
      v20,
      &v21,
      &v24);
    if ( (unsigned int)dword_1801BD288 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)word_18019996A,
        v15,
        v16,
        (__int64)&v21);
    *(_OWORD *)a2 = v24;
  }
  else
  {
    if ( (unsigned int)dword_1801BD288 > 5 )
    {
      v21 = ProcessId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_18019999B,
        v12,
        v13,
        (__int64)&v21);
    }
    std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
      a2,
      (_QWORD *)(v11 + 40));
  }
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&ppInterface);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return a2;
}

```

## disassembly

```asm
0x180069f20  mov     [rsp-28h+arg_10], rbx
0x180069f25  push    rbp
0x180069f26  push    rsi
0x180069f27  push    rdi
0x180069f28  push    r14
0x180069f2a  push    r15
0x180069f2c  mov     rbp, rsp
0x180069f2f  sub     rsp, 80h
0x180069f36  mov     rax, cs:__security_cookie
0x180069f3d  xor     rax, rsp
0x180069f40  mov     [rbp+var_8], rax
0x180069f44  mov     rsi, rdx
0x180069f47  mov     r14, rcx
0x180069f4a  mov     [rbp+var_40], rdx
0x180069f4e  mov     [rbp+Process], 0
0x180069f56  mov     [rbp+ppInterface], 0
0x180069f5e  lea     rdx, [rbp+ppInterface]; ppInterface
0x180069f62  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180069f69  call    cs:__imp_CoGetCallContext
0x180069f6f  cmp     eax, 80010117h
0x180069f74  jz      short loc_180069FBA
0x180069f76  mov     rcx, [rbp+28h]; this
0x180069f7a  test    eax, eax
0x180069f7c  js      loc_18006A0EB
0x180069f82  mov     rdi, [rbp+ppInterface]
0x180069f86  mov     rax, [rdi]
0x180069f89  mov     rbx, [rax+18h]
0x180069f8d  xor     edx, edx
0x180069f8f  lea     rcx, [rbp+Process]
0x180069f93  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180069f98  lea     r8, [rbp+Process]
0x180069f9c  mov     edx, 101000h
0x180069fa1  mov     rcx, rdi
0x180069fa4  mov     rax, rbx
0x180069fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069fac  mov     rcx, [rbp+28h]; this
0x180069fb0  test    eax, eax
0x180069fb2  js      loc_18006A100
0x180069fb8  jmp     short loc_180069FCC
0x180069fba  call    cs:__imp_GetCurrentProcess
0x180069fc0  mov     rdx, rax
0x180069fc3  lea     rcx, [rbp+Process]
0x180069fc7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180069fcc  mov     rcx, [rbp+Process]; Process
0x180069fd0  call    cs:__imp_GetProcessId
0x180069fd6  mov     r15d, eax
0x180069fd9  mov     [rbp+var_30], eax
0x180069fdc  mov     [rbp+lpCriticalSection], 0
0x180069fe4  lea     rdx, [r14+28h]
0x180069fe8  lea     rcx, [rbp+lpCriticalSection]
0x180069fec  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180069ff1  nop
0x180069ff2  lea     rdi, [r14+68h]
0x180069ff6  lea     rdx, [rbp+var_30]
0x180069ffa  mov     rcx, rdi
0x180069ffd  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VConnectedProcess@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<ConnectedProcess>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>>,0>>::_Find<ulong>(ulong const &)
0x18006a002  mov     rbx, rax
0x18006a005  cmp     rax, [rdi]
0x18006a008  jz      short loc_18006A03C
0x18006a00a  mov     eax, cs:dword_1801BD288
0x18006a010  cmp     eax, 5
0x18006a013  jbe     short loc_18006A02E
0x18006a015  mov     [rbp+var_30], r15d
0x18006a019  lea     rax, [rbp+var_30]
0x18006a01d  mov     qword ptr [rsp+80h+var_60], rax
0x18006a022  lea     rdx, byte_18019999B
0x18006a029  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006a02e  lea     rdx, [rbx+28h]
0x18006a032  mov     rcx, rsi
0x18006a035  call    ??$?0V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::vector<KryptonSchema::Wlan::WlanInterfaceInfo>>> const &)
0x18006a03a  jmp     short loc_18006A0A2
0x18006a03c  xorps   xmm0, xmm0
0x18006a03f  movups  [rbp+var_18], xmm0
0x18006a043  mov     [rbp+var_40], r14
0x18006a047  lea     r8, [rbp+var_40]
0x18006a04b  lea     rdx, [rbp+Process]
0x18006a04f  lea     rcx, [rbp+var_18]
0x18006a053  call    ??$make_shared@VConnectedProcess@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAVConnectionPointContainer@@@std@@YA?AV?$shared_ptr@VConnectedProcess@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAPEAVConnectionPointContainer@@@Z; std::make_shared<ConnectedProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ConnectionPointContainer *>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ConnectionPointContainer * &&)
0x18006a058  nop
0x18006a059  lea     r9, [rbp+var_18]
0x18006a05d  lea     r8, [rbp+var_30]
0x18006a061  lea     rdx, [rbp+var_40]
0x18006a065  mov     rcx, rdi
0x18006a068  call    ??$_Emplace@AEBKAEAV?$shared_ptr@VConnectedProcess@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VConnectedProcess@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@PEAX@std@@_N@1@AEBKAEAV?$shared_ptr@VConnectedProcess@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<ConnectedProcess>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>>,0>>::_Emplace<ulong const &,std::shared_ptr<ConnectedProcess> &>(ulong const &,std::shared_ptr<ConnectedProcess> &)
0x18006a06d  mov     eax, cs:dword_1801BD288
0x18006a073  cmp     eax, 4
0x18006a076  jbe     short loc_18006A093
0x18006a078  mov     eax, [rbp+var_30]
0x18006a07b  mov     [rbp+var_30], eax
0x18006a07e  lea     rax, [rbp+var_30]
0x18006a082  mov     qword ptr [rsp+80h+var_60], rax
0x18006a087  lea     rdx, word_18019996A
0x18006a08e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006a093  mov     rax, qword ptr [rbp+var_18]
0x18006a097  mov     [rsi], rax
0x18006a09a  mov     rax, qword ptr [rbp+var_18+8]
0x18006a09e  mov     [rsi+8], rax
0x18006a0a2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18006a0a6  test    rcx, rcx
0x18006a0a9  jz      short loc_18006A0B2
0x18006a0ab  call    cs:__imp_LeaveCriticalSection
0x18006a0b1  nop
0x18006a0b2  lea     rcx, [rbp+ppInterface]
0x18006a0b6  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18006a0bb  nop
0x18006a0bc  lea     rcx, [rbp+Process]
0x18006a0c0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006a0c5  mov     rax, rsi
0x18006a0c8  mov     rcx, [rbp+var_8]
0x18006a0cc  xor     rcx, rsp; StackCookie
0x18006a0cf  call    __security_check_cookie
0x18006a0d4  mov     rbx, [rsp+80h+arg_10]
0x18006a0dc  add     rsp, 80h
0x18006a0e3  pop     r15
0x18006a0e5  pop     r14
0x18006a0e7  pop     rdi
0x18006a0e8  pop     rsi
0x18006a0e9  pop     rbp
0x18006a0ea  retn
0x18006a0eb  mov     r9d, eax; char *
0x18006a0ee  lea     r8, aOnecoreNetNetp_29; "onecore\\net\\netprofiles\\service\\src"...
0x18006a0f5  mov     edx, 9Bh; void *
0x18006a0fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a100  mov     r9d, eax; char *
0x18006a103  lea     r8, aOnecoreNetNetp_29; "onecore\\net\\netprofiles\\service\\src"...
0x18006a10a  mov     edx, 9Ch; void *
0x18006a10f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
