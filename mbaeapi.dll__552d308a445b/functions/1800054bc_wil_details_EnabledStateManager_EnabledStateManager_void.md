# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800054bc`
- end: `0x180005614`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005b470`

## callees

- `0x1800054bc`
- `0x180007d9c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005507`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005507`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055f4`

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
0x1800054bc  mov     [rsp+arg_0], rbx
0x1800054c1  mov     [rsp+arg_8], rsi
0x1800054c6  push    rdi
0x1800054c7  sub     rsp, 20h
0x1800054cb  mov     rdi, rcx
0x1800054ce  mov     dword ptr [rcx], 0
0x1800054d4  mov     rsi, [rcx+10h]
0x1800054d8  test    rsi, rsi
0x1800054db  jz      short loc_180005515
0x1800054dd  call    cs:__imp_GetLastError
0x1800054e3  mov     ebx, eax
0x1800054e5  xor     r9d, r9d; msWindowLength
0x1800054e8  xor     r8d, r8d; msPeriod
0x1800054eb  xor     edx, edx; pftDueTime
0x1800054ed  mov     rcx, rsi; pti
0x1800054f0  call    cs:__imp_SetThreadpoolTimer
0x1800054f6  mov     edx, 1; fCancelPendingCallbacks
0x1800054fb  mov     rcx, rsi; pti
0x1800054fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005504  mov     rcx, rsi; pti
0x180005507  call    cs:__imp_CloseThreadpoolTimer
0x18000550d  mov     ecx, ebx; dwErrCode
0x18000550f  call    cs:__imp_SetLastError
0x180005515  mov     qword ptr [rdi+10h], 0
0x18000551d  mov     rcx, rdi; this
0x180005520  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180005525  mov     rcx, [rdi+68h]
0x180005529  test    rcx, rcx
0x18000552c  jz      short loc_18000555E
0x18000552e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005535  test    rax, rax
0x180005538  jnz     short loc_180005549
0x18000553a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005541  test    rdx, rdx
0x180005544  jz      short loc_18000555C
0x180005546  mov     rax, rdx
0x180005549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005555  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000555c  jmp     short loc_18000556C
0x18000555e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005565  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000556c  mov     rcx, [rdi+60h]
0x180005570  test    rcx, rcx
0x180005573  jz      short loc_180005588
0x180005575  test    rax, rax
0x180005578  jnz     short loc_180005582
0x18000557a  test    rdx, rdx
0x18000557d  jz      short loc_180005588
0x18000557f  mov     rax, rdx
0x180005582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005587  nop
0x180005588  mov     rbx, [rdi+58h]
0x18000558c  mov     qword ptr [rdi+58h], 0
0x180005594  test    rbx, rbx
0x180005597  jz      short loc_1800055AD
0x180005599  call    cs:__imp_GetProcessHeap
0x18000559f  mov     rcx, rax; hHeap
0x1800055a2  mov     r8, rbx; lpMem
0x1800055a5  xor     edx, edx; dwFlags
0x1800055a7  call    cs:__imp_HeapFree
0x1800055ad  mov     rbx, [rdi+38h]
0x1800055b1  mov     qword ptr [rdi+38h], 0
0x1800055b9  test    rbx, rbx
0x1800055bc  jz      short loc_1800055D2
0x1800055be  call    cs:__imp_GetProcessHeap
0x1800055c4  mov     rcx, rax; hHeap
0x1800055c7  mov     r8, rbx; lpMem
0x1800055ca  xor     edx, edx; dwFlags
0x1800055cc  call    cs:__imp_HeapFree
0x1800055d2  mov     rbx, [rdi+10h]
0x1800055d6  test    rbx, rbx
0x1800055d9  jz      short loc_180005604
0x1800055db  xor     r9d, r9d; msWindowLength
0x1800055de  xor     r8d, r8d; msPeriod
0x1800055e1  xor     edx, edx; pftDueTime
0x1800055e3  mov     rcx, rbx; pti
0x1800055e6  call    cs:__imp_SetThreadpoolTimer
0x1800055ec  mov     edx, 1; fCancelPendingCallbacks
0x1800055f1  mov     rcx, rbx; pti
0x1800055f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800055fa  mov     rcx, rbx; pti
0x1800055fd  call    cs:__imp_CloseThreadpoolTimer
0x180005603  nop
0x180005604  mov     rbx, [rsp+28h+arg_0]
0x180005609  mov     rsi, [rsp+28h+arg_8]
0x18000560e  add     rsp, 20h
0x180005612  pop     rdi
0x180005613  retn
```
