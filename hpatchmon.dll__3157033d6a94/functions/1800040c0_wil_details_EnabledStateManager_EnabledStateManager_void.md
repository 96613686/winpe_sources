# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800040c0`
- end: `0x180004218`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014560`

## callees

- `0x1800040c0`
- `0x180007f1c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004113`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000419d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000419d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800040f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800041ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800040f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800041ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000410b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004201`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000410b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004201`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004102`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800041f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004102`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800041f8`

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
0x1800040c0  mov     [rsp+arg_0], rbx
0x1800040c5  mov     [rsp+arg_8], rsi
0x1800040ca  push    rdi
0x1800040cb  sub     rsp, 20h
0x1800040cf  mov     rdi, rcx
0x1800040d2  mov     dword ptr [rcx], 0
0x1800040d8  mov     rsi, [rcx+10h]
0x1800040dc  test    rsi, rsi
0x1800040df  jz      short loc_180004119
0x1800040e1  call    cs:__imp_GetLastError
0x1800040e7  mov     ebx, eax
0x1800040e9  xor     r9d, r9d; msWindowLength
0x1800040ec  xor     r8d, r8d; msPeriod
0x1800040ef  xor     edx, edx; pftDueTime
0x1800040f1  mov     rcx, rsi; pti
0x1800040f4  call    cs:__imp_SetThreadpoolTimer
0x1800040fa  mov     edx, 1; fCancelPendingCallbacks
0x1800040ff  mov     rcx, rsi; pti
0x180004102  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004108  mov     rcx, rsi; pti
0x18000410b  call    cs:__imp_CloseThreadpoolTimer
0x180004111  mov     ecx, ebx; dwErrCode
0x180004113  call    cs:__imp_SetLastError
0x180004119  mov     qword ptr [rdi+10h], 0
0x180004121  mov     rcx, rdi; this
0x180004124  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180004129  mov     rcx, [rdi+68h]
0x18000412d  test    rcx, rcx
0x180004130  jz      short loc_180004162
0x180004132  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004139  test    rax, rax
0x18000413c  jnz     short loc_18000414D
0x18000413e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004145  test    rdx, rdx
0x180004148  jz      short loc_180004160
0x18000414a  mov     rax, rdx
0x18000414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004152  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004159  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004160  jmp     short loc_180004170
0x180004162  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004169  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004170  mov     rcx, [rdi+60h]
0x180004174  test    rcx, rcx
0x180004177  jz      short loc_18000418C
0x180004179  test    rax, rax
0x18000417c  jnz     short loc_180004186
0x18000417e  test    rdx, rdx
0x180004181  jz      short loc_18000418C
0x180004183  mov     rax, rdx
0x180004186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418b  nop
0x18000418c  mov     rbx, [rdi+58h]
0x180004190  mov     qword ptr [rdi+58h], 0
0x180004198  test    rbx, rbx
0x18000419b  jz      short loc_1800041B1
0x18000419d  call    cs:__imp_GetProcessHeap
0x1800041a3  mov     rcx, rax; hHeap
0x1800041a6  mov     r8, rbx; lpMem
0x1800041a9  xor     edx, edx; dwFlags
0x1800041ab  call    cs:__imp_HeapFree
0x1800041b1  mov     rbx, [rdi+38h]
0x1800041b5  mov     qword ptr [rdi+38h], 0
0x1800041bd  test    rbx, rbx
0x1800041c0  jz      short loc_1800041D6
0x1800041c2  call    cs:__imp_GetProcessHeap
0x1800041c8  mov     rcx, rax; hHeap
0x1800041cb  mov     r8, rbx; lpMem
0x1800041ce  xor     edx, edx; dwFlags
0x1800041d0  call    cs:__imp_HeapFree
0x1800041d6  mov     rbx, [rdi+10h]
0x1800041da  test    rbx, rbx
0x1800041dd  jz      short loc_180004208
0x1800041df  xor     r9d, r9d; msWindowLength
0x1800041e2  xor     r8d, r8d; msPeriod
0x1800041e5  xor     edx, edx; pftDueTime
0x1800041e7  mov     rcx, rbx; pti
0x1800041ea  call    cs:__imp_SetThreadpoolTimer
0x1800041f0  mov     edx, 1; fCancelPendingCallbacks
0x1800041f5  mov     rcx, rbx; pti
0x1800041f8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800041fe  mov     rcx, rbx; pti
0x180004201  call    cs:__imp_CloseThreadpoolTimer
0x180004207  nop
0x180004208  mov     rbx, [rsp+28h+arg_0]
0x18000420d  mov     rsi, [rsp+28h+arg_8]
0x180004212  add     rsp, 20h
0x180004216  pop     rdi
0x180004217  retn
```
