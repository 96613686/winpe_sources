# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180022710`
- end: `0x180022888`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `376`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002f810`

## callees

- `0x180022710`
- `0x1800263b0`
- `0x180029820`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022745`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022745`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002275b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002275b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022798`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022766`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002281c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002283d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002281c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002283d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002280e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002282f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002280e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002282f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022857`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022857`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022787`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022865`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022787`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022865`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022790`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002286e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022790`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002286e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 16,
    0);
  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( this != (wil::details::EnabledStateManager *)-8LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_17;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_17;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_17:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x180022710  mov     [rsp+arg_8], rbx
0x180022715  mov     [rsp+arg_10], rbp
0x18002271a  push    rsi
0x18002271b  push    rdi
0x18002271c  push    r14
0x18002271e  sub     rsp, 20h
0x180022722  mov     rdi, rcx
0x180022725  xor     ebp, ebp
0x180022727  mov     [rcx], ebp
0x180022729  xor     edx, edx
0x18002272b  add     rcx, 10h
0x18002272f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180022734  mov     [rdi], ebp
0x180022736  mov     rsi, [rdi+10h]
0x18002273a  mov     [rdi+10h], rbp
0x18002273e  lea     rbx, [rdi+8]
0x180022742  mov     rcx, rbx; SRWLock
0x180022745  call    cs:__imp_AcquireSRWLockExclusive
0x18002274b  mov     rcx, rdi
0x18002274e  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180022753  test    rbx, rbx
0x180022756  jz      short loc_180022761
0x180022758  mov     rcx, rbx; SRWLock
0x18002275b  call    cs:__imp_ReleaseSRWLockExclusive
0x180022761  test    rsi, rsi
0x180022764  jz      short loc_18002279E
0x180022766  call    cs:__imp_GetLastError
0x18002276c  mov     ebx, eax
0x18002276e  xor     r9d, r9d; msWindowLength
0x180022771  xor     r8d, r8d; msPeriod
0x180022774  xor     edx, edx; pftDueTime
0x180022776  mov     rcx, rsi; pti
0x180022779  call    cs:__imp_SetThreadpoolTimer
0x18002277f  mov     edx, 1; fCancelPendingCallbacks
0x180022784  mov     rcx, rsi; pti
0x180022787  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002278d  mov     rcx, rsi; pti
0x180022790  call    cs:__imp_CloseThreadpoolTimer
0x180022796  mov     ecx, ebx; dwErrCode
0x180022798  call    cs:__imp_SetLastError
0x18002279e  mov     rcx, [rdi+68h]
0x1800227a2  test    rcx, rcx
0x1800227a5  jz      short loc_1800227D7
0x1800227a7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800227ae  test    rax, rax
0x1800227b1  jnz     short loc_1800227C2
0x1800227b3  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800227ba  test    rdx, rdx
0x1800227bd  jz      short loc_1800227D5
0x1800227bf  mov     rax, rdx
0x1800227c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227c7  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800227ce  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800227d5  jmp     short loc_1800227E5
0x1800227d7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800227de  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800227e5  mov     rcx, [rdi+60h]
0x1800227e9  test    rcx, rcx
0x1800227ec  jz      short loc_180022801
0x1800227ee  test    rax, rax
0x1800227f1  jnz     short loc_1800227FB
0x1800227f3  test    rdx, rdx
0x1800227f6  jz      short loc_180022801
0x1800227f8  mov     rax, rdx
0x1800227fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022800  nop
0x180022801  mov     rbx, [rdi+58h]
0x180022805  mov     [rdi+58h], rbp
0x180022809  test    rbx, rbx
0x18002280c  jz      short loc_180022822
0x18002280e  call    cs:__imp_GetProcessHeap
0x180022814  mov     rcx, rax; hHeap
0x180022817  mov     r8, rbx; lpMem
0x18002281a  xor     edx, edx; dwFlags
0x18002281c  call    cs:__imp_HeapFree
0x180022822  mov     rbx, [rdi+38h]
0x180022826  mov     [rdi+38h], rbp
0x18002282a  test    rbx, rbx
0x18002282d  jz      short loc_180022843
0x18002282f  call    cs:__imp_GetProcessHeap
0x180022835  mov     rcx, rax; hHeap
0x180022838  mov     r8, rbx; lpMem
0x18002283b  xor     edx, edx; dwFlags
0x18002283d  call    cs:__imp_HeapFree
0x180022843  mov     rbx, [rdi+10h]
0x180022847  test    rbx, rbx
0x18002284a  jz      short loc_180022875
0x18002284c  xor     r9d, r9d; msWindowLength
0x18002284f  xor     r8d, r8d; msPeriod
0x180022852  xor     edx, edx; pftDueTime
0x180022854  mov     rcx, rbx; pti
0x180022857  call    cs:__imp_SetThreadpoolTimer
0x18002285d  mov     edx, 1; fCancelPendingCallbacks
0x180022862  mov     rcx, rbx; pti
0x180022865  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002286b  mov     rcx, rbx; pti
0x18002286e  call    cs:__imp_CloseThreadpoolTimer
0x180022874  nop
0x180022875  mov     rbx, [rsp+38h+arg_8]
0x18002287a  mov     rbp, [rsp+38h+arg_10]
0x18002287f  add     rsp, 20h
0x180022883  pop     r14
0x180022885  pop     rdi
0x180022886  pop     rsi
0x180022887  retn
```
