# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000d200`
- end: `0x18000d3ee`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18018cb60`

## callees

- `0x18000cf5c`
- `0x18000d200`
- `0x1800116dc`
- `0x18001301c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d325`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d366`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d325`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d30e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d34e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d30e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d34e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d31c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d35c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d31c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d35c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d267`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d231`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d27a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d380`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d231`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d27a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d380`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d248`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d291`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d397`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d248`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d291`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d397`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d23f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d288`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d38e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d23f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d288`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d38e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3bf`

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
  if ( v8 && qword_1801FE5A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1801FE5A8[25], qword_1801FE5A8, v8);
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
0x18000d200  mov     [rsp+arg_0], rbx
0x18000d205  mov     [rsp+arg_8], rsi
0x18000d20a  push    rdi
0x18000d20b  sub     rsp, 20h
0x18000d20f  mov     rdi, rcx
0x18000d212  mov     byte ptr [rcx], 0
0x18000d215  mov     rsi, [rcx+30h]
0x18000d219  test    rsi, rsi
0x18000d21c  jz      short loc_18000D256
0x18000d21e  call    cs:__imp_GetLastError
0x18000d224  mov     ebx, eax
0x18000d226  xor     r9d, r9d; msWindowLength
0x18000d229  xor     r8d, r8d; msPeriod
0x18000d22c  xor     edx, edx; pftDueTime
0x18000d22e  mov     rcx, rsi; pti
0x18000d231  call    cs:__imp_SetThreadpoolTimer
0x18000d237  mov     edx, 1; fCancelPendingCallbacks
0x18000d23c  mov     rcx, rsi; pti
0x18000d23f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d245  mov     rcx, rsi; pti
0x18000d248  call    cs:__imp_CloseThreadpoolTimer
0x18000d24e  mov     ecx, ebx; dwErrCode
0x18000d250  call    cs:__imp_SetLastError
0x18000d256  mov     qword ptr [rdi+30h], 0
0x18000d25e  mov     rsi, [rdi+38h]
0x18000d262  test    rsi, rsi
0x18000d265  jz      short loc_18000D29F
0x18000d267  call    cs:__imp_GetLastError
0x18000d26d  mov     ebx, eax
0x18000d26f  xor     r9d, r9d; msWindowLength
0x18000d272  xor     r8d, r8d; msPeriod
0x18000d275  xor     edx, edx; pftDueTime
0x18000d277  mov     rcx, rsi; pti
0x18000d27a  call    cs:__imp_SetThreadpoolTimer
0x18000d280  mov     edx, 1; fCancelPendingCallbacks
0x18000d285  mov     rcx, rsi; pti
0x18000d288  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d28e  mov     rcx, rsi; pti
0x18000d291  call    cs:__imp_CloseThreadpoolTimer
0x18000d297  mov     ecx, ebx; dwErrCode
0x18000d299  call    cs:__imp_SetLastError
0x18000d29f  mov     qword ptr [rdi+38h], 0
0x18000d2a7  mov     rbx, [rdi+100h]
0x18000d2ae  mov     qword ptr [rdi+100h], 0
0x18000d2b9  test    rbx, rbx
0x18000d2bc  jz      short loc_18000D2D2
0x18000d2be  call    cs:__imp_GetProcessHeap
0x18000d2c4  mov     rcx, rax; hHeap
0x18000d2c7  mov     r8, rbx; lpMem
0x18000d2ca  xor     edx, edx; dwFlags
0x18000d2cc  call    cs:__imp_HeapFree
0x18000d2d2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000d2d9  test    r8, r8
0x18000d2dc  jz      short loc_18000D2F6
0x18000d2de  mov     rdx, cs:qword_1801FE5A8; SRWLock
0x18000d2e5  test    rdx, rdx
0x18000d2e8  jz      short loc_18000D2F6
0x18000d2ea  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000d2f1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000d2f6  lea     rbx, [rdi+98h]
0x18000d2fd  mov     rsi, [rbx+40h]
0x18000d301  mov     qword ptr [rbx+40h], 0
0x18000d309  test    rsi, rsi
0x18000d30c  jz      short loc_18000D322
0x18000d30e  call    cs:__imp_GetProcessHeap
0x18000d314  mov     rcx, rax; hHeap
0x18000d317  mov     r8, rsi; lpMem
0x18000d31a  xor     edx, edx; dwFlags
0x18000d31c  call    cs:__imp_HeapFree
0x18000d322  mov     rcx, rbx; lpCriticalSection
0x18000d325  call    cs:__imp_DeleteCriticalSection
0x18000d32b  lea     rcx, [rdi+90h]
0x18000d332  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000d337  mov     rsi, [rdi+88h]
0x18000d33e  mov     qword ptr [rdi+88h], 0
0x18000d349  test    rsi, rsi
0x18000d34c  jz      short loc_18000D362
0x18000d34e  call    cs:__imp_GetProcessHeap
0x18000d354  mov     rcx, rax; hHeap
0x18000d357  mov     r8, rsi; lpMem
0x18000d35a  xor     edx, edx; dwFlags
0x18000d35c  call    cs:__imp_HeapFree
0x18000d362  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000d366  call    cs:__imp_DeleteCriticalSection
0x18000d36c  mov     rbx, [rdi+38h]
0x18000d370  test    rbx, rbx
0x18000d373  jz      short loc_18000D39D
0x18000d375  xor     r9d, r9d; msWindowLength
0x18000d378  xor     r8d, r8d; msPeriod
0x18000d37b  xor     edx, edx; pftDueTime
0x18000d37d  mov     rcx, rbx; pti
0x18000d380  call    cs:__imp_SetThreadpoolTimer
0x18000d386  mov     edx, 1; fCancelPendingCallbacks
0x18000d38b  mov     rcx, rbx; pti
0x18000d38e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d394  mov     rcx, rbx; pti
0x18000d397  call    cs:__imp_CloseThreadpoolTimer
0x18000d39d  mov     rbx, [rdi+30h]
0x18000d3a1  test    rbx, rbx
0x18000d3a4  jz      short loc_18000D3CF
0x18000d3a6  xor     r9d, r9d; msWindowLength
0x18000d3a9  xor     r8d, r8d; msPeriod
0x18000d3ac  xor     edx, edx; pftDueTime
0x18000d3ae  mov     rcx, rbx; pti
0x18000d3b1  call    cs:__imp_SetThreadpoolTimer
0x18000d3b7  mov     edx, 1; fCancelPendingCallbacks
0x18000d3bc  mov     rcx, rbx; pti
0x18000d3bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d3c5  mov     rcx, rbx; pti
0x18000d3c8  call    cs:__imp_CloseThreadpoolTimer
0x18000d3ce  nop
0x18000d3cf  mov     rcx, [rdi+10h]; lpMem
0x18000d3d3  test    rcx, rcx
0x18000d3d6  jz      short loc_18000D3DE
0x18000d3d8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000d3dd  nop
0x18000d3de  mov     rbx, [rsp+28h+arg_0]
0x18000d3e3  mov     rsi, [rsp+28h+arg_8]
0x18000d3e8  add     rsp, 20h
0x18000d3ec  pop     rdi
0x18000d3ed  retn
```
