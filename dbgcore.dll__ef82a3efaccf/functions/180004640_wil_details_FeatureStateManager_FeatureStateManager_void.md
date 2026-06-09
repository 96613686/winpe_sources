# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004640`
- end: `0x180004838`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b880`

## callees

- `0x1800043a0`
- `0x180004640`
- `0x180009da8`
- `0x18000b4f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000476f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800047b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000476f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800047b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004758`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004758`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004766`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004766`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000469a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000469a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046e3`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180004689`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x1800046d2`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x1800047d8`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180004809`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180004689`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x1800046d2`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x1800047d8`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180004809`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180004692`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800046db`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800047e1`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180004812`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180004692`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800046db`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800047e1`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180004812`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x18000467b`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800046c4`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800047ca`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800047fb`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x18000467b`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800046c4`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800047ca`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800047fb`

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
  if ( v8 && qword_18003C078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003C078[25], qword_18003C078, v8);
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
0x180004640  push    rdi
0x180004642  sub     rsp, 30h
0x180004646  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000464f  mov     [rsp+38h+arg_0], rbx
0x180004654  mov     [rsp+38h+arg_8], rsi
0x180004659  mov     rdi, rcx
0x18000465c  mov     byte ptr [rcx], 0
0x18000465f  mov     rsi, [rcx+30h]
0x180004663  test    rsi, rsi
0x180004666  jz      short loc_1800046A0
0x180004668  call    cs:__imp_GetLastError
0x18000466e  mov     ebx, eax
0x180004670  xor     r9d, r9d; msWindowLength
0x180004673  xor     r8d, r8d; msPeriod
0x180004676  xor     edx, edx; pftDueTime
0x180004678  mov     rcx, rsi; pti
0x18000467b  call    cs:__imp_SetThreadpoolTimer
0x180004681  mov     edx, 1; fCancelPendingCallbacks
0x180004686  mov     rcx, rsi; pti
0x180004689  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000468f  mov     rcx, rsi; pti
0x180004692  call    cs:__imp_CloseThreadpoolTimer
0x180004698  mov     ecx, ebx; dwErrCode
0x18000469a  call    cs:__imp_SetLastError
0x1800046a0  mov     qword ptr [rdi+30h], 0
0x1800046a8  mov     rsi, [rdi+38h]
0x1800046ac  test    rsi, rsi
0x1800046af  jz      short loc_1800046E9
0x1800046b1  call    cs:__imp_GetLastError
0x1800046b7  mov     ebx, eax
0x1800046b9  xor     r9d, r9d; msWindowLength
0x1800046bc  xor     r8d, r8d; msPeriod
0x1800046bf  xor     edx, edx; pftDueTime
0x1800046c1  mov     rcx, rsi; pti
0x1800046c4  call    cs:__imp_SetThreadpoolTimer
0x1800046ca  mov     edx, 1; fCancelPendingCallbacks
0x1800046cf  mov     rcx, rsi; pti
0x1800046d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800046d8  mov     rcx, rsi; pti
0x1800046db  call    cs:__imp_CloseThreadpoolTimer
0x1800046e1  mov     ecx, ebx; dwErrCode
0x1800046e3  call    cs:__imp_SetLastError
0x1800046e9  mov     qword ptr [rdi+38h], 0
0x1800046f1  mov     rbx, [rdi+100h]
0x1800046f8  mov     qword ptr [rdi+100h], 0
0x180004703  test    rbx, rbx
0x180004706  jz      short loc_18000471C
0x180004708  call    cs:__imp_GetProcessHeap
0x18000470e  mov     rcx, rax; hHeap
0x180004711  mov     r8, rbx; lpMem
0x180004714  xor     edx, edx; dwFlags
0x180004716  call    cs:__imp_HeapFree
0x18000471c  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180004723  test    r8, r8
0x180004726  jz      short loc_180004740
0x180004728  mov     rdx, cs:qword_18003C078; SRWLock
0x18000472f  test    rdx, rdx
0x180004732  jz      short loc_180004740
0x180004734  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000473b  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004740  lea     rbx, [rdi+98h]
0x180004747  mov     rsi, [rbx+40h]
0x18000474b  mov     qword ptr [rbx+40h], 0
0x180004753  test    rsi, rsi
0x180004756  jz      short loc_18000476C
0x180004758  call    cs:__imp_GetProcessHeap
0x18000475e  mov     rcx, rax; hHeap
0x180004761  mov     r8, rsi; lpMem
0x180004764  xor     edx, edx; dwFlags
0x180004766  call    cs:__imp_HeapFree
0x18000476c  mov     rcx, rbx; lpCriticalSection
0x18000476f  call    cs:__imp_DeleteCriticalSection
0x180004775  lea     rcx, [rdi+90h]
0x18000477c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004781  mov     rsi, [rdi+88h]
0x180004788  mov     qword ptr [rdi+88h], 0
0x180004793  test    rsi, rsi
0x180004796  jz      short loc_1800047AC
0x180004798  call    cs:__imp_GetProcessHeap
0x18000479e  mov     rcx, rax; hHeap
0x1800047a1  mov     r8, rsi; lpMem
0x1800047a4  xor     edx, edx; dwFlags
0x1800047a6  call    cs:__imp_HeapFree
0x1800047ac  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800047b0  call    cs:__imp_DeleteCriticalSection
0x1800047b6  mov     rbx, [rdi+38h]
0x1800047ba  test    rbx, rbx
0x1800047bd  jz      short loc_1800047E7
0x1800047bf  xor     r9d, r9d; msWindowLength
0x1800047c2  xor     r8d, r8d; msPeriod
0x1800047c5  xor     edx, edx; pftDueTime
0x1800047c7  mov     rcx, rbx; pti
0x1800047ca  call    cs:__imp_SetThreadpoolTimer
0x1800047d0  mov     edx, 1; fCancelPendingCallbacks
0x1800047d5  mov     rcx, rbx; pti
0x1800047d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800047de  mov     rcx, rbx; pti
0x1800047e1  call    cs:__imp_CloseThreadpoolTimer
0x1800047e7  mov     rbx, [rdi+30h]
0x1800047eb  test    rbx, rbx
0x1800047ee  jz      short loc_180004819
0x1800047f0  xor     r9d, r9d; msWindowLength
0x1800047f3  xor     r8d, r8d; msPeriod
0x1800047f6  xor     edx, edx; pftDueTime
0x1800047f8  mov     rcx, rbx; pti
0x1800047fb  call    cs:__imp_SetThreadpoolTimer
0x180004801  mov     edx, 1; fCancelPendingCallbacks
0x180004806  mov     rcx, rbx; pti
0x180004809  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000480f  mov     rcx, rbx; pti
0x180004812  call    cs:__imp_CloseThreadpoolTimer
0x180004818  nop
0x180004819  mov     rcx, [rdi+10h]; lpMem
0x18000481d  test    rcx, rcx
0x180004820  jz      short loc_180004828
0x180004822  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004827  nop
0x180004828  mov     rbx, [rsp+38h+arg_0]
0x18000482d  mov     rsi, [rsp+38h+arg_8]
0x180004832  add     rsp, 30h
0x180004836  pop     rdi
0x180004837  retn
```
