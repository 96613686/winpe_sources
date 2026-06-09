# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800078d4`
- end: `0x180007ac2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013e40`

## callees

- `0x180007600`
- `0x1800078d4`
- `0x180010190`
- `0x180011714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000796d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000796d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000791c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007965`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000791c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007965`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007913`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000795c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007913`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000795c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007905`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000794e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007905`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000794e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a85`

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
  if ( v8 && qword_18001D078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001D078[25], qword_18001D078, v8);
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
0x1800078d4  mov     [rsp+arg_0], rbx
0x1800078d9  mov     [rsp+arg_8], rsi
0x1800078de  push    rdi
0x1800078df  sub     rsp, 20h
0x1800078e3  mov     rdi, rcx
0x1800078e6  mov     byte ptr [rcx], 0
0x1800078e9  mov     rsi, [rcx+30h]
0x1800078ed  test    rsi, rsi
0x1800078f0  jz      short loc_18000792A
0x1800078f2  call    cs:__imp_GetLastError
0x1800078f8  mov     ebx, eax
0x1800078fa  xor     r9d, r9d; msWindowLength
0x1800078fd  xor     r8d, r8d; msPeriod
0x180007900  xor     edx, edx; pftDueTime
0x180007902  mov     rcx, rsi; pti
0x180007905  call    cs:__imp_SetThreadpoolTimer
0x18000790b  mov     edx, 1; fCancelPendingCallbacks
0x180007910  mov     rcx, rsi; pti
0x180007913  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007919  mov     rcx, rsi; pti
0x18000791c  call    cs:__imp_CloseThreadpoolTimer
0x180007922  mov     ecx, ebx; dwErrCode
0x180007924  call    cs:__imp_SetLastError
0x18000792a  mov     qword ptr [rdi+30h], 0
0x180007932  mov     rsi, [rdi+38h]
0x180007936  test    rsi, rsi
0x180007939  jz      short loc_180007973
0x18000793b  call    cs:__imp_GetLastError
0x180007941  mov     ebx, eax
0x180007943  xor     r9d, r9d; msWindowLength
0x180007946  xor     r8d, r8d; msPeriod
0x180007949  xor     edx, edx; pftDueTime
0x18000794b  mov     rcx, rsi; pti
0x18000794e  call    cs:__imp_SetThreadpoolTimer
0x180007954  mov     edx, 1; fCancelPendingCallbacks
0x180007959  mov     rcx, rsi; pti
0x18000795c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007962  mov     rcx, rsi; pti
0x180007965  call    cs:__imp_CloseThreadpoolTimer
0x18000796b  mov     ecx, ebx; dwErrCode
0x18000796d  call    cs:__imp_SetLastError
0x180007973  mov     qword ptr [rdi+38h], 0
0x18000797b  mov     rbx, [rdi+100h]
0x180007982  mov     qword ptr [rdi+100h], 0
0x18000798d  test    rbx, rbx
0x180007990  jz      short loc_1800079A6
0x180007992  call    cs:__imp_GetProcessHeap
0x180007998  mov     rcx, rax; hHeap
0x18000799b  mov     r8, rbx; lpMem
0x18000799e  xor     edx, edx; dwFlags
0x1800079a0  call    cs:__imp_HeapFree
0x1800079a6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800079ad  test    r8, r8
0x1800079b0  jz      short loc_1800079CA
0x1800079b2  mov     rdx, cs:qword_18001D078; SRWLock
0x1800079b9  test    rdx, rdx
0x1800079bc  jz      short loc_1800079CA
0x1800079be  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800079c5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800079ca  lea     rbx, [rdi+98h]
0x1800079d1  mov     rsi, [rbx+40h]
0x1800079d5  mov     qword ptr [rbx+40h], 0
0x1800079dd  test    rsi, rsi
0x1800079e0  jz      short loc_1800079F6
0x1800079e2  call    cs:__imp_GetProcessHeap
0x1800079e8  mov     rcx, rax; hHeap
0x1800079eb  mov     r8, rsi; lpMem
0x1800079ee  xor     edx, edx; dwFlags
0x1800079f0  call    cs:__imp_HeapFree
0x1800079f6  mov     rcx, rbx; lpCriticalSection
0x1800079f9  call    cs:__imp_DeleteCriticalSection
0x1800079ff  lea     rcx, [rdi+90h]
0x180007a06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007a0b  mov     rsi, [rdi+88h]
0x180007a12  mov     qword ptr [rdi+88h], 0
0x180007a1d  test    rsi, rsi
0x180007a20  jz      short loc_180007A36
0x180007a22  call    cs:__imp_GetProcessHeap
0x180007a28  mov     rcx, rax; hHeap
0x180007a2b  mov     r8, rsi; lpMem
0x180007a2e  xor     edx, edx; dwFlags
0x180007a30  call    cs:__imp_HeapFree
0x180007a36  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007a3a  call    cs:__imp_DeleteCriticalSection
0x180007a40  mov     rbx, [rdi+38h]
0x180007a44  test    rbx, rbx
0x180007a47  jz      short loc_180007A71
0x180007a49  xor     r9d, r9d; msWindowLength
0x180007a4c  xor     r8d, r8d; msPeriod
0x180007a4f  xor     edx, edx; pftDueTime
0x180007a51  mov     rcx, rbx; pti
0x180007a54  call    cs:__imp_SetThreadpoolTimer
0x180007a5a  mov     edx, 1; fCancelPendingCallbacks
0x180007a5f  mov     rcx, rbx; pti
0x180007a62  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007a68  mov     rcx, rbx; pti
0x180007a6b  call    cs:__imp_CloseThreadpoolTimer
0x180007a71  mov     rbx, [rdi+30h]
0x180007a75  test    rbx, rbx
0x180007a78  jz      short loc_180007AA3
0x180007a7a  xor     r9d, r9d; msWindowLength
0x180007a7d  xor     r8d, r8d; msPeriod
0x180007a80  xor     edx, edx; pftDueTime
0x180007a82  mov     rcx, rbx; pti
0x180007a85  call    cs:__imp_SetThreadpoolTimer
0x180007a8b  mov     edx, 1; fCancelPendingCallbacks
0x180007a90  mov     rcx, rbx; pti
0x180007a93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007a99  mov     rcx, rbx; pti
0x180007a9c  call    cs:__imp_CloseThreadpoolTimer
0x180007aa2  nop
0x180007aa3  mov     rcx, [rdi+10h]; lpMem
0x180007aa7  test    rcx, rcx
0x180007aaa  jz      short loc_180007AB2
0x180007aac  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180007ab1  nop
0x180007ab2  mov     rbx, [rsp+28h+arg_0]
0x180007ab7  mov     rsi, [rsp+28h+arg_8]
0x180007abc  add     rsp, 20h
0x180007ac0  pop     rdi
0x180007ac1  retn
```
