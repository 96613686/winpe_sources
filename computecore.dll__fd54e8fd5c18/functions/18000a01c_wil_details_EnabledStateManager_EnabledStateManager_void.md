# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000a01c`
- end: `0x18000a174`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a1950`

## callees

- `0x18000a01c`
- `0x18000d70c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a12c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a12c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a11e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a11e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a06f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a067`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a15d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a067`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a15d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a05e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a154`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a05e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a154`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a050`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a146`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a050`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a146`

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
0x18000a01c  mov     [rsp+arg_0], rbx
0x18000a021  mov     [rsp+arg_8], rsi
0x18000a026  push    rdi
0x18000a027  sub     rsp, 20h
0x18000a02b  mov     rdi, rcx
0x18000a02e  mov     dword ptr [rcx], 0
0x18000a034  mov     rsi, [rcx+10h]
0x18000a038  test    rsi, rsi
0x18000a03b  jz      short loc_18000A075
0x18000a03d  call    cs:__imp_GetLastError
0x18000a043  mov     ebx, eax
0x18000a045  xor     r9d, r9d; msWindowLength
0x18000a048  xor     r8d, r8d; msPeriod
0x18000a04b  xor     edx, edx; pftDueTime
0x18000a04d  mov     rcx, rsi; pti
0x18000a050  call    cs:__imp_SetThreadpoolTimer
0x18000a056  mov     edx, 1; fCancelPendingCallbacks
0x18000a05b  mov     rcx, rsi; pti
0x18000a05e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a064  mov     rcx, rsi; pti
0x18000a067  call    cs:__imp_CloseThreadpoolTimer
0x18000a06d  mov     ecx, ebx; dwErrCode
0x18000a06f  call    cs:__imp_SetLastError
0x18000a075  mov     qword ptr [rdi+10h], 0
0x18000a07d  mov     rcx, rdi; this
0x18000a080  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000a085  mov     rcx, [rdi+68h]
0x18000a089  test    rcx, rcx
0x18000a08c  jz      short loc_18000A0BE
0x18000a08e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a095  test    rax, rax
0x18000a098  jnz     short loc_18000A0A9
0x18000a09a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a0a1  test    rdx, rdx
0x18000a0a4  jz      short loc_18000A0BC
0x18000a0a6  mov     rax, rdx
0x18000a0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0ae  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a0b5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a0bc  jmp     short loc_18000A0CC
0x18000a0be  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a0c5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a0cc  mov     rcx, [rdi+60h]
0x18000a0d0  test    rcx, rcx
0x18000a0d3  jz      short loc_18000A0E8
0x18000a0d5  test    rax, rax
0x18000a0d8  jnz     short loc_18000A0E2
0x18000a0da  test    rdx, rdx
0x18000a0dd  jz      short loc_18000A0E8
0x18000a0df  mov     rax, rdx
0x18000a0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e7  nop
0x18000a0e8  mov     rbx, [rdi+58h]
0x18000a0ec  mov     qword ptr [rdi+58h], 0
0x18000a0f4  test    rbx, rbx
0x18000a0f7  jz      short loc_18000A10D
0x18000a0f9  call    cs:__imp_GetProcessHeap
0x18000a0ff  mov     rcx, rax; hHeap
0x18000a102  mov     r8, rbx; lpMem
0x18000a105  xor     edx, edx; dwFlags
0x18000a107  call    cs:__imp_HeapFree
0x18000a10d  mov     rbx, [rdi+38h]
0x18000a111  mov     qword ptr [rdi+38h], 0
0x18000a119  test    rbx, rbx
0x18000a11c  jz      short loc_18000A132
0x18000a11e  call    cs:__imp_GetProcessHeap
0x18000a124  mov     rcx, rax; hHeap
0x18000a127  mov     r8, rbx; lpMem
0x18000a12a  xor     edx, edx; dwFlags
0x18000a12c  call    cs:__imp_HeapFree
0x18000a132  mov     rbx, [rdi+10h]
0x18000a136  test    rbx, rbx
0x18000a139  jz      short loc_18000A164
0x18000a13b  xor     r9d, r9d; msWindowLength
0x18000a13e  xor     r8d, r8d; msPeriod
0x18000a141  xor     edx, edx; pftDueTime
0x18000a143  mov     rcx, rbx; pti
0x18000a146  call    cs:__imp_SetThreadpoolTimer
0x18000a14c  mov     edx, 1; fCancelPendingCallbacks
0x18000a151  mov     rcx, rbx; pti
0x18000a154  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a15a  mov     rcx, rbx; pti
0x18000a15d  call    cs:__imp_CloseThreadpoolTimer
0x18000a163  nop
0x18000a164  mov     rbx, [rsp+28h+arg_0]
0x18000a169  mov     rsi, [rsp+28h+arg_8]
0x18000a16e  add     rsp, 20h
0x18000a172  pop     rdi
0x18000a173  retn
```
