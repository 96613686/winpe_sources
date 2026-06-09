# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800076fc`
- end: `0x180007854`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180039c40`

## callees

- `0x1800076fc`
- `0x18000a35c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000780c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000780c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000774f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000774f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000771d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000771d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007747`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000783d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007747`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000783d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000773e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007834`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000773e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007834`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007730`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007826`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007730`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007826`

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
0x1800076fc  mov     [rsp+arg_0], rbx
0x180007701  mov     [rsp+arg_8], rsi
0x180007706  push    rdi
0x180007707  sub     rsp, 20h
0x18000770b  mov     rdi, rcx
0x18000770e  mov     dword ptr [rcx], 0
0x180007714  mov     rsi, [rcx+10h]
0x180007718  test    rsi, rsi
0x18000771b  jz      short loc_180007755
0x18000771d  call    cs:__imp_GetLastError
0x180007723  mov     ebx, eax
0x180007725  xor     r9d, r9d; msWindowLength
0x180007728  xor     r8d, r8d; msPeriod
0x18000772b  xor     edx, edx; pftDueTime
0x18000772d  mov     rcx, rsi; pti
0x180007730  call    cs:__imp_SetThreadpoolTimer
0x180007736  mov     edx, 1; fCancelPendingCallbacks
0x18000773b  mov     rcx, rsi; pti
0x18000773e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007744  mov     rcx, rsi; pti
0x180007747  call    cs:__imp_CloseThreadpoolTimer
0x18000774d  mov     ecx, ebx; dwErrCode
0x18000774f  call    cs:__imp_SetLastError
0x180007755  mov     qword ptr [rdi+10h], 0
0x18000775d  mov     rcx, rdi; this
0x180007760  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180007765  mov     rcx, [rdi+68h]
0x180007769  test    rcx, rcx
0x18000776c  jz      short loc_18000779E
0x18000776e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007775  test    rax, rax
0x180007778  jnz     short loc_180007789
0x18000777a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007781  test    rdx, rdx
0x180007784  jz      short loc_18000779C
0x180007786  mov     rax, rdx
0x180007789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007795  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000779c  jmp     short loc_1800077AC
0x18000779e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800077a5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800077ac  mov     rcx, [rdi+60h]
0x1800077b0  test    rcx, rcx
0x1800077b3  jz      short loc_1800077C8
0x1800077b5  test    rax, rax
0x1800077b8  jnz     short loc_1800077C2
0x1800077ba  test    rdx, rdx
0x1800077bd  jz      short loc_1800077C8
0x1800077bf  mov     rax, rdx
0x1800077c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c7  nop
0x1800077c8  mov     rbx, [rdi+58h]
0x1800077cc  mov     qword ptr [rdi+58h], 0
0x1800077d4  test    rbx, rbx
0x1800077d7  jz      short loc_1800077ED
0x1800077d9  call    cs:__imp_GetProcessHeap
0x1800077df  mov     rcx, rax; hHeap
0x1800077e2  mov     r8, rbx; lpMem
0x1800077e5  xor     edx, edx; dwFlags
0x1800077e7  call    cs:__imp_HeapFree
0x1800077ed  mov     rbx, [rdi+38h]
0x1800077f1  mov     qword ptr [rdi+38h], 0
0x1800077f9  test    rbx, rbx
0x1800077fc  jz      short loc_180007812
0x1800077fe  call    cs:__imp_GetProcessHeap
0x180007804  mov     rcx, rax; hHeap
0x180007807  mov     r8, rbx; lpMem
0x18000780a  xor     edx, edx; dwFlags
0x18000780c  call    cs:__imp_HeapFree
0x180007812  mov     rbx, [rdi+10h]
0x180007816  test    rbx, rbx
0x180007819  jz      short loc_180007844
0x18000781b  xor     r9d, r9d; msWindowLength
0x18000781e  xor     r8d, r8d; msPeriod
0x180007821  xor     edx, edx; pftDueTime
0x180007823  mov     rcx, rbx; pti
0x180007826  call    cs:__imp_SetThreadpoolTimer
0x18000782c  mov     edx, 1; fCancelPendingCallbacks
0x180007831  mov     rcx, rbx; pti
0x180007834  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000783a  mov     rcx, rbx; pti
0x18000783d  call    cs:__imp_CloseThreadpoolTimer
0x180007843  nop
0x180007844  mov     rbx, [rsp+28h+arg_0]
0x180007849  mov     rsi, [rsp+28h+arg_8]
0x18000784e  add     rsp, 20h
0x180007852  pop     rdi
0x180007853  retn
```
