# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180002d1c`
- end: `0x180002f08`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000faf0`

## callees

- `0x180002bd8`
- `0x180002d1c`
- `0x1800065a0`
- `0x1800072bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002de8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002de8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002d6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002db5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002d6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002db5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002e9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ecd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002d96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002e9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ecd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002d64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002eb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002ee4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002d64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002eb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002ee4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002d5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002da4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002eaa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002edb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002d5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002da4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002eaa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002edb`

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
  if ( v8 && qword_180015018 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180015018[25], qword_180015018, v8);
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
0x180002d1c  mov     [rsp+arg_0], rbx
0x180002d21  mov     [rsp+arg_8], rsi
0x180002d26  push    rdi
0x180002d27  sub     rsp, 20h
0x180002d2b  mov     byte ptr [rcx], 0
0x180002d2e  mov     rdi, rcx
0x180002d31  mov     rsi, [rcx+30h]
0x180002d35  test    rsi, rsi
0x180002d38  jz      short loc_180002D72
0x180002d3a  call    cs:__imp_GetLastError
0x180002d40  xor     r9d, r9d; msWindowLength
0x180002d43  xor     r8d, r8d; msPeriod
0x180002d46  xor     edx, edx; pftDueTime
0x180002d48  mov     rcx, rsi; pti
0x180002d4b  mov     ebx, eax
0x180002d4d  call    cs:__imp_SetThreadpoolTimer
0x180002d53  mov     edx, 1; fCancelPendingCallbacks
0x180002d58  mov     rcx, rsi; pti
0x180002d5b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002d61  mov     rcx, rsi; pti
0x180002d64  call    cs:__imp_CloseThreadpoolTimer
0x180002d6a  mov     ecx, ebx; dwErrCode
0x180002d6c  call    cs:__imp_SetLastError
0x180002d72  mov     qword ptr [rdi+30h], 0
0x180002d7a  mov     rsi, [rdi+38h]
0x180002d7e  test    rsi, rsi
0x180002d81  jz      short loc_180002DBB
0x180002d83  call    cs:__imp_GetLastError
0x180002d89  xor     r9d, r9d; msWindowLength
0x180002d8c  xor     r8d, r8d; msPeriod
0x180002d8f  xor     edx, edx; pftDueTime
0x180002d91  mov     rcx, rsi; pti
0x180002d94  mov     ebx, eax
0x180002d96  call    cs:__imp_SetThreadpoolTimer
0x180002d9c  mov     edx, 1; fCancelPendingCallbacks
0x180002da1  mov     rcx, rsi; pti
0x180002da4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002daa  mov     rcx, rsi; pti
0x180002dad  call    cs:__imp_CloseThreadpoolTimer
0x180002db3  mov     ecx, ebx; dwErrCode
0x180002db5  call    cs:__imp_SetLastError
0x180002dbb  mov     qword ptr [rdi+38h], 0
0x180002dc3  mov     rbx, [rdi+100h]
0x180002dca  mov     qword ptr [rdi+100h], 0
0x180002dd5  test    rbx, rbx
0x180002dd8  jz      short loc_180002DEE
0x180002dda  call    cs:__imp_GetProcessHeap
0x180002de0  mov     r8, rbx; lpMem
0x180002de3  xor     edx, edx; dwFlags
0x180002de5  mov     rcx, rax; hHeap
0x180002de8  call    cs:__imp_HeapFree
0x180002dee  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180002df5  test    r8, r8
0x180002df8  jz      short loc_180002E12
0x180002dfa  mov     rdx, cs:qword_180015018; SRWLock
0x180002e01  test    rdx, rdx
0x180002e04  jz      short loc_180002E12
0x180002e06  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180002e0d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180002e12  lea     rbx, [rdi+98h]
0x180002e19  mov     rsi, [rbx+40h]
0x180002e1d  mov     qword ptr [rbx+40h], 0
0x180002e25  test    rsi, rsi
0x180002e28  jz      short loc_180002E3E
0x180002e2a  call    cs:__imp_GetProcessHeap
0x180002e30  mov     r8, rsi; lpMem
0x180002e33  xor     edx, edx; dwFlags
0x180002e35  mov     rcx, rax; hHeap
0x180002e38  call    cs:__imp_HeapFree
0x180002e3e  mov     rcx, rbx; lpCriticalSection
0x180002e41  call    cs:__imp_DeleteCriticalSection
0x180002e47  lea     rcx, [rdi+90h]
0x180002e4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180002e53  mov     rsi, [rdi+88h]
0x180002e5a  mov     qword ptr [rdi+88h], 0
0x180002e65  test    rsi, rsi
0x180002e68  jz      short loc_180002E7E
0x180002e6a  call    cs:__imp_GetProcessHeap
0x180002e70  mov     r8, rsi; lpMem
0x180002e73  xor     edx, edx; dwFlags
0x180002e75  mov     rcx, rax; hHeap
0x180002e78  call    cs:__imp_HeapFree
0x180002e7e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180002e82  call    cs:__imp_DeleteCriticalSection
0x180002e88  mov     rbx, [rdi+38h]
0x180002e8c  test    rbx, rbx
0x180002e8f  jz      short loc_180002EB9
0x180002e91  xor     r9d, r9d; msWindowLength
0x180002e94  xor     r8d, r8d; msPeriod
0x180002e97  xor     edx, edx; pftDueTime
0x180002e99  mov     rcx, rbx; pti
0x180002e9c  call    cs:__imp_SetThreadpoolTimer
0x180002ea2  mov     edx, 1; fCancelPendingCallbacks
0x180002ea7  mov     rcx, rbx; pti
0x180002eaa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002eb0  mov     rcx, rbx; pti
0x180002eb3  call    cs:__imp_CloseThreadpoolTimer
0x180002eb9  mov     rbx, [rdi+30h]
0x180002ebd  test    rbx, rbx
0x180002ec0  jz      short loc_180002EEA
0x180002ec2  xor     r9d, r9d; msWindowLength
0x180002ec5  xor     r8d, r8d; msPeriod
0x180002ec8  xor     edx, edx; pftDueTime
0x180002eca  mov     rcx, rbx; pti
0x180002ecd  call    cs:__imp_SetThreadpoolTimer
0x180002ed3  mov     edx, 1; fCancelPendingCallbacks
0x180002ed8  mov     rcx, rbx; pti
0x180002edb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002ee1  mov     rcx, rbx; pti
0x180002ee4  call    cs:__imp_CloseThreadpoolTimer
0x180002eea  mov     rcx, [rdi+10h]; lpMem
0x180002eee  test    rcx, rcx
0x180002ef1  jz      short loc_180002EF8
0x180002ef3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180002ef8  mov     rbx, [rsp+28h+arg_0]
0x180002efd  mov     rsi, [rsp+28h+arg_8]
0x180002f02  add     rsp, 20h
0x180002f06  pop     rdi
0x180002f07  retn
```
