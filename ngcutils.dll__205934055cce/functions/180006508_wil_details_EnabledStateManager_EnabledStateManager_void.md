# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006508`
- end: `0x180006660`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180060600`

## callees

- `0x180006508`
- `0x180008ea8`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006618`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000660a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000660a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000655b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000655b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006529`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000653c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006632`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000653c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006632`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006553`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006649`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006553`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006649`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000654a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006640`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000654a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006640`

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
0x180006508  mov     [rsp+arg_0], rbx
0x18000650d  mov     [rsp+arg_8], rsi
0x180006512  push    rdi
0x180006513  sub     rsp, 20h
0x180006517  mov     rdi, rcx
0x18000651a  mov     dword ptr [rcx], 0
0x180006520  mov     rsi, [rcx+10h]
0x180006524  test    rsi, rsi
0x180006527  jz      short loc_180006561
0x180006529  call    cs:__imp_GetLastError
0x18000652f  mov     ebx, eax
0x180006531  xor     r9d, r9d; msWindowLength
0x180006534  xor     r8d, r8d; msPeriod
0x180006537  xor     edx, edx; pftDueTime
0x180006539  mov     rcx, rsi; pti
0x18000653c  call    cs:__imp_SetThreadpoolTimer
0x180006542  mov     edx, 1; fCancelPendingCallbacks
0x180006547  mov     rcx, rsi; pti
0x18000654a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006550  mov     rcx, rsi; pti
0x180006553  call    cs:__imp_CloseThreadpoolTimer
0x180006559  mov     ecx, ebx; dwErrCode
0x18000655b  call    cs:__imp_SetLastError
0x180006561  mov     qword ptr [rdi+10h], 0
0x180006569  mov     rcx, rdi; this
0x18000656c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180006571  mov     rcx, [rdi+68h]
0x180006575  test    rcx, rcx
0x180006578  jz      short loc_1800065AA
0x18000657a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006581  test    rax, rax
0x180006584  jnz     short loc_180006595
0x180006586  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000658d  test    rdx, rdx
0x180006590  jz      short loc_1800065A8
0x180006592  mov     rax, rdx
0x180006595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800065a1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800065a8  jmp     short loc_1800065B8
0x1800065aa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800065b1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800065b8  mov     rcx, [rdi+60h]
0x1800065bc  test    rcx, rcx
0x1800065bf  jz      short loc_1800065D4
0x1800065c1  test    rax, rax
0x1800065c4  jnz     short loc_1800065CE
0x1800065c6  test    rdx, rdx
0x1800065c9  jz      short loc_1800065D4
0x1800065cb  mov     rax, rdx
0x1800065ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d3  nop
0x1800065d4  mov     rbx, [rdi+58h]
0x1800065d8  mov     qword ptr [rdi+58h], 0
0x1800065e0  test    rbx, rbx
0x1800065e3  jz      short loc_1800065F9
0x1800065e5  call    cs:__imp_GetProcessHeap
0x1800065eb  mov     rcx, rax; hHeap
0x1800065ee  mov     r8, rbx; lpMem
0x1800065f1  xor     edx, edx; dwFlags
0x1800065f3  call    cs:__imp_HeapFree
0x1800065f9  mov     rbx, [rdi+38h]
0x1800065fd  mov     qword ptr [rdi+38h], 0
0x180006605  test    rbx, rbx
0x180006608  jz      short loc_18000661E
0x18000660a  call    cs:__imp_GetProcessHeap
0x180006610  mov     rcx, rax; hHeap
0x180006613  mov     r8, rbx; lpMem
0x180006616  xor     edx, edx; dwFlags
0x180006618  call    cs:__imp_HeapFree
0x18000661e  mov     rbx, [rdi+10h]
0x180006622  test    rbx, rbx
0x180006625  jz      short loc_180006650
0x180006627  xor     r9d, r9d; msWindowLength
0x18000662a  xor     r8d, r8d; msPeriod
0x18000662d  xor     edx, edx; pftDueTime
0x18000662f  mov     rcx, rbx; pti
0x180006632  call    cs:__imp_SetThreadpoolTimer
0x180006638  mov     edx, 1; fCancelPendingCallbacks
0x18000663d  mov     rcx, rbx; pti
0x180006640  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006646  mov     rcx, rbx; pti
0x180006649  call    cs:__imp_CloseThreadpoolTimer
0x18000664f  nop
0x180006650  mov     rbx, [rsp+28h+arg_0]
0x180006655  mov     rsi, [rsp+28h+arg_8]
0x18000665a  add     rsp, 20h
0x18000665e  pop     rdi
0x18000665f  retn
```
