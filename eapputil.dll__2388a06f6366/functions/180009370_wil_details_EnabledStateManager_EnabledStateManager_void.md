# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009370`
- end: `0x1800094c8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032a30`

## callees

- `0x180009370`
- `0x18000a57c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000944d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000944d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000945b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000945b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009480`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009391`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800093bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800094b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800093bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800094b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800093a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000949a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800093a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000949a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800093b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800094a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800093b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800094a8`

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
0x180009370  mov     [rsp+arg_0], rbx
0x180009375  mov     [rsp+arg_8], rsi
0x18000937a  push    rdi
0x18000937b  sub     rsp, 20h
0x18000937f  mov     rdi, rcx
0x180009382  mov     dword ptr [rcx], 0
0x180009388  mov     rsi, [rcx+10h]
0x18000938c  test    rsi, rsi
0x18000938f  jz      short loc_1800093C9
0x180009391  call    cs:__imp_GetLastError
0x180009397  mov     ebx, eax
0x180009399  xor     r9d, r9d; msWindowLength
0x18000939c  xor     r8d, r8d; msPeriod
0x18000939f  xor     edx, edx; pftDueTime
0x1800093a1  mov     rcx, rsi; pti
0x1800093a4  call    cs:__imp_SetThreadpoolTimer
0x1800093aa  mov     edx, 1; fCancelPendingCallbacks
0x1800093af  mov     rcx, rsi; pti
0x1800093b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800093b8  mov     rcx, rsi; pti
0x1800093bb  call    cs:__imp_CloseThreadpoolTimer
0x1800093c1  mov     ecx, ebx; dwErrCode
0x1800093c3  call    cs:__imp_SetLastError
0x1800093c9  mov     qword ptr [rdi+10h], 0
0x1800093d1  mov     rcx, rdi; this
0x1800093d4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800093d9  mov     rcx, [rdi+68h]
0x1800093dd  test    rcx, rcx
0x1800093e0  jz      short loc_180009412
0x1800093e2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800093e9  test    rax, rax
0x1800093ec  jnz     short loc_1800093FD
0x1800093ee  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800093f5  test    rdx, rdx
0x1800093f8  jz      short loc_180009410
0x1800093fa  mov     rax, rdx
0x1800093fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009402  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009409  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009410  jmp     short loc_180009420
0x180009412  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009419  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009420  mov     rcx, [rdi+60h]
0x180009424  test    rcx, rcx
0x180009427  jz      short loc_18000943C
0x180009429  test    rax, rax
0x18000942c  jnz     short loc_180009436
0x18000942e  test    rdx, rdx
0x180009431  jz      short loc_18000943C
0x180009433  mov     rax, rdx
0x180009436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943b  nop
0x18000943c  mov     rbx, [rdi+58h]
0x180009440  mov     qword ptr [rdi+58h], 0
0x180009448  test    rbx, rbx
0x18000944b  jz      short loc_180009461
0x18000944d  call    cs:__imp_GetProcessHeap
0x180009453  mov     rcx, rax; hHeap
0x180009456  mov     r8, rbx; lpMem
0x180009459  xor     edx, edx; dwFlags
0x18000945b  call    cs:__imp_HeapFree
0x180009461  mov     rbx, [rdi+38h]
0x180009465  mov     qword ptr [rdi+38h], 0
0x18000946d  test    rbx, rbx
0x180009470  jz      short loc_180009486
0x180009472  call    cs:__imp_GetProcessHeap
0x180009478  mov     rcx, rax; hHeap
0x18000947b  mov     r8, rbx; lpMem
0x18000947e  xor     edx, edx; dwFlags
0x180009480  call    cs:__imp_HeapFree
0x180009486  mov     rbx, [rdi+10h]
0x18000948a  test    rbx, rbx
0x18000948d  jz      short loc_1800094B8
0x18000948f  xor     r9d, r9d; msWindowLength
0x180009492  xor     r8d, r8d; msPeriod
0x180009495  xor     edx, edx; pftDueTime
0x180009497  mov     rcx, rbx; pti
0x18000949a  call    cs:__imp_SetThreadpoolTimer
0x1800094a0  mov     edx, 1; fCancelPendingCallbacks
0x1800094a5  mov     rcx, rbx; pti
0x1800094a8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800094ae  mov     rcx, rbx; pti
0x1800094b1  call    cs:__imp_CloseThreadpoolTimer
0x1800094b7  nop
0x1800094b8  mov     rbx, [rsp+28h+arg_0]
0x1800094bd  mov     rsi, [rsp+28h+arg_8]
0x1800094c2  add     rsp, 20h
0x1800094c6  pop     rdi
0x1800094c7  retn
```
