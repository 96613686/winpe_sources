# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800090b8`
- end: `0x1800092a6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002fca0`

## callees

- `0x180008b80`
- `0x1800090b8`
- `0x18000bfd8`
- `0x18000f6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800091dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000921e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800091dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000921e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009214`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009206`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009151`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009151`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800090f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009140`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009246`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009277`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800090f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009140`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009246`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009277`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009100`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009149`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000924f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009280`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009100`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009149`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000924f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009280`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009132`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009238`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009269`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009132`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009238`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009269`

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
  if ( v8 && qword_18003F060 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003F060[25], qword_18003F060, v8);
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
0x1800090b8  mov     [rsp+arg_0], rbx
0x1800090bd  mov     [rsp+arg_8], rsi
0x1800090c2  push    rdi
0x1800090c3  sub     rsp, 20h
0x1800090c7  mov     rdi, rcx
0x1800090ca  mov     byte ptr [rcx], 0
0x1800090cd  mov     rsi, [rcx+30h]
0x1800090d1  test    rsi, rsi
0x1800090d4  jz      short loc_18000910E
0x1800090d6  call    cs:__imp_GetLastError
0x1800090dc  mov     ebx, eax
0x1800090de  xor     r9d, r9d; msWindowLength
0x1800090e1  xor     r8d, r8d; msPeriod
0x1800090e4  xor     edx, edx; pftDueTime
0x1800090e6  mov     rcx, rsi; pti
0x1800090e9  call    cs:__imp_SetThreadpoolTimer
0x1800090ef  mov     edx, 1; fCancelPendingCallbacks
0x1800090f4  mov     rcx, rsi; pti
0x1800090f7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800090fd  mov     rcx, rsi; pti
0x180009100  call    cs:__imp_CloseThreadpoolTimer
0x180009106  mov     ecx, ebx; dwErrCode
0x180009108  call    cs:__imp_SetLastError
0x18000910e  mov     qword ptr [rdi+30h], 0
0x180009116  mov     rsi, [rdi+38h]
0x18000911a  test    rsi, rsi
0x18000911d  jz      short loc_180009157
0x18000911f  call    cs:__imp_GetLastError
0x180009125  mov     ebx, eax
0x180009127  xor     r9d, r9d; msWindowLength
0x18000912a  xor     r8d, r8d; msPeriod
0x18000912d  xor     edx, edx; pftDueTime
0x18000912f  mov     rcx, rsi; pti
0x180009132  call    cs:__imp_SetThreadpoolTimer
0x180009138  mov     edx, 1; fCancelPendingCallbacks
0x18000913d  mov     rcx, rsi; pti
0x180009140  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009146  mov     rcx, rsi; pti
0x180009149  call    cs:__imp_CloseThreadpoolTimer
0x18000914f  mov     ecx, ebx; dwErrCode
0x180009151  call    cs:__imp_SetLastError
0x180009157  mov     qword ptr [rdi+38h], 0
0x18000915f  mov     rbx, [rdi+100h]
0x180009166  mov     qword ptr [rdi+100h], 0
0x180009171  test    rbx, rbx
0x180009174  jz      short loc_18000918A
0x180009176  call    cs:__imp_GetProcessHeap
0x18000917c  mov     rcx, rax; hHeap
0x18000917f  mov     r8, rbx; lpMem
0x180009182  xor     edx, edx; dwFlags
0x180009184  call    cs:__imp_HeapFree
0x18000918a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009191  test    r8, r8
0x180009194  jz      short loc_1800091AE
0x180009196  mov     rdx, cs:qword_18003F060; SRWLock
0x18000919d  test    rdx, rdx
0x1800091a0  jz      short loc_1800091AE
0x1800091a2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800091a9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800091ae  lea     rbx, [rdi+98h]
0x1800091b5  mov     rsi, [rbx+40h]
0x1800091b9  mov     qword ptr [rbx+40h], 0
0x1800091c1  test    rsi, rsi
0x1800091c4  jz      short loc_1800091DA
0x1800091c6  call    cs:__imp_GetProcessHeap
0x1800091cc  mov     rcx, rax; hHeap
0x1800091cf  mov     r8, rsi; lpMem
0x1800091d2  xor     edx, edx; dwFlags
0x1800091d4  call    cs:__imp_HeapFree
0x1800091da  mov     rcx, rbx; lpCriticalSection
0x1800091dd  call    cs:__imp_DeleteCriticalSection
0x1800091e3  lea     rcx, [rdi+90h]
0x1800091ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800091ef  mov     rsi, [rdi+88h]
0x1800091f6  mov     qword ptr [rdi+88h], 0
0x180009201  test    rsi, rsi
0x180009204  jz      short loc_18000921A
0x180009206  call    cs:__imp_GetProcessHeap
0x18000920c  mov     rcx, rax; hHeap
0x18000920f  mov     r8, rsi; lpMem
0x180009212  xor     edx, edx; dwFlags
0x180009214  call    cs:__imp_HeapFree
0x18000921a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000921e  call    cs:__imp_DeleteCriticalSection
0x180009224  mov     rbx, [rdi+38h]
0x180009228  test    rbx, rbx
0x18000922b  jz      short loc_180009255
0x18000922d  xor     r9d, r9d; msWindowLength
0x180009230  xor     r8d, r8d; msPeriod
0x180009233  xor     edx, edx; pftDueTime
0x180009235  mov     rcx, rbx; pti
0x180009238  call    cs:__imp_SetThreadpoolTimer
0x18000923e  mov     edx, 1; fCancelPendingCallbacks
0x180009243  mov     rcx, rbx; pti
0x180009246  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000924c  mov     rcx, rbx; pti
0x18000924f  call    cs:__imp_CloseThreadpoolTimer
0x180009255  mov     rbx, [rdi+30h]
0x180009259  test    rbx, rbx
0x18000925c  jz      short loc_180009287
0x18000925e  xor     r9d, r9d; msWindowLength
0x180009261  xor     r8d, r8d; msPeriod
0x180009264  xor     edx, edx; pftDueTime
0x180009266  mov     rcx, rbx; pti
0x180009269  call    cs:__imp_SetThreadpoolTimer
0x18000926f  mov     edx, 1; fCancelPendingCallbacks
0x180009274  mov     rcx, rbx; pti
0x180009277  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000927d  mov     rcx, rbx; pti
0x180009280  call    cs:__imp_CloseThreadpoolTimer
0x180009286  nop
0x180009287  mov     rcx, [rdi+10h]; lpMem
0x18000928b  test    rcx, rcx
0x18000928e  jz      short loc_180009296
0x180009290  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009295  nop
0x180009296  mov     rbx, [rsp+28h+arg_0]
0x18000929b  mov     rsi, [rsp+28h+arg_8]
0x1800092a0  add     rsp, 20h
0x1800092a4  pop     rdi
0x1800092a5  retn
```
