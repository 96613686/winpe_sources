# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000e1a4`
- end: `0x18000e392`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036cb0`

## callees

- `0x18000dd84`
- `0x18000e1a4`
- `0x180015d6c`
- `0x18001b488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e30a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e30a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e2c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e300`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e2c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e300`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e20b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e20b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e23d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e23d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e1d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e21e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e324`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e355`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e1d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e21e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e324`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e355`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e1ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e235`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e33b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e36c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e1ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e235`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e33b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e36c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e1e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e22c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e332`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e363`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e1e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e22c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e332`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e363`

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
  if ( v8 && qword_18004A0C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18004A0C8[25], qword_18004A0C8, v8);
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
0x18000e1a4  mov     [rsp+arg_0], rbx
0x18000e1a9  mov     [rsp+arg_8], rsi
0x18000e1ae  push    rdi
0x18000e1af  sub     rsp, 20h
0x18000e1b3  mov     rdi, rcx
0x18000e1b6  mov     byte ptr [rcx], 0
0x18000e1b9  mov     rsi, [rcx+30h]
0x18000e1bd  test    rsi, rsi
0x18000e1c0  jz      short loc_18000E1FA
0x18000e1c2  call    cs:__imp_GetLastError
0x18000e1c8  mov     ebx, eax
0x18000e1ca  xor     r9d, r9d; msWindowLength
0x18000e1cd  xor     r8d, r8d; msPeriod
0x18000e1d0  xor     edx, edx; pftDueTime
0x18000e1d2  mov     rcx, rsi; pti
0x18000e1d5  call    cs:__imp_SetThreadpoolTimer
0x18000e1db  mov     edx, 1; fCancelPendingCallbacks
0x18000e1e0  mov     rcx, rsi; pti
0x18000e1e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e1e9  mov     rcx, rsi; pti
0x18000e1ec  call    cs:__imp_CloseThreadpoolTimer
0x18000e1f2  mov     ecx, ebx; dwErrCode
0x18000e1f4  call    cs:__imp_SetLastError
0x18000e1fa  mov     qword ptr [rdi+30h], 0
0x18000e202  mov     rsi, [rdi+38h]
0x18000e206  test    rsi, rsi
0x18000e209  jz      short loc_18000E243
0x18000e20b  call    cs:__imp_GetLastError
0x18000e211  mov     ebx, eax
0x18000e213  xor     r9d, r9d; msWindowLength
0x18000e216  xor     r8d, r8d; msPeriod
0x18000e219  xor     edx, edx; pftDueTime
0x18000e21b  mov     rcx, rsi; pti
0x18000e21e  call    cs:__imp_SetThreadpoolTimer
0x18000e224  mov     edx, 1; fCancelPendingCallbacks
0x18000e229  mov     rcx, rsi; pti
0x18000e22c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e232  mov     rcx, rsi; pti
0x18000e235  call    cs:__imp_CloseThreadpoolTimer
0x18000e23b  mov     ecx, ebx; dwErrCode
0x18000e23d  call    cs:__imp_SetLastError
0x18000e243  mov     qword ptr [rdi+38h], 0
0x18000e24b  mov     rbx, [rdi+100h]
0x18000e252  mov     qword ptr [rdi+100h], 0
0x18000e25d  test    rbx, rbx
0x18000e260  jz      short loc_18000E276
0x18000e262  call    cs:__imp_GetProcessHeap
0x18000e268  mov     rcx, rax; hHeap
0x18000e26b  mov     r8, rbx; lpMem
0x18000e26e  xor     edx, edx; dwFlags
0x18000e270  call    cs:__imp_HeapFree
0x18000e276  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000e27d  test    r8, r8
0x18000e280  jz      short loc_18000E29A
0x18000e282  mov     rdx, cs:qword_18004A0C8; SRWLock
0x18000e289  test    rdx, rdx
0x18000e28c  jz      short loc_18000E29A
0x18000e28e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000e295  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000e29a  lea     rbx, [rdi+98h]
0x18000e2a1  mov     rsi, [rbx+40h]
0x18000e2a5  mov     qword ptr [rbx+40h], 0
0x18000e2ad  test    rsi, rsi
0x18000e2b0  jz      short loc_18000E2C6
0x18000e2b2  call    cs:__imp_GetProcessHeap
0x18000e2b8  mov     rcx, rax; hHeap
0x18000e2bb  mov     r8, rsi; lpMem
0x18000e2be  xor     edx, edx; dwFlags
0x18000e2c0  call    cs:__imp_HeapFree
0x18000e2c6  mov     rcx, rbx; lpCriticalSection
0x18000e2c9  call    cs:__imp_DeleteCriticalSection
0x18000e2cf  lea     rcx, [rdi+90h]
0x18000e2d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000e2db  mov     rsi, [rdi+88h]
0x18000e2e2  mov     qword ptr [rdi+88h], 0
0x18000e2ed  test    rsi, rsi
0x18000e2f0  jz      short loc_18000E306
0x18000e2f2  call    cs:__imp_GetProcessHeap
0x18000e2f8  mov     rcx, rax; hHeap
0x18000e2fb  mov     r8, rsi; lpMem
0x18000e2fe  xor     edx, edx; dwFlags
0x18000e300  call    cs:__imp_HeapFree
0x18000e306  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000e30a  call    cs:__imp_DeleteCriticalSection
0x18000e310  mov     rbx, [rdi+38h]
0x18000e314  test    rbx, rbx
0x18000e317  jz      short loc_18000E341
0x18000e319  xor     r9d, r9d; msWindowLength
0x18000e31c  xor     r8d, r8d; msPeriod
0x18000e31f  xor     edx, edx; pftDueTime
0x18000e321  mov     rcx, rbx; pti
0x18000e324  call    cs:__imp_SetThreadpoolTimer
0x18000e32a  mov     edx, 1; fCancelPendingCallbacks
0x18000e32f  mov     rcx, rbx; pti
0x18000e332  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e338  mov     rcx, rbx; pti
0x18000e33b  call    cs:__imp_CloseThreadpoolTimer
0x18000e341  mov     rbx, [rdi+30h]
0x18000e345  test    rbx, rbx
0x18000e348  jz      short loc_18000E373
0x18000e34a  xor     r9d, r9d; msWindowLength
0x18000e34d  xor     r8d, r8d; msPeriod
0x18000e350  xor     edx, edx; pftDueTime
0x18000e352  mov     rcx, rbx; pti
0x18000e355  call    cs:__imp_SetThreadpoolTimer
0x18000e35b  mov     edx, 1; fCancelPendingCallbacks
0x18000e360  mov     rcx, rbx; pti
0x18000e363  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e369  mov     rcx, rbx; pti
0x18000e36c  call    cs:__imp_CloseThreadpoolTimer
0x18000e372  nop
0x18000e373  mov     rcx, [rdi+10h]; lpMem
0x18000e377  test    rcx, rcx
0x18000e37a  jz      short loc_18000E382
0x18000e37c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000e381  nop
0x18000e382  mov     rbx, [rsp+28h+arg_0]
0x18000e387  mov     rsi, [rsp+28h+arg_8]
0x18000e38c  add     rsp, 20h
0x18000e390  pop     rdi
0x18000e391  retn
```
