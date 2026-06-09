# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800056f4`
- end: `0x1800058e2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005b4c0`

## callees

- `0x18000540c`
- `0x1800056f4`
- `0x180009140`
- `0x18000a71c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000585a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000585a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005850`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005802`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005802`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005842`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000578d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000578d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000575b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000575b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000576e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005874`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800058a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000576e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005874`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800058a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000573c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005785`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000588b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800058bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000573c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005785`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000588b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800058bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000577c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005882`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800058b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000577c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005882`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800058b3`

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
  if ( v8 && qword_180084290 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180084290[25], qword_180084290, v8);
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
0x1800056f4  mov     [rsp+arg_0], rbx
0x1800056f9  mov     [rsp+arg_8], rsi
0x1800056fe  push    rdi
0x1800056ff  sub     rsp, 20h
0x180005703  mov     rdi, rcx
0x180005706  mov     byte ptr [rcx], 0
0x180005709  mov     rsi, [rcx+30h]
0x18000570d  test    rsi, rsi
0x180005710  jz      short loc_18000574A
0x180005712  call    cs:__imp_GetLastError
0x180005718  mov     ebx, eax
0x18000571a  xor     r9d, r9d; msWindowLength
0x18000571d  xor     r8d, r8d; msPeriod
0x180005720  xor     edx, edx; pftDueTime
0x180005722  mov     rcx, rsi; pti
0x180005725  call    cs:__imp_SetThreadpoolTimer
0x18000572b  mov     edx, 1; fCancelPendingCallbacks
0x180005730  mov     rcx, rsi; pti
0x180005733  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005739  mov     rcx, rsi; pti
0x18000573c  call    cs:__imp_CloseThreadpoolTimer
0x180005742  mov     ecx, ebx; dwErrCode
0x180005744  call    cs:__imp_SetLastError
0x18000574a  mov     qword ptr [rdi+30h], 0
0x180005752  mov     rsi, [rdi+38h]
0x180005756  test    rsi, rsi
0x180005759  jz      short loc_180005793
0x18000575b  call    cs:__imp_GetLastError
0x180005761  mov     ebx, eax
0x180005763  xor     r9d, r9d; msWindowLength
0x180005766  xor     r8d, r8d; msPeriod
0x180005769  xor     edx, edx; pftDueTime
0x18000576b  mov     rcx, rsi; pti
0x18000576e  call    cs:__imp_SetThreadpoolTimer
0x180005774  mov     edx, 1; fCancelPendingCallbacks
0x180005779  mov     rcx, rsi; pti
0x18000577c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005782  mov     rcx, rsi; pti
0x180005785  call    cs:__imp_CloseThreadpoolTimer
0x18000578b  mov     ecx, ebx; dwErrCode
0x18000578d  call    cs:__imp_SetLastError
0x180005793  mov     qword ptr [rdi+38h], 0
0x18000579b  mov     rbx, [rdi+100h]
0x1800057a2  mov     qword ptr [rdi+100h], 0
0x1800057ad  test    rbx, rbx
0x1800057b0  jz      short loc_1800057C6
0x1800057b2  call    cs:__imp_GetProcessHeap
0x1800057b8  mov     rcx, rax; hHeap
0x1800057bb  mov     r8, rbx; lpMem
0x1800057be  xor     edx, edx; dwFlags
0x1800057c0  call    cs:__imp_HeapFree
0x1800057c6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800057cd  test    r8, r8
0x1800057d0  jz      short loc_1800057EA
0x1800057d2  mov     rdx, cs:qword_180084290; SRWLock
0x1800057d9  test    rdx, rdx
0x1800057dc  jz      short loc_1800057EA
0x1800057de  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800057e5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800057ea  lea     rbx, [rdi+98h]
0x1800057f1  mov     rsi, [rbx+40h]
0x1800057f5  mov     qword ptr [rbx+40h], 0
0x1800057fd  test    rsi, rsi
0x180005800  jz      short loc_180005816
0x180005802  call    cs:__imp_GetProcessHeap
0x180005808  mov     rcx, rax; hHeap
0x18000580b  mov     r8, rsi; lpMem
0x18000580e  xor     edx, edx; dwFlags
0x180005810  call    cs:__imp_HeapFree
0x180005816  mov     rcx, rbx; lpCriticalSection
0x180005819  call    cs:__imp_DeleteCriticalSection
0x18000581f  lea     rcx, [rdi+90h]
0x180005826  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000582b  mov     rsi, [rdi+88h]
0x180005832  mov     qword ptr [rdi+88h], 0
0x18000583d  test    rsi, rsi
0x180005840  jz      short loc_180005856
0x180005842  call    cs:__imp_GetProcessHeap
0x180005848  mov     rcx, rax; hHeap
0x18000584b  mov     r8, rsi; lpMem
0x18000584e  xor     edx, edx; dwFlags
0x180005850  call    cs:__imp_HeapFree
0x180005856  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000585a  call    cs:__imp_DeleteCriticalSection
0x180005860  mov     rbx, [rdi+38h]
0x180005864  test    rbx, rbx
0x180005867  jz      short loc_180005891
0x180005869  xor     r9d, r9d; msWindowLength
0x18000586c  xor     r8d, r8d; msPeriod
0x18000586f  xor     edx, edx; pftDueTime
0x180005871  mov     rcx, rbx; pti
0x180005874  call    cs:__imp_SetThreadpoolTimer
0x18000587a  mov     edx, 1; fCancelPendingCallbacks
0x18000587f  mov     rcx, rbx; pti
0x180005882  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005888  mov     rcx, rbx; pti
0x18000588b  call    cs:__imp_CloseThreadpoolTimer
0x180005891  mov     rbx, [rdi+30h]
0x180005895  test    rbx, rbx
0x180005898  jz      short loc_1800058C3
0x18000589a  xor     r9d, r9d; msWindowLength
0x18000589d  xor     r8d, r8d; msPeriod
0x1800058a0  xor     edx, edx; pftDueTime
0x1800058a2  mov     rcx, rbx; pti
0x1800058a5  call    cs:__imp_SetThreadpoolTimer
0x1800058ab  mov     edx, 1; fCancelPendingCallbacks
0x1800058b0  mov     rcx, rbx; pti
0x1800058b3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800058b9  mov     rcx, rbx; pti
0x1800058bc  call    cs:__imp_CloseThreadpoolTimer
0x1800058c2  nop
0x1800058c3  mov     rcx, [rdi+10h]; lpMem
0x1800058c7  test    rcx, rcx
0x1800058ca  jz      short loc_1800058D2
0x1800058cc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800058d1  nop
0x1800058d2  mov     rbx, [rsp+28h+arg_0]
0x1800058d7  mov     rsi, [rsp+28h+arg_8]
0x1800058dc  add     rsp, 20h
0x1800058e0  pop     rdi
0x1800058e1  retn
```
