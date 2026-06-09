# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000769c`
- end: `0x1800077f4`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013df0`

## callees

- `0x18000769c`
- `0x18000ee88`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000779e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000779e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800076e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800077dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800076e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800077dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800076de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800077d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800076de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800077d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800077c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800077c6`

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
0x18000769c  mov     [rsp+arg_0], rbx
0x1800076a1  mov     [rsp+arg_8], rsi
0x1800076a6  push    rdi
0x1800076a7  sub     rsp, 20h
0x1800076ab  mov     rdi, rcx
0x1800076ae  mov     dword ptr [rcx], 0
0x1800076b4  mov     rsi, [rcx+10h]
0x1800076b8  test    rsi, rsi
0x1800076bb  jz      short loc_1800076F5
0x1800076bd  call    cs:__imp_GetLastError
0x1800076c3  mov     ebx, eax
0x1800076c5  xor     r9d, r9d; msWindowLength
0x1800076c8  xor     r8d, r8d; msPeriod
0x1800076cb  xor     edx, edx; pftDueTime
0x1800076cd  mov     rcx, rsi; pti
0x1800076d0  call    cs:__imp_SetThreadpoolTimer
0x1800076d6  mov     edx, 1; fCancelPendingCallbacks
0x1800076db  mov     rcx, rsi; pti
0x1800076de  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800076e4  mov     rcx, rsi; pti
0x1800076e7  call    cs:__imp_CloseThreadpoolTimer
0x1800076ed  mov     ecx, ebx; dwErrCode
0x1800076ef  call    cs:__imp_SetLastError
0x1800076f5  mov     qword ptr [rdi+10h], 0
0x1800076fd  mov     rcx, rdi; this
0x180007700  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180007705  mov     rcx, [rdi+68h]
0x180007709  test    rcx, rcx
0x18000770c  jz      short loc_18000773E
0x18000770e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007715  test    rax, rax
0x180007718  jnz     short loc_180007729
0x18000771a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007721  test    rdx, rdx
0x180007724  jz      short loc_18000773C
0x180007726  mov     rax, rdx
0x180007729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000772e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180007735  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000773c  jmp     short loc_18000774C
0x18000773e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007745  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000774c  mov     rcx, [rdi+60h]
0x180007750  test    rcx, rcx
0x180007753  jz      short loc_180007768
0x180007755  test    rax, rax
0x180007758  jnz     short loc_180007762
0x18000775a  test    rdx, rdx
0x18000775d  jz      short loc_180007768
0x18000775f  mov     rax, rdx
0x180007762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007767  nop
0x180007768  mov     rbx, [rdi+58h]
0x18000776c  mov     qword ptr [rdi+58h], 0
0x180007774  test    rbx, rbx
0x180007777  jz      short loc_18000778D
0x180007779  call    cs:__imp_GetProcessHeap
0x18000777f  mov     rcx, rax; hHeap
0x180007782  mov     r8, rbx; lpMem
0x180007785  xor     edx, edx; dwFlags
0x180007787  call    cs:__imp_HeapFree
0x18000778d  mov     rbx, [rdi+38h]
0x180007791  mov     qword ptr [rdi+38h], 0
0x180007799  test    rbx, rbx
0x18000779c  jz      short loc_1800077B2
0x18000779e  call    cs:__imp_GetProcessHeap
0x1800077a4  mov     rcx, rax; hHeap
0x1800077a7  mov     r8, rbx; lpMem
0x1800077aa  xor     edx, edx; dwFlags
0x1800077ac  call    cs:__imp_HeapFree
0x1800077b2  mov     rbx, [rdi+10h]
0x1800077b6  test    rbx, rbx
0x1800077b9  jz      short loc_1800077E4
0x1800077bb  xor     r9d, r9d; msWindowLength
0x1800077be  xor     r8d, r8d; msPeriod
0x1800077c1  xor     edx, edx; pftDueTime
0x1800077c3  mov     rcx, rbx; pti
0x1800077c6  call    cs:__imp_SetThreadpoolTimer
0x1800077cc  mov     edx, 1; fCancelPendingCallbacks
0x1800077d1  mov     rcx, rbx; pti
0x1800077d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800077da  mov     rcx, rbx; pti
0x1800077dd  call    cs:__imp_CloseThreadpoolTimer
0x1800077e3  nop
0x1800077e4  mov     rbx, [rsp+28h+arg_0]
0x1800077e9  mov     rsi, [rsp+28h+arg_8]
0x1800077ee  add     rsp, 20h
0x1800077f2  pop     rdi
0x1800077f3  retn
```
