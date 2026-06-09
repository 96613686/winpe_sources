# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400050a8`
- end: `0x140005296`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140013a00`

## callees

- `0x140004f40`
- `0x1400050a8`
- `0x140009550`
- `0x14000a94c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000520e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000520e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005174`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400051c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005174`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400051c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000510f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000510f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005141`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005141`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400050f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005139`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000523f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005270`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400050f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005139`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000523f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005270`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400050d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005122`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005228`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005259`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400050d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005122`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005228`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005259`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400050e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005130`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005236`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005267`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400050e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005130`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005236`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005267`

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
  if ( v8 && qword_14001D050 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14001D050[25], qword_14001D050, v8);
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
0x1400050a8  mov     [rsp+arg_0], rbx
0x1400050ad  mov     [rsp+arg_8], rsi
0x1400050b2  push    rdi
0x1400050b3  sub     rsp, 20h
0x1400050b7  mov     rdi, rcx
0x1400050ba  mov     byte ptr [rcx], 0
0x1400050bd  mov     rsi, [rcx+30h]
0x1400050c1  test    rsi, rsi
0x1400050c4  jz      short loc_1400050FE
0x1400050c6  call    cs:__imp_GetLastError
0x1400050cc  mov     ebx, eax
0x1400050ce  xor     r9d, r9d; msWindowLength
0x1400050d1  xor     r8d, r8d; msPeriod
0x1400050d4  xor     edx, edx; pftDueTime
0x1400050d6  mov     rcx, rsi; pti
0x1400050d9  call    cs:__imp_SetThreadpoolTimer
0x1400050df  mov     edx, 1; fCancelPendingCallbacks
0x1400050e4  mov     rcx, rsi; pti
0x1400050e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400050ed  mov     rcx, rsi; pti
0x1400050f0  call    cs:__imp_CloseThreadpoolTimer
0x1400050f6  mov     ecx, ebx; dwErrCode
0x1400050f8  call    cs:__imp_SetLastError
0x1400050fe  mov     qword ptr [rdi+30h], 0
0x140005106  mov     rsi, [rdi+38h]
0x14000510a  test    rsi, rsi
0x14000510d  jz      short loc_140005147
0x14000510f  call    cs:__imp_GetLastError
0x140005115  mov     ebx, eax
0x140005117  xor     r9d, r9d; msWindowLength
0x14000511a  xor     r8d, r8d; msPeriod
0x14000511d  xor     edx, edx; pftDueTime
0x14000511f  mov     rcx, rsi; pti
0x140005122  call    cs:__imp_SetThreadpoolTimer
0x140005128  mov     edx, 1; fCancelPendingCallbacks
0x14000512d  mov     rcx, rsi; pti
0x140005130  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005136  mov     rcx, rsi; pti
0x140005139  call    cs:__imp_CloseThreadpoolTimer
0x14000513f  mov     ecx, ebx; dwErrCode
0x140005141  call    cs:__imp_SetLastError
0x140005147  mov     qword ptr [rdi+38h], 0
0x14000514f  mov     rbx, [rdi+100h]
0x140005156  mov     qword ptr [rdi+100h], 0
0x140005161  test    rbx, rbx
0x140005164  jz      short loc_14000517A
0x140005166  call    cs:__imp_GetProcessHeap
0x14000516c  mov     rcx, rax; hHeap
0x14000516f  mov     r8, rbx; lpMem
0x140005172  xor     edx, edx; dwFlags
0x140005174  call    cs:__imp_HeapFree
0x14000517a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005181  test    r8, r8
0x140005184  jz      short loc_14000519E
0x140005186  mov     rdx, cs:qword_14001D050; SRWLock
0x14000518d  test    rdx, rdx
0x140005190  jz      short loc_14000519E
0x140005192  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140005199  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000519e  lea     rbx, [rdi+98h]
0x1400051a5  mov     rsi, [rbx+40h]
0x1400051a9  mov     qword ptr [rbx+40h], 0
0x1400051b1  test    rsi, rsi
0x1400051b4  jz      short loc_1400051CA
0x1400051b6  call    cs:__imp_GetProcessHeap
0x1400051bc  mov     rcx, rax; hHeap
0x1400051bf  mov     r8, rsi; lpMem
0x1400051c2  xor     edx, edx; dwFlags
0x1400051c4  call    cs:__imp_HeapFree
0x1400051ca  mov     rcx, rbx; lpCriticalSection
0x1400051cd  call    cs:__imp_DeleteCriticalSection
0x1400051d3  lea     rcx, [rdi+90h]
0x1400051da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400051df  mov     rsi, [rdi+88h]
0x1400051e6  mov     qword ptr [rdi+88h], 0
0x1400051f1  test    rsi, rsi
0x1400051f4  jz      short loc_14000520A
0x1400051f6  call    cs:__imp_GetProcessHeap
0x1400051fc  mov     rcx, rax; hHeap
0x1400051ff  mov     r8, rsi; lpMem
0x140005202  xor     edx, edx; dwFlags
0x140005204  call    cs:__imp_HeapFree
0x14000520a  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000520e  call    cs:__imp_DeleteCriticalSection
0x140005214  mov     rbx, [rdi+38h]
0x140005218  test    rbx, rbx
0x14000521b  jz      short loc_140005245
0x14000521d  xor     r9d, r9d; msWindowLength
0x140005220  xor     r8d, r8d; msPeriod
0x140005223  xor     edx, edx; pftDueTime
0x140005225  mov     rcx, rbx; pti
0x140005228  call    cs:__imp_SetThreadpoolTimer
0x14000522e  mov     edx, 1; fCancelPendingCallbacks
0x140005233  mov     rcx, rbx; pti
0x140005236  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000523c  mov     rcx, rbx; pti
0x14000523f  call    cs:__imp_CloseThreadpoolTimer
0x140005245  mov     rbx, [rdi+30h]
0x140005249  test    rbx, rbx
0x14000524c  jz      short loc_140005277
0x14000524e  xor     r9d, r9d; msWindowLength
0x140005251  xor     r8d, r8d; msPeriod
0x140005254  xor     edx, edx; pftDueTime
0x140005256  mov     rcx, rbx; pti
0x140005259  call    cs:__imp_SetThreadpoolTimer
0x14000525f  mov     edx, 1; fCancelPendingCallbacks
0x140005264  mov     rcx, rbx; pti
0x140005267  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000526d  mov     rcx, rbx; pti
0x140005270  call    cs:__imp_CloseThreadpoolTimer
0x140005276  nop
0x140005277  mov     rcx, [rdi+10h]; lpMem
0x14000527b  test    rcx, rcx
0x14000527e  jz      short loc_140005286
0x140005280  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005285  nop
0x140005286  mov     rbx, [rsp+28h+arg_0]
0x14000528b  mov     rsi, [rsp+28h+arg_8]
0x140005290  add     rsp, 20h
0x140005294  pop     rdi
0x140005295  retn
```
