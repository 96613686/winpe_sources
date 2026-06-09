# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180004748`
- end: `0x18000488e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d210`

## callees

- `0x180004748`
- `0x1800080dc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000479b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000479b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004839`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004847`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004847`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000477c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004861`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000477c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004861`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004793`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004878`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004793`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004878`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000478a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000486f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000478a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000486f`

## pseudocode

```c
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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x180004748  mov     [rsp+arg_0], rbx
0x18000474d  mov     [rsp+arg_8], rsi
0x180004752  push    rdi
0x180004753  sub     rsp, 20h
0x180004757  mov     dword ptr [rcx], 0
0x18000475d  mov     rdi, rcx
0x180004760  mov     rsi, [rcx+10h]
0x180004764  test    rsi, rsi
0x180004767  jz      short loc_1800047A1
0x180004769  call    cs:__imp_GetLastError
0x18000476f  xor     r9d, r9d; msWindowLength
0x180004772  xor     r8d, r8d; msPeriod
0x180004775  xor     edx, edx; pftDueTime
0x180004777  mov     rcx, rsi; pti
0x18000477a  mov     ebx, eax
0x18000477c  call    cs:__imp_SetThreadpoolTimer
0x180004782  mov     edx, 1; fCancelPendingCallbacks
0x180004787  mov     rcx, rsi; pti
0x18000478a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004790  mov     rcx, rsi; pti
0x180004793  call    cs:__imp_CloseThreadpoolTimer
0x180004799  mov     ecx, ebx; dwErrCode
0x18000479b  call    cs:__imp_SetLastError
0x1800047a1  mov     rcx, rdi; this
0x1800047a4  mov     qword ptr [rdi+10h], 0
0x1800047ac  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800047b1  mov     rcx, [rdi+68h]
0x1800047b5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800047bc  test    rcx, rcx
0x1800047bf  jz      short loc_1800047E1
0x1800047c1  test    rax, rax
0x1800047c4  jnz     short loc_1800047D5
0x1800047c6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800047cd  test    rdx, rdx
0x1800047d0  jz      short loc_1800047E8
0x1800047d2  mov     rax, rdx
0x1800047d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047da  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800047e1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800047e8  mov     rcx, [rdi+60h]
0x1800047ec  test    rcx, rcx
0x1800047ef  jz      short loc_180004803
0x1800047f1  test    rax, rax
0x1800047f4  jnz     short loc_1800047FE
0x1800047f6  test    rdx, rdx
0x1800047f9  jz      short loc_180004803
0x1800047fb  mov     rax, rdx
0x1800047fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004803  mov     rbx, [rdi+58h]
0x180004807  mov     qword ptr [rdi+58h], 0
0x18000480f  test    rbx, rbx
0x180004812  jz      short loc_180004828
0x180004814  call    cs:__imp_GetProcessHeap
0x18000481a  mov     r8, rbx; lpMem
0x18000481d  xor     edx, edx; dwFlags
0x18000481f  mov     rcx, rax; hHeap
0x180004822  call    cs:__imp_HeapFree
0x180004828  mov     rbx, [rdi+38h]
0x18000482c  mov     qword ptr [rdi+38h], 0
0x180004834  test    rbx, rbx
0x180004837  jz      short loc_18000484D
0x180004839  call    cs:__imp_GetProcessHeap
0x18000483f  mov     r8, rbx; lpMem
0x180004842  xor     edx, edx; dwFlags
0x180004844  mov     rcx, rax; hHeap
0x180004847  call    cs:__imp_HeapFree
0x18000484d  mov     rbx, [rdi+10h]
0x180004851  test    rbx, rbx
0x180004854  jz      short loc_18000487E
0x180004856  xor     r9d, r9d; msWindowLength
0x180004859  xor     r8d, r8d; msPeriod
0x18000485c  xor     edx, edx; pftDueTime
0x18000485e  mov     rcx, rbx; pti
0x180004861  call    cs:__imp_SetThreadpoolTimer
0x180004867  mov     edx, 1; fCancelPendingCallbacks
0x18000486c  mov     rcx, rbx; pti
0x18000486f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004875  mov     rcx, rbx; pti
0x180004878  call    cs:__imp_CloseThreadpoolTimer
0x18000487e  mov     rbx, [rsp+28h+arg_0]
0x180004883  mov     rsi, [rsp+28h+arg_8]
0x180004888  add     rsp, 20h
0x18000488c  pop     rdi
0x18000488d  retn
```
