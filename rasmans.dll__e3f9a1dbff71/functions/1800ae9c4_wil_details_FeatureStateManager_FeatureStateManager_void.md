# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800ae9c4`
- end: `0x1800aebb0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800e8380`

## callees

- `0x1800ae5d8`
- `0x1800ae9c4`
- `0x1800b67c4`
- `0x1800b7974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae9e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae9e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aeae9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aeb2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aeae9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aeb2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aea90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aeae0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aeb20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aea90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aeae0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aeb20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aea82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aead2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aeb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aea82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aead2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aeb12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aea03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aea4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aeb52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aeb83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aea03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aea4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aeb52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aeb83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aea0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aea55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aeb5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aeb8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aea0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aea55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aeb5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aeb8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae9f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aea3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aeb44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aeb75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae9f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aea3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aeb44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aeb75`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_18010A270 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18010A270[25], qword_18010A270, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x1800ae9c4  mov     [rsp+arg_0], rbx
0x1800ae9c9  mov     [rsp+arg_8], rsi
0x1800ae9ce  push    rdi
0x1800ae9cf  sub     rsp, 20h
0x1800ae9d3  mov     byte ptr [rcx], 0
0x1800ae9d6  mov     rdi, rcx
0x1800ae9d9  mov     rsi, [rcx+30h]
0x1800ae9dd  test    rsi, rsi
0x1800ae9e0  jz      short loc_1800AEA1A
0x1800ae9e2  call    cs:__imp_GetLastError
0x1800ae9e8  xor     r9d, r9d; msWindowLength
0x1800ae9eb  xor     r8d, r8d; msPeriod
0x1800ae9ee  xor     edx, edx; pftDueTime
0x1800ae9f0  mov     rcx, rsi; pti
0x1800ae9f3  mov     ebx, eax
0x1800ae9f5  call    cs:__imp_SetThreadpoolTimer
0x1800ae9fb  mov     edx, 1; fCancelPendingCallbacks
0x1800aea00  mov     rcx, rsi; pti
0x1800aea03  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aea09  mov     rcx, rsi; pti
0x1800aea0c  call    cs:__imp_CloseThreadpoolTimer
0x1800aea12  mov     ecx, ebx; dwErrCode
0x1800aea14  call    cs:__imp_SetLastError
0x1800aea1a  mov     qword ptr [rdi+30h], 0
0x1800aea22  mov     rsi, [rdi+38h]
0x1800aea26  test    rsi, rsi
0x1800aea29  jz      short loc_1800AEA63
0x1800aea2b  call    cs:__imp_GetLastError
0x1800aea31  xor     r9d, r9d; msWindowLength
0x1800aea34  xor     r8d, r8d; msPeriod
0x1800aea37  xor     edx, edx; pftDueTime
0x1800aea39  mov     rcx, rsi; pti
0x1800aea3c  mov     ebx, eax
0x1800aea3e  call    cs:__imp_SetThreadpoolTimer
0x1800aea44  mov     edx, 1; fCancelPendingCallbacks
0x1800aea49  mov     rcx, rsi; pti
0x1800aea4c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aea52  mov     rcx, rsi; pti
0x1800aea55  call    cs:__imp_CloseThreadpoolTimer
0x1800aea5b  mov     ecx, ebx; dwErrCode
0x1800aea5d  call    cs:__imp_SetLastError
0x1800aea63  mov     qword ptr [rdi+38h], 0
0x1800aea6b  mov     rbx, [rdi+100h]
0x1800aea72  mov     qword ptr [rdi+100h], 0
0x1800aea7d  test    rbx, rbx
0x1800aea80  jz      short loc_1800AEA96
0x1800aea82  call    cs:__imp_GetProcessHeap
0x1800aea88  mov     r8, rbx; lpMem
0x1800aea8b  xor     edx, edx; dwFlags
0x1800aea8d  mov     rcx, rax; hHeap
0x1800aea90  call    cs:__imp_HeapFree
0x1800aea96  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800aea9d  test    r8, r8
0x1800aeaa0  jz      short loc_1800AEABA
0x1800aeaa2  mov     rdx, cs:qword_18010A270; SRWLock
0x1800aeaa9  test    rdx, rdx
0x1800aeaac  jz      short loc_1800AEABA
0x1800aeaae  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800aeab5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800aeaba  lea     rbx, [rdi+98h]
0x1800aeac1  mov     rsi, [rbx+40h]
0x1800aeac5  mov     qword ptr [rbx+40h], 0
0x1800aeacd  test    rsi, rsi
0x1800aead0  jz      short loc_1800AEAE6
0x1800aead2  call    cs:__imp_GetProcessHeap
0x1800aead8  mov     r8, rsi; lpMem
0x1800aeadb  xor     edx, edx; dwFlags
0x1800aeadd  mov     rcx, rax; hHeap
0x1800aeae0  call    cs:__imp_HeapFree
0x1800aeae6  mov     rcx, rbx; lpCriticalSection
0x1800aeae9  call    cs:__imp_DeleteCriticalSection
0x1800aeaef  lea     rcx, [rdi+90h]
0x1800aeaf6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aeafb  mov     rsi, [rdi+88h]
0x1800aeb02  mov     qword ptr [rdi+88h], 0
0x1800aeb0d  test    rsi, rsi
0x1800aeb10  jz      short loc_1800AEB26
0x1800aeb12  call    cs:__imp_GetProcessHeap
0x1800aeb18  mov     r8, rsi; lpMem
0x1800aeb1b  xor     edx, edx; dwFlags
0x1800aeb1d  mov     rcx, rax; hHeap
0x1800aeb20  call    cs:__imp_HeapFree
0x1800aeb26  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800aeb2a  call    cs:__imp_DeleteCriticalSection
0x1800aeb30  mov     rbx, [rdi+38h]
0x1800aeb34  test    rbx, rbx
0x1800aeb37  jz      short loc_1800AEB61
0x1800aeb39  xor     r9d, r9d; msWindowLength
0x1800aeb3c  xor     r8d, r8d; msPeriod
0x1800aeb3f  xor     edx, edx; pftDueTime
0x1800aeb41  mov     rcx, rbx; pti
0x1800aeb44  call    cs:__imp_SetThreadpoolTimer
0x1800aeb4a  mov     edx, 1; fCancelPendingCallbacks
0x1800aeb4f  mov     rcx, rbx; pti
0x1800aeb52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aeb58  mov     rcx, rbx; pti
0x1800aeb5b  call    cs:__imp_CloseThreadpoolTimer
0x1800aeb61  mov     rbx, [rdi+30h]
0x1800aeb65  test    rbx, rbx
0x1800aeb68  jz      short loc_1800AEB92
0x1800aeb6a  xor     r9d, r9d; msWindowLength
0x1800aeb6d  xor     r8d, r8d; msPeriod
0x1800aeb70  xor     edx, edx; pftDueTime
0x1800aeb72  mov     rcx, rbx; pti
0x1800aeb75  call    cs:__imp_SetThreadpoolTimer
0x1800aeb7b  mov     edx, 1; fCancelPendingCallbacks
0x1800aeb80  mov     rcx, rbx; pti
0x1800aeb83  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aeb89  mov     rcx, rbx; pti
0x1800aeb8c  call    cs:__imp_CloseThreadpoolTimer
0x1800aeb92  mov     rcx, [rdi+10h]; lpMem
0x1800aeb96  test    rcx, rcx
0x1800aeb99  jz      short loc_1800AEBA0
0x1800aeb9b  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800aeba0  mov     rbx, [rsp+28h+arg_0]
0x1800aeba5  mov     rsi, [rsp+28h+arg_8]
0x1800aebaa  add     rsp, 20h
0x1800aebae  pop     rdi
0x1800aebaf  retn
```
