# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180010fe0`
- end: `0x1800111ce`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180046d50`

## callees

- `0x1800108cc`
- `0x180010fe0`
- `0x18001c5d8`
- `0x18002028c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001109e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001112e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001109e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001112e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001113c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001113c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011105`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011146`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011105`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011146`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011079`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011047`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011011`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001105a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011160`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011191`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011011`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001105a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011160`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011191`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011028`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011071`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011177`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800111a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011028`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011071`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011177`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800111a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001101f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011068`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001116e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001119f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001101f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011068`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001116e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001119f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  if ( v8 && qword_18005A198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18005A198[25], qword_18005A198, v8);
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
0x180010fe0  mov     [rsp+arg_0], rbx
0x180010fe5  mov     [rsp+arg_8], rsi
0x180010fea  push    rdi
0x180010feb  sub     rsp, 20h
0x180010fef  mov     rdi, rcx
0x180010ff2  mov     byte ptr [rcx], 0
0x180010ff5  mov     rsi, [rcx+30h]
0x180010ff9  test    rsi, rsi
0x180010ffc  jz      short loc_180011036
0x180010ffe  call    cs:__imp_GetLastError
0x180011004  mov     ebx, eax
0x180011006  xor     r9d, r9d; msWindowLength
0x180011009  xor     r8d, r8d; msPeriod
0x18001100c  xor     edx, edx; pftDueTime
0x18001100e  mov     rcx, rsi; pti
0x180011011  call    cs:__imp_SetThreadpoolTimer
0x180011017  mov     edx, 1; fCancelPendingCallbacks
0x18001101c  mov     rcx, rsi; pti
0x18001101f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011025  mov     rcx, rsi; pti
0x180011028  call    cs:__imp_CloseThreadpoolTimer
0x18001102e  mov     ecx, ebx; dwErrCode
0x180011030  call    cs:__imp_SetLastError
0x180011036  mov     qword ptr [rdi+30h], 0
0x18001103e  mov     rsi, [rdi+38h]
0x180011042  test    rsi, rsi
0x180011045  jz      short loc_18001107F
0x180011047  call    cs:__imp_GetLastError
0x18001104d  mov     ebx, eax
0x18001104f  xor     r9d, r9d; msWindowLength
0x180011052  xor     r8d, r8d; msPeriod
0x180011055  xor     edx, edx; pftDueTime
0x180011057  mov     rcx, rsi; pti
0x18001105a  call    cs:__imp_SetThreadpoolTimer
0x180011060  mov     edx, 1; fCancelPendingCallbacks
0x180011065  mov     rcx, rsi; pti
0x180011068  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001106e  mov     rcx, rsi; pti
0x180011071  call    cs:__imp_CloseThreadpoolTimer
0x180011077  mov     ecx, ebx; dwErrCode
0x180011079  call    cs:__imp_SetLastError
0x18001107f  mov     qword ptr [rdi+38h], 0
0x180011087  mov     rbx, [rdi+100h]
0x18001108e  mov     qword ptr [rdi+100h], 0
0x180011099  test    rbx, rbx
0x18001109c  jz      short loc_1800110B2
0x18001109e  call    cs:__imp_GetProcessHeap
0x1800110a4  mov     rcx, rax; hHeap
0x1800110a7  mov     r8, rbx; lpMem
0x1800110aa  xor     edx, edx; dwFlags
0x1800110ac  call    cs:__imp_HeapFree
0x1800110b2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800110b9  test    r8, r8
0x1800110bc  jz      short loc_1800110D6
0x1800110be  mov     rdx, cs:qword_18005A198; SRWLock
0x1800110c5  test    rdx, rdx
0x1800110c8  jz      short loc_1800110D6
0x1800110ca  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800110d1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800110d6  lea     rbx, [rdi+98h]
0x1800110dd  mov     rsi, [rbx+40h]
0x1800110e1  mov     qword ptr [rbx+40h], 0
0x1800110e9  test    rsi, rsi
0x1800110ec  jz      short loc_180011102
0x1800110ee  call    cs:__imp_GetProcessHeap
0x1800110f4  mov     rcx, rax; hHeap
0x1800110f7  mov     r8, rsi; lpMem
0x1800110fa  xor     edx, edx; dwFlags
0x1800110fc  call    cs:__imp_HeapFree
0x180011102  mov     rcx, rbx; lpCriticalSection
0x180011105  call    cs:__imp_DeleteCriticalSection
0x18001110b  lea     rcx, [rdi+90h]
0x180011112  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011117  mov     rsi, [rdi+88h]
0x18001111e  mov     qword ptr [rdi+88h], 0
0x180011129  test    rsi, rsi
0x18001112c  jz      short loc_180011142
0x18001112e  call    cs:__imp_GetProcessHeap
0x180011134  mov     rcx, rax; hHeap
0x180011137  mov     r8, rsi; lpMem
0x18001113a  xor     edx, edx; dwFlags
0x18001113c  call    cs:__imp_HeapFree
0x180011142  lea     rcx, [rdi+48h]; lpCriticalSection
0x180011146  call    cs:__imp_DeleteCriticalSection
0x18001114c  mov     rbx, [rdi+38h]
0x180011150  test    rbx, rbx
0x180011153  jz      short loc_18001117D
0x180011155  xor     r9d, r9d; msWindowLength
0x180011158  xor     r8d, r8d; msPeriod
0x18001115b  xor     edx, edx; pftDueTime
0x18001115d  mov     rcx, rbx; pti
0x180011160  call    cs:__imp_SetThreadpoolTimer
0x180011166  mov     edx, 1; fCancelPendingCallbacks
0x18001116b  mov     rcx, rbx; pti
0x18001116e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011174  mov     rcx, rbx; pti
0x180011177  call    cs:__imp_CloseThreadpoolTimer
0x18001117d  mov     rbx, [rdi+30h]
0x180011181  test    rbx, rbx
0x180011184  jz      short loc_1800111AF
0x180011186  xor     r9d, r9d; msWindowLength
0x180011189  xor     r8d, r8d; msPeriod
0x18001118c  xor     edx, edx; pftDueTime
0x18001118e  mov     rcx, rbx; pti
0x180011191  call    cs:__imp_SetThreadpoolTimer
0x180011197  mov     edx, 1; fCancelPendingCallbacks
0x18001119c  mov     rcx, rbx; pti
0x18001119f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800111a5  mov     rcx, rbx; pti
0x1800111a8  call    cs:__imp_CloseThreadpoolTimer
0x1800111ae  nop
0x1800111af  mov     rcx, [rdi+10h]; lpMem
0x1800111b3  test    rcx, rcx
0x1800111b6  jz      short loc_1800111BE
0x1800111b8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800111bd  nop
0x1800111be  mov     rbx, [rsp+28h+arg_0]
0x1800111c3  mov     rsi, [rsp+28h+arg_8]
0x1800111c8  add     rsp, 20h
0x1800111cc  pop     rdi
0x1800111cd  retn
```
