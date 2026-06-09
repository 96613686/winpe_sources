# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800035ec`
- end: `0x1800037d8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cca0`

## callees

- `0x18000335c`
- `0x1800035ec`
- `0x1800077a4`
- `0x18000886c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003711`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003752`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003711`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003752`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003748`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003748`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000373a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000373a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000360a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000360a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003653`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000363c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003685`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000363c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003685`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000361d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003666`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000376c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000379d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000361d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003666`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000376c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000379d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003634`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000367d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003634`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000367d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000362b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003674`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000377a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000362b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003674`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000377a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037ab`

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
  if ( v8 && qword_1800120D8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800120D8[25], qword_1800120D8, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x1800035ec  mov     [rsp+arg_0], rbx
0x1800035f1  mov     [rsp+arg_8], rsi
0x1800035f6  push    rdi
0x1800035f7  sub     rsp, 20h
0x1800035fb  mov     byte ptr [rcx], 0
0x1800035fe  mov     rdi, rcx
0x180003601  mov     rsi, [rcx+30h]
0x180003605  test    rsi, rsi
0x180003608  jz      short loc_180003642
0x18000360a  call    cs:__imp_GetLastError
0x180003610  xor     r9d, r9d; msWindowLength
0x180003613  xor     r8d, r8d; msPeriod
0x180003616  xor     edx, edx; pftDueTime
0x180003618  mov     rcx, rsi; pti
0x18000361b  mov     ebx, eax
0x18000361d  call    cs:__imp_SetThreadpoolTimer
0x180003623  mov     edx, 1; fCancelPendingCallbacks
0x180003628  mov     rcx, rsi; pti
0x18000362b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003631  mov     rcx, rsi; pti
0x180003634  call    cs:__imp_CloseThreadpoolTimer
0x18000363a  mov     ecx, ebx; dwErrCode
0x18000363c  call    cs:__imp_SetLastError
0x180003642  mov     qword ptr [rdi+30h], 0
0x18000364a  mov     rsi, [rdi+38h]
0x18000364e  test    rsi, rsi
0x180003651  jz      short loc_18000368B
0x180003653  call    cs:__imp_GetLastError
0x180003659  xor     r9d, r9d; msWindowLength
0x18000365c  xor     r8d, r8d; msPeriod
0x18000365f  xor     edx, edx; pftDueTime
0x180003661  mov     rcx, rsi; pti
0x180003664  mov     ebx, eax
0x180003666  call    cs:__imp_SetThreadpoolTimer
0x18000366c  mov     edx, 1; fCancelPendingCallbacks
0x180003671  mov     rcx, rsi; pti
0x180003674  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000367a  mov     rcx, rsi; pti
0x18000367d  call    cs:__imp_CloseThreadpoolTimer
0x180003683  mov     ecx, ebx; dwErrCode
0x180003685  call    cs:__imp_SetLastError
0x18000368b  mov     qword ptr [rdi+38h], 0
0x180003693  mov     rbx, [rdi+100h]
0x18000369a  mov     qword ptr [rdi+100h], 0
0x1800036a5  test    rbx, rbx
0x1800036a8  jz      short loc_1800036BE
0x1800036aa  call    cs:__imp_GetProcessHeap
0x1800036b0  mov     r8, rbx; lpMem
0x1800036b3  xor     edx, edx; dwFlags
0x1800036b5  mov     rcx, rax; hHeap
0x1800036b8  call    cs:__imp_HeapFree
0x1800036be  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800036c5  test    r8, r8
0x1800036c8  jz      short loc_1800036E2
0x1800036ca  mov     rdx, cs:qword_1800120D8; SRWLock
0x1800036d1  test    rdx, rdx
0x1800036d4  jz      short loc_1800036E2
0x1800036d6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800036dd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800036e2  lea     rbx, [rdi+98h]
0x1800036e9  mov     rsi, [rbx+40h]
0x1800036ed  mov     qword ptr [rbx+40h], 0
0x1800036f5  test    rsi, rsi
0x1800036f8  jz      short loc_18000370E
0x1800036fa  call    cs:__imp_GetProcessHeap
0x180003700  mov     r8, rsi; lpMem
0x180003703  xor     edx, edx; dwFlags
0x180003705  mov     rcx, rax; hHeap
0x180003708  call    cs:__imp_HeapFree
0x18000370e  mov     rcx, rbx; lpCriticalSection
0x180003711  call    cs:__imp_DeleteCriticalSection
0x180003717  lea     rcx, [rdi+90h]
0x18000371e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003723  mov     rsi, [rdi+88h]
0x18000372a  mov     qword ptr [rdi+88h], 0
0x180003735  test    rsi, rsi
0x180003738  jz      short loc_18000374E
0x18000373a  call    cs:__imp_GetProcessHeap
0x180003740  mov     r8, rsi; lpMem
0x180003743  xor     edx, edx; dwFlags
0x180003745  mov     rcx, rax; hHeap
0x180003748  call    cs:__imp_HeapFree
0x18000374e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003752  call    cs:__imp_DeleteCriticalSection
0x180003758  mov     rbx, [rdi+38h]
0x18000375c  test    rbx, rbx
0x18000375f  jz      short loc_180003789
0x180003761  xor     r9d, r9d; msWindowLength
0x180003764  xor     r8d, r8d; msPeriod
0x180003767  xor     edx, edx; pftDueTime
0x180003769  mov     rcx, rbx; pti
0x18000376c  call    cs:__imp_SetThreadpoolTimer
0x180003772  mov     edx, 1; fCancelPendingCallbacks
0x180003777  mov     rcx, rbx; pti
0x18000377a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003780  mov     rcx, rbx; pti
0x180003783  call    cs:__imp_CloseThreadpoolTimer
0x180003789  mov     rbx, [rdi+30h]
0x18000378d  test    rbx, rbx
0x180003790  jz      short loc_1800037BA
0x180003792  xor     r9d, r9d; msWindowLength
0x180003795  xor     r8d, r8d; msPeriod
0x180003798  xor     edx, edx; pftDueTime
0x18000379a  mov     rcx, rbx; pti
0x18000379d  call    cs:__imp_SetThreadpoolTimer
0x1800037a3  mov     edx, 1; fCancelPendingCallbacks
0x1800037a8  mov     rcx, rbx; pti
0x1800037ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037b1  mov     rcx, rbx; pti
0x1800037b4  call    cs:__imp_CloseThreadpoolTimer
0x1800037ba  mov     rcx, [rdi+10h]; lpMem
0x1800037be  test    rcx, rcx
0x1800037c1  jz      short loc_1800037C8
0x1800037c3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800037c8  mov     rbx, [rsp+28h+arg_0]
0x1800037cd  mov     rsi, [rsp+28h+arg_8]
0x1800037d2  add     rsp, 20h
0x1800037d6  pop     rdi
0x1800037d7  retn
```
