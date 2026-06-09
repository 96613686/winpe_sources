# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003d58`
- end: `0x180003e9e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027390`

## callees

- `0x180003d58`
- `0x180007514`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003da3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003da3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e7f`

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
0x180003d58  mov     [rsp+arg_0], rbx
0x180003d5d  mov     [rsp+arg_8], rsi
0x180003d62  push    rdi
0x180003d63  sub     rsp, 20h
0x180003d67  mov     dword ptr [rcx], 0
0x180003d6d  mov     rdi, rcx
0x180003d70  mov     rsi, [rcx+10h]
0x180003d74  test    rsi, rsi
0x180003d77  jz      short loc_180003DB1
0x180003d79  call    cs:__imp_GetLastError
0x180003d7f  xor     r9d, r9d; msWindowLength
0x180003d82  xor     r8d, r8d; msPeriod
0x180003d85  xor     edx, edx; pftDueTime
0x180003d87  mov     rcx, rsi; pti
0x180003d8a  mov     ebx, eax
0x180003d8c  call    cs:__imp_SetThreadpoolTimer
0x180003d92  mov     edx, 1; fCancelPendingCallbacks
0x180003d97  mov     rcx, rsi; pti
0x180003d9a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003da0  mov     rcx, rsi; pti
0x180003da3  call    cs:__imp_CloseThreadpoolTimer
0x180003da9  mov     ecx, ebx; dwErrCode
0x180003dab  call    cs:__imp_SetLastError
0x180003db1  mov     rcx, rdi; this
0x180003db4  mov     qword ptr [rdi+10h], 0
0x180003dbc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003dc1  mov     rcx, [rdi+68h]
0x180003dc5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003dcc  test    rcx, rcx
0x180003dcf  jz      short loc_180003DF1
0x180003dd1  test    rax, rax
0x180003dd4  jnz     short loc_180003DE5
0x180003dd6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003ddd  test    rdx, rdx
0x180003de0  jz      short loc_180003DF8
0x180003de2  mov     rax, rdx
0x180003de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dea  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003df1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003df8  mov     rcx, [rdi+60h]
0x180003dfc  test    rcx, rcx
0x180003dff  jz      short loc_180003E13
0x180003e01  test    rax, rax
0x180003e04  jnz     short loc_180003E0E
0x180003e06  test    rdx, rdx
0x180003e09  jz      short loc_180003E13
0x180003e0b  mov     rax, rdx
0x180003e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e13  mov     rbx, [rdi+58h]
0x180003e17  mov     qword ptr [rdi+58h], 0
0x180003e1f  test    rbx, rbx
0x180003e22  jz      short loc_180003E38
0x180003e24  call    cs:__imp_GetProcessHeap
0x180003e2a  mov     r8, rbx; lpMem
0x180003e2d  xor     edx, edx; dwFlags
0x180003e2f  mov     rcx, rax; hHeap
0x180003e32  call    cs:__imp_HeapFree
0x180003e38  mov     rbx, [rdi+38h]
0x180003e3c  mov     qword ptr [rdi+38h], 0
0x180003e44  test    rbx, rbx
0x180003e47  jz      short loc_180003E5D
0x180003e49  call    cs:__imp_GetProcessHeap
0x180003e4f  mov     r8, rbx; lpMem
0x180003e52  xor     edx, edx; dwFlags
0x180003e54  mov     rcx, rax; hHeap
0x180003e57  call    cs:__imp_HeapFree
0x180003e5d  mov     rbx, [rdi+10h]
0x180003e61  test    rbx, rbx
0x180003e64  jz      short loc_180003E8E
0x180003e66  xor     r9d, r9d; msWindowLength
0x180003e69  xor     r8d, r8d; msPeriod
0x180003e6c  xor     edx, edx; pftDueTime
0x180003e6e  mov     rcx, rbx; pti
0x180003e71  call    cs:__imp_SetThreadpoolTimer
0x180003e77  mov     edx, 1; fCancelPendingCallbacks
0x180003e7c  mov     rcx, rbx; pti
0x180003e7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e85  mov     rcx, rbx; pti
0x180003e88  call    cs:__imp_CloseThreadpoolTimer
0x180003e8e  mov     rbx, [rsp+28h+arg_0]
0x180003e93  mov     rsi, [rsp+28h+arg_8]
0x180003e98  add     rsp, 20h
0x180003e9c  pop     rdi
0x180003e9d  retn
```
