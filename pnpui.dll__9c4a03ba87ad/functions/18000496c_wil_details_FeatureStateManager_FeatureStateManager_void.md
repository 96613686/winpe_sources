# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000496c`
- end: `0x180004b58`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d260`

## callees

- `0x1800046dc`
- `0x18000496c`
- `0x180009394`
- `0x180009f3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000498a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000498a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ad2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ac8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000499d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004aec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000499d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004aec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b34`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004afa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004afa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b2b`

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
  if ( v8 && qword_180014018 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180014018[25], qword_180014018, v8);
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
0x18000496c  mov     [rsp+arg_0], rbx
0x180004971  mov     [rsp+arg_8], rsi
0x180004976  push    rdi
0x180004977  sub     rsp, 20h
0x18000497b  mov     byte ptr [rcx], 0
0x18000497e  mov     rdi, rcx
0x180004981  mov     rsi, [rcx+30h]
0x180004985  test    rsi, rsi
0x180004988  jz      short loc_1800049C2
0x18000498a  call    cs:__imp_GetLastError
0x180004990  xor     r9d, r9d; msWindowLength
0x180004993  xor     r8d, r8d; msPeriod
0x180004996  xor     edx, edx; pftDueTime
0x180004998  mov     rcx, rsi; pti
0x18000499b  mov     ebx, eax
0x18000499d  call    cs:__imp_SetThreadpoolTimer
0x1800049a3  mov     edx, 1; fCancelPendingCallbacks
0x1800049a8  mov     rcx, rsi; pti
0x1800049ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049b1  mov     rcx, rsi; pti
0x1800049b4  call    cs:__imp_CloseThreadpoolTimer
0x1800049ba  mov     ecx, ebx; dwErrCode
0x1800049bc  call    cs:__imp_SetLastError
0x1800049c2  mov     qword ptr [rdi+30h], 0
0x1800049ca  mov     rsi, [rdi+38h]
0x1800049ce  test    rsi, rsi
0x1800049d1  jz      short loc_180004A0B
0x1800049d3  call    cs:__imp_GetLastError
0x1800049d9  xor     r9d, r9d; msWindowLength
0x1800049dc  xor     r8d, r8d; msPeriod
0x1800049df  xor     edx, edx; pftDueTime
0x1800049e1  mov     rcx, rsi; pti
0x1800049e4  mov     ebx, eax
0x1800049e6  call    cs:__imp_SetThreadpoolTimer
0x1800049ec  mov     edx, 1; fCancelPendingCallbacks
0x1800049f1  mov     rcx, rsi; pti
0x1800049f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049fa  mov     rcx, rsi; pti
0x1800049fd  call    cs:__imp_CloseThreadpoolTimer
0x180004a03  mov     ecx, ebx; dwErrCode
0x180004a05  call    cs:__imp_SetLastError
0x180004a0b  mov     qword ptr [rdi+38h], 0
0x180004a13  mov     rbx, [rdi+100h]
0x180004a1a  mov     qword ptr [rdi+100h], 0
0x180004a25  test    rbx, rbx
0x180004a28  jz      short loc_180004A3E
0x180004a2a  call    cs:__imp_GetProcessHeap
0x180004a30  mov     r8, rbx; lpMem
0x180004a33  xor     edx, edx; dwFlags
0x180004a35  mov     rcx, rax; hHeap
0x180004a38  call    cs:__imp_HeapFree
0x180004a3e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180004a45  test    r8, r8
0x180004a48  jz      short loc_180004A62
0x180004a4a  mov     rdx, cs:qword_180014018; SRWLock
0x180004a51  test    rdx, rdx
0x180004a54  jz      short loc_180004A62
0x180004a56  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180004a5d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004a62  lea     rbx, [rdi+98h]
0x180004a69  mov     rsi, [rbx+40h]
0x180004a6d  mov     qword ptr [rbx+40h], 0
0x180004a75  test    rsi, rsi
0x180004a78  jz      short loc_180004A8E
0x180004a7a  call    cs:__imp_GetProcessHeap
0x180004a80  mov     r8, rsi; lpMem
0x180004a83  xor     edx, edx; dwFlags
0x180004a85  mov     rcx, rax; hHeap
0x180004a88  call    cs:__imp_HeapFree
0x180004a8e  mov     rcx, rbx; lpCriticalSection
0x180004a91  call    cs:__imp_DeleteCriticalSection
0x180004a97  lea     rcx, [rdi+90h]
0x180004a9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004aa3  mov     rsi, [rdi+88h]
0x180004aaa  mov     qword ptr [rdi+88h], 0
0x180004ab5  test    rsi, rsi
0x180004ab8  jz      short loc_180004ACE
0x180004aba  call    cs:__imp_GetProcessHeap
0x180004ac0  mov     r8, rsi; lpMem
0x180004ac3  xor     edx, edx; dwFlags
0x180004ac5  mov     rcx, rax; hHeap
0x180004ac8  call    cs:__imp_HeapFree
0x180004ace  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004ad2  call    cs:__imp_DeleteCriticalSection
0x180004ad8  mov     rbx, [rdi+38h]
0x180004adc  test    rbx, rbx
0x180004adf  jz      short loc_180004B09
0x180004ae1  xor     r9d, r9d; msWindowLength
0x180004ae4  xor     r8d, r8d; msPeriod
0x180004ae7  xor     edx, edx; pftDueTime
0x180004ae9  mov     rcx, rbx; pti
0x180004aec  call    cs:__imp_SetThreadpoolTimer
0x180004af2  mov     edx, 1; fCancelPendingCallbacks
0x180004af7  mov     rcx, rbx; pti
0x180004afa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b00  mov     rcx, rbx; pti
0x180004b03  call    cs:__imp_CloseThreadpoolTimer
0x180004b09  mov     rbx, [rdi+30h]
0x180004b0d  test    rbx, rbx
0x180004b10  jz      short loc_180004B3A
0x180004b12  xor     r9d, r9d; msWindowLength
0x180004b15  xor     r8d, r8d; msPeriod
0x180004b18  xor     edx, edx; pftDueTime
0x180004b1a  mov     rcx, rbx; pti
0x180004b1d  call    cs:__imp_SetThreadpoolTimer
0x180004b23  mov     edx, 1; fCancelPendingCallbacks
0x180004b28  mov     rcx, rbx; pti
0x180004b2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b31  mov     rcx, rbx; pti
0x180004b34  call    cs:__imp_CloseThreadpoolTimer
0x180004b3a  mov     rcx, [rdi+10h]; lpMem
0x180004b3e  test    rcx, rcx
0x180004b41  jz      short loc_180004B48
0x180004b43  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004b48  mov     rbx, [rsp+28h+arg_0]
0x180004b4d  mov     rsi, [rsp+28h+arg_8]
0x180004b52  add     rsp, 20h
0x180004b56  pop     rdi
0x180004b57  retn
```
