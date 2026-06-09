# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800086c8`
- end: `0x180008820`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180115180`

## callees

- `0x1800086c8`
- `0x18000b7bc`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000871b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000870a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008800`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000870a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008800`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800087f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800087f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008713`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008809`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008713`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008809`

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
0x1800086c8  mov     [rsp+arg_0], rbx
0x1800086cd  mov     [rsp+arg_8], rsi
0x1800086d2  push    rdi
0x1800086d3  sub     rsp, 20h
0x1800086d7  mov     rdi, rcx
0x1800086da  mov     dword ptr [rcx], 0
0x1800086e0  mov     rsi, [rcx+10h]
0x1800086e4  test    rsi, rsi
0x1800086e7  jz      short loc_180008721
0x1800086e9  call    cs:__imp_GetLastError
0x1800086ef  mov     ebx, eax
0x1800086f1  xor     r9d, r9d; msWindowLength
0x1800086f4  xor     r8d, r8d; msPeriod
0x1800086f7  xor     edx, edx; pftDueTime
0x1800086f9  mov     rcx, rsi; pti
0x1800086fc  call    cs:__imp_SetThreadpoolTimer
0x180008702  mov     edx, 1; fCancelPendingCallbacks
0x180008707  mov     rcx, rsi; pti
0x18000870a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008710  mov     rcx, rsi; pti
0x180008713  call    cs:__imp_CloseThreadpoolTimer
0x180008719  mov     ecx, ebx; dwErrCode
0x18000871b  call    cs:__imp_SetLastError
0x180008721  mov     qword ptr [rdi+10h], 0
0x180008729  mov     rcx, rdi; this
0x18000872c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180008731  mov     rcx, [rdi+68h]
0x180008735  test    rcx, rcx
0x180008738  jz      short loc_18000876A
0x18000873a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008741  test    rax, rax
0x180008744  jnz     short loc_180008755
0x180008746  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000874d  test    rdx, rdx
0x180008750  jz      short loc_180008768
0x180008752  mov     rax, rdx
0x180008755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008761  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008768  jmp     short loc_180008778
0x18000876a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008771  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008778  mov     rcx, [rdi+60h]
0x18000877c  test    rcx, rcx
0x18000877f  jz      short loc_180008794
0x180008781  test    rax, rax
0x180008784  jnz     short loc_18000878E
0x180008786  test    rdx, rdx
0x180008789  jz      short loc_180008794
0x18000878b  mov     rax, rdx
0x18000878e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008793  nop
0x180008794  mov     rbx, [rdi+58h]
0x180008798  mov     qword ptr [rdi+58h], 0
0x1800087a0  test    rbx, rbx
0x1800087a3  jz      short loc_1800087B9
0x1800087a5  call    cs:__imp_GetProcessHeap
0x1800087ab  mov     rcx, rax; hHeap
0x1800087ae  mov     r8, rbx; lpMem
0x1800087b1  xor     edx, edx; dwFlags
0x1800087b3  call    cs:__imp_HeapFree
0x1800087b9  mov     rbx, [rdi+38h]
0x1800087bd  mov     qword ptr [rdi+38h], 0
0x1800087c5  test    rbx, rbx
0x1800087c8  jz      short loc_1800087DE
0x1800087ca  call    cs:__imp_GetProcessHeap
0x1800087d0  mov     rcx, rax; hHeap
0x1800087d3  mov     r8, rbx; lpMem
0x1800087d6  xor     edx, edx; dwFlags
0x1800087d8  call    cs:__imp_HeapFree
0x1800087de  mov     rbx, [rdi+10h]
0x1800087e2  test    rbx, rbx
0x1800087e5  jz      short loc_180008810
0x1800087e7  xor     r9d, r9d; msWindowLength
0x1800087ea  xor     r8d, r8d; msPeriod
0x1800087ed  xor     edx, edx; pftDueTime
0x1800087ef  mov     rcx, rbx; pti
0x1800087f2  call    cs:__imp_SetThreadpoolTimer
0x1800087f8  mov     edx, 1; fCancelPendingCallbacks
0x1800087fd  mov     rcx, rbx; pti
0x180008800  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008806  mov     rcx, rbx; pti
0x180008809  call    cs:__imp_CloseThreadpoolTimer
0x18000880f  nop
0x180008810  mov     rbx, [rsp+28h+arg_0]
0x180008815  mov     rsi, [rsp+28h+arg_8]
0x18000881a  add     rsp, 20h
0x18000881e  pop     rdi
0x18000881f  retn
```
