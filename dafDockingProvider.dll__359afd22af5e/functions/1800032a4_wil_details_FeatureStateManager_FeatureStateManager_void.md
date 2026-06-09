# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800032a4`
- end: `0x180003492`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e370`

## callees

- `0x180003160`
- `0x1800032a4`
- `0x1800068c4`
- `0x180007980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000340a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000340a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003400`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000330b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000330b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000333d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000333d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000332c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003432`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003463`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000332c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003432`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000331e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003424`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000331e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003424`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003455`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003335`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000343b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000346c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003335`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000343b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000346c`

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
  if ( v8 && qword_180026068 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180026068[25], qword_180026068, v8);
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
0x1800032a4  mov     [rsp+arg_0], rbx
0x1800032a9  mov     [rsp+arg_8], rsi
0x1800032ae  push    rdi
0x1800032af  sub     rsp, 20h
0x1800032b3  mov     rdi, rcx
0x1800032b6  mov     byte ptr [rcx], 0
0x1800032b9  mov     rsi, [rcx+30h]
0x1800032bd  test    rsi, rsi
0x1800032c0  jz      short loc_1800032FA
0x1800032c2  call    cs:__imp_GetLastError
0x1800032c8  mov     ebx, eax
0x1800032ca  xor     r9d, r9d; msWindowLength
0x1800032cd  xor     r8d, r8d; msPeriod
0x1800032d0  xor     edx, edx; pftDueTime
0x1800032d2  mov     rcx, rsi; pti
0x1800032d5  call    cs:__imp_SetThreadpoolTimer
0x1800032db  mov     edx, 1; fCancelPendingCallbacks
0x1800032e0  mov     rcx, rsi; pti
0x1800032e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800032e9  mov     rcx, rsi; pti
0x1800032ec  call    cs:__imp_CloseThreadpoolTimer
0x1800032f2  mov     ecx, ebx; dwErrCode
0x1800032f4  call    cs:__imp_SetLastError
0x1800032fa  mov     qword ptr [rdi+30h], 0
0x180003302  mov     rsi, [rdi+38h]
0x180003306  test    rsi, rsi
0x180003309  jz      short loc_180003343
0x18000330b  call    cs:__imp_GetLastError
0x180003311  mov     ebx, eax
0x180003313  xor     r9d, r9d; msWindowLength
0x180003316  xor     r8d, r8d; msPeriod
0x180003319  xor     edx, edx; pftDueTime
0x18000331b  mov     rcx, rsi; pti
0x18000331e  call    cs:__imp_SetThreadpoolTimer
0x180003324  mov     edx, 1; fCancelPendingCallbacks
0x180003329  mov     rcx, rsi; pti
0x18000332c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003332  mov     rcx, rsi; pti
0x180003335  call    cs:__imp_CloseThreadpoolTimer
0x18000333b  mov     ecx, ebx; dwErrCode
0x18000333d  call    cs:__imp_SetLastError
0x180003343  mov     qword ptr [rdi+38h], 0
0x18000334b  mov     rbx, [rdi+100h]
0x180003352  mov     qword ptr [rdi+100h], 0
0x18000335d  test    rbx, rbx
0x180003360  jz      short loc_180003376
0x180003362  call    cs:__imp_GetProcessHeap
0x180003368  mov     rcx, rax; hHeap
0x18000336b  mov     r8, rbx; lpMem
0x18000336e  xor     edx, edx; dwFlags
0x180003370  call    cs:__imp_HeapFree
0x180003376  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000337d  test    r8, r8
0x180003380  jz      short loc_18000339A
0x180003382  mov     rdx, cs:qword_180026068; SRWLock
0x180003389  test    rdx, rdx
0x18000338c  jz      short loc_18000339A
0x18000338e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003395  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000339a  lea     rbx, [rdi+98h]
0x1800033a1  mov     rsi, [rbx+40h]
0x1800033a5  mov     qword ptr [rbx+40h], 0
0x1800033ad  test    rsi, rsi
0x1800033b0  jz      short loc_1800033C6
0x1800033b2  call    cs:__imp_GetProcessHeap
0x1800033b8  mov     rcx, rax; hHeap
0x1800033bb  mov     r8, rsi; lpMem
0x1800033be  xor     edx, edx; dwFlags
0x1800033c0  call    cs:__imp_HeapFree
0x1800033c6  mov     rcx, rbx; lpCriticalSection
0x1800033c9  call    cs:__imp_DeleteCriticalSection
0x1800033cf  lea     rcx, [rdi+90h]
0x1800033d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800033db  mov     rsi, [rdi+88h]
0x1800033e2  mov     qword ptr [rdi+88h], 0
0x1800033ed  test    rsi, rsi
0x1800033f0  jz      short loc_180003406
0x1800033f2  call    cs:__imp_GetProcessHeap
0x1800033f8  mov     rcx, rax; hHeap
0x1800033fb  mov     r8, rsi; lpMem
0x1800033fe  xor     edx, edx; dwFlags
0x180003400  call    cs:__imp_HeapFree
0x180003406  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000340a  call    cs:__imp_DeleteCriticalSection
0x180003410  mov     rbx, [rdi+38h]
0x180003414  test    rbx, rbx
0x180003417  jz      short loc_180003441
0x180003419  xor     r9d, r9d; msWindowLength
0x18000341c  xor     r8d, r8d; msPeriod
0x18000341f  xor     edx, edx; pftDueTime
0x180003421  mov     rcx, rbx; pti
0x180003424  call    cs:__imp_SetThreadpoolTimer
0x18000342a  mov     edx, 1; fCancelPendingCallbacks
0x18000342f  mov     rcx, rbx; pti
0x180003432  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003438  mov     rcx, rbx; pti
0x18000343b  call    cs:__imp_CloseThreadpoolTimer
0x180003441  mov     rbx, [rdi+30h]
0x180003445  test    rbx, rbx
0x180003448  jz      short loc_180003473
0x18000344a  xor     r9d, r9d; msWindowLength
0x18000344d  xor     r8d, r8d; msPeriod
0x180003450  xor     edx, edx; pftDueTime
0x180003452  mov     rcx, rbx; pti
0x180003455  call    cs:__imp_SetThreadpoolTimer
0x18000345b  mov     edx, 1; fCancelPendingCallbacks
0x180003460  mov     rcx, rbx; pti
0x180003463  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003469  mov     rcx, rbx; pti
0x18000346c  call    cs:__imp_CloseThreadpoolTimer
0x180003472  nop
0x180003473  mov     rcx, [rdi+10h]; lpMem
0x180003477  test    rcx, rcx
0x18000347a  jz      short loc_180003482
0x18000347c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003481  nop
0x180003482  mov     rbx, [rsp+28h+arg_0]
0x180003487  mov     rsi, [rsp+28h+arg_8]
0x18000348c  add     rsp, 20h
0x180003490  pop     rdi
0x180003491  retn
```
