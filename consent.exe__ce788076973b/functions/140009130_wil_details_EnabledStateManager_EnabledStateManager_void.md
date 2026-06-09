# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140009130`
- end: `0x14000926d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `317`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e910`

## callees

- `0x140009130`
- `0x140016cbc`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000921e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000921e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000920b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000922c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000920b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000922c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000917b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000917b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009149`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009173`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000925d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009173`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000925d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000916a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009254`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000916a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009254`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000915c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009246`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000915c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009246`

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
0x140009130  push    rbx
0x140009132  push    rbp
0x140009133  push    rsi
0x140009134  push    rdi
0x140009135  sub     rsp, 28h
0x140009139  mov     rdi, rcx
0x14000913c  xor     ebp, ebp
0x14000913e  mov     [rcx], ebp
0x140009140  mov     rsi, [rcx+10h]
0x140009144  test    rsi, rsi
0x140009147  jz      short loc_140009181
0x140009149  call    cs:__imp_GetLastError
0x14000914f  mov     ebx, eax
0x140009151  xor     r9d, r9d; msWindowLength
0x140009154  xor     r8d, r8d; msPeriod
0x140009157  xor     edx, edx; pftDueTime
0x140009159  mov     rcx, rsi; pti
0x14000915c  call    cs:__imp_SetThreadpoolTimer
0x140009162  mov     edx, 1; fCancelPendingCallbacks
0x140009167  mov     rcx, rsi; pti
0x14000916a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009170  mov     rcx, rsi; pti
0x140009173  call    cs:__imp_CloseThreadpoolTimer
0x140009179  mov     ecx, ebx; dwErrCode
0x14000917b  call    cs:__imp_SetLastError
0x140009181  mov     [rdi+10h], rbp
0x140009185  mov     rcx, rdi; this
0x140009188  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000918d  mov     rcx, [rdi+68h]
0x140009191  test    rcx, rcx
0x140009194  jz      short loc_1400091C6
0x140009196  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000919d  test    rax, rax
0x1400091a0  jnz     short loc_1400091B1
0x1400091a2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400091a9  test    rdx, rdx
0x1400091ac  jz      short loc_1400091C4
0x1400091ae  mov     rax, rdx
0x1400091b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400091bd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400091c4  jmp     short loc_1400091D4
0x1400091c6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400091cd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400091d4  mov     rcx, [rdi+60h]
0x1400091d8  test    rcx, rcx
0x1400091db  jz      short loc_1400091F0
0x1400091dd  test    rax, rax
0x1400091e0  jnz     short loc_1400091EA
0x1400091e2  test    rdx, rdx
0x1400091e5  jz      short loc_1400091F0
0x1400091e7  mov     rax, rdx
0x1400091ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091ef  nop
0x1400091f0  mov     rbx, [rdi+58h]
0x1400091f4  mov     [rdi+58h], rbp
0x1400091f8  test    rbx, rbx
0x1400091fb  jz      short loc_140009211
0x1400091fd  call    cs:__imp_GetProcessHeap
0x140009203  mov     rcx, rax; hHeap
0x140009206  mov     r8, rbx; lpMem
0x140009209  xor     edx, edx; dwFlags
0x14000920b  call    cs:__imp_HeapFree
0x140009211  mov     rbx, [rdi+38h]
0x140009215  mov     [rdi+38h], rbp
0x140009219  test    rbx, rbx
0x14000921c  jz      short loc_140009232
0x14000921e  call    cs:__imp_GetProcessHeap
0x140009224  mov     rcx, rax; hHeap
0x140009227  mov     r8, rbx; lpMem
0x14000922a  xor     edx, edx; dwFlags
0x14000922c  call    cs:__imp_HeapFree
0x140009232  mov     rbx, [rdi+10h]
0x140009236  test    rbx, rbx
0x140009239  jz      short loc_140009264
0x14000923b  xor     r9d, r9d; msWindowLength
0x14000923e  xor     r8d, r8d; msPeriod
0x140009241  xor     edx, edx; pftDueTime
0x140009243  mov     rcx, rbx; pti
0x140009246  call    cs:__imp_SetThreadpoolTimer
0x14000924c  mov     edx, 1; fCancelPendingCallbacks
0x140009251  mov     rcx, rbx; pti
0x140009254  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000925a  mov     rcx, rbx; pti
0x14000925d  call    cs:__imp_CloseThreadpoolTimer
0x140009263  nop
0x140009264  add     rsp, 28h
0x140009268  pop     rdi
0x140009269  pop     rsi
0x14000926a  pop     rbp
0x14000926b  pop     rbx
0x14000926c  retn
```
