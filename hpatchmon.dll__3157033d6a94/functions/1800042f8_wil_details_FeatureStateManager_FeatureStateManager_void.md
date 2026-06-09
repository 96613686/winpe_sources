# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800042f8`
- end: `0x1800044e6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800145b0`

## callees

- `0x180004054`
- `0x1800042f8`
- `0x180009440`
- `0x18000bf40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000435f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000435f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004391`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004391`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000441d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000445e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000441d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000445e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004414`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004414`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004454`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004406`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004406`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004446`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004372`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004478`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800044a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004372`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004478`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800044a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004340`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004389`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000448f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800044c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004340`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004389`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000448f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800044c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004337`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004380`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004486`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800044b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004337`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004380`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004486`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800044b7`

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
  if ( v8 && qword_18001E3C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001E3C8[25], qword_18001E3C8, v8);
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
0x1800042f8  mov     [rsp+arg_0], rbx
0x1800042fd  mov     [rsp+arg_8], rsi
0x180004302  push    rdi
0x180004303  sub     rsp, 20h
0x180004307  mov     rdi, rcx
0x18000430a  mov     byte ptr [rcx], 0
0x18000430d  mov     rsi, [rcx+30h]
0x180004311  test    rsi, rsi
0x180004314  jz      short loc_18000434E
0x180004316  call    cs:__imp_GetLastError
0x18000431c  mov     ebx, eax
0x18000431e  xor     r9d, r9d; msWindowLength
0x180004321  xor     r8d, r8d; msPeriod
0x180004324  xor     edx, edx; pftDueTime
0x180004326  mov     rcx, rsi; pti
0x180004329  call    cs:__imp_SetThreadpoolTimer
0x18000432f  mov     edx, 1; fCancelPendingCallbacks
0x180004334  mov     rcx, rsi; pti
0x180004337  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000433d  mov     rcx, rsi; pti
0x180004340  call    cs:__imp_CloseThreadpoolTimer
0x180004346  mov     ecx, ebx; dwErrCode
0x180004348  call    cs:__imp_SetLastError
0x18000434e  mov     qword ptr [rdi+30h], 0
0x180004356  mov     rsi, [rdi+38h]
0x18000435a  test    rsi, rsi
0x18000435d  jz      short loc_180004397
0x18000435f  call    cs:__imp_GetLastError
0x180004365  mov     ebx, eax
0x180004367  xor     r9d, r9d; msWindowLength
0x18000436a  xor     r8d, r8d; msPeriod
0x18000436d  xor     edx, edx; pftDueTime
0x18000436f  mov     rcx, rsi; pti
0x180004372  call    cs:__imp_SetThreadpoolTimer
0x180004378  mov     edx, 1; fCancelPendingCallbacks
0x18000437d  mov     rcx, rsi; pti
0x180004380  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004386  mov     rcx, rsi; pti
0x180004389  call    cs:__imp_CloseThreadpoolTimer
0x18000438f  mov     ecx, ebx; dwErrCode
0x180004391  call    cs:__imp_SetLastError
0x180004397  mov     qword ptr [rdi+38h], 0
0x18000439f  mov     rbx, [rdi+100h]
0x1800043a6  mov     qword ptr [rdi+100h], 0
0x1800043b1  test    rbx, rbx
0x1800043b4  jz      short loc_1800043CA
0x1800043b6  call    cs:__imp_GetProcessHeap
0x1800043bc  mov     rcx, rax; hHeap
0x1800043bf  mov     r8, rbx; lpMem
0x1800043c2  xor     edx, edx; dwFlags
0x1800043c4  call    cs:__imp_HeapFree
0x1800043ca  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800043d1  test    r8, r8
0x1800043d4  jz      short loc_1800043EE
0x1800043d6  mov     rdx, cs:qword_18001E3C8; SRWLock
0x1800043dd  test    rdx, rdx
0x1800043e0  jz      short loc_1800043EE
0x1800043e2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800043e9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800043ee  lea     rbx, [rdi+98h]
0x1800043f5  mov     rsi, [rbx+40h]
0x1800043f9  mov     qword ptr [rbx+40h], 0
0x180004401  test    rsi, rsi
0x180004404  jz      short loc_18000441A
0x180004406  call    cs:__imp_GetProcessHeap
0x18000440c  mov     rcx, rax; hHeap
0x18000440f  mov     r8, rsi; lpMem
0x180004412  xor     edx, edx; dwFlags
0x180004414  call    cs:__imp_HeapFree
0x18000441a  mov     rcx, rbx; lpCriticalSection
0x18000441d  call    cs:__imp_DeleteCriticalSection
0x180004423  lea     rcx, [rdi+90h]
0x18000442a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000442f  mov     rsi, [rdi+88h]
0x180004436  mov     qword ptr [rdi+88h], 0
0x180004441  test    rsi, rsi
0x180004444  jz      short loc_18000445A
0x180004446  call    cs:__imp_GetProcessHeap
0x18000444c  mov     rcx, rax; hHeap
0x18000444f  mov     r8, rsi; lpMem
0x180004452  xor     edx, edx; dwFlags
0x180004454  call    cs:__imp_HeapFree
0x18000445a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000445e  call    cs:__imp_DeleteCriticalSection
0x180004464  mov     rbx, [rdi+38h]
0x180004468  test    rbx, rbx
0x18000446b  jz      short loc_180004495
0x18000446d  xor     r9d, r9d; msWindowLength
0x180004470  xor     r8d, r8d; msPeriod
0x180004473  xor     edx, edx; pftDueTime
0x180004475  mov     rcx, rbx; pti
0x180004478  call    cs:__imp_SetThreadpoolTimer
0x18000447e  mov     edx, 1; fCancelPendingCallbacks
0x180004483  mov     rcx, rbx; pti
0x180004486  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000448c  mov     rcx, rbx; pti
0x18000448f  call    cs:__imp_CloseThreadpoolTimer
0x180004495  mov     rbx, [rdi+30h]
0x180004499  test    rbx, rbx
0x18000449c  jz      short loc_1800044C7
0x18000449e  xor     r9d, r9d; msWindowLength
0x1800044a1  xor     r8d, r8d; msPeriod
0x1800044a4  xor     edx, edx; pftDueTime
0x1800044a6  mov     rcx, rbx; pti
0x1800044a9  call    cs:__imp_SetThreadpoolTimer
0x1800044af  mov     edx, 1; fCancelPendingCallbacks
0x1800044b4  mov     rcx, rbx; pti
0x1800044b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800044bd  mov     rcx, rbx; pti
0x1800044c0  call    cs:__imp_CloseThreadpoolTimer
0x1800044c6  nop
0x1800044c7  mov     rcx, [rdi+10h]; lpMem
0x1800044cb  test    rcx, rcx
0x1800044ce  jz      short loc_1800044D6
0x1800044d0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800044d5  nop
0x1800044d6  mov     rbx, [rsp+28h+arg_0]
0x1800044db  mov     rsi, [rsp+28h+arg_8]
0x1800044e0  add     rsp, 20h
0x1800044e4  pop     rdi
0x1800044e5  retn
```
