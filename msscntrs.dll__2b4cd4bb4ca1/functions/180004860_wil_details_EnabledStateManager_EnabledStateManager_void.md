# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180004860`
- end: `0x1800049b8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016f00`

## callees

- `0x180004860`
- `0x18000746c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000493d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000493d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000494b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004970`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000494b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004881`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004894`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000498a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004894`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000498a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004998`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004998`

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
0x180004860  mov     [rsp+arg_0], rbx
0x180004865  mov     [rsp+arg_8], rsi
0x18000486a  push    rdi
0x18000486b  sub     rsp, 20h
0x18000486f  mov     rdi, rcx
0x180004872  mov     dword ptr [rcx], 0
0x180004878  mov     rsi, [rcx+10h]
0x18000487c  test    rsi, rsi
0x18000487f  jz      short loc_1800048B9
0x180004881  call    cs:__imp_GetLastError
0x180004887  mov     ebx, eax
0x180004889  xor     r9d, r9d; msWindowLength
0x18000488c  xor     r8d, r8d; msPeriod
0x18000488f  xor     edx, edx; pftDueTime
0x180004891  mov     rcx, rsi; pti
0x180004894  call    cs:__imp_SetThreadpoolTimer
0x18000489a  mov     edx, 1; fCancelPendingCallbacks
0x18000489f  mov     rcx, rsi; pti
0x1800048a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800048a8  mov     rcx, rsi; pti
0x1800048ab  call    cs:__imp_CloseThreadpoolTimer
0x1800048b1  mov     ecx, ebx; dwErrCode
0x1800048b3  call    cs:__imp_SetLastError
0x1800048b9  mov     qword ptr [rdi+10h], 0
0x1800048c1  mov     rcx, rdi; this
0x1800048c4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800048c9  mov     rcx, [rdi+68h]
0x1800048cd  test    rcx, rcx
0x1800048d0  jz      short loc_180004902
0x1800048d2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800048d9  test    rax, rax
0x1800048dc  jnz     short loc_1800048ED
0x1800048de  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800048e5  test    rdx, rdx
0x1800048e8  jz      short loc_180004900
0x1800048ea  mov     rax, rdx
0x1800048ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800048f9  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004900  jmp     short loc_180004910
0x180004902  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004909  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004910  mov     rcx, [rdi+60h]
0x180004914  test    rcx, rcx
0x180004917  jz      short loc_18000492C
0x180004919  test    rax, rax
0x18000491c  jnz     short loc_180004926
0x18000491e  test    rdx, rdx
0x180004921  jz      short loc_18000492C
0x180004923  mov     rax, rdx
0x180004926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492b  nop
0x18000492c  mov     rbx, [rdi+58h]
0x180004930  mov     qword ptr [rdi+58h], 0
0x180004938  test    rbx, rbx
0x18000493b  jz      short loc_180004951
0x18000493d  call    cs:__imp_GetProcessHeap
0x180004943  mov     rcx, rax; hHeap
0x180004946  mov     r8, rbx; lpMem
0x180004949  xor     edx, edx; dwFlags
0x18000494b  call    cs:__imp_HeapFree
0x180004951  mov     rbx, [rdi+38h]
0x180004955  mov     qword ptr [rdi+38h], 0
0x18000495d  test    rbx, rbx
0x180004960  jz      short loc_180004976
0x180004962  call    cs:__imp_GetProcessHeap
0x180004968  mov     rcx, rax; hHeap
0x18000496b  mov     r8, rbx; lpMem
0x18000496e  xor     edx, edx; dwFlags
0x180004970  call    cs:__imp_HeapFree
0x180004976  mov     rbx, [rdi+10h]
0x18000497a  test    rbx, rbx
0x18000497d  jz      short loc_1800049A8
0x18000497f  xor     r9d, r9d; msWindowLength
0x180004982  xor     r8d, r8d; msPeriod
0x180004985  xor     edx, edx; pftDueTime
0x180004987  mov     rcx, rbx; pti
0x18000498a  call    cs:__imp_SetThreadpoolTimer
0x180004990  mov     edx, 1; fCancelPendingCallbacks
0x180004995  mov     rcx, rbx; pti
0x180004998  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000499e  mov     rcx, rbx; pti
0x1800049a1  call    cs:__imp_CloseThreadpoolTimer
0x1800049a7  nop
0x1800049a8  mov     rbx, [rsp+28h+arg_0]
0x1800049ad  mov     rsi, [rsp+28h+arg_8]
0x1800049b2  add     rsp, 20h
0x1800049b6  pop     rdi
0x1800049b7  retn
```
