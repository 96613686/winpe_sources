# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003f7c`
- end: `0x180004168`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800273e0`

## callees

- `0x180003cec`
- `0x180003f7c`
- `0x180008a04`
- `0x180009d74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004098`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004098`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000403a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000408a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000403a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000408a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004015`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003fc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000400d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004113`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004144`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003fc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000400d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004113`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004144`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003fad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ff6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800040fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000412d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003fad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ff6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800040fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000412d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003fbb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004004`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000410a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000413b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003fbb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004004`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000410a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000413b`

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
  if ( v8 && qword_180032198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180032198[25], qword_180032198, v8);
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
0x180003f7c  mov     [rsp+arg_0], rbx
0x180003f81  mov     [rsp+arg_8], rsi
0x180003f86  push    rdi
0x180003f87  sub     rsp, 20h
0x180003f8b  mov     byte ptr [rcx], 0
0x180003f8e  mov     rdi, rcx
0x180003f91  mov     rsi, [rcx+30h]
0x180003f95  test    rsi, rsi
0x180003f98  jz      short loc_180003FD2
0x180003f9a  call    cs:__imp_GetLastError
0x180003fa0  xor     r9d, r9d; msWindowLength
0x180003fa3  xor     r8d, r8d; msPeriod
0x180003fa6  xor     edx, edx; pftDueTime
0x180003fa8  mov     rcx, rsi; pti
0x180003fab  mov     ebx, eax
0x180003fad  call    cs:__imp_SetThreadpoolTimer
0x180003fb3  mov     edx, 1; fCancelPendingCallbacks
0x180003fb8  mov     rcx, rsi; pti
0x180003fbb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003fc1  mov     rcx, rsi; pti
0x180003fc4  call    cs:__imp_CloseThreadpoolTimer
0x180003fca  mov     ecx, ebx; dwErrCode
0x180003fcc  call    cs:__imp_SetLastError
0x180003fd2  mov     qword ptr [rdi+30h], 0
0x180003fda  mov     rsi, [rdi+38h]
0x180003fde  test    rsi, rsi
0x180003fe1  jz      short loc_18000401B
0x180003fe3  call    cs:__imp_GetLastError
0x180003fe9  xor     r9d, r9d; msWindowLength
0x180003fec  xor     r8d, r8d; msPeriod
0x180003fef  xor     edx, edx; pftDueTime
0x180003ff1  mov     rcx, rsi; pti
0x180003ff4  mov     ebx, eax
0x180003ff6  call    cs:__imp_SetThreadpoolTimer
0x180003ffc  mov     edx, 1; fCancelPendingCallbacks
0x180004001  mov     rcx, rsi; pti
0x180004004  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000400a  mov     rcx, rsi; pti
0x18000400d  call    cs:__imp_CloseThreadpoolTimer
0x180004013  mov     ecx, ebx; dwErrCode
0x180004015  call    cs:__imp_SetLastError
0x18000401b  mov     qword ptr [rdi+38h], 0
0x180004023  mov     rbx, [rdi+100h]
0x18000402a  mov     qword ptr [rdi+100h], 0
0x180004035  test    rbx, rbx
0x180004038  jz      short loc_18000404E
0x18000403a  call    cs:__imp_GetProcessHeap
0x180004040  mov     r8, rbx; lpMem
0x180004043  xor     edx, edx; dwFlags
0x180004045  mov     rcx, rax; hHeap
0x180004048  call    cs:__imp_HeapFree
0x18000404e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180004055  test    r8, r8
0x180004058  jz      short loc_180004072
0x18000405a  mov     rdx, cs:qword_180032198; SRWLock
0x180004061  test    rdx, rdx
0x180004064  jz      short loc_180004072
0x180004066  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000406d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004072  lea     rbx, [rdi+98h]
0x180004079  mov     rsi, [rbx+40h]
0x18000407d  mov     qword ptr [rbx+40h], 0
0x180004085  test    rsi, rsi
0x180004088  jz      short loc_18000409E
0x18000408a  call    cs:__imp_GetProcessHeap
0x180004090  mov     r8, rsi; lpMem
0x180004093  xor     edx, edx; dwFlags
0x180004095  mov     rcx, rax; hHeap
0x180004098  call    cs:__imp_HeapFree
0x18000409e  mov     rcx, rbx; lpCriticalSection
0x1800040a1  call    cs:__imp_DeleteCriticalSection
0x1800040a7  lea     rcx, [rdi+90h]
0x1800040ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800040b3  mov     rsi, [rdi+88h]
0x1800040ba  mov     qword ptr [rdi+88h], 0
0x1800040c5  test    rsi, rsi
0x1800040c8  jz      short loc_1800040DE
0x1800040ca  call    cs:__imp_GetProcessHeap
0x1800040d0  mov     r8, rsi; lpMem
0x1800040d3  xor     edx, edx; dwFlags
0x1800040d5  mov     rcx, rax; hHeap
0x1800040d8  call    cs:__imp_HeapFree
0x1800040de  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800040e2  call    cs:__imp_DeleteCriticalSection
0x1800040e8  mov     rbx, [rdi+38h]
0x1800040ec  test    rbx, rbx
0x1800040ef  jz      short loc_180004119
0x1800040f1  xor     r9d, r9d; msWindowLength
0x1800040f4  xor     r8d, r8d; msPeriod
0x1800040f7  xor     edx, edx; pftDueTime
0x1800040f9  mov     rcx, rbx; pti
0x1800040fc  call    cs:__imp_SetThreadpoolTimer
0x180004102  mov     edx, 1; fCancelPendingCallbacks
0x180004107  mov     rcx, rbx; pti
0x18000410a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004110  mov     rcx, rbx; pti
0x180004113  call    cs:__imp_CloseThreadpoolTimer
0x180004119  mov     rbx, [rdi+30h]
0x18000411d  test    rbx, rbx
0x180004120  jz      short loc_18000414A
0x180004122  xor     r9d, r9d; msWindowLength
0x180004125  xor     r8d, r8d; msPeriod
0x180004128  xor     edx, edx; pftDueTime
0x18000412a  mov     rcx, rbx; pti
0x18000412d  call    cs:__imp_SetThreadpoolTimer
0x180004133  mov     edx, 1; fCancelPendingCallbacks
0x180004138  mov     rcx, rbx; pti
0x18000413b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004141  mov     rcx, rbx; pti
0x180004144  call    cs:__imp_CloseThreadpoolTimer
0x18000414a  mov     rcx, [rdi+10h]; lpMem
0x18000414e  test    rcx, rcx
0x180004151  jz      short loc_180004158
0x180004153  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004158  mov     rbx, [rsp+28h+arg_0]
0x18000415d  mov     rsi, [rsp+28h+arg_8]
0x180004162  add     rsp, 20h
0x180004166  pop     rdi
0x180004167  retn
```
