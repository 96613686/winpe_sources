# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003b84`
- end: `0x180003cdc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015fe0`

## callees

- `0x180003b84`
- `0x1800068e4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003cae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003cae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bcf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003cc5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bcf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003cc5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003cbc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003cbc`

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
0x180003b84  mov     [rsp+arg_0], rbx
0x180003b89  mov     [rsp+arg_8], rsi
0x180003b8e  push    rdi
0x180003b8f  sub     rsp, 20h
0x180003b93  mov     rdi, rcx
0x180003b96  mov     dword ptr [rcx], 0
0x180003b9c  mov     rsi, [rcx+10h]
0x180003ba0  test    rsi, rsi
0x180003ba3  jz      short loc_180003BDD
0x180003ba5  call    cs:__imp_GetLastError
0x180003bab  mov     ebx, eax
0x180003bad  xor     r9d, r9d; msWindowLength
0x180003bb0  xor     r8d, r8d; msPeriod
0x180003bb3  xor     edx, edx; pftDueTime
0x180003bb5  mov     rcx, rsi; pti
0x180003bb8  call    cs:__imp_SetThreadpoolTimer
0x180003bbe  mov     edx, 1; fCancelPendingCallbacks
0x180003bc3  mov     rcx, rsi; pti
0x180003bc6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003bcc  mov     rcx, rsi; pti
0x180003bcf  call    cs:__imp_CloseThreadpoolTimer
0x180003bd5  mov     ecx, ebx; dwErrCode
0x180003bd7  call    cs:__imp_SetLastError
0x180003bdd  mov     qword ptr [rdi+10h], 0
0x180003be5  mov     rcx, rdi; this
0x180003be8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003bed  mov     rcx, [rdi+68h]
0x180003bf1  test    rcx, rcx
0x180003bf4  jz      short loc_180003C26
0x180003bf6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003bfd  test    rax, rax
0x180003c00  jnz     short loc_180003C11
0x180003c02  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003c09  test    rdx, rdx
0x180003c0c  jz      short loc_180003C24
0x180003c0e  mov     rax, rdx
0x180003c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c16  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003c1d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003c24  jmp     short loc_180003C34
0x180003c26  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003c2d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003c34  mov     rcx, [rdi+60h]
0x180003c38  test    rcx, rcx
0x180003c3b  jz      short loc_180003C50
0x180003c3d  test    rax, rax
0x180003c40  jnz     short loc_180003C4A
0x180003c42  test    rdx, rdx
0x180003c45  jz      short loc_180003C50
0x180003c47  mov     rax, rdx
0x180003c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4f  nop
0x180003c50  mov     rbx, [rdi+58h]
0x180003c54  mov     qword ptr [rdi+58h], 0
0x180003c5c  test    rbx, rbx
0x180003c5f  jz      short loc_180003C75
0x180003c61  call    cs:__imp_GetProcessHeap
0x180003c67  mov     rcx, rax; hHeap
0x180003c6a  mov     r8, rbx; lpMem
0x180003c6d  xor     edx, edx; dwFlags
0x180003c6f  call    cs:__imp_HeapFree
0x180003c75  mov     rbx, [rdi+38h]
0x180003c79  mov     qword ptr [rdi+38h], 0
0x180003c81  test    rbx, rbx
0x180003c84  jz      short loc_180003C9A
0x180003c86  call    cs:__imp_GetProcessHeap
0x180003c8c  mov     rcx, rax; hHeap
0x180003c8f  mov     r8, rbx; lpMem
0x180003c92  xor     edx, edx; dwFlags
0x180003c94  call    cs:__imp_HeapFree
0x180003c9a  mov     rbx, [rdi+10h]
0x180003c9e  test    rbx, rbx
0x180003ca1  jz      short loc_180003CCC
0x180003ca3  xor     r9d, r9d; msWindowLength
0x180003ca6  xor     r8d, r8d; msPeriod
0x180003ca9  xor     edx, edx; pftDueTime
0x180003cab  mov     rcx, rbx; pti
0x180003cae  call    cs:__imp_SetThreadpoolTimer
0x180003cb4  mov     edx, 1; fCancelPendingCallbacks
0x180003cb9  mov     rcx, rbx; pti
0x180003cbc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003cc2  mov     rcx, rbx; pti
0x180003cc5  call    cs:__imp_CloseThreadpoolTimer
0x180003ccb  nop
0x180003ccc  mov     rbx, [rsp+28h+arg_0]
0x180003cd1  mov     rsi, [rsp+28h+arg_8]
0x180003cd6  add     rsp, 20h
0x180003cda  pop     rdi
0x180003cdb  retn
```
