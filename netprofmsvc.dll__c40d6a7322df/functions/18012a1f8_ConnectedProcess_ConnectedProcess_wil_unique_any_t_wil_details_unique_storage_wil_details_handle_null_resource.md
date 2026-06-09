# ConnectedProcess::ConnectedProcess(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>)

- ea: `0x18012a1f8`
- end: `0x18012a30e`
- name: `??0ConnectedProcess@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@2@@Z`
- size: `278`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18012a080`

## callees

- `0x180035fec`
- `0x1800369d8`
- `0x18004fbe4`
- `0x180053988`
- `0x1800baf04`
- `0x18012a1f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18012a275`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18012a275`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18012a2ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18012a2ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18012a29e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18012a29e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18012a22d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18012a22d`
- `combase!__imp_CoAddRefSharedService` at `0x18012a2d9`
- `combase!__imp_CoAddRefSharedService` at `0x18012a2d9`

## string_xrefs

- `0x18012a2bf`: `onecore\net\netprofiles\service\src\common\connectionpointcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char *__fastcall ConnectedProcess::ConnectedProcess(char *pv, HANDLE *a2, __int64 *a3)
{
  __int64 v6; // rax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v8; // r9
  __int64 v9; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(pv, 0, 1, 1);
  *((_DWORD *)pv + 70) = GetProcessId(*a2);
  *((_QWORD *)pv + 36) = *a2;
  *a2 = 0;
  *((_QWORD *)pv + 37) = 0;
  v6 = *a3;
  *a3 = 0;
  *((_QWORD *)pv + 38) = v6;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(pv + 312), 0, 0);
  *((_QWORD *)pv + 44) = 0;
  *((_DWORD *)pv + 90) = 0;
  ThreadpoolWait = CreateThreadpoolWait(ConnectedProcess::ThreadpoolWaitCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    pv + 296,
    ThreadpoolWait);
  if ( !*((_QWORD *)pv + 37) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpointcontainer.cpp",
      v8);
  v9 = Microsoft::WRL::Details::OutOfProcModuleBase<NetworkProfileServiceModule>::Create(retaddr);
  CoAddRefSharedService(*(unsigned int *)(v9 + 24));
  SetThreadpoolWait(*((PTP_WAIT *)pv + 37), *((HANDLE *)pv + 36), 0);
  wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(a3);
  return pv;
}

```

## disassembly

```asm
0x18012a1f8  mov     rax, rsp
0x18012a1fb  mov     [rax+10h], rbx
0x18012a1ff  mov     [rax+20h], rsi
0x18012a203  mov     [rax+18h], r8
0x18012a207  mov     [rax+8], rcx
0x18012a20b  push    rdi
0x18012a20c  sub     rsp, 20h
0x18012a210  mov     rsi, r8
0x18012a213  mov     rbx, rdx
0x18012a216  mov     rdi, rcx
0x18012a219  mov     r8d, 1
0x18012a21f  mov     r9d, r8d
0x18012a222  xor     edx, edx
0x18012a224  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x18012a229  nop
0x18012a22a  mov     rcx, [rbx]; Process
0x18012a22d  call    cs:__imp_GetProcessId
0x18012a233  mov     [rdi+118h], eax
0x18012a239  mov     rax, [rbx]
0x18012a23c  mov     [rdi+120h], rax
0x18012a243  mov     qword ptr [rbx], 0
0x18012a24a  lea     rbx, [rdi+128h]
0x18012a251  mov     qword ptr [rbx], 0
0x18012a258  mov     rax, [rsi]
0x18012a25b  mov     qword ptr [rsi], 0
0x18012a262  mov     [rdi+130h], rax
0x18012a269  lea     rcx, [rdi+138h]; lpCriticalSection
0x18012a270  xor     r8d, r8d; Flags
0x18012a273  xor     edx, edx; dwSpinCount
0x18012a275  call    cs:__imp_InitializeCriticalSectionEx
0x18012a27b  nop
0x18012a27c  mov     qword ptr [rdi+160h], 0
0x18012a287  mov     dword ptr [rdi+168h], 0
0x18012a291  xor     r8d, r8d; pcbe
0x18012a294  mov     rdx, rdi; pv
0x18012a297  lea     rcx, ?ThreadpoolWaitCallback@ConnectedProcess@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18012a29e  call    cs:__imp_CreateThreadpoolWait
0x18012a2a4  mov     rdx, rax
0x18012a2a7  mov     rcx, rbx
0x18012a2aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18012a2af  cmp     qword ptr [rbx], 0
0x18012a2b3  setz    al
0x18012a2b6  mov     rcx, [rsp+28h]; this
0x18012a2bb  test    al, al
0x18012a2bd  jz      short loc_18012A2D1
0x18012a2bf  lea     r8, aOnecoreNetNetp_29; "onecore\\net\\netprofiles\\service\\src"...
0x18012a2c6  mov     edx, 11h; void *
0x18012a2cb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18012a2d1  call    ?Create@?$OutOfProcModuleBase@VNetworkProfileServiceModule@@@Details@WRL@Microsoft@@SAAEAVNetworkProfileServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NetworkProfileServiceModule>::Create(void)
0x18012a2d6  mov     ecx, [rax+18h]
0x18012a2d9  call    cs:__imp_CoAddRefSharedService
0x18012a2df  xor     r8d, r8d; pftTimeout
0x18012a2e2  mov     rdx, [rdi+120h]; h
0x18012a2e9  mov     rcx, [rbx]; pwa
0x18012a2ec  call    cs:__imp_SetThreadpoolWait
0x18012a2f2  nop
0x18012a2f3  mov     rcx, rsi
0x18012a2f6  call    ??1?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(void)
0x18012a2fb  mov     rax, rdi
0x18012a2fe  mov     rbx, [rsp+28h+arg_8]
0x18012a303  mov     rsi, [rsp+28h+arg_18]
0x18012a308  add     rsp, 20h
0x18012a30c  pop     rdi
0x18012a30d  retn
```
