# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800039cc`
- end: `0x180003b12`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800124d0`

## callees

- `0x1800039cc`
- `0x1800052a0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003afc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003afc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ae5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ae5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003af3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003af3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003abd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003acb`

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
0x1800039cc  mov     [rsp+arg_0], rbx
0x1800039d1  mov     [rsp+arg_8], rsi
0x1800039d6  push    rdi
0x1800039d7  sub     rsp, 20h
0x1800039db  mov     dword ptr [rcx], 0
0x1800039e1  mov     rdi, rcx
0x1800039e4  mov     rsi, [rcx+10h]
0x1800039e8  test    rsi, rsi
0x1800039eb  jz      short loc_180003A25
0x1800039ed  call    cs:__imp_GetLastError
0x1800039f3  xor     r9d, r9d; msWindowLength
0x1800039f6  xor     r8d, r8d; msPeriod
0x1800039f9  xor     edx, edx; pftDueTime
0x1800039fb  mov     rcx, rsi; pti
0x1800039fe  mov     ebx, eax
0x180003a00  call    cs:__imp_SetThreadpoolTimer
0x180003a06  mov     edx, 1; fCancelPendingCallbacks
0x180003a0b  mov     rcx, rsi; pti
0x180003a0e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a14  mov     rcx, rsi; pti
0x180003a17  call    cs:__imp_CloseThreadpoolTimer
0x180003a1d  mov     ecx, ebx; dwErrCode
0x180003a1f  call    cs:__imp_SetLastError
0x180003a25  mov     rcx, rdi; this
0x180003a28  mov     qword ptr [rdi+10h], 0
0x180003a30  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003a35  mov     rcx, [rdi+68h]
0x180003a39  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a40  test    rcx, rcx
0x180003a43  jz      short loc_180003A65
0x180003a45  test    rax, rax
0x180003a48  jnz     short loc_180003A59
0x180003a4a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a51  test    rdx, rdx
0x180003a54  jz      short loc_180003A6C
0x180003a56  mov     rax, rdx
0x180003a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a65  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a6c  mov     rcx, [rdi+60h]
0x180003a70  test    rcx, rcx
0x180003a73  jz      short loc_180003A87
0x180003a75  test    rax, rax
0x180003a78  jnz     short loc_180003A82
0x180003a7a  test    rdx, rdx
0x180003a7d  jz      short loc_180003A87
0x180003a7f  mov     rax, rdx
0x180003a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a87  mov     rbx, [rdi+58h]
0x180003a8b  mov     qword ptr [rdi+58h], 0
0x180003a93  test    rbx, rbx
0x180003a96  jz      short loc_180003AAC
0x180003a98  call    cs:__imp_GetProcessHeap
0x180003a9e  mov     r8, rbx; lpMem
0x180003aa1  xor     edx, edx; dwFlags
0x180003aa3  mov     rcx, rax; hHeap
0x180003aa6  call    cs:__imp_HeapFree
0x180003aac  mov     rbx, [rdi+38h]
0x180003ab0  mov     qword ptr [rdi+38h], 0
0x180003ab8  test    rbx, rbx
0x180003abb  jz      short loc_180003AD1
0x180003abd  call    cs:__imp_GetProcessHeap
0x180003ac3  mov     r8, rbx; lpMem
0x180003ac6  xor     edx, edx; dwFlags
0x180003ac8  mov     rcx, rax; hHeap
0x180003acb  call    cs:__imp_HeapFree
0x180003ad1  mov     rbx, [rdi+10h]
0x180003ad5  test    rbx, rbx
0x180003ad8  jz      short loc_180003B02
0x180003ada  xor     r9d, r9d; msWindowLength
0x180003add  xor     r8d, r8d; msPeriod
0x180003ae0  xor     edx, edx; pftDueTime
0x180003ae2  mov     rcx, rbx; pti
0x180003ae5  call    cs:__imp_SetThreadpoolTimer
0x180003aeb  mov     edx, 1; fCancelPendingCallbacks
0x180003af0  mov     rcx, rbx; pti
0x180003af3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003af9  mov     rcx, rbx; pti
0x180003afc  call    cs:__imp_CloseThreadpoolTimer
0x180003b02  mov     rbx, [rsp+28h+arg_0]
0x180003b07  mov     rsi, [rsp+28h+arg_8]
0x180003b0c  add     rsp, 20h
0x180003b10  pop     rdi
0x180003b11  retn
```
