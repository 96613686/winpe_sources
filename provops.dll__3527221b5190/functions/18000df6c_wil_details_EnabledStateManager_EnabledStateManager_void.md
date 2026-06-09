# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000df6c`
- end: `0x18000e0c4`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180036c60`

## callees

- `0x18000df6c`
- `0x1800142b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e07c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e07c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e06e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dfa0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e096`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dfa0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e096`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000dfb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e0ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000dfb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e0ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000dfae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e0a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000dfae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e0a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
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
0x18000df6c  mov     [rsp+arg_0], rbx
0x18000df71  mov     [rsp+arg_8], rsi
0x18000df76  push    rdi
0x18000df77  sub     rsp, 20h
0x18000df7b  mov     rdi, rcx
0x18000df7e  mov     dword ptr [rcx], 0
0x18000df84  mov     rsi, [rcx+10h]
0x18000df88  test    rsi, rsi
0x18000df8b  jz      short loc_18000DFC5
0x18000df8d  call    cs:__imp_GetLastError
0x18000df93  mov     ebx, eax
0x18000df95  xor     r9d, r9d; msWindowLength
0x18000df98  xor     r8d, r8d; msPeriod
0x18000df9b  xor     edx, edx; pftDueTime
0x18000df9d  mov     rcx, rsi; pti
0x18000dfa0  call    cs:__imp_SetThreadpoolTimer
0x18000dfa6  mov     edx, 1; fCancelPendingCallbacks
0x18000dfab  mov     rcx, rsi; pti
0x18000dfae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000dfb4  mov     rcx, rsi; pti
0x18000dfb7  call    cs:__imp_CloseThreadpoolTimer
0x18000dfbd  mov     ecx, ebx; dwErrCode
0x18000dfbf  call    cs:__imp_SetLastError
0x18000dfc5  mov     qword ptr [rdi+10h], 0
0x18000dfcd  mov     rcx, rdi; this
0x18000dfd0  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000dfd5  mov     rcx, [rdi+68h]
0x18000dfd9  test    rcx, rcx
0x18000dfdc  jz      short loc_18000E00E
0x18000dfde  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000dfe5  test    rax, rax
0x18000dfe8  jnz     short loc_18000DFF9
0x18000dfea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000dff1  test    rdx, rdx
0x18000dff4  jz      short loc_18000E00C
0x18000dff6  mov     rax, rdx
0x18000dff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dffe  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000e005  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000e00c  jmp     short loc_18000E01C
0x18000e00e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000e015  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000e01c  mov     rcx, [rdi+60h]
0x18000e020  test    rcx, rcx
0x18000e023  jz      short loc_18000E038
0x18000e025  test    rax, rax
0x18000e028  jnz     short loc_18000E032
0x18000e02a  test    rdx, rdx
0x18000e02d  jz      short loc_18000E038
0x18000e02f  mov     rax, rdx
0x18000e032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e037  nop
0x18000e038  mov     rbx, [rdi+58h]
0x18000e03c  mov     qword ptr [rdi+58h], 0
0x18000e044  test    rbx, rbx
0x18000e047  jz      short loc_18000E05D
0x18000e049  call    cs:__imp_GetProcessHeap
0x18000e04f  mov     rcx, rax; hHeap
0x18000e052  mov     r8, rbx; lpMem
0x18000e055  xor     edx, edx; dwFlags
0x18000e057  call    cs:__imp_HeapFree
0x18000e05d  mov     rbx, [rdi+38h]
0x18000e061  mov     qword ptr [rdi+38h], 0
0x18000e069  test    rbx, rbx
0x18000e06c  jz      short loc_18000E082
0x18000e06e  call    cs:__imp_GetProcessHeap
0x18000e074  mov     rcx, rax; hHeap
0x18000e077  mov     r8, rbx; lpMem
0x18000e07a  xor     edx, edx; dwFlags
0x18000e07c  call    cs:__imp_HeapFree
0x18000e082  mov     rbx, [rdi+10h]
0x18000e086  test    rbx, rbx
0x18000e089  jz      short loc_18000E0B4
0x18000e08b  xor     r9d, r9d; msWindowLength
0x18000e08e  xor     r8d, r8d; msPeriod
0x18000e091  xor     edx, edx; pftDueTime
0x18000e093  mov     rcx, rbx; pti
0x18000e096  call    cs:__imp_SetThreadpoolTimer
0x18000e09c  mov     edx, 1; fCancelPendingCallbacks
0x18000e0a1  mov     rcx, rbx; pti
0x18000e0a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e0aa  mov     rcx, rbx; pti
0x18000e0ad  call    cs:__imp_CloseThreadpoolTimer
0x18000e0b3  nop
0x18000e0b4  mov     rbx, [rsp+28h+arg_0]
0x18000e0b9  mov     rsi, [rsp+28h+arg_8]
0x18000e0be  add     rsp, 20h
0x18000e0c2  pop     rdi
0x18000e0c3  retn
```
