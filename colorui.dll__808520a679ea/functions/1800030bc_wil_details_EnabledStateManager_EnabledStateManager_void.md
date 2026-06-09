# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800030bc`
- end: `0x180003202`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018960`

## callees

- `0x1800030bc`
- `0x180007688`
- `0x180019010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800030fe`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800031e3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800030fe`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800031e3`
- `KERNEL32!GetLastError` at `0x1800030dd`
- `KERNEL32!GetLastError` at `0x1800030dd`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003107`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800031ec`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003107`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800031ec`
- `KERNEL32!SetThreadpoolTimer` at `0x1800030f0`
- `KERNEL32!SetThreadpoolTimer` at `0x1800031d5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800030f0`
- `KERNEL32!SetThreadpoolTimer` at `0x1800031d5`
- `KERNEL32!GetProcessHeap` at `0x180003188`
- `KERNEL32!GetProcessHeap` at `0x1800031ad`
- `KERNEL32!GetProcessHeap` at `0x180003188`
- `KERNEL32!GetProcessHeap` at `0x1800031ad`
- `KERNEL32!HeapFree` at `0x180003196`
- `KERNEL32!HeapFree` at `0x1800031bb`
- `KERNEL32!HeapFree` at `0x180003196`
- `KERNEL32!HeapFree` at `0x1800031bb`
- `KERNEL32!SetLastError` at `0x18000310f`
- `KERNEL32!SetLastError` at `0x18000310f`

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
0x1800030bc  mov     [rsp+arg_0], rbx
0x1800030c1  mov     [rsp+arg_8], rsi
0x1800030c6  push    rdi
0x1800030c7  sub     rsp, 20h
0x1800030cb  mov     dword ptr [rcx], 0
0x1800030d1  mov     rdi, rcx
0x1800030d4  mov     rsi, [rcx+10h]
0x1800030d8  test    rsi, rsi
0x1800030db  jz      short loc_180003115
0x1800030dd  call    cs:__imp_GetLastError
0x1800030e3  xor     r9d, r9d; msWindowLength
0x1800030e6  xor     r8d, r8d; msPeriod
0x1800030e9  xor     edx, edx; pftDueTime
0x1800030eb  mov     rcx, rsi; pti
0x1800030ee  mov     ebx, eax
0x1800030f0  call    cs:__imp_SetThreadpoolTimer
0x1800030f6  mov     edx, 1; fCancelPendingCallbacks
0x1800030fb  mov     rcx, rsi; pti
0x1800030fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003104  mov     rcx, rsi; pti
0x180003107  call    cs:__imp_CloseThreadpoolTimer
0x18000310d  mov     ecx, ebx; dwErrCode
0x18000310f  call    cs:__imp_SetLastError
0x180003115  mov     rcx, rdi; this
0x180003118  mov     qword ptr [rdi+10h], 0
0x180003120  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003125  mov     rcx, [rdi+68h]
0x180003129  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003130  test    rcx, rcx
0x180003133  jz      short loc_180003155
0x180003135  test    rax, rax
0x180003138  jnz     short loc_180003149
0x18000313a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003141  test    rdx, rdx
0x180003144  jz      short loc_18000315C
0x180003146  mov     rax, rdx
0x180003149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003155  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000315c  mov     rcx, [rdi+60h]
0x180003160  test    rcx, rcx
0x180003163  jz      short loc_180003177
0x180003165  test    rax, rax
0x180003168  jnz     short loc_180003172
0x18000316a  test    rdx, rdx
0x18000316d  jz      short loc_180003177
0x18000316f  mov     rax, rdx
0x180003172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003177  mov     rbx, [rdi+58h]
0x18000317b  mov     qword ptr [rdi+58h], 0
0x180003183  test    rbx, rbx
0x180003186  jz      short loc_18000319C
0x180003188  call    cs:__imp_GetProcessHeap
0x18000318e  mov     r8, rbx; lpMem
0x180003191  xor     edx, edx; dwFlags
0x180003193  mov     rcx, rax; hHeap
0x180003196  call    cs:__imp_HeapFree
0x18000319c  mov     rbx, [rdi+38h]
0x1800031a0  mov     qword ptr [rdi+38h], 0
0x1800031a8  test    rbx, rbx
0x1800031ab  jz      short loc_1800031C1
0x1800031ad  call    cs:__imp_GetProcessHeap
0x1800031b3  mov     r8, rbx; lpMem
0x1800031b6  xor     edx, edx; dwFlags
0x1800031b8  mov     rcx, rax; hHeap
0x1800031bb  call    cs:__imp_HeapFree
0x1800031c1  mov     rbx, [rdi+10h]
0x1800031c5  test    rbx, rbx
0x1800031c8  jz      short loc_1800031F2
0x1800031ca  xor     r9d, r9d; msWindowLength
0x1800031cd  xor     r8d, r8d; msPeriod
0x1800031d0  xor     edx, edx; pftDueTime
0x1800031d2  mov     rcx, rbx; pti
0x1800031d5  call    cs:__imp_SetThreadpoolTimer
0x1800031db  mov     edx, 1; fCancelPendingCallbacks
0x1800031e0  mov     rcx, rbx; pti
0x1800031e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800031e9  mov     rcx, rbx; pti
0x1800031ec  call    cs:__imp_CloseThreadpoolTimer
0x1800031f2  mov     rbx, [rsp+28h+arg_0]
0x1800031f7  mov     rsi, [rsp+28h+arg_8]
0x1800031fc  add     rsp, 20h
0x180003200  pop     rdi
0x180003201  retn
```
