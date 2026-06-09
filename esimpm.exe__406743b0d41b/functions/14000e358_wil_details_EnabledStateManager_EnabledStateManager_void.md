# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000e358`
- end: `0x14000e4b0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003da20`

## callees

- `0x14000e358`
- `0x140010e9c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e468`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e435`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e45a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e435`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e379`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e3ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e3ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e499`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e499`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e39a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e490`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e39a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e490`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e38c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e482`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e38c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e482`

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
0x14000e358  mov     [rsp+arg_0], rbx
0x14000e35d  mov     [rsp+arg_8], rsi
0x14000e362  push    rdi
0x14000e363  sub     rsp, 20h
0x14000e367  mov     rdi, rcx
0x14000e36a  mov     dword ptr [rcx], 0
0x14000e370  mov     rsi, [rcx+10h]
0x14000e374  test    rsi, rsi
0x14000e377  jz      short loc_14000E3B1
0x14000e379  call    cs:__imp_GetLastError
0x14000e37f  mov     ebx, eax
0x14000e381  xor     r9d, r9d; msWindowLength
0x14000e384  xor     r8d, r8d; msPeriod
0x14000e387  xor     edx, edx; pftDueTime
0x14000e389  mov     rcx, rsi; pti
0x14000e38c  call    cs:__imp_SetThreadpoolTimer
0x14000e392  mov     edx, 1; fCancelPendingCallbacks
0x14000e397  mov     rcx, rsi; pti
0x14000e39a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e3a0  mov     rcx, rsi; pti
0x14000e3a3  call    cs:__imp_CloseThreadpoolTimer
0x14000e3a9  mov     ecx, ebx; dwErrCode
0x14000e3ab  call    cs:__imp_SetLastError
0x14000e3b1  mov     qword ptr [rdi+10h], 0
0x14000e3b9  mov     rcx, rdi; this
0x14000e3bc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000e3c1  mov     rcx, [rdi+68h]
0x14000e3c5  test    rcx, rcx
0x14000e3c8  jz      short loc_14000E3FA
0x14000e3ca  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000e3d1  test    rax, rax
0x14000e3d4  jnz     short loc_14000E3E5
0x14000e3d6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000e3dd  test    rdx, rdx
0x14000e3e0  jz      short loc_14000E3F8
0x14000e3e2  mov     rax, rdx
0x14000e3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000e3f1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000e3f8  jmp     short loc_14000E408
0x14000e3fa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000e401  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000e408  mov     rcx, [rdi+60h]
0x14000e40c  test    rcx, rcx
0x14000e40f  jz      short loc_14000E424
0x14000e411  test    rax, rax
0x14000e414  jnz     short loc_14000E41E
0x14000e416  test    rdx, rdx
0x14000e419  jz      short loc_14000E424
0x14000e41b  mov     rax, rdx
0x14000e41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e423  nop
0x14000e424  mov     rbx, [rdi+58h]
0x14000e428  mov     qword ptr [rdi+58h], 0
0x14000e430  test    rbx, rbx
0x14000e433  jz      short loc_14000E449
0x14000e435  call    cs:__imp_GetProcessHeap
0x14000e43b  mov     rcx, rax; hHeap
0x14000e43e  mov     r8, rbx; lpMem
0x14000e441  xor     edx, edx; dwFlags
0x14000e443  call    cs:__imp_HeapFree
0x14000e449  mov     rbx, [rdi+38h]
0x14000e44d  mov     qword ptr [rdi+38h], 0
0x14000e455  test    rbx, rbx
0x14000e458  jz      short loc_14000E46E
0x14000e45a  call    cs:__imp_GetProcessHeap
0x14000e460  mov     rcx, rax; hHeap
0x14000e463  mov     r8, rbx; lpMem
0x14000e466  xor     edx, edx; dwFlags
0x14000e468  call    cs:__imp_HeapFree
0x14000e46e  mov     rbx, [rdi+10h]
0x14000e472  test    rbx, rbx
0x14000e475  jz      short loc_14000E4A0
0x14000e477  xor     r9d, r9d; msWindowLength
0x14000e47a  xor     r8d, r8d; msPeriod
0x14000e47d  xor     edx, edx; pftDueTime
0x14000e47f  mov     rcx, rbx; pti
0x14000e482  call    cs:__imp_SetThreadpoolTimer
0x14000e488  mov     edx, 1; fCancelPendingCallbacks
0x14000e48d  mov     rcx, rbx; pti
0x14000e490  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e496  mov     rcx, rbx; pti
0x14000e499  call    cs:__imp_CloseThreadpoolTimer
0x14000e49f  nop
0x14000e4a0  mov     rbx, [rsp+28h+arg_0]
0x14000e4a5  mov     rsi, [rsp+28h+arg_8]
0x14000e4aa  add     rsp, 20h
0x14000e4ae  pop     rdi
0x14000e4af  retn
```
