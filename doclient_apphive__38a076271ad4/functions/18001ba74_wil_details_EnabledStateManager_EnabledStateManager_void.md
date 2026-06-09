# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18001ba74`
- end: `0x18001bbcc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180118e20`

## callees

- `0x18001ba74`
- `0x18001bc68`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bac4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bac4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001babc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbb5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001babc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bab3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bbac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bab3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bbac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001baa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bb9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001baa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bb9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bafc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bafc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001baee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001baee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb13`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x18001ba74  mov     [rsp+arg_0], rbx
0x18001ba79  mov     [rsp+arg_8], rsi
0x18001ba7e  push    rdi
0x18001ba7f  sub     rsp, 20h
0x18001ba83  mov     rdi, rcx
0x18001ba86  mov     byte ptr [rcx], 0
0x18001ba89  mov     rsi, [rcx+10h]
0x18001ba8d  test    rsi, rsi
0x18001ba90  jz      short loc_18001BACA
0x18001ba92  call    cs:__imp_GetLastError
0x18001ba98  mov     ebx, eax
0x18001ba9a  xor     r9d, r9d; msWindowLength
0x18001ba9d  xor     r8d, r8d; msPeriod
0x18001baa0  xor     edx, edx; pftDueTime
0x18001baa2  mov     rcx, rsi; pti
0x18001baa5  call    cs:__imp_SetThreadpoolTimer
0x18001baab  mov     edx, 1; fCancelPendingCallbacks
0x18001bab0  mov     rcx, rsi; pti
0x18001bab3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bab9  mov     rcx, rsi; pti
0x18001babc  call    cs:__imp_CloseThreadpoolTimer
0x18001bac2  mov     ecx, ebx; dwErrCode
0x18001bac4  call    cs:__imp_SetLastError
0x18001baca  mov     qword ptr [rdi+10h], 0
0x18001bad2  mov     byte ptr [rdi], 0
0x18001bad5  mov     rcx, rdi; this
0x18001bad8  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18001badd  mov     rbx, [rdi+68h]
0x18001bae1  mov     qword ptr [rdi+68h], 0
0x18001bae9  test    rbx, rbx
0x18001baec  jz      short loc_18001BB02
0x18001baee  call    cs:__imp_GetProcessHeap
0x18001baf4  mov     rcx, rax; hHeap
0x18001baf7  mov     r8, rbx; lpMem
0x18001bafa  xor     edx, edx; dwFlags
0x18001bafc  call    cs:__imp_HeapFree
0x18001bb02  mov     rbx, [rdi+48h]
0x18001bb06  mov     qword ptr [rdi+48h], 0
0x18001bb0e  test    rbx, rbx
0x18001bb11  jz      short loc_18001BB27
0x18001bb13  call    cs:__imp_GetProcessHeap
0x18001bb19  mov     rcx, rax; hHeap
0x18001bb1c  mov     r8, rbx; lpMem
0x18001bb1f  xor     edx, edx; dwFlags
0x18001bb21  call    cs:__imp_HeapFree
0x18001bb27  mov     rcx, [rdi+28h]
0x18001bb2b  test    rcx, rcx
0x18001bb2e  jz      short loc_18001BB60
0x18001bb30  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001bb37  test    rax, rax
0x18001bb3a  jnz     short loc_18001BB4B
0x18001bb3c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001bb43  test    rdx, rdx
0x18001bb46  jz      short loc_18001BB5E
0x18001bb48  mov     rax, rdx
0x18001bb4b  call    _guard_dispatch_icall
0x18001bb50  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001bb57  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001bb5e  jmp     short loc_18001BB6E
0x18001bb60  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001bb67  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001bb6e  mov     rcx, [rdi+20h]
0x18001bb72  test    rcx, rcx
0x18001bb75  jz      short loc_18001BB8A
0x18001bb77  test    rax, rax
0x18001bb7a  jnz     short loc_18001BB84
0x18001bb7c  test    rdx, rdx
0x18001bb7f  jz      short loc_18001BB8A
0x18001bb81  mov     rax, rdx
0x18001bb84  call    _guard_dispatch_icall
0x18001bb89  nop
0x18001bb8a  mov     rbx, [rdi+10h]
0x18001bb8e  test    rbx, rbx
0x18001bb91  jz      short loc_18001BBBC
0x18001bb93  xor     r9d, r9d; msWindowLength
0x18001bb96  xor     r8d, r8d; msPeriod
0x18001bb99  xor     edx, edx; pftDueTime
0x18001bb9b  mov     rcx, rbx; pti
0x18001bb9e  call    cs:__imp_SetThreadpoolTimer
0x18001bba4  mov     edx, 1; fCancelPendingCallbacks
0x18001bba9  mov     rcx, rbx; pti
0x18001bbac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bbb2  mov     rcx, rbx; pti
0x18001bbb5  call    cs:__imp_CloseThreadpoolTimer
0x18001bbbb  nop
0x18001bbbc  mov     rbx, [rsp+28h+arg_0]
0x18001bbc1  mov     rsi, [rsp+28h+arg_8]
0x18001bbc6  add     rsp, 20h
0x18001bbca  pop     rdi
0x18001bbcb  retn
```
