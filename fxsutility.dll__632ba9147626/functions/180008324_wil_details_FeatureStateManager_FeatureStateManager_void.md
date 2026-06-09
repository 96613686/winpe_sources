# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008324`
- end: `0x180008512`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016290`

## callees

- `0x1800081e0`
- `0x180008324`
- `0x18000b9f4`
- `0x18000c980`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008374`
- `KERNEL32!SetLastError` at `0x1800083bd`
- `KERNEL32!SetLastError` at `0x180008374`
- `KERNEL32!SetLastError` at `0x1800083bd`
- `KERNEL32!HeapFree` at `0x1800083f0`
- `KERNEL32!HeapFree` at `0x180008440`
- `KERNEL32!HeapFree` at `0x180008480`
- `KERNEL32!HeapFree` at `0x1800083f0`
- `KERNEL32!HeapFree` at `0x180008440`
- `KERNEL32!HeapFree` at `0x180008480`
- `KERNEL32!GetProcessHeap` at `0x1800083e2`
- `KERNEL32!GetProcessHeap` at `0x180008432`
- `KERNEL32!GetProcessHeap` at `0x180008472`
- `KERNEL32!GetProcessHeap` at `0x1800083e2`
- `KERNEL32!GetProcessHeap` at `0x180008432`
- `KERNEL32!GetProcessHeap` at `0x180008472`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008363`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800083ac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800084b2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800084e3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008363`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800083ac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800084b2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800084e3`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000836c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800083b5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800084bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800084ec`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000836c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800083b5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800084bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800084ec`
- `KERNEL32!SetThreadpoolTimer` at `0x180008355`
- `KERNEL32!SetThreadpoolTimer` at `0x18000839e`
- `KERNEL32!SetThreadpoolTimer` at `0x1800084a4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800084d5`
- `KERNEL32!SetThreadpoolTimer` at `0x180008355`
- `KERNEL32!SetThreadpoolTimer` at `0x18000839e`
- `KERNEL32!SetThreadpoolTimer` at `0x1800084a4`
- `KERNEL32!SetThreadpoolTimer` at `0x1800084d5`
- `KERNEL32!DeleteCriticalSection` at `0x180008449`
- `KERNEL32!DeleteCriticalSection` at `0x18000848a`
- `KERNEL32!DeleteCriticalSection` at `0x180008449`
- `KERNEL32!DeleteCriticalSection` at `0x18000848a`
- `KERNEL32!GetLastError` at `0x180008342`
- `KERNEL32!GetLastError` at `0x18000838b`
- `KERNEL32!GetLastError` at `0x180008342`
- `KERNEL32!GetLastError` at `0x18000838b`

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
  if ( v8 && qword_18001E2B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001E2B8[25], qword_18001E2B8, v8);
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
0x180008324  mov     [rsp+arg_0], rbx
0x180008329  mov     [rsp+arg_8], rsi
0x18000832e  push    rdi
0x18000832f  sub     rsp, 20h
0x180008333  mov     rdi, rcx
0x180008336  mov     byte ptr [rcx], 0
0x180008339  mov     rsi, [rcx+30h]
0x18000833d  test    rsi, rsi
0x180008340  jz      short loc_18000837A
0x180008342  call    cs:__imp_GetLastError
0x180008348  mov     ebx, eax
0x18000834a  xor     r9d, r9d; msWindowLength
0x18000834d  xor     r8d, r8d; msPeriod
0x180008350  xor     edx, edx; pftDueTime
0x180008352  mov     rcx, rsi; pti
0x180008355  call    cs:__imp_SetThreadpoolTimer
0x18000835b  mov     edx, 1; fCancelPendingCallbacks
0x180008360  mov     rcx, rsi; pti
0x180008363  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008369  mov     rcx, rsi; pti
0x18000836c  call    cs:__imp_CloseThreadpoolTimer
0x180008372  mov     ecx, ebx; dwErrCode
0x180008374  call    cs:__imp_SetLastError
0x18000837a  mov     qword ptr [rdi+30h], 0
0x180008382  mov     rsi, [rdi+38h]
0x180008386  test    rsi, rsi
0x180008389  jz      short loc_1800083C3
0x18000838b  call    cs:__imp_GetLastError
0x180008391  mov     ebx, eax
0x180008393  xor     r9d, r9d; msWindowLength
0x180008396  xor     r8d, r8d; msPeriod
0x180008399  xor     edx, edx; pftDueTime
0x18000839b  mov     rcx, rsi; pti
0x18000839e  call    cs:__imp_SetThreadpoolTimer
0x1800083a4  mov     edx, 1; fCancelPendingCallbacks
0x1800083a9  mov     rcx, rsi; pti
0x1800083ac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083b2  mov     rcx, rsi; pti
0x1800083b5  call    cs:__imp_CloseThreadpoolTimer
0x1800083bb  mov     ecx, ebx; dwErrCode
0x1800083bd  call    cs:__imp_SetLastError
0x1800083c3  mov     qword ptr [rdi+38h], 0
0x1800083cb  mov     rbx, [rdi+100h]
0x1800083d2  mov     qword ptr [rdi+100h], 0
0x1800083dd  test    rbx, rbx
0x1800083e0  jz      short loc_1800083F6
0x1800083e2  call    cs:__imp_GetProcessHeap
0x1800083e8  mov     rcx, rax; hHeap
0x1800083eb  mov     r8, rbx; lpMem
0x1800083ee  xor     edx, edx; dwFlags
0x1800083f0  call    cs:__imp_HeapFree
0x1800083f6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800083fd  test    r8, r8
0x180008400  jz      short loc_18000841A
0x180008402  mov     rdx, cs:qword_18001E2B8; SRWLock
0x180008409  test    rdx, rdx
0x18000840c  jz      short loc_18000841A
0x18000840e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008415  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000841a  lea     rbx, [rdi+98h]
0x180008421  mov     rsi, [rbx+40h]
0x180008425  mov     qword ptr [rbx+40h], 0
0x18000842d  test    rsi, rsi
0x180008430  jz      short loc_180008446
0x180008432  call    cs:__imp_GetProcessHeap
0x180008438  mov     rcx, rax; hHeap
0x18000843b  mov     r8, rsi; lpMem
0x18000843e  xor     edx, edx; dwFlags
0x180008440  call    cs:__imp_HeapFree
0x180008446  mov     rcx, rbx; lpCriticalSection
0x180008449  call    cs:__imp_DeleteCriticalSection
0x18000844f  lea     rcx, [rdi+90h]
0x180008456  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000845b  mov     rsi, [rdi+88h]
0x180008462  mov     qword ptr [rdi+88h], 0
0x18000846d  test    rsi, rsi
0x180008470  jz      short loc_180008486
0x180008472  call    cs:__imp_GetProcessHeap
0x180008478  mov     rcx, rax; hHeap
0x18000847b  mov     r8, rsi; lpMem
0x18000847e  xor     edx, edx; dwFlags
0x180008480  call    cs:__imp_HeapFree
0x180008486  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000848a  call    cs:__imp_DeleteCriticalSection
0x180008490  mov     rbx, [rdi+38h]
0x180008494  test    rbx, rbx
0x180008497  jz      short loc_1800084C1
0x180008499  xor     r9d, r9d; msWindowLength
0x18000849c  xor     r8d, r8d; msPeriod
0x18000849f  xor     edx, edx; pftDueTime
0x1800084a1  mov     rcx, rbx; pti
0x1800084a4  call    cs:__imp_SetThreadpoolTimer
0x1800084aa  mov     edx, 1; fCancelPendingCallbacks
0x1800084af  mov     rcx, rbx; pti
0x1800084b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800084b8  mov     rcx, rbx; pti
0x1800084bb  call    cs:__imp_CloseThreadpoolTimer
0x1800084c1  mov     rbx, [rdi+30h]
0x1800084c5  test    rbx, rbx
0x1800084c8  jz      short loc_1800084F3
0x1800084ca  xor     r9d, r9d; msWindowLength
0x1800084cd  xor     r8d, r8d; msPeriod
0x1800084d0  xor     edx, edx; pftDueTime
0x1800084d2  mov     rcx, rbx; pti
0x1800084d5  call    cs:__imp_SetThreadpoolTimer
0x1800084db  mov     edx, 1; fCancelPendingCallbacks
0x1800084e0  mov     rcx, rbx; pti
0x1800084e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800084e9  mov     rcx, rbx; pti
0x1800084ec  call    cs:__imp_CloseThreadpoolTimer
0x1800084f2  nop
0x1800084f3  mov     rcx, [rdi+10h]; lpMem
0x1800084f7  test    rcx, rcx
0x1800084fa  jz      short loc_180008502
0x1800084fc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008501  nop
0x180008502  mov     rbx, [rsp+28h+arg_0]
0x180008507  mov     rsi, [rsp+28h+arg_8]
0x18000850c  add     rsp, 20h
0x180008510  pop     rdi
0x180008511  retn
```
