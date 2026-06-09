# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18006cf20`
- end: `0x18006d078`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1802a8620`

## callees

- `0x18006cf20`
- `0x180073168`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cffd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d022`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cffd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d022`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d00b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d00b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006cf6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d061`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006cf6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d061`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006cf62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d058`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006cf62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d058`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006cf54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d04a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006cf54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d04a`

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
0x18006cf20  mov     [rsp+arg_0], rbx
0x18006cf25  mov     [rsp+arg_8], rsi
0x18006cf2a  push    rdi
0x18006cf2b  sub     rsp, 20h
0x18006cf2f  mov     rdi, rcx
0x18006cf32  mov     dword ptr [rcx], 0
0x18006cf38  mov     rsi, [rcx+10h]
0x18006cf3c  test    rsi, rsi
0x18006cf3f  jz      short loc_18006CF79
0x18006cf41  call    cs:__imp_GetLastError
0x18006cf47  mov     ebx, eax
0x18006cf49  xor     r9d, r9d; msWindowLength
0x18006cf4c  xor     r8d, r8d; msPeriod
0x18006cf4f  xor     edx, edx; pftDueTime
0x18006cf51  mov     rcx, rsi; pti
0x18006cf54  call    cs:__imp_SetThreadpoolTimer
0x18006cf5a  mov     edx, 1; fCancelPendingCallbacks
0x18006cf5f  mov     rcx, rsi; pti
0x18006cf62  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006cf68  mov     rcx, rsi; pti
0x18006cf6b  call    cs:__imp_CloseThreadpoolTimer
0x18006cf71  mov     ecx, ebx; dwErrCode
0x18006cf73  call    cs:__imp_SetLastError
0x18006cf79  mov     qword ptr [rdi+10h], 0
0x18006cf81  mov     rcx, rdi; this
0x18006cf84  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18006cf89  mov     rcx, [rdi+68h]
0x18006cf8d  test    rcx, rcx
0x18006cf90  jz      short loc_18006CFC2
0x18006cf92  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006cf99  test    rax, rax
0x18006cf9c  jnz     short loc_18006CFAD
0x18006cf9e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006cfa5  test    rdx, rdx
0x18006cfa8  jz      short loc_18006CFC0
0x18006cfaa  mov     rax, rdx
0x18006cfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfb2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006cfb9  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006cfc0  jmp     short loc_18006CFD0
0x18006cfc2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18006cfc9  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18006cfd0  mov     rcx, [rdi+60h]
0x18006cfd4  test    rcx, rcx
0x18006cfd7  jz      short loc_18006CFEC
0x18006cfd9  test    rax, rax
0x18006cfdc  jnz     short loc_18006CFE6
0x18006cfde  test    rdx, rdx
0x18006cfe1  jz      short loc_18006CFEC
0x18006cfe3  mov     rax, rdx
0x18006cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfeb  nop
0x18006cfec  mov     rbx, [rdi+58h]
0x18006cff0  mov     qword ptr [rdi+58h], 0
0x18006cff8  test    rbx, rbx
0x18006cffb  jz      short loc_18006D011
0x18006cffd  call    cs:__imp_GetProcessHeap
0x18006d003  mov     rcx, rax; hHeap
0x18006d006  mov     r8, rbx; lpMem
0x18006d009  xor     edx, edx; dwFlags
0x18006d00b  call    cs:__imp_HeapFree
0x18006d011  mov     rbx, [rdi+38h]
0x18006d015  mov     qword ptr [rdi+38h], 0
0x18006d01d  test    rbx, rbx
0x18006d020  jz      short loc_18006D036
0x18006d022  call    cs:__imp_GetProcessHeap
0x18006d028  mov     rcx, rax; hHeap
0x18006d02b  mov     r8, rbx; lpMem
0x18006d02e  xor     edx, edx; dwFlags
0x18006d030  call    cs:__imp_HeapFree
0x18006d036  mov     rbx, [rdi+10h]
0x18006d03a  test    rbx, rbx
0x18006d03d  jz      short loc_18006D068
0x18006d03f  xor     r9d, r9d; msWindowLength
0x18006d042  xor     r8d, r8d; msPeriod
0x18006d045  xor     edx, edx; pftDueTime
0x18006d047  mov     rcx, rbx; pti
0x18006d04a  call    cs:__imp_SetThreadpoolTimer
0x18006d050  mov     edx, 1; fCancelPendingCallbacks
0x18006d055  mov     rcx, rbx; pti
0x18006d058  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006d05e  mov     rcx, rbx; pti
0x18006d061  call    cs:__imp_CloseThreadpoolTimer
0x18006d067  nop
0x18006d068  mov     rbx, [rsp+28h+arg_0]
0x18006d06d  mov     rsi, [rsp+28h+arg_8]
0x18006d072  add     rsp, 20h
0x18006d076  pop     rdi
0x18006d077  retn
```
