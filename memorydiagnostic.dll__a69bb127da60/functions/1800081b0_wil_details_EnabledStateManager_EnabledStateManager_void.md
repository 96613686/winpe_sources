# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800081b0`
- end: `0x180008308`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022150`

## callees

- `0x1800081b0`
- `0x18000e750`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000828d`
- `KERNEL32!GetProcessHeap` at `0x1800082b2`
- `KERNEL32!GetProcessHeap` at `0x18000828d`
- `KERNEL32!GetProcessHeap` at `0x1800082b2`
- `KERNEL32!SetThreadpoolTimer` at `0x1800081e4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800082da`
- `KERNEL32!SetThreadpoolTimer` at `0x1800081e4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800082da`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800081fb`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800082f1`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800081fb`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800082f1`
- `KERNEL32!GetLastError` at `0x1800081d1`
- `KERNEL32!GetLastError` at `0x1800081d1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800081f2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800082e8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800081f2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800082e8`
- `KERNEL32!SetLastError` at `0x180008203`
- `KERNEL32!SetLastError` at `0x180008203`
- `KERNEL32!HeapFree` at `0x18000829b`
- `KERNEL32!HeapFree` at `0x1800082c0`
- `KERNEL32!HeapFree` at `0x18000829b`
- `KERNEL32!HeapFree` at `0x1800082c0`

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
0x1800081b0  mov     [rsp+arg_0], rbx
0x1800081b5  mov     [rsp+arg_8], rsi
0x1800081ba  push    rdi
0x1800081bb  sub     rsp, 20h
0x1800081bf  mov     rdi, rcx
0x1800081c2  mov     dword ptr [rcx], 0
0x1800081c8  mov     rsi, [rcx+10h]
0x1800081cc  test    rsi, rsi
0x1800081cf  jz      short loc_180008209
0x1800081d1  call    cs:__imp_GetLastError
0x1800081d7  mov     ebx, eax
0x1800081d9  xor     r9d, r9d; msWindowLength
0x1800081dc  xor     r8d, r8d; msPeriod
0x1800081df  xor     edx, edx; pftDueTime
0x1800081e1  mov     rcx, rsi; pti
0x1800081e4  call    cs:__imp_SetThreadpoolTimer
0x1800081ea  mov     edx, 1; fCancelPendingCallbacks
0x1800081ef  mov     rcx, rsi; pti
0x1800081f2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800081f8  mov     rcx, rsi; pti
0x1800081fb  call    cs:__imp_CloseThreadpoolTimer
0x180008201  mov     ecx, ebx; dwErrCode
0x180008203  call    cs:__imp_SetLastError
0x180008209  mov     qword ptr [rdi+10h], 0
0x180008211  mov     rcx, rdi; this
0x180008214  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180008219  mov     rcx, [rdi+68h]
0x18000821d  test    rcx, rcx
0x180008220  jz      short loc_180008252
0x180008222  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008229  test    rax, rax
0x18000822c  jnz     short loc_18000823D
0x18000822e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008235  test    rdx, rdx
0x180008238  jz      short loc_180008250
0x18000823a  mov     rax, rdx
0x18000823d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008242  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008249  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008250  jmp     short loc_180008260
0x180008252  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008259  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008260  mov     rcx, [rdi+60h]
0x180008264  test    rcx, rcx
0x180008267  jz      short loc_18000827C
0x180008269  test    rax, rax
0x18000826c  jnz     short loc_180008276
0x18000826e  test    rdx, rdx
0x180008271  jz      short loc_18000827C
0x180008273  mov     rax, rdx
0x180008276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827b  nop
0x18000827c  mov     rbx, [rdi+58h]
0x180008280  mov     qword ptr [rdi+58h], 0
0x180008288  test    rbx, rbx
0x18000828b  jz      short loc_1800082A1
0x18000828d  call    cs:__imp_GetProcessHeap
0x180008293  mov     rcx, rax; hHeap
0x180008296  mov     r8, rbx; lpMem
0x180008299  xor     edx, edx; dwFlags
0x18000829b  call    cs:__imp_HeapFree
0x1800082a1  mov     rbx, [rdi+38h]
0x1800082a5  mov     qword ptr [rdi+38h], 0
0x1800082ad  test    rbx, rbx
0x1800082b0  jz      short loc_1800082C6
0x1800082b2  call    cs:__imp_GetProcessHeap
0x1800082b8  mov     rcx, rax; hHeap
0x1800082bb  mov     r8, rbx; lpMem
0x1800082be  xor     edx, edx; dwFlags
0x1800082c0  call    cs:__imp_HeapFree
0x1800082c6  mov     rbx, [rdi+10h]
0x1800082ca  test    rbx, rbx
0x1800082cd  jz      short loc_1800082F8
0x1800082cf  xor     r9d, r9d; msWindowLength
0x1800082d2  xor     r8d, r8d; msPeriod
0x1800082d5  xor     edx, edx; pftDueTime
0x1800082d7  mov     rcx, rbx; pti
0x1800082da  call    cs:__imp_SetThreadpoolTimer
0x1800082e0  mov     edx, 1; fCancelPendingCallbacks
0x1800082e5  mov     rcx, rbx; pti
0x1800082e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082ee  mov     rcx, rbx; pti
0x1800082f1  call    cs:__imp_CloseThreadpoolTimer
0x1800082f7  nop
0x1800082f8  mov     rbx, [rsp+28h+arg_0]
0x1800082fd  mov     rsi, [rsp+28h+arg_8]
0x180008302  add     rsp, 20h
0x180008306  pop     rdi
0x180008307  retn
```
