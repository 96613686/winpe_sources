# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140003428`
- end: `0x140003616`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001b1b0`

## callees

- `0x1400032e4`
- `0x140003428`
- `0x1400069c0`
- `0x140007e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000354d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000358e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000354d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000358e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400034f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400034f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400034e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400034e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000348f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000348f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400034c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400034c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003459`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400034a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400035a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400035d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003459`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400034a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400035a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400035d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400034b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400035bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400035f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400034b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400035bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400035f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003467`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400034b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400035b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400035e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003467`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400034b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400035b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400035e7`

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
  if ( v8 && qword_1400290B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400290B8[25], qword_1400290B8, v8);
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
0x140003428  mov     [rsp+arg_0], rbx
0x14000342d  mov     [rsp+arg_8], rsi
0x140003432  push    rdi
0x140003433  sub     rsp, 20h
0x140003437  mov     rdi, rcx
0x14000343a  mov     byte ptr [rcx], 0
0x14000343d  mov     rsi, [rcx+30h]
0x140003441  test    rsi, rsi
0x140003444  jz      short loc_14000347E
0x140003446  call    cs:__imp_GetLastError
0x14000344c  mov     ebx, eax
0x14000344e  xor     r9d, r9d; msWindowLength
0x140003451  xor     r8d, r8d; msPeriod
0x140003454  xor     edx, edx; pftDueTime
0x140003456  mov     rcx, rsi; pti
0x140003459  call    cs:__imp_SetThreadpoolTimer
0x14000345f  mov     edx, 1; fCancelPendingCallbacks
0x140003464  mov     rcx, rsi; pti
0x140003467  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000346d  mov     rcx, rsi; pti
0x140003470  call    cs:__imp_CloseThreadpoolTimer
0x140003476  mov     ecx, ebx; dwErrCode
0x140003478  call    cs:__imp_SetLastError
0x14000347e  mov     qword ptr [rdi+30h], 0
0x140003486  mov     rsi, [rdi+38h]
0x14000348a  test    rsi, rsi
0x14000348d  jz      short loc_1400034C7
0x14000348f  call    cs:__imp_GetLastError
0x140003495  mov     ebx, eax
0x140003497  xor     r9d, r9d; msWindowLength
0x14000349a  xor     r8d, r8d; msPeriod
0x14000349d  xor     edx, edx; pftDueTime
0x14000349f  mov     rcx, rsi; pti
0x1400034a2  call    cs:__imp_SetThreadpoolTimer
0x1400034a8  mov     edx, 1; fCancelPendingCallbacks
0x1400034ad  mov     rcx, rsi; pti
0x1400034b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400034b6  mov     rcx, rsi; pti
0x1400034b9  call    cs:__imp_CloseThreadpoolTimer
0x1400034bf  mov     ecx, ebx; dwErrCode
0x1400034c1  call    cs:__imp_SetLastError
0x1400034c7  mov     qword ptr [rdi+38h], 0
0x1400034cf  mov     rbx, [rdi+100h]
0x1400034d6  mov     qword ptr [rdi+100h], 0
0x1400034e1  test    rbx, rbx
0x1400034e4  jz      short loc_1400034FA
0x1400034e6  call    cs:__imp_GetProcessHeap
0x1400034ec  mov     rcx, rax; hHeap
0x1400034ef  mov     r8, rbx; lpMem
0x1400034f2  xor     edx, edx; dwFlags
0x1400034f4  call    cs:__imp_HeapFree
0x1400034fa  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140003501  test    r8, r8
0x140003504  jz      short loc_14000351E
0x140003506  mov     rdx, cs:qword_1400290B8; SRWLock
0x14000350d  test    rdx, rdx
0x140003510  jz      short loc_14000351E
0x140003512  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140003519  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000351e  lea     rbx, [rdi+98h]
0x140003525  mov     rsi, [rbx+40h]
0x140003529  mov     qword ptr [rbx+40h], 0
0x140003531  test    rsi, rsi
0x140003534  jz      short loc_14000354A
0x140003536  call    cs:__imp_GetProcessHeap
0x14000353c  mov     rcx, rax; hHeap
0x14000353f  mov     r8, rsi; lpMem
0x140003542  xor     edx, edx; dwFlags
0x140003544  call    cs:__imp_HeapFree
0x14000354a  mov     rcx, rbx; lpCriticalSection
0x14000354d  call    cs:__imp_DeleteCriticalSection
0x140003553  lea     rcx, [rdi+90h]
0x14000355a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000355f  mov     rsi, [rdi+88h]
0x140003566  mov     qword ptr [rdi+88h], 0
0x140003571  test    rsi, rsi
0x140003574  jz      short loc_14000358A
0x140003576  call    cs:__imp_GetProcessHeap
0x14000357c  mov     rcx, rax; hHeap
0x14000357f  mov     r8, rsi; lpMem
0x140003582  xor     edx, edx; dwFlags
0x140003584  call    cs:__imp_HeapFree
0x14000358a  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000358e  call    cs:__imp_DeleteCriticalSection
0x140003594  mov     rbx, [rdi+38h]
0x140003598  test    rbx, rbx
0x14000359b  jz      short loc_1400035C5
0x14000359d  xor     r9d, r9d; msWindowLength
0x1400035a0  xor     r8d, r8d; msPeriod
0x1400035a3  xor     edx, edx; pftDueTime
0x1400035a5  mov     rcx, rbx; pti
0x1400035a8  call    cs:__imp_SetThreadpoolTimer
0x1400035ae  mov     edx, 1; fCancelPendingCallbacks
0x1400035b3  mov     rcx, rbx; pti
0x1400035b6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400035bc  mov     rcx, rbx; pti
0x1400035bf  call    cs:__imp_CloseThreadpoolTimer
0x1400035c5  mov     rbx, [rdi+30h]
0x1400035c9  test    rbx, rbx
0x1400035cc  jz      short loc_1400035F7
0x1400035ce  xor     r9d, r9d; msWindowLength
0x1400035d1  xor     r8d, r8d; msPeriod
0x1400035d4  xor     edx, edx; pftDueTime
0x1400035d6  mov     rcx, rbx; pti
0x1400035d9  call    cs:__imp_SetThreadpoolTimer
0x1400035df  mov     edx, 1; fCancelPendingCallbacks
0x1400035e4  mov     rcx, rbx; pti
0x1400035e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400035ed  mov     rcx, rbx; pti
0x1400035f0  call    cs:__imp_CloseThreadpoolTimer
0x1400035f6  nop
0x1400035f7  mov     rcx, [rdi+10h]; lpMem
0x1400035fb  test    rcx, rcx
0x1400035fe  jz      short loc_140003606
0x140003600  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140003605  nop
0x140003606  mov     rbx, [rsp+28h+arg_0]
0x14000360b  mov     rsi, [rsp+28h+arg_8]
0x140003610  add     rsp, 20h
0x140003614  pop     rdi
0x140003615  retn
```
