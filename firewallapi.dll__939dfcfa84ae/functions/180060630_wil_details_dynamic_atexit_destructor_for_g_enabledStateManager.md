# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x180060630`
- end: `0x180060817`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b168`
- `0x180060630`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060679`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800606c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800606c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800606f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060728`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800606f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006073c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006073c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180060692`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800607c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180060692`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800607c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800606b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800607eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800606b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800607eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800606a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800607dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800606a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800607dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__()
{
  struct _TP_TIMER *v0; // rdi
  DWORD LastError; // ebx
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // rbx
  HANDLE v5; // rax
  void (*v6)(void); // rax
  __int64 v7; // rdx
  struct _TP_TIMER *v8; // rbx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
    return;
  }
  wil::details::g_enabledStateManager = 0;
  v0 = pti;
  if ( pti )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
    SetLastError(LastError);
  }
  pti = 0;
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  v2 = lpMem;
  lpMem = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = qword_18009BD20;
  qword_18009BD20 = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  if ( !qword_18009BD00 )
  {
    v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_17;
  }
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_17;
    v6 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v6();
  v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_17:
  if ( !qword_18009BCF8 )
    goto LABEL_22;
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_22;
    v6 = (void (*)(void))v7;
  }
  v6();
LABEL_22:
  v8 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
}

```

## disassembly

```asm
0x180060630  mov     [rsp+arg_0], rbx
0x180060635  mov     [rsp+arg_8], rsi
0x18006063a  push    rdi
0x18006063b  sub     rsp, 20h
0x18006063f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180060646  jnz     loc_1800607F9
0x18006064c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180060653  test    rax, rax
0x180060656  jz      short loc_180060665
0x180060658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006065d  test    al, al
0x18006065f  jnz     loc_1800607F9
0x180060665  xor     esi, esi
0x180060667  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, esi; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18006066d  mov     rdi, cs:pti
0x180060674  test    rdi, rdi
0x180060677  jz      short loc_1800606CF
0x180060679  call    cs:__imp_GetLastError
0x180060680  nop     dword ptr [rax+rax+00h]
0x180060685  mov     ebx, eax
0x180060687  xor     r9d, r9d; msWindowLength
0x18006068a  xor     r8d, r8d; msPeriod
0x18006068d  xor     edx, edx; pftDueTime
0x18006068f  mov     rcx, rdi; pti
0x180060692  call    cs:__imp_SetThreadpoolTimer
0x180060699  nop     dword ptr [rax+rax+00h]
0x18006069e  mov     edx, 1; fCancelPendingCallbacks
0x1800606a3  mov     rcx, rdi; pti
0x1800606a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800606ad  nop     dword ptr [rax+rax+00h]
0x1800606b2  mov     rcx, rdi; pti
0x1800606b5  call    cs:__imp_CloseThreadpoolTimer
0x1800606bc  nop     dword ptr [rax+rax+00h]
0x1800606c1  mov     ecx, ebx; dwErrCode
0x1800606c3  call    cs:__imp_SetLastError
0x1800606ca  nop     dword ptr [rax+rax+00h]
0x1800606cf  mov     cs:pti, rsi
0x1800606d6  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800606dd  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800606e2  mov     rbx, cs:lpMem
0x1800606e9  mov     cs:lpMem, rsi
0x1800606f0  test    rbx, rbx
0x1800606f3  jz      short loc_180060715
0x1800606f5  call    cs:__imp_GetProcessHeap
0x1800606fc  nop     dword ptr [rax+rax+00h]
0x180060701  mov     rcx, rax; hHeap
0x180060704  mov     r8, rbx; lpMem
0x180060707  xor     edx, edx; dwFlags
0x180060709  call    cs:__imp_HeapFree
0x180060710  nop     dword ptr [rax+rax+00h]
0x180060715  mov     rbx, cs:qword_18009BD20
0x18006071c  mov     cs:qword_18009BD20, rsi
0x180060723  test    rbx, rbx
0x180060726  jz      short loc_180060748
0x180060728  call    cs:__imp_GetProcessHeap
0x18006072f  nop     dword ptr [rax+rax+00h]
0x180060734  mov     rcx, rax; hHeap
0x180060737  mov     r8, rbx; lpMem
0x18006073a  xor     edx, edx; dwFlags
0x18006073c  call    cs:__imp_HeapFree
0x180060743  nop     dword ptr [rax+rax+00h]
0x180060748  mov     rcx, cs:qword_18009BD00
0x18006074f  test    rcx, rcx
0x180060752  jz      short loc_180060784
0x180060754  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006075b  test    rax, rax
0x18006075e  jnz     short loc_18006076F
0x180060760  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180060767  test    rdx, rdx
0x18006076a  jz      short loc_180060782
0x18006076c  mov     rax, rdx
0x18006076f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060774  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006077b  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180060782  jmp     short loc_180060792
0x180060784  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006078b  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180060792  mov     rcx, cs:qword_18009BCF8
0x180060799  test    rcx, rcx
0x18006079c  jz      short loc_1800607B1
0x18006079e  test    rax, rax
0x1800607a1  jnz     short loc_1800607AB
0x1800607a3  test    rdx, rdx
0x1800607a6  jz      short loc_1800607B1
0x1800607a8  mov     rax, rdx
0x1800607ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607b0  nop
0x1800607b1  mov     rbx, cs:pti
0x1800607b8  test    rbx, rbx
0x1800607bb  jz      short loc_180060806
0x1800607bd  xor     r9d, r9d; msWindowLength
0x1800607c0  xor     r8d, r8d; msPeriod
0x1800607c3  xor     edx, edx; pftDueTime
0x1800607c5  mov     rcx, rbx; pti
0x1800607c8  call    cs:__imp_SetThreadpoolTimer
0x1800607cf  nop     dword ptr [rax+rax+00h]
0x1800607d4  mov     edx, 1; fCancelPendingCallbacks
0x1800607d9  mov     rcx, rbx; pti
0x1800607dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800607e3  nop     dword ptr [rax+rax+00h]
0x1800607e8  mov     rcx, rbx; pti
0x1800607eb  call    cs:__imp_CloseThreadpoolTimer
0x1800607f2  nop     dword ptr [rax+rax+00h]
0x1800607f7  jmp     short loc_180060806
0x1800607f9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180060800  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180060805  nop
0x180060806  mov     rbx, [rsp+28h+arg_0]
0x18006080b  mov     rsi, [rsp+28h+arg_8]
0x180060810  add     rsp, 20h
0x180060814  pop     rdi
0x180060815  retn
```
