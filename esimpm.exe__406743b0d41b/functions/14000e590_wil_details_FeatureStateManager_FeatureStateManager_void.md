# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000e590`
- end: `0x14000e77e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14003da70`

## callees

- `0x14000e2ec`
- `0x14000e590`
- `0x140012230`
- `0x140013740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e6b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e6f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e6b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e6f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e65c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e65c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e6ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e64e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e69e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e6de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e64e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e69e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e6de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e629`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e629`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e5d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e621`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e727`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e758`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e5d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e621`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e727`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e758`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e5cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e618`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e71e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e74f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e5cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e618`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e71e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e74f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e5c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e60a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e710`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e741`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e5c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e60a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e710`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e741`

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
  if ( v8 && qword_140075108 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140075108[25], qword_140075108, v8);
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
0x14000e590  mov     [rsp+arg_0], rbx
0x14000e595  mov     [rsp+arg_8], rsi
0x14000e59a  push    rdi
0x14000e59b  sub     rsp, 20h
0x14000e59f  mov     rdi, rcx
0x14000e5a2  mov     byte ptr [rcx], 0
0x14000e5a5  mov     rsi, [rcx+30h]
0x14000e5a9  test    rsi, rsi
0x14000e5ac  jz      short loc_14000E5E6
0x14000e5ae  call    cs:__imp_GetLastError
0x14000e5b4  mov     ebx, eax
0x14000e5b6  xor     r9d, r9d; msWindowLength
0x14000e5b9  xor     r8d, r8d; msPeriod
0x14000e5bc  xor     edx, edx; pftDueTime
0x14000e5be  mov     rcx, rsi; pti
0x14000e5c1  call    cs:__imp_SetThreadpoolTimer
0x14000e5c7  mov     edx, 1; fCancelPendingCallbacks
0x14000e5cc  mov     rcx, rsi; pti
0x14000e5cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e5d5  mov     rcx, rsi; pti
0x14000e5d8  call    cs:__imp_CloseThreadpoolTimer
0x14000e5de  mov     ecx, ebx; dwErrCode
0x14000e5e0  call    cs:__imp_SetLastError
0x14000e5e6  mov     qword ptr [rdi+30h], 0
0x14000e5ee  mov     rsi, [rdi+38h]
0x14000e5f2  test    rsi, rsi
0x14000e5f5  jz      short loc_14000E62F
0x14000e5f7  call    cs:__imp_GetLastError
0x14000e5fd  mov     ebx, eax
0x14000e5ff  xor     r9d, r9d; msWindowLength
0x14000e602  xor     r8d, r8d; msPeriod
0x14000e605  xor     edx, edx; pftDueTime
0x14000e607  mov     rcx, rsi; pti
0x14000e60a  call    cs:__imp_SetThreadpoolTimer
0x14000e610  mov     edx, 1; fCancelPendingCallbacks
0x14000e615  mov     rcx, rsi; pti
0x14000e618  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e61e  mov     rcx, rsi; pti
0x14000e621  call    cs:__imp_CloseThreadpoolTimer
0x14000e627  mov     ecx, ebx; dwErrCode
0x14000e629  call    cs:__imp_SetLastError
0x14000e62f  mov     qword ptr [rdi+38h], 0
0x14000e637  mov     rbx, [rdi+100h]
0x14000e63e  mov     qword ptr [rdi+100h], 0
0x14000e649  test    rbx, rbx
0x14000e64c  jz      short loc_14000E662
0x14000e64e  call    cs:__imp_GetProcessHeap
0x14000e654  mov     rcx, rax; hHeap
0x14000e657  mov     r8, rbx; lpMem
0x14000e65a  xor     edx, edx; dwFlags
0x14000e65c  call    cs:__imp_HeapFree
0x14000e662  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14000e669  test    r8, r8
0x14000e66c  jz      short loc_14000E686
0x14000e66e  mov     rdx, cs:qword_140075108; SRWLock
0x14000e675  test    rdx, rdx
0x14000e678  jz      short loc_14000E686
0x14000e67a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000e681  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000e686  lea     rbx, [rdi+98h]
0x14000e68d  mov     rsi, [rbx+40h]
0x14000e691  mov     qword ptr [rbx+40h], 0
0x14000e699  test    rsi, rsi
0x14000e69c  jz      short loc_14000E6B2
0x14000e69e  call    cs:__imp_GetProcessHeap
0x14000e6a4  mov     rcx, rax; hHeap
0x14000e6a7  mov     r8, rsi; lpMem
0x14000e6aa  xor     edx, edx; dwFlags
0x14000e6ac  call    cs:__imp_HeapFree
0x14000e6b2  mov     rcx, rbx; lpCriticalSection
0x14000e6b5  call    cs:__imp_DeleteCriticalSection
0x14000e6bb  lea     rcx, [rdi+90h]
0x14000e6c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000e6c7  mov     rsi, [rdi+88h]
0x14000e6ce  mov     qword ptr [rdi+88h], 0
0x14000e6d9  test    rsi, rsi
0x14000e6dc  jz      short loc_14000E6F2
0x14000e6de  call    cs:__imp_GetProcessHeap
0x14000e6e4  mov     rcx, rax; hHeap
0x14000e6e7  mov     r8, rsi; lpMem
0x14000e6ea  xor     edx, edx; dwFlags
0x14000e6ec  call    cs:__imp_HeapFree
0x14000e6f2  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000e6f6  call    cs:__imp_DeleteCriticalSection
0x14000e6fc  mov     rbx, [rdi+38h]
0x14000e700  test    rbx, rbx
0x14000e703  jz      short loc_14000E72D
0x14000e705  xor     r9d, r9d; msWindowLength
0x14000e708  xor     r8d, r8d; msPeriod
0x14000e70b  xor     edx, edx; pftDueTime
0x14000e70d  mov     rcx, rbx; pti
0x14000e710  call    cs:__imp_SetThreadpoolTimer
0x14000e716  mov     edx, 1; fCancelPendingCallbacks
0x14000e71b  mov     rcx, rbx; pti
0x14000e71e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e724  mov     rcx, rbx; pti
0x14000e727  call    cs:__imp_CloseThreadpoolTimer
0x14000e72d  mov     rbx, [rdi+30h]
0x14000e731  test    rbx, rbx
0x14000e734  jz      short loc_14000E75F
0x14000e736  xor     r9d, r9d; msWindowLength
0x14000e739  xor     r8d, r8d; msPeriod
0x14000e73c  xor     edx, edx; pftDueTime
0x14000e73e  mov     rcx, rbx; pti
0x14000e741  call    cs:__imp_SetThreadpoolTimer
0x14000e747  mov     edx, 1; fCancelPendingCallbacks
0x14000e74c  mov     rcx, rbx; pti
0x14000e74f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e755  mov     rcx, rbx; pti
0x14000e758  call    cs:__imp_CloseThreadpoolTimer
0x14000e75e  nop
0x14000e75f  mov     rcx, [rdi+10h]; lpMem
0x14000e763  test    rcx, rcx
0x14000e766  jz      short loc_14000E76E
0x14000e768  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000e76d  nop
0x14000e76e  mov     rbx, [rsp+28h+arg_0]
0x14000e773  mov     rsi, [rsp+28h+arg_8]
0x14000e778  add     rsp, 20h
0x14000e77c  pop     rdi
0x14000e77d  retn
```
