# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400682a4`
- end: `0x140068492`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140084c40`

## callees

- `0x140068160`
- `0x1400682a4`
- `0x14006bd24`
- `0x14006cde8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1400682d5`
- `KERNEL32!SetThreadpoolTimer` at `0x14006831e`
- `KERNEL32!SetThreadpoolTimer` at `0x140068424`
- `KERNEL32!SetThreadpoolTimer` at `0x140068455`
- `KERNEL32!SetThreadpoolTimer` at `0x1400682d5`
- `KERNEL32!SetThreadpoolTimer` at `0x14006831e`
- `KERNEL32!SetThreadpoolTimer` at `0x140068424`
- `KERNEL32!SetThreadpoolTimer` at `0x140068455`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400682ec`
- `KERNEL32!CloseThreadpoolTimer` at `0x140068335`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006843b`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006846c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400682ec`
- `KERNEL32!CloseThreadpoolTimer` at `0x140068335`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006843b`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006846c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400682e3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006832c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140068432`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140068463`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400682e3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006832c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140068432`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140068463`
- `KERNEL32!GetLastError` at `0x1400682c2`
- `KERNEL32!GetLastError` at `0x14006830b`
- `KERNEL32!GetLastError` at `0x1400682c2`
- `KERNEL32!GetLastError` at `0x14006830b`
- `KERNEL32!GetProcessHeap` at `0x140068362`
- `KERNEL32!GetProcessHeap` at `0x1400683b2`
- `KERNEL32!GetProcessHeap` at `0x1400683f2`
- `KERNEL32!GetProcessHeap` at `0x140068362`
- `KERNEL32!GetProcessHeap` at `0x1400683b2`
- `KERNEL32!GetProcessHeap` at `0x1400683f2`
- `KERNEL32!SetLastError` at `0x1400682f4`
- `KERNEL32!SetLastError` at `0x14006833d`
- `KERNEL32!SetLastError` at `0x1400682f4`
- `KERNEL32!SetLastError` at `0x14006833d`
- `KERNEL32!HeapFree` at `0x140068370`
- `KERNEL32!HeapFree` at `0x1400683c0`
- `KERNEL32!HeapFree` at `0x140068400`
- `KERNEL32!HeapFree` at `0x140068370`
- `KERNEL32!HeapFree` at `0x1400683c0`
- `KERNEL32!HeapFree` at `0x140068400`
- `KERNEL32!DeleteCriticalSection` at `0x1400683c9`
- `KERNEL32!DeleteCriticalSection` at `0x14006840a`
- `KERNEL32!DeleteCriticalSection` at `0x1400683c9`
- `KERNEL32!DeleteCriticalSection` at `0x14006840a`

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
  if ( v8 && qword_14009D8A0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14009D8A0[25], qword_14009D8A0, v8);
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
0x1400682a4  mov     [rsp+arg_0], rbx
0x1400682a9  mov     [rsp+arg_8], rsi
0x1400682ae  push    rdi
0x1400682af  sub     rsp, 20h
0x1400682b3  mov     rdi, rcx
0x1400682b6  mov     byte ptr [rcx], 0
0x1400682b9  mov     rsi, [rcx+30h]
0x1400682bd  test    rsi, rsi
0x1400682c0  jz      short loc_1400682FA
0x1400682c2  call    cs:__imp_GetLastError
0x1400682c8  mov     ebx, eax
0x1400682ca  xor     r9d, r9d; msWindowLength
0x1400682cd  xor     r8d, r8d; msPeriod
0x1400682d0  xor     edx, edx; pftDueTime
0x1400682d2  mov     rcx, rsi; pti
0x1400682d5  call    cs:__imp_SetThreadpoolTimer
0x1400682db  mov     edx, 1; fCancelPendingCallbacks
0x1400682e0  mov     rcx, rsi; pti
0x1400682e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400682e9  mov     rcx, rsi; pti
0x1400682ec  call    cs:__imp_CloseThreadpoolTimer
0x1400682f2  mov     ecx, ebx; dwErrCode
0x1400682f4  call    cs:__imp_SetLastError
0x1400682fa  mov     qword ptr [rdi+30h], 0
0x140068302  mov     rsi, [rdi+38h]
0x140068306  test    rsi, rsi
0x140068309  jz      short loc_140068343
0x14006830b  call    cs:__imp_GetLastError
0x140068311  mov     ebx, eax
0x140068313  xor     r9d, r9d; msWindowLength
0x140068316  xor     r8d, r8d; msPeriod
0x140068319  xor     edx, edx; pftDueTime
0x14006831b  mov     rcx, rsi; pti
0x14006831e  call    cs:__imp_SetThreadpoolTimer
0x140068324  mov     edx, 1; fCancelPendingCallbacks
0x140068329  mov     rcx, rsi; pti
0x14006832c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140068332  mov     rcx, rsi; pti
0x140068335  call    cs:__imp_CloseThreadpoolTimer
0x14006833b  mov     ecx, ebx; dwErrCode
0x14006833d  call    cs:__imp_SetLastError
0x140068343  mov     qword ptr [rdi+38h], 0
0x14006834b  mov     rbx, [rdi+100h]
0x140068352  mov     qword ptr [rdi+100h], 0
0x14006835d  test    rbx, rbx
0x140068360  jz      short loc_140068376
0x140068362  call    cs:__imp_GetProcessHeap
0x140068368  mov     rcx, rax; hHeap
0x14006836b  mov     r8, rbx; lpMem
0x14006836e  xor     edx, edx; dwFlags
0x140068370  call    cs:__imp_HeapFree
0x140068376  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14006837d  test    r8, r8
0x140068380  jz      short loc_14006839A
0x140068382  mov     rdx, cs:qword_14009D8A0; SRWLock
0x140068389  test    rdx, rdx
0x14006838c  jz      short loc_14006839A
0x14006838e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140068395  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14006839a  lea     rbx, [rdi+98h]
0x1400683a1  mov     rsi, [rbx+40h]
0x1400683a5  mov     qword ptr [rbx+40h], 0
0x1400683ad  test    rsi, rsi
0x1400683b0  jz      short loc_1400683C6
0x1400683b2  call    cs:__imp_GetProcessHeap
0x1400683b8  mov     rcx, rax; hHeap
0x1400683bb  mov     r8, rsi; lpMem
0x1400683be  xor     edx, edx; dwFlags
0x1400683c0  call    cs:__imp_HeapFree
0x1400683c6  mov     rcx, rbx; lpCriticalSection
0x1400683c9  call    cs:__imp_DeleteCriticalSection
0x1400683cf  lea     rcx, [rdi+90h]
0x1400683d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400683db  mov     rsi, [rdi+88h]
0x1400683e2  mov     qword ptr [rdi+88h], 0
0x1400683ed  test    rsi, rsi
0x1400683f0  jz      short loc_140068406
0x1400683f2  call    cs:__imp_GetProcessHeap
0x1400683f8  mov     rcx, rax; hHeap
0x1400683fb  mov     r8, rsi; lpMem
0x1400683fe  xor     edx, edx; dwFlags
0x140068400  call    cs:__imp_HeapFree
0x140068406  lea     rcx, [rdi+48h]; lpCriticalSection
0x14006840a  call    cs:__imp_DeleteCriticalSection
0x140068410  mov     rbx, [rdi+38h]
0x140068414  test    rbx, rbx
0x140068417  jz      short loc_140068441
0x140068419  xor     r9d, r9d; msWindowLength
0x14006841c  xor     r8d, r8d; msPeriod
0x14006841f  xor     edx, edx; pftDueTime
0x140068421  mov     rcx, rbx; pti
0x140068424  call    cs:__imp_SetThreadpoolTimer
0x14006842a  mov     edx, 1; fCancelPendingCallbacks
0x14006842f  mov     rcx, rbx; pti
0x140068432  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140068438  mov     rcx, rbx; pti
0x14006843b  call    cs:__imp_CloseThreadpoolTimer
0x140068441  mov     rbx, [rdi+30h]
0x140068445  test    rbx, rbx
0x140068448  jz      short loc_140068473
0x14006844a  xor     r9d, r9d; msWindowLength
0x14006844d  xor     r8d, r8d; msPeriod
0x140068450  xor     edx, edx; pftDueTime
0x140068452  mov     rcx, rbx; pti
0x140068455  call    cs:__imp_SetThreadpoolTimer
0x14006845b  mov     edx, 1; fCancelPendingCallbacks
0x140068460  mov     rcx, rbx; pti
0x140068463  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140068469  mov     rcx, rbx; pti
0x14006846c  call    cs:__imp_CloseThreadpoolTimer
0x140068472  nop
0x140068473  mov     rcx, [rdi+10h]; lpMem
0x140068477  test    rcx, rcx
0x14006847a  jz      short loc_140068482
0x14006847c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140068481  nop
0x140068482  mov     rbx, [rsp+28h+arg_0]
0x140068487  mov     rsi, [rsp+28h+arg_8]
0x14006848c  add     rsp, 20h
0x140068490  pop     rdi
0x140068491  retn
```
