# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180016254`
- end: `0x180016442`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003e2c0`

## callees

- `0x180015f34`
- `0x180016254`
- `0x180023af0`
- `0x18002437c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016312`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016312`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016320`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016320`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016285`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800163d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016405`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016285`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800163d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016405`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016293`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800162dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800163e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016413`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016293`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800162dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800163e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016413`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001629c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800163eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001641c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001629c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800163eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001641c`

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
  if ( v8 && qword_1800521E8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800521E8[25], qword_1800521E8, v8);
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
0x180016254  mov     [rsp+arg_0], rbx
0x180016259  mov     [rsp+arg_8], rsi
0x18001625e  push    rdi
0x18001625f  sub     rsp, 20h
0x180016263  mov     rdi, rcx
0x180016266  mov     byte ptr [rcx], 0
0x180016269  mov     rsi, [rcx+30h]
0x18001626d  test    rsi, rsi
0x180016270  jz      short loc_1800162AA
0x180016272  call    cs:__imp_GetLastError
0x180016278  mov     ebx, eax
0x18001627a  xor     r9d, r9d; msWindowLength
0x18001627d  xor     r8d, r8d; msPeriod
0x180016280  xor     edx, edx; pftDueTime
0x180016282  mov     rcx, rsi; pti
0x180016285  call    cs:__imp_SetThreadpoolTimer
0x18001628b  mov     edx, 1; fCancelPendingCallbacks
0x180016290  mov     rcx, rsi; pti
0x180016293  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016299  mov     rcx, rsi; pti
0x18001629c  call    cs:__imp_CloseThreadpoolTimer
0x1800162a2  mov     ecx, ebx; dwErrCode
0x1800162a4  call    cs:__imp_SetLastError
0x1800162aa  mov     qword ptr [rdi+30h], 0
0x1800162b2  mov     rsi, [rdi+38h]
0x1800162b6  test    rsi, rsi
0x1800162b9  jz      short loc_1800162F3
0x1800162bb  call    cs:__imp_GetLastError
0x1800162c1  mov     ebx, eax
0x1800162c3  xor     r9d, r9d; msWindowLength
0x1800162c6  xor     r8d, r8d; msPeriod
0x1800162c9  xor     edx, edx; pftDueTime
0x1800162cb  mov     rcx, rsi; pti
0x1800162ce  call    cs:__imp_SetThreadpoolTimer
0x1800162d4  mov     edx, 1; fCancelPendingCallbacks
0x1800162d9  mov     rcx, rsi; pti
0x1800162dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800162e2  mov     rcx, rsi; pti
0x1800162e5  call    cs:__imp_CloseThreadpoolTimer
0x1800162eb  mov     ecx, ebx; dwErrCode
0x1800162ed  call    cs:__imp_SetLastError
0x1800162f3  mov     qword ptr [rdi+38h], 0
0x1800162fb  mov     rbx, [rdi+100h]
0x180016302  mov     qword ptr [rdi+100h], 0
0x18001630d  test    rbx, rbx
0x180016310  jz      short loc_180016326
0x180016312  call    cs:__imp_GetProcessHeap
0x180016318  mov     rcx, rax; hHeap
0x18001631b  mov     r8, rbx; lpMem
0x18001631e  xor     edx, edx; dwFlags
0x180016320  call    cs:__imp_HeapFree
0x180016326  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18001632d  test    r8, r8
0x180016330  jz      short loc_18001634A
0x180016332  mov     rdx, cs:qword_1800521E8; SRWLock
0x180016339  test    rdx, rdx
0x18001633c  jz      short loc_18001634A
0x18001633e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180016345  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001634a  lea     rbx, [rdi+98h]
0x180016351  mov     rsi, [rbx+40h]
0x180016355  mov     qword ptr [rbx+40h], 0
0x18001635d  test    rsi, rsi
0x180016360  jz      short loc_180016376
0x180016362  call    cs:__imp_GetProcessHeap
0x180016368  mov     rcx, rax; hHeap
0x18001636b  mov     r8, rsi; lpMem
0x18001636e  xor     edx, edx; dwFlags
0x180016370  call    cs:__imp_HeapFree
0x180016376  mov     rcx, rbx; lpCriticalSection
0x180016379  call    cs:__imp_DeleteCriticalSection
0x18001637f  lea     rcx, [rdi+90h]
0x180016386  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001638b  mov     rsi, [rdi+88h]
0x180016392  mov     qword ptr [rdi+88h], 0
0x18001639d  test    rsi, rsi
0x1800163a0  jz      short loc_1800163B6
0x1800163a2  call    cs:__imp_GetProcessHeap
0x1800163a8  mov     rcx, rax; hHeap
0x1800163ab  mov     r8, rsi; lpMem
0x1800163ae  xor     edx, edx; dwFlags
0x1800163b0  call    cs:__imp_HeapFree
0x1800163b6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800163ba  call    cs:__imp_DeleteCriticalSection
0x1800163c0  mov     rbx, [rdi+38h]
0x1800163c4  test    rbx, rbx
0x1800163c7  jz      short loc_1800163F1
0x1800163c9  xor     r9d, r9d; msWindowLength
0x1800163cc  xor     r8d, r8d; msPeriod
0x1800163cf  xor     edx, edx; pftDueTime
0x1800163d1  mov     rcx, rbx; pti
0x1800163d4  call    cs:__imp_SetThreadpoolTimer
0x1800163da  mov     edx, 1; fCancelPendingCallbacks
0x1800163df  mov     rcx, rbx; pti
0x1800163e2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800163e8  mov     rcx, rbx; pti
0x1800163eb  call    cs:__imp_CloseThreadpoolTimer
0x1800163f1  mov     rbx, [rdi+30h]
0x1800163f5  test    rbx, rbx
0x1800163f8  jz      short loc_180016423
0x1800163fa  xor     r9d, r9d; msWindowLength
0x1800163fd  xor     r8d, r8d; msPeriod
0x180016400  xor     edx, edx; pftDueTime
0x180016402  mov     rcx, rbx; pti
0x180016405  call    cs:__imp_SetThreadpoolTimer
0x18001640b  mov     edx, 1; fCancelPendingCallbacks
0x180016410  mov     rcx, rbx; pti
0x180016413  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016419  mov     rcx, rbx; pti
0x18001641c  call    cs:__imp_CloseThreadpoolTimer
0x180016422  nop
0x180016423  mov     rcx, [rdi+10h]; lpMem
0x180016427  test    rcx, rcx
0x18001642a  jz      short loc_180016432
0x18001642c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180016431  nop
0x180016432  mov     rbx, [rsp+28h+arg_0]
0x180016437  mov     rsi, [rsp+28h+arg_8]
0x18001643c  add     rsp, 20h
0x180016440  pop     rdi
0x180016441  retn
```
