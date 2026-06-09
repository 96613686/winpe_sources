# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008900`
- end: `0x180008aee`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801151d0`

## callees

- `0x18000865c`
- `0x180008900`
- `0x18000ccd0`
- `0x18000e474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008a25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008a66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008a25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008999`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000891e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000891e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008967`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000893f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008988`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008abf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000893f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008988`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008abf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008931`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000897a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008ab1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008931`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000897a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008ab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008948`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008991`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ac8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008948`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008991`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ac8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_180155898 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180155898[25], qword_180155898, v8);
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
0x180008900  mov     [rsp+arg_0], rbx
0x180008905  mov     [rsp+arg_8], rsi
0x18000890a  push    rdi
0x18000890b  sub     rsp, 20h
0x18000890f  mov     rdi, rcx
0x180008912  mov     byte ptr [rcx], 0
0x180008915  mov     rsi, [rcx+30h]
0x180008919  test    rsi, rsi
0x18000891c  jz      short loc_180008956
0x18000891e  call    cs:__imp_GetLastError
0x180008924  mov     ebx, eax
0x180008926  xor     r9d, r9d; msWindowLength
0x180008929  xor     r8d, r8d; msPeriod
0x18000892c  xor     edx, edx; pftDueTime
0x18000892e  mov     rcx, rsi; pti
0x180008931  call    cs:__imp_SetThreadpoolTimer
0x180008937  mov     edx, 1; fCancelPendingCallbacks
0x18000893c  mov     rcx, rsi; pti
0x18000893f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008945  mov     rcx, rsi; pti
0x180008948  call    cs:__imp_CloseThreadpoolTimer
0x18000894e  mov     ecx, ebx; dwErrCode
0x180008950  call    cs:__imp_SetLastError
0x180008956  mov     qword ptr [rdi+30h], 0
0x18000895e  mov     rsi, [rdi+38h]
0x180008962  test    rsi, rsi
0x180008965  jz      short loc_18000899F
0x180008967  call    cs:__imp_GetLastError
0x18000896d  mov     ebx, eax
0x18000896f  xor     r9d, r9d; msWindowLength
0x180008972  xor     r8d, r8d; msPeriod
0x180008975  xor     edx, edx; pftDueTime
0x180008977  mov     rcx, rsi; pti
0x18000897a  call    cs:__imp_SetThreadpoolTimer
0x180008980  mov     edx, 1; fCancelPendingCallbacks
0x180008985  mov     rcx, rsi; pti
0x180008988  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000898e  mov     rcx, rsi; pti
0x180008991  call    cs:__imp_CloseThreadpoolTimer
0x180008997  mov     ecx, ebx; dwErrCode
0x180008999  call    cs:__imp_SetLastError
0x18000899f  mov     qword ptr [rdi+38h], 0
0x1800089a7  mov     rbx, [rdi+100h]
0x1800089ae  mov     qword ptr [rdi+100h], 0
0x1800089b9  test    rbx, rbx
0x1800089bc  jz      short loc_1800089D2
0x1800089be  call    cs:__imp_GetProcessHeap
0x1800089c4  mov     rcx, rax; hHeap
0x1800089c7  mov     r8, rbx; lpMem
0x1800089ca  xor     edx, edx; dwFlags
0x1800089cc  call    cs:__imp_HeapFree
0x1800089d2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800089d9  test    r8, r8
0x1800089dc  jz      short loc_1800089F6
0x1800089de  mov     rdx, cs:qword_180155898; SRWLock
0x1800089e5  test    rdx, rdx
0x1800089e8  jz      short loc_1800089F6
0x1800089ea  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800089f1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800089f6  lea     rbx, [rdi+98h]
0x1800089fd  mov     rsi, [rbx+40h]
0x180008a01  mov     qword ptr [rbx+40h], 0
0x180008a09  test    rsi, rsi
0x180008a0c  jz      short loc_180008A22
0x180008a0e  call    cs:__imp_GetProcessHeap
0x180008a14  mov     rcx, rax; hHeap
0x180008a17  mov     r8, rsi; lpMem
0x180008a1a  xor     edx, edx; dwFlags
0x180008a1c  call    cs:__imp_HeapFree
0x180008a22  mov     rcx, rbx; lpCriticalSection
0x180008a25  call    cs:__imp_DeleteCriticalSection
0x180008a2b  lea     rcx, [rdi+90h]
0x180008a32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008a37  mov     rsi, [rdi+88h]
0x180008a3e  mov     qword ptr [rdi+88h], 0
0x180008a49  test    rsi, rsi
0x180008a4c  jz      short loc_180008A62
0x180008a4e  call    cs:__imp_GetProcessHeap
0x180008a54  mov     rcx, rax; hHeap
0x180008a57  mov     r8, rsi; lpMem
0x180008a5a  xor     edx, edx; dwFlags
0x180008a5c  call    cs:__imp_HeapFree
0x180008a62  lea     rcx, [rdi+48h]; lpCriticalSection
0x180008a66  call    cs:__imp_DeleteCriticalSection
0x180008a6c  mov     rbx, [rdi+38h]
0x180008a70  test    rbx, rbx
0x180008a73  jz      short loc_180008A9D
0x180008a75  xor     r9d, r9d; msWindowLength
0x180008a78  xor     r8d, r8d; msPeriod
0x180008a7b  xor     edx, edx; pftDueTime
0x180008a7d  mov     rcx, rbx; pti
0x180008a80  call    cs:__imp_SetThreadpoolTimer
0x180008a86  mov     edx, 1; fCancelPendingCallbacks
0x180008a8b  mov     rcx, rbx; pti
0x180008a8e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a94  mov     rcx, rbx; pti
0x180008a97  call    cs:__imp_CloseThreadpoolTimer
0x180008a9d  mov     rbx, [rdi+30h]
0x180008aa1  test    rbx, rbx
0x180008aa4  jz      short loc_180008ACF
0x180008aa6  xor     r9d, r9d; msWindowLength
0x180008aa9  xor     r8d, r8d; msPeriod
0x180008aac  xor     edx, edx; pftDueTime
0x180008aae  mov     rcx, rbx; pti
0x180008ab1  call    cs:__imp_SetThreadpoolTimer
0x180008ab7  mov     edx, 1; fCancelPendingCallbacks
0x180008abc  mov     rcx, rbx; pti
0x180008abf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008ac5  mov     rcx, rbx; pti
0x180008ac8  call    cs:__imp_CloseThreadpoolTimer
0x180008ace  nop
0x180008acf  mov     rcx, [rdi+10h]; lpMem
0x180008ad3  test    rcx, rcx
0x180008ad6  jz      short loc_180008ADE
0x180008ad8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008add  nop
0x180008ade  mov     rbx, [rsp+28h+arg_0]
0x180008ae3  mov     rsi, [rsp+28h+arg_8]
0x180008ae8  add     rsp, 20h
0x180008aec  pop     rdi
0x180008aed  retn
```
