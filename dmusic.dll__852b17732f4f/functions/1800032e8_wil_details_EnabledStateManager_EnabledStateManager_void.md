# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800032e8`
- end: `0x180003440`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021cf0`

## callees

- `0x1800032e8`
- `0x1800060e0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003309`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000333b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000333b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000331c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003412`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000331c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003412`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003333`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003429`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003333`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003429`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000332a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003420`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000332a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003420`

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
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
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
0x1800032e8  mov     [rsp+arg_0], rbx
0x1800032ed  mov     [rsp+arg_8], rsi
0x1800032f2  push    rdi
0x1800032f3  sub     rsp, 20h
0x1800032f7  mov     rdi, rcx
0x1800032fa  mov     dword ptr [rcx], 0
0x180003300  mov     rsi, [rcx+10h]
0x180003304  test    rsi, rsi
0x180003307  jz      short loc_180003341
0x180003309  call    cs:__imp_GetLastError
0x18000330f  mov     ebx, eax
0x180003311  xor     r9d, r9d; msWindowLength
0x180003314  xor     r8d, r8d; msPeriod
0x180003317  xor     edx, edx; pftDueTime
0x180003319  mov     rcx, rsi; pti
0x18000331c  call    cs:__imp_SetThreadpoolTimer
0x180003322  mov     edx, 1; fCancelPendingCallbacks
0x180003327  mov     rcx, rsi; pti
0x18000332a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003330  mov     rcx, rsi; pti
0x180003333  call    cs:__imp_CloseThreadpoolTimer
0x180003339  mov     ecx, ebx; dwErrCode
0x18000333b  call    cs:__imp_SetLastError
0x180003341  mov     qword ptr [rdi+10h], 0
0x180003349  mov     rcx, rdi; this
0x18000334c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003351  mov     rcx, [rdi+68h]
0x180003355  test    rcx, rcx
0x180003358  jz      short loc_18000338A
0x18000335a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003361  test    rax, rax
0x180003364  jnz     short loc_180003375
0x180003366  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000336d  test    rdx, rdx
0x180003370  jz      short loc_180003388
0x180003372  mov     rax, rdx
0x180003375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000337a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003381  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003388  jmp     short loc_180003398
0x18000338a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003391  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003398  mov     rcx, [rdi+60h]
0x18000339c  test    rcx, rcx
0x18000339f  jz      short loc_1800033B4
0x1800033a1  test    rax, rax
0x1800033a4  jnz     short loc_1800033AE
0x1800033a6  test    rdx, rdx
0x1800033a9  jz      short loc_1800033B4
0x1800033ab  mov     rax, rdx
0x1800033ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b3  nop
0x1800033b4  mov     rbx, [rdi+58h]
0x1800033b8  mov     qword ptr [rdi+58h], 0
0x1800033c0  test    rbx, rbx
0x1800033c3  jz      short loc_1800033D9
0x1800033c5  call    cs:__imp_GetProcessHeap
0x1800033cb  mov     rcx, rax; hHeap
0x1800033ce  mov     r8, rbx; lpMem
0x1800033d1  xor     edx, edx; dwFlags
0x1800033d3  call    cs:__imp_HeapFree
0x1800033d9  mov     rbx, [rdi+38h]
0x1800033dd  mov     qword ptr [rdi+38h], 0
0x1800033e5  test    rbx, rbx
0x1800033e8  jz      short loc_1800033FE
0x1800033ea  call    cs:__imp_GetProcessHeap
0x1800033f0  mov     rcx, rax; hHeap
0x1800033f3  mov     r8, rbx; lpMem
0x1800033f6  xor     edx, edx; dwFlags
0x1800033f8  call    cs:__imp_HeapFree
0x1800033fe  mov     rbx, [rdi+10h]
0x180003402  test    rbx, rbx
0x180003405  jz      short loc_180003430
0x180003407  xor     r9d, r9d; msWindowLength
0x18000340a  xor     r8d, r8d; msPeriod
0x18000340d  xor     edx, edx; pftDueTime
0x18000340f  mov     rcx, rbx; pti
0x180003412  call    cs:__imp_SetThreadpoolTimer
0x180003418  mov     edx, 1; fCancelPendingCallbacks
0x18000341d  mov     rcx, rbx; pti
0x180003420  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003426  mov     rcx, rbx; pti
0x180003429  call    cs:__imp_CloseThreadpoolTimer
0x18000342f  nop
0x180003430  mov     rbx, [rsp+28h+arg_0]
0x180003435  mov     rsi, [rsp+28h+arg_8]
0x18000343a  add     rsp, 20h
0x18000343e  pop     rdi
0x18000343f  retn
```
