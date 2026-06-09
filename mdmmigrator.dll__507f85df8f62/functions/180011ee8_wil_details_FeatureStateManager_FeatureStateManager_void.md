# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180011ee8`
- end: `0x1800120d4`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001fb60`

## callees

- `0x180011c60`
- `0x180011ee8`
- `0x180018ab0`
- `0x18001c91c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001200d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001204e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001200d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001204e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012036`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012044`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f81`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012076`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800120a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012076`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800120a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001207f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800120b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001207f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800120b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012068`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012099`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012068`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012099`

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
  if ( v8 && qword_18002B198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002B198[25], qword_18002B198, v8);
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
0x180011ee8  mov     [rsp+arg_0], rbx
0x180011eed  mov     [rsp+arg_8], rsi
0x180011ef2  push    rdi
0x180011ef3  sub     rsp, 20h
0x180011ef7  mov     rdi, rcx
0x180011efa  mov     byte ptr [rcx], 0
0x180011efd  mov     rsi, [rcx+30h]
0x180011f01  test    rsi, rsi
0x180011f04  jz      short loc_180011F3E
0x180011f06  call    cs:__imp_GetLastError
0x180011f0c  mov     ebx, eax
0x180011f0e  xor     r9d, r9d; msWindowLength
0x180011f11  xor     r8d, r8d; msPeriod
0x180011f14  xor     edx, edx; pftDueTime
0x180011f16  mov     rcx, rsi; pti
0x180011f19  call    cs:__imp_SetThreadpoolTimer
0x180011f1f  mov     edx, 1; fCancelPendingCallbacks
0x180011f24  mov     rcx, rsi; pti
0x180011f27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011f2d  mov     rcx, rsi; pti
0x180011f30  call    cs:__imp_CloseThreadpoolTimer
0x180011f36  mov     ecx, ebx; dwErrCode
0x180011f38  call    cs:__imp_SetLastError
0x180011f3e  mov     qword ptr [rdi+30h], 0
0x180011f46  mov     rsi, [rdi+38h]
0x180011f4a  test    rsi, rsi
0x180011f4d  jz      short loc_180011F87
0x180011f4f  call    cs:__imp_GetLastError
0x180011f55  mov     ebx, eax
0x180011f57  xor     r9d, r9d; msWindowLength
0x180011f5a  xor     r8d, r8d; msPeriod
0x180011f5d  xor     edx, edx; pftDueTime
0x180011f5f  mov     rcx, rsi; pti
0x180011f62  call    cs:__imp_SetThreadpoolTimer
0x180011f68  mov     edx, 1; fCancelPendingCallbacks
0x180011f6d  mov     rcx, rsi; pti
0x180011f70  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011f76  mov     rcx, rsi; pti
0x180011f79  call    cs:__imp_CloseThreadpoolTimer
0x180011f7f  mov     ecx, ebx; dwErrCode
0x180011f81  call    cs:__imp_SetLastError
0x180011f87  mov     qword ptr [rdi+38h], 0
0x180011f8f  mov     rbx, [rdi+100h]
0x180011f96  mov     qword ptr [rdi+100h], 0
0x180011fa1  test    rbx, rbx
0x180011fa4  jz      short loc_180011FBA
0x180011fa6  call    cs:__imp_GetProcessHeap
0x180011fac  mov     rcx, rax; hHeap
0x180011faf  mov     r8, rbx; lpMem
0x180011fb2  xor     edx, edx; dwFlags
0x180011fb4  call    cs:__imp_HeapFree
0x180011fba  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180011fc1  test    r8, r8
0x180011fc4  jz      short loc_180011FDE
0x180011fc6  mov     rdx, cs:qword_18002B198; SRWLock
0x180011fcd  test    rdx, rdx
0x180011fd0  jz      short loc_180011FDE
0x180011fd2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011fd9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180011fde  lea     rbx, [rdi+98h]
0x180011fe5  mov     rsi, [rbx+40h]
0x180011fe9  mov     qword ptr [rbx+40h], 0
0x180011ff1  test    rsi, rsi
0x180011ff4  jz      short loc_18001200A
0x180011ff6  call    cs:__imp_GetProcessHeap
0x180011ffc  mov     rcx, rax; hHeap
0x180011fff  mov     r8, rsi; lpMem
0x180012002  xor     edx, edx; dwFlags
0x180012004  call    cs:__imp_HeapFree
0x18001200a  mov     rcx, rbx; lpCriticalSection
0x18001200d  call    cs:__imp_DeleteCriticalSection
0x180012013  lea     rcx, [rdi+90h]
0x18001201a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001201f  mov     rsi, [rdi+88h]
0x180012026  mov     qword ptr [rdi+88h], 0
0x180012031  test    rsi, rsi
0x180012034  jz      short loc_18001204A
0x180012036  call    cs:__imp_GetProcessHeap
0x18001203c  mov     rcx, rax; hHeap
0x18001203f  mov     r8, rsi; lpMem
0x180012042  xor     edx, edx; dwFlags
0x180012044  call    cs:__imp_HeapFree
0x18001204a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001204e  call    cs:__imp_DeleteCriticalSection
0x180012054  mov     rbx, [rdi+38h]
0x180012058  test    rbx, rbx
0x18001205b  jz      short loc_180012085
0x18001205d  xor     r9d, r9d; msWindowLength
0x180012060  xor     r8d, r8d; msPeriod
0x180012063  xor     edx, edx; pftDueTime
0x180012065  mov     rcx, rbx; pti
0x180012068  call    cs:__imp_SetThreadpoolTimer
0x18001206e  mov     edx, 1; fCancelPendingCallbacks
0x180012073  mov     rcx, rbx; pti
0x180012076  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001207c  mov     rcx, rbx; pti
0x18001207f  call    cs:__imp_CloseThreadpoolTimer
0x180012085  mov     rbx, [rdi+30h]
0x180012089  test    rbx, rbx
0x18001208c  jz      short loc_1800120B6
0x18001208e  xor     r9d, r9d; msWindowLength
0x180012091  xor     r8d, r8d; msPeriod
0x180012094  xor     edx, edx; pftDueTime
0x180012096  mov     rcx, rbx; pti
0x180012099  call    cs:__imp_SetThreadpoolTimer
0x18001209f  mov     edx, 1; fCancelPendingCallbacks
0x1800120a4  mov     rcx, rbx; pti
0x1800120a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800120ad  mov     rcx, rbx; pti
0x1800120b0  call    cs:__imp_CloseThreadpoolTimer
0x1800120b6  mov     rcx, [rdi+10h]; lpMem
0x1800120ba  test    rcx, rcx
0x1800120bd  jz      short loc_1800120C4
0x1800120bf  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800120c4  mov     rbx, [rsp+28h+arg_0]
0x1800120c9  mov     rsi, [rsp+28h+arg_8]
0x1800120ce  add     rsp, 20h
0x1800120d2  pop     rdi
0x1800120d3  retn
```
