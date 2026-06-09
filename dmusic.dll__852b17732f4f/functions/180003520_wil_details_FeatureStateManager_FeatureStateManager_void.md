# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003520`
- end: `0x18000370e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180021d40`

## callees

- `0x18000327c`
- `0x180003520`
- `0x1800074b0`
- `0x18000888c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003645`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003686`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003645`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000363c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000367c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000363c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000367c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000362e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000362e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003570`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003570`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003551`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000359a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003551`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000359a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003568`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003568`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000355f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000355f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036df`

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
  if ( v8 && qword_18002A058 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002A058[25], qword_18002A058, v8);
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
0x180003520  mov     [rsp+arg_0], rbx
0x180003525  mov     [rsp+arg_8], rsi
0x18000352a  push    rdi
0x18000352b  sub     rsp, 20h
0x18000352f  mov     rdi, rcx
0x180003532  mov     byte ptr [rcx], 0
0x180003535  mov     rsi, [rcx+30h]
0x180003539  test    rsi, rsi
0x18000353c  jz      short loc_180003576
0x18000353e  call    cs:__imp_GetLastError
0x180003544  mov     ebx, eax
0x180003546  xor     r9d, r9d; msWindowLength
0x180003549  xor     r8d, r8d; msPeriod
0x18000354c  xor     edx, edx; pftDueTime
0x18000354e  mov     rcx, rsi; pti
0x180003551  call    cs:__imp_SetThreadpoolTimer
0x180003557  mov     edx, 1; fCancelPendingCallbacks
0x18000355c  mov     rcx, rsi; pti
0x18000355f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003565  mov     rcx, rsi; pti
0x180003568  call    cs:__imp_CloseThreadpoolTimer
0x18000356e  mov     ecx, ebx; dwErrCode
0x180003570  call    cs:__imp_SetLastError
0x180003576  mov     qword ptr [rdi+30h], 0
0x18000357e  mov     rsi, [rdi+38h]
0x180003582  test    rsi, rsi
0x180003585  jz      short loc_1800035BF
0x180003587  call    cs:__imp_GetLastError
0x18000358d  mov     ebx, eax
0x18000358f  xor     r9d, r9d; msWindowLength
0x180003592  xor     r8d, r8d; msPeriod
0x180003595  xor     edx, edx; pftDueTime
0x180003597  mov     rcx, rsi; pti
0x18000359a  call    cs:__imp_SetThreadpoolTimer
0x1800035a0  mov     edx, 1; fCancelPendingCallbacks
0x1800035a5  mov     rcx, rsi; pti
0x1800035a8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800035ae  mov     rcx, rsi; pti
0x1800035b1  call    cs:__imp_CloseThreadpoolTimer
0x1800035b7  mov     ecx, ebx; dwErrCode
0x1800035b9  call    cs:__imp_SetLastError
0x1800035bf  mov     qword ptr [rdi+38h], 0
0x1800035c7  mov     rbx, [rdi+100h]
0x1800035ce  mov     qword ptr [rdi+100h], 0
0x1800035d9  test    rbx, rbx
0x1800035dc  jz      short loc_1800035F2
0x1800035de  call    cs:__imp_GetProcessHeap
0x1800035e4  mov     rcx, rax; hHeap
0x1800035e7  mov     r8, rbx; lpMem
0x1800035ea  xor     edx, edx; dwFlags
0x1800035ec  call    cs:__imp_HeapFree
0x1800035f2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800035f9  test    r8, r8
0x1800035fc  jz      short loc_180003616
0x1800035fe  mov     rdx, cs:qword_18002A058; SRWLock
0x180003605  test    rdx, rdx
0x180003608  jz      short loc_180003616
0x18000360a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003611  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003616  lea     rbx, [rdi+98h]
0x18000361d  mov     rsi, [rbx+40h]
0x180003621  mov     qword ptr [rbx+40h], 0
0x180003629  test    rsi, rsi
0x18000362c  jz      short loc_180003642
0x18000362e  call    cs:__imp_GetProcessHeap
0x180003634  mov     rcx, rax; hHeap
0x180003637  mov     r8, rsi; lpMem
0x18000363a  xor     edx, edx; dwFlags
0x18000363c  call    cs:__imp_HeapFree
0x180003642  mov     rcx, rbx; lpCriticalSection
0x180003645  call    cs:__imp_DeleteCriticalSection
0x18000364b  lea     rcx, [rdi+90h]
0x180003652  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003657  mov     rsi, [rdi+88h]
0x18000365e  mov     qword ptr [rdi+88h], 0
0x180003669  test    rsi, rsi
0x18000366c  jz      short loc_180003682
0x18000366e  call    cs:__imp_GetProcessHeap
0x180003674  mov     rcx, rax; hHeap
0x180003677  mov     r8, rsi; lpMem
0x18000367a  xor     edx, edx; dwFlags
0x18000367c  call    cs:__imp_HeapFree
0x180003682  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003686  call    cs:__imp_DeleteCriticalSection
0x18000368c  mov     rbx, [rdi+38h]
0x180003690  test    rbx, rbx
0x180003693  jz      short loc_1800036BD
0x180003695  xor     r9d, r9d; msWindowLength
0x180003698  xor     r8d, r8d; msPeriod
0x18000369b  xor     edx, edx; pftDueTime
0x18000369d  mov     rcx, rbx; pti
0x1800036a0  call    cs:__imp_SetThreadpoolTimer
0x1800036a6  mov     edx, 1; fCancelPendingCallbacks
0x1800036ab  mov     rcx, rbx; pti
0x1800036ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036b4  mov     rcx, rbx; pti
0x1800036b7  call    cs:__imp_CloseThreadpoolTimer
0x1800036bd  mov     rbx, [rdi+30h]
0x1800036c1  test    rbx, rbx
0x1800036c4  jz      short loc_1800036EF
0x1800036c6  xor     r9d, r9d; msWindowLength
0x1800036c9  xor     r8d, r8d; msPeriod
0x1800036cc  xor     edx, edx; pftDueTime
0x1800036ce  mov     rcx, rbx; pti
0x1800036d1  call    cs:__imp_SetThreadpoolTimer
0x1800036d7  mov     edx, 1; fCancelPendingCallbacks
0x1800036dc  mov     rcx, rbx; pti
0x1800036df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036e5  mov     rcx, rbx; pti
0x1800036e8  call    cs:__imp_CloseThreadpoolTimer
0x1800036ee  nop
0x1800036ef  mov     rcx, [rdi+10h]; lpMem
0x1800036f3  test    rcx, rcx
0x1800036f6  jz      short loc_1800036FE
0x1800036f8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800036fd  nop
0x1800036fe  mov     rbx, [rsp+28h+arg_0]
0x180003703  mov     rsi, [rsp+28h+arg_8]
0x180003708  add     rsp, 20h
0x18000370c  pop     rdi
0x18000370d  retn
```
