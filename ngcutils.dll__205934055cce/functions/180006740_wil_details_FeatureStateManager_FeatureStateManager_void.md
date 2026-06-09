# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180006740`
- end: `0x18000692e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180060650`

## callees

- `0x18000649c`
- `0x180006740`
- `0x18000a258`
- `0x18000b7ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006865`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006865`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000680c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000685c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000689c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000680c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000685c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000689c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000688e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000688e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006790`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006790`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000675e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000675e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006771`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800067ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006771`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800067ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006788`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006908`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006788`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006908`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000677f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800067c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000677f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800067c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068ff`

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
  if ( v8 && qword_1800750A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800750A8[25], qword_1800750A8, v8);
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
0x180006740  mov     [rsp+arg_0], rbx
0x180006745  mov     [rsp+arg_8], rsi
0x18000674a  push    rdi
0x18000674b  sub     rsp, 20h
0x18000674f  mov     rdi, rcx
0x180006752  mov     byte ptr [rcx], 0
0x180006755  mov     rsi, [rcx+30h]
0x180006759  test    rsi, rsi
0x18000675c  jz      short loc_180006796
0x18000675e  call    cs:__imp_GetLastError
0x180006764  mov     ebx, eax
0x180006766  xor     r9d, r9d; msWindowLength
0x180006769  xor     r8d, r8d; msPeriod
0x18000676c  xor     edx, edx; pftDueTime
0x18000676e  mov     rcx, rsi; pti
0x180006771  call    cs:__imp_SetThreadpoolTimer
0x180006777  mov     edx, 1; fCancelPendingCallbacks
0x18000677c  mov     rcx, rsi; pti
0x18000677f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006785  mov     rcx, rsi; pti
0x180006788  call    cs:__imp_CloseThreadpoolTimer
0x18000678e  mov     ecx, ebx; dwErrCode
0x180006790  call    cs:__imp_SetLastError
0x180006796  mov     qword ptr [rdi+30h], 0
0x18000679e  mov     rsi, [rdi+38h]
0x1800067a2  test    rsi, rsi
0x1800067a5  jz      short loc_1800067DF
0x1800067a7  call    cs:__imp_GetLastError
0x1800067ad  mov     ebx, eax
0x1800067af  xor     r9d, r9d; msWindowLength
0x1800067b2  xor     r8d, r8d; msPeriod
0x1800067b5  xor     edx, edx; pftDueTime
0x1800067b7  mov     rcx, rsi; pti
0x1800067ba  call    cs:__imp_SetThreadpoolTimer
0x1800067c0  mov     edx, 1; fCancelPendingCallbacks
0x1800067c5  mov     rcx, rsi; pti
0x1800067c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800067ce  mov     rcx, rsi; pti
0x1800067d1  call    cs:__imp_CloseThreadpoolTimer
0x1800067d7  mov     ecx, ebx; dwErrCode
0x1800067d9  call    cs:__imp_SetLastError
0x1800067df  mov     qword ptr [rdi+38h], 0
0x1800067e7  mov     rbx, [rdi+100h]
0x1800067ee  mov     qword ptr [rdi+100h], 0
0x1800067f9  test    rbx, rbx
0x1800067fc  jz      short loc_180006812
0x1800067fe  call    cs:__imp_GetProcessHeap
0x180006804  mov     rcx, rax; hHeap
0x180006807  mov     r8, rbx; lpMem
0x18000680a  xor     edx, edx; dwFlags
0x18000680c  call    cs:__imp_HeapFree
0x180006812  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180006819  test    r8, r8
0x18000681c  jz      short loc_180006836
0x18000681e  mov     rdx, cs:qword_1800750A8; SRWLock
0x180006825  test    rdx, rdx
0x180006828  jz      short loc_180006836
0x18000682a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180006831  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180006836  lea     rbx, [rdi+98h]
0x18000683d  mov     rsi, [rbx+40h]
0x180006841  mov     qword ptr [rbx+40h], 0
0x180006849  test    rsi, rsi
0x18000684c  jz      short loc_180006862
0x18000684e  call    cs:__imp_GetProcessHeap
0x180006854  mov     rcx, rax; hHeap
0x180006857  mov     r8, rsi; lpMem
0x18000685a  xor     edx, edx; dwFlags
0x18000685c  call    cs:__imp_HeapFree
0x180006862  mov     rcx, rbx; lpCriticalSection
0x180006865  call    cs:__imp_DeleteCriticalSection
0x18000686b  lea     rcx, [rdi+90h]
0x180006872  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006877  mov     rsi, [rdi+88h]
0x18000687e  mov     qword ptr [rdi+88h], 0
0x180006889  test    rsi, rsi
0x18000688c  jz      short loc_1800068A2
0x18000688e  call    cs:__imp_GetProcessHeap
0x180006894  mov     rcx, rax; hHeap
0x180006897  mov     r8, rsi; lpMem
0x18000689a  xor     edx, edx; dwFlags
0x18000689c  call    cs:__imp_HeapFree
0x1800068a2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800068a6  call    cs:__imp_DeleteCriticalSection
0x1800068ac  mov     rbx, [rdi+38h]
0x1800068b0  test    rbx, rbx
0x1800068b3  jz      short loc_1800068DD
0x1800068b5  xor     r9d, r9d; msWindowLength
0x1800068b8  xor     r8d, r8d; msPeriod
0x1800068bb  xor     edx, edx; pftDueTime
0x1800068bd  mov     rcx, rbx; pti
0x1800068c0  call    cs:__imp_SetThreadpoolTimer
0x1800068c6  mov     edx, 1; fCancelPendingCallbacks
0x1800068cb  mov     rcx, rbx; pti
0x1800068ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068d4  mov     rcx, rbx; pti
0x1800068d7  call    cs:__imp_CloseThreadpoolTimer
0x1800068dd  mov     rbx, [rdi+30h]
0x1800068e1  test    rbx, rbx
0x1800068e4  jz      short loc_18000690F
0x1800068e6  xor     r9d, r9d; msWindowLength
0x1800068e9  xor     r8d, r8d; msPeriod
0x1800068ec  xor     edx, edx; pftDueTime
0x1800068ee  mov     rcx, rbx; pti
0x1800068f1  call    cs:__imp_SetThreadpoolTimer
0x1800068f7  mov     edx, 1; fCancelPendingCallbacks
0x1800068fc  mov     rcx, rbx; pti
0x1800068ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006905  mov     rcx, rbx; pti
0x180006908  call    cs:__imp_CloseThreadpoolTimer
0x18000690e  nop
0x18000690f  mov     rcx, [rdi+10h]; lpMem
0x180006913  test    rcx, rcx
0x180006916  jz      short loc_18000691E
0x180006918  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000691d  nop
0x18000691e  mov     rbx, [rsp+28h+arg_0]
0x180006923  mov     rsi, [rsp+28h+arg_8]
0x180006928  add     rsp, 20h
0x18000692c  pop     rdi
0x18000692d  retn
```
