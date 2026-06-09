# HnsListener::Start(std::function<void (_GUID const &,KryptonSchema::ContainerState)> &&,std::function<void (_GUID const &,std::vector<KryptonSchema::ContainerInterface,std::allocator<KryptonSchema::ContainerInterface>> const &)> &&,std::function<void (void)> &&)

- ea: `0x1801334d4`
- end: `0x180133634`
- name: `?Start@HnsListener@@AEAAX$$QEAV?$function@$$A6AXAEBU_GUID@@W4ContainerState@KryptonSchema@@@Z@std@@$$QEAV?$function@$$A6AXAEBU_GUID@@AEBV?$vector@UContainerInterface@KryptonSchema@@V?$allocator@UContainerInterface@KryptonSchema@@@std@@@std@@@Z@3@$$QEAV?$function@$$A6AXXZ@3@@Z`
- size: `352`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180082d0c`

## callees

- `0x180009990`
- `0x18000c160`
- `0x1800704dc`
- `0x18008c804`
- `0x180131c24`
- `0x180131cdc`
- `0x1801334d4`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801335db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013360c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801335db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013360c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180133621`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180133621`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18013358f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18013358f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HnsListener::Start(char *pv, char *a2, char *a3, __int64 a4)
{
  char *v8; // rcx
  char *v9; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v11; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v13[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( pv != a2 )
  {
    std::_Func_class<void,>::~_Func_class<void,>(pv);
    v8 = (char *)*((_QWORD *)a2 + 7);
    if ( v8 )
    {
      if ( v8 == a2 )
      {
        *((_QWORD *)pv + 7) = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v8 + 8LL))(v8, pv);
        std::_Func_class<void,>::~_Func_class<void,>(a2);
      }
      else
      {
        *((_QWORD *)pv + 7) = v8;
        *((_QWORD *)a2 + 7) = 0;
      }
    }
  }
  if ( pv + 64 != a3 )
  {
    std::_Func_class<void,>::~_Func_class<void,>(pv + 64);
    v9 = (char *)*((_QWORD *)a3 + 7);
    if ( v9 )
    {
      if ( v9 == a3 )
      {
        *((_QWORD *)pv + 15) = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v9 + 8LL))(v9, pv + 64);
        std::_Func_class<void,>::~_Func_class<void,>(a3);
      }
      else
      {
        *((_QWORD *)pv + 15) = v9;
        *((_QWORD *)a3 + 7) = 0;
      }
    }
  }
  std::function<void (void)>::operator=(pv + 128, a4);
  ThreadpoolTimer = CreateThreadpoolTimer(HnsListener::RetryConnectingHnsTimerCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    pv + 496,
    ThreadpoolTimer);
  v13[0] = pv;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, pv + 224);
  try
  {
    if ( pv[488] )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( *((_DWORD *)pv + 54) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__HnsListener::Start_::_3_::_lambda_1___(
          pv + 368,
          v13);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__HnsListener::Start_::_3_::_lambda_1___(
          pv + 448,
          v13);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      _InterlockedIncrement64((volatile signed __int64 *)pv + 44);
      SubmitThreadpoolWork(*((PTP_WORK *)pv + 43));
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnslistener.cpp",
      v11);
  }
}

```

## disassembly

```asm
0x1801334d4  push    rbx
0x1801334d6  push    rsi
0x1801334d7  push    rdi
0x1801334d8  push    r14
0x1801334da  sub     rsp, 38h
0x1801334de  mov     r14, r9
0x1801334e1  mov     rsi, r8
0x1801334e4  mov     rdi, rdx
0x1801334e7  mov     rbx, rcx
0x1801334ea  cmp     rcx, rdx
0x1801334ed  jz      short loc_18013352B
0x1801334ef  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1801334f4  mov     rcx, [rdi+38h]
0x1801334f8  test    rcx, rcx
0x1801334fb  jz      short loc_18013352B
0x1801334fd  cmp     rcx, rdi
0x180133500  jnz     short loc_18013351F
0x180133502  mov     rax, [rcx]
0x180133505  mov     rdx, rbx
0x180133508  mov     rax, [rax+8]
0x18013350c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133511  mov     [rbx+38h], rax
0x180133515  mov     rcx, rdi
0x180133518  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18013351d  jmp     short loc_18013352B
0x18013351f  mov     [rbx+38h], rcx
0x180133523  mov     qword ptr [rdi+38h], 0
0x18013352b  lea     rdi, [rbx+40h]
0x18013352f  cmp     rdi, rsi
0x180133532  jz      short loc_180133573
0x180133534  mov     rcx, rdi
0x180133537  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18013353c  mov     rcx, [rsi+38h]
0x180133540  test    rcx, rcx
0x180133543  jz      short loc_180133573
0x180133545  cmp     rcx, rsi
0x180133548  jnz     short loc_180133567
0x18013354a  mov     rax, [rcx]
0x18013354d  mov     rdx, rdi
0x180133550  mov     rax, [rax+8]
0x180133554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133559  mov     [rdi+38h], rax
0x18013355d  mov     rcx, rsi
0x180133560  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180133565  jmp     short loc_180133573
0x180133567  mov     [rdi+38h], rcx
0x18013356b  mov     qword ptr [rsi+38h], 0
0x180133573  lea     rcx, [rbx+80h]
0x18013357a  mov     rdx, r14
0x18013357d  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180133582  xor     r8d, r8d; pcbe
0x180133585  mov     rdx, rbx; pv
0x180133588  lea     rcx, ?RetryConnectingHnsTimerCallback@HnsListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18013358f  call    cs:__imp_CreateThreadpoolTimer
0x180133595  mov     rdx, rax
0x180133598  lea     rcx, [rbx+1F0h]
0x18013359f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801335a4  mov     [rsp+58h+var_30], rbx
0x1801335a9  mov     [rsp+58h+lpCriticalSection], 0
0x1801335b2  lea     rdx, [rbx+0E0h]
0x1801335b9  lea     rcx, [rsp+58h+lpCriticalSection]
0x1801335be  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801335c3  nop
0x1801335c4  lea     rcx, [rbx+170h]
0x1801335cb  cmp     byte ptr [rcx+78h], 0
0x1801335cf  jz      short loc_1801335E3
0x1801335d1  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1801335d6  test    rcx, rcx
0x1801335d9  jz      short loc_180133628
0x1801335db  call    cs:__imp_LeaveCriticalSection
0x1801335e1  jmp     short loc_180133628
0x1801335e3  lea     rdx, [rsp+58h+var_30]
0x1801335e8  cmp     dword ptr [rbx+0D8h], 1
0x1801335ef  jnz     short loc_1801335F8
0x1801335f1  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__HnsListener__Start____3____lambda_1___
0x1801335f6  jmp     short loc_180133602
0x1801335f8  add     rcx, 50h ; 'P'
0x1801335fc  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__HnsListener__Start____3____lambda_1___
0x180133601  nop
0x180133602  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180133607  test    rcx, rcx
0x18013360a  jz      short loc_180133612
0x18013360c  call    cs:__imp_LeaveCriticalSection
0x180133612  lock inc qword ptr [rbx+160h]
0x18013361a  mov     rcx, [rbx+158h]; pwk
0x180133621  call    cs:__imp_SubmitThreadpoolWork
0x180133627  nop
0x180133628  jmp     short $+2
0x18013362a  add     rsp, 38h
0x18013362e  pop     r14
0x180133630  pop     rdi
0x180133631  pop     rsi
0x180133632  pop     rbx
0x180133633  retn
```
