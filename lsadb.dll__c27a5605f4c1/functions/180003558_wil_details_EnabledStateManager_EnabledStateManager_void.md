# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003558`
- end: `0x18000369e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003ae90`

## callees

- `0x180003558`
- `0x1800065dc`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003632`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003632`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003657`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003649`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003579`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003688`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003688`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000358c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000358c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003671`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000359a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000367f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000359a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000367f`

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
0x180003558  mov     [rsp+arg_0], rbx
0x18000355d  mov     [rsp+arg_8], rsi
0x180003562  push    rdi
0x180003563  sub     rsp, 20h
0x180003567  mov     dword ptr [rcx], 0
0x18000356d  mov     rdi, rcx
0x180003570  mov     rsi, [rcx+10h]
0x180003574  test    rsi, rsi
0x180003577  jz      short loc_1800035B1
0x180003579  call    cs:__imp_GetLastError
0x18000357f  xor     r9d, r9d; msWindowLength
0x180003582  xor     r8d, r8d; msPeriod
0x180003585  xor     edx, edx; pftDueTime
0x180003587  mov     rcx, rsi; pti
0x18000358a  mov     ebx, eax
0x18000358c  call    cs:__imp_SetThreadpoolTimer
0x180003592  mov     edx, 1; fCancelPendingCallbacks
0x180003597  mov     rcx, rsi; pti
0x18000359a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800035a0  mov     rcx, rsi; pti
0x1800035a3  call    cs:__imp_CloseThreadpoolTimer
0x1800035a9  mov     ecx, ebx; dwErrCode
0x1800035ab  call    cs:__imp_SetLastError
0x1800035b1  mov     rcx, rdi; this
0x1800035b4  mov     qword ptr [rdi+10h], 0
0x1800035bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800035c1  mov     rcx, [rdi+68h]
0x1800035c5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800035cc  test    rcx, rcx
0x1800035cf  jz      short loc_1800035F1
0x1800035d1  test    rax, rax
0x1800035d4  jnz     short loc_1800035E5
0x1800035d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800035dd  test    rdx, rdx
0x1800035e0  jz      short loc_1800035F8
0x1800035e2  mov     rax, rdx
0x1800035e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ea  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800035f1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800035f8  mov     rcx, [rdi+60h]
0x1800035fc  test    rcx, rcx
0x1800035ff  jz      short loc_180003613
0x180003601  test    rax, rax
0x180003604  jnz     short loc_18000360E
0x180003606  test    rdx, rdx
0x180003609  jz      short loc_180003613
0x18000360b  mov     rax, rdx
0x18000360e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003613  mov     rbx, [rdi+58h]
0x180003617  mov     qword ptr [rdi+58h], 0
0x18000361f  test    rbx, rbx
0x180003622  jz      short loc_180003638
0x180003624  call    cs:__imp_GetProcessHeap
0x18000362a  mov     r8, rbx; lpMem
0x18000362d  xor     edx, edx; dwFlags
0x18000362f  mov     rcx, rax; hHeap
0x180003632  call    cs:__imp_HeapFree
0x180003638  mov     rbx, [rdi+38h]
0x18000363c  mov     qword ptr [rdi+38h], 0
0x180003644  test    rbx, rbx
0x180003647  jz      short loc_18000365D
0x180003649  call    cs:__imp_GetProcessHeap
0x18000364f  mov     r8, rbx; lpMem
0x180003652  xor     edx, edx; dwFlags
0x180003654  mov     rcx, rax; hHeap
0x180003657  call    cs:__imp_HeapFree
0x18000365d  mov     rbx, [rdi+10h]
0x180003661  test    rbx, rbx
0x180003664  jz      short loc_18000368E
0x180003666  xor     r9d, r9d; msWindowLength
0x180003669  xor     r8d, r8d; msPeriod
0x18000366c  xor     edx, edx; pftDueTime
0x18000366e  mov     rcx, rbx; pti
0x180003671  call    cs:__imp_SetThreadpoolTimer
0x180003677  mov     edx, 1; fCancelPendingCallbacks
0x18000367c  mov     rcx, rbx; pti
0x18000367f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003685  mov     rcx, rbx; pti
0x180003688  call    cs:__imp_CloseThreadpoolTimer
0x18000368e  mov     rbx, [rsp+28h+arg_0]
0x180003693  mov     rsi, [rsp+28h+arg_8]
0x180003698  add     rsp, 20h
0x18000369c  pop     rdi
0x18000369d  retn
```
