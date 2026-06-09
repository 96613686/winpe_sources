# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000cfc8`
- end: `0x18000d120`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18018cb10`

## callees

- `0x18000cfc8`
- `0x18001017c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d01b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cffc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d0f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cffc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d0f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d013`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d109`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d013`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d109`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d00a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d100`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d00a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d100`

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
0x18000cfc8  mov     [rsp+arg_0], rbx
0x18000cfcd  mov     [rsp+arg_8], rsi
0x18000cfd2  push    rdi
0x18000cfd3  sub     rsp, 20h
0x18000cfd7  mov     rdi, rcx
0x18000cfda  mov     dword ptr [rcx], 0
0x18000cfe0  mov     rsi, [rcx+10h]
0x18000cfe4  test    rsi, rsi
0x18000cfe7  jz      short loc_18000D021
0x18000cfe9  call    cs:__imp_GetLastError
0x18000cfef  mov     ebx, eax
0x18000cff1  xor     r9d, r9d; msWindowLength
0x18000cff4  xor     r8d, r8d; msPeriod
0x18000cff7  xor     edx, edx; pftDueTime
0x18000cff9  mov     rcx, rsi; pti
0x18000cffc  call    cs:__imp_SetThreadpoolTimer
0x18000d002  mov     edx, 1; fCancelPendingCallbacks
0x18000d007  mov     rcx, rsi; pti
0x18000d00a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d010  mov     rcx, rsi; pti
0x18000d013  call    cs:__imp_CloseThreadpoolTimer
0x18000d019  mov     ecx, ebx; dwErrCode
0x18000d01b  call    cs:__imp_SetLastError
0x18000d021  mov     qword ptr [rdi+10h], 0
0x18000d029  mov     rcx, rdi; this
0x18000d02c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000d031  mov     rcx, [rdi+68h]
0x18000d035  test    rcx, rcx
0x18000d038  jz      short loc_18000D06A
0x18000d03a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d041  test    rax, rax
0x18000d044  jnz     short loc_18000D055
0x18000d046  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d04d  test    rdx, rdx
0x18000d050  jz      short loc_18000D068
0x18000d052  mov     rax, rdx
0x18000d055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d05a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d061  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d068  jmp     short loc_18000D078
0x18000d06a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000d071  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000d078  mov     rcx, [rdi+60h]
0x18000d07c  test    rcx, rcx
0x18000d07f  jz      short loc_18000D094
0x18000d081  test    rax, rax
0x18000d084  jnz     short loc_18000D08E
0x18000d086  test    rdx, rdx
0x18000d089  jz      short loc_18000D094
0x18000d08b  mov     rax, rdx
0x18000d08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d093  nop
0x18000d094  mov     rbx, [rdi+58h]
0x18000d098  mov     qword ptr [rdi+58h], 0
0x18000d0a0  test    rbx, rbx
0x18000d0a3  jz      short loc_18000D0B9
0x18000d0a5  call    cs:__imp_GetProcessHeap
0x18000d0ab  mov     rcx, rax; hHeap
0x18000d0ae  mov     r8, rbx; lpMem
0x18000d0b1  xor     edx, edx; dwFlags
0x18000d0b3  call    cs:__imp_HeapFree
0x18000d0b9  mov     rbx, [rdi+38h]
0x18000d0bd  mov     qword ptr [rdi+38h], 0
0x18000d0c5  test    rbx, rbx
0x18000d0c8  jz      short loc_18000D0DE
0x18000d0ca  call    cs:__imp_GetProcessHeap
0x18000d0d0  mov     rcx, rax; hHeap
0x18000d0d3  mov     r8, rbx; lpMem
0x18000d0d6  xor     edx, edx; dwFlags
0x18000d0d8  call    cs:__imp_HeapFree
0x18000d0de  mov     rbx, [rdi+10h]
0x18000d0e2  test    rbx, rbx
0x18000d0e5  jz      short loc_18000D110
0x18000d0e7  xor     r9d, r9d; msWindowLength
0x18000d0ea  xor     r8d, r8d; msPeriod
0x18000d0ed  xor     edx, edx; pftDueTime
0x18000d0ef  mov     rcx, rbx; pti
0x18000d0f2  call    cs:__imp_SetThreadpoolTimer
0x18000d0f8  mov     edx, 1; fCancelPendingCallbacks
0x18000d0fd  mov     rcx, rbx; pti
0x18000d100  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d106  mov     rcx, rbx; pti
0x18000d109  call    cs:__imp_CloseThreadpoolTimer
0x18000d10f  nop
0x18000d110  mov     rbx, [rsp+28h+arg_0]
0x18000d115  mov     rsi, [rsp+28h+arg_8]
0x18000d11a  add     rsp, 20h
0x18000d11e  pop     rdi
0x18000d11f  retn
```
