# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003c38`
- end: `0x180003d90`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011f50`

## callees

- `0x180003c38`
- `0x18000695c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d79`

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
0x180003c38  mov     [rsp+arg_0], rbx
0x180003c3d  mov     [rsp+arg_8], rsi
0x180003c42  push    rdi
0x180003c43  sub     rsp, 20h
0x180003c47  mov     rdi, rcx
0x180003c4a  mov     dword ptr [rcx], 0
0x180003c50  mov     rsi, [rcx+10h]
0x180003c54  test    rsi, rsi
0x180003c57  jz      short loc_180003C91
0x180003c59  call    cs:__imp_GetLastError
0x180003c5f  mov     ebx, eax
0x180003c61  xor     r9d, r9d; msWindowLength
0x180003c64  xor     r8d, r8d; msPeriod
0x180003c67  xor     edx, edx; pftDueTime
0x180003c69  mov     rcx, rsi; pti
0x180003c6c  call    cs:__imp_SetThreadpoolTimer
0x180003c72  mov     edx, 1; fCancelPendingCallbacks
0x180003c77  mov     rcx, rsi; pti
0x180003c7a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c80  mov     rcx, rsi; pti
0x180003c83  call    cs:__imp_CloseThreadpoolTimer
0x180003c89  mov     ecx, ebx; dwErrCode
0x180003c8b  call    cs:__imp_SetLastError
0x180003c91  mov     qword ptr [rdi+10h], 0
0x180003c99  mov     rcx, rdi; this
0x180003c9c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003ca1  mov     rcx, [rdi+68h]
0x180003ca5  test    rcx, rcx
0x180003ca8  jz      short loc_180003CDA
0x180003caa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003cb1  test    rax, rax
0x180003cb4  jnz     short loc_180003CC5
0x180003cb6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003cbd  test    rdx, rdx
0x180003cc0  jz      short loc_180003CD8
0x180003cc2  mov     rax, rdx
0x180003cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cca  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003cd1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003cd8  jmp     short loc_180003CE8
0x180003cda  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003ce1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003ce8  mov     rcx, [rdi+60h]
0x180003cec  test    rcx, rcx
0x180003cef  jz      short loc_180003D04
0x180003cf1  test    rax, rax
0x180003cf4  jnz     short loc_180003CFE
0x180003cf6  test    rdx, rdx
0x180003cf9  jz      short loc_180003D04
0x180003cfb  mov     rax, rdx
0x180003cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d03  nop
0x180003d04  mov     rbx, [rdi+58h]
0x180003d08  mov     qword ptr [rdi+58h], 0
0x180003d10  test    rbx, rbx
0x180003d13  jz      short loc_180003D29
0x180003d15  call    cs:__imp_GetProcessHeap
0x180003d1b  mov     rcx, rax; hHeap
0x180003d1e  mov     r8, rbx; lpMem
0x180003d21  xor     edx, edx; dwFlags
0x180003d23  call    cs:__imp_HeapFree
0x180003d29  mov     rbx, [rdi+38h]
0x180003d2d  mov     qword ptr [rdi+38h], 0
0x180003d35  test    rbx, rbx
0x180003d38  jz      short loc_180003D4E
0x180003d3a  call    cs:__imp_GetProcessHeap
0x180003d40  mov     rcx, rax; hHeap
0x180003d43  mov     r8, rbx; lpMem
0x180003d46  xor     edx, edx; dwFlags
0x180003d48  call    cs:__imp_HeapFree
0x180003d4e  mov     rbx, [rdi+10h]
0x180003d52  test    rbx, rbx
0x180003d55  jz      short loc_180003D80
0x180003d57  xor     r9d, r9d; msWindowLength
0x180003d5a  xor     r8d, r8d; msPeriod
0x180003d5d  xor     edx, edx; pftDueTime
0x180003d5f  mov     rcx, rbx; pti
0x180003d62  call    cs:__imp_SetThreadpoolTimer
0x180003d68  mov     edx, 1; fCancelPendingCallbacks
0x180003d6d  mov     rcx, rbx; pti
0x180003d70  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003d76  mov     rcx, rbx; pti
0x180003d79  call    cs:__imp_CloseThreadpoolTimer
0x180003d7f  nop
0x180003d80  mov     rbx, [rsp+28h+arg_0]
0x180003d85  mov     rsi, [rsp+28h+arg_8]
0x180003d8a  add     rsp, 20h
0x180003d8e  pop     rdi
0x180003d8f  retn
```
