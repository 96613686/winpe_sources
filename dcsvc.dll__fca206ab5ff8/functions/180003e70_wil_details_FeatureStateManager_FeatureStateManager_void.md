# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003e70`
- end: `0x18000405e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011fa0`

## callees

- `0x180003bcc`
- `0x180003e70`
- `0x180007fec`
- `0x180009afc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ec0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ec0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003fd6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003fd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ea1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003eea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ff0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004021`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ea1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003eea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ff0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004021`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eaf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ef8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ffe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000402f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eaf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ef8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ffe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000402f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004007`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004038`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004007`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004038`

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
  if ( v8 && qword_18001B148 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001B148[25], qword_18001B148, v8);
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
0x180003e70  mov     [rsp+arg_0], rbx
0x180003e75  mov     [rsp+arg_8], rsi
0x180003e7a  push    rdi
0x180003e7b  sub     rsp, 20h
0x180003e7f  mov     rdi, rcx
0x180003e82  mov     byte ptr [rcx], 0
0x180003e85  mov     rsi, [rcx+30h]
0x180003e89  test    rsi, rsi
0x180003e8c  jz      short loc_180003EC6
0x180003e8e  call    cs:__imp_GetLastError
0x180003e94  mov     ebx, eax
0x180003e96  xor     r9d, r9d; msWindowLength
0x180003e99  xor     r8d, r8d; msPeriod
0x180003e9c  xor     edx, edx; pftDueTime
0x180003e9e  mov     rcx, rsi; pti
0x180003ea1  call    cs:__imp_SetThreadpoolTimer
0x180003ea7  mov     edx, 1; fCancelPendingCallbacks
0x180003eac  mov     rcx, rsi; pti
0x180003eaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003eb5  mov     rcx, rsi; pti
0x180003eb8  call    cs:__imp_CloseThreadpoolTimer
0x180003ebe  mov     ecx, ebx; dwErrCode
0x180003ec0  call    cs:__imp_SetLastError
0x180003ec6  mov     qword ptr [rdi+30h], 0
0x180003ece  mov     rsi, [rdi+38h]
0x180003ed2  test    rsi, rsi
0x180003ed5  jz      short loc_180003F0F
0x180003ed7  call    cs:__imp_GetLastError
0x180003edd  mov     ebx, eax
0x180003edf  xor     r9d, r9d; msWindowLength
0x180003ee2  xor     r8d, r8d; msPeriod
0x180003ee5  xor     edx, edx; pftDueTime
0x180003ee7  mov     rcx, rsi; pti
0x180003eea  call    cs:__imp_SetThreadpoolTimer
0x180003ef0  mov     edx, 1; fCancelPendingCallbacks
0x180003ef5  mov     rcx, rsi; pti
0x180003ef8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003efe  mov     rcx, rsi; pti
0x180003f01  call    cs:__imp_CloseThreadpoolTimer
0x180003f07  mov     ecx, ebx; dwErrCode
0x180003f09  call    cs:__imp_SetLastError
0x180003f0f  mov     qword ptr [rdi+38h], 0
0x180003f17  mov     rbx, [rdi+100h]
0x180003f1e  mov     qword ptr [rdi+100h], 0
0x180003f29  test    rbx, rbx
0x180003f2c  jz      short loc_180003F42
0x180003f2e  call    cs:__imp_GetProcessHeap
0x180003f34  mov     rcx, rax; hHeap
0x180003f37  mov     r8, rbx; lpMem
0x180003f3a  xor     edx, edx; dwFlags
0x180003f3c  call    cs:__imp_HeapFree
0x180003f42  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003f49  test    r8, r8
0x180003f4c  jz      short loc_180003F66
0x180003f4e  mov     rdx, cs:qword_18001B148; SRWLock
0x180003f55  test    rdx, rdx
0x180003f58  jz      short loc_180003F66
0x180003f5a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003f61  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003f66  lea     rbx, [rdi+98h]
0x180003f6d  mov     rsi, [rbx+40h]
0x180003f71  mov     qword ptr [rbx+40h], 0
0x180003f79  test    rsi, rsi
0x180003f7c  jz      short loc_180003F92
0x180003f7e  call    cs:__imp_GetProcessHeap
0x180003f84  mov     rcx, rax; hHeap
0x180003f87  mov     r8, rsi; lpMem
0x180003f8a  xor     edx, edx; dwFlags
0x180003f8c  call    cs:__imp_HeapFree
0x180003f92  mov     rcx, rbx; lpCriticalSection
0x180003f95  call    cs:__imp_DeleteCriticalSection
0x180003f9b  lea     rcx, [rdi+90h]
0x180003fa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003fa7  mov     rsi, [rdi+88h]
0x180003fae  mov     qword ptr [rdi+88h], 0
0x180003fb9  test    rsi, rsi
0x180003fbc  jz      short loc_180003FD2
0x180003fbe  call    cs:__imp_GetProcessHeap
0x180003fc4  mov     rcx, rax; hHeap
0x180003fc7  mov     r8, rsi; lpMem
0x180003fca  xor     edx, edx; dwFlags
0x180003fcc  call    cs:__imp_HeapFree
0x180003fd2  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003fd6  call    cs:__imp_DeleteCriticalSection
0x180003fdc  mov     rbx, [rdi+38h]
0x180003fe0  test    rbx, rbx
0x180003fe3  jz      short loc_18000400D
0x180003fe5  xor     r9d, r9d; msWindowLength
0x180003fe8  xor     r8d, r8d; msPeriod
0x180003feb  xor     edx, edx; pftDueTime
0x180003fed  mov     rcx, rbx; pti
0x180003ff0  call    cs:__imp_SetThreadpoolTimer
0x180003ff6  mov     edx, 1; fCancelPendingCallbacks
0x180003ffb  mov     rcx, rbx; pti
0x180003ffe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004004  mov     rcx, rbx; pti
0x180004007  call    cs:__imp_CloseThreadpoolTimer
0x18000400d  mov     rbx, [rdi+30h]
0x180004011  test    rbx, rbx
0x180004014  jz      short loc_18000403F
0x180004016  xor     r9d, r9d; msWindowLength
0x180004019  xor     r8d, r8d; msPeriod
0x18000401c  xor     edx, edx; pftDueTime
0x18000401e  mov     rcx, rbx; pti
0x180004021  call    cs:__imp_SetThreadpoolTimer
0x180004027  mov     edx, 1; fCancelPendingCallbacks
0x18000402c  mov     rcx, rbx; pti
0x18000402f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004035  mov     rcx, rbx; pti
0x180004038  call    cs:__imp_CloseThreadpoolTimer
0x18000403e  nop
0x18000403f  mov     rcx, [rdi+10h]; lpMem
0x180004043  test    rcx, rcx
0x180004046  jz      short loc_18000404E
0x180004048  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000404d  nop
0x18000404e  mov     rbx, [rsp+28h+arg_0]
0x180004053  mov     rsi, [rsp+28h+arg_8]
0x180004058  add     rsp, 20h
0x18000405c  pop     rdi
0x18000405d  retn
```
