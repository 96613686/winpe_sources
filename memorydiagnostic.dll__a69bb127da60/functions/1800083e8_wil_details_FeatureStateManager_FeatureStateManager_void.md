# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800083e8`
- end: `0x1800085d6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800221e0`

## callees

- `0x180007e78`
- `0x1800083e8`
- `0x18000ffa0`
- `0x180014808`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800084a6`
- `KERNEL32!GetProcessHeap` at `0x1800084f6`
- `KERNEL32!GetProcessHeap` at `0x180008536`
- `KERNEL32!GetProcessHeap` at `0x1800084a6`
- `KERNEL32!GetProcessHeap` at `0x1800084f6`
- `KERNEL32!GetProcessHeap` at `0x180008536`
- `KERNEL32!DeleteCriticalSection` at `0x18000850d`
- `KERNEL32!DeleteCriticalSection` at `0x18000854e`
- `KERNEL32!DeleteCriticalSection` at `0x18000850d`
- `KERNEL32!DeleteCriticalSection` at `0x18000854e`
- `KERNEL32!SetThreadpoolTimer` at `0x180008419`
- `KERNEL32!SetThreadpoolTimer` at `0x180008462`
- `KERNEL32!SetThreadpoolTimer` at `0x180008568`
- `KERNEL32!SetThreadpoolTimer` at `0x180008599`
- `KERNEL32!SetThreadpoolTimer` at `0x180008419`
- `KERNEL32!SetThreadpoolTimer` at `0x180008462`
- `KERNEL32!SetThreadpoolTimer` at `0x180008568`
- `KERNEL32!SetThreadpoolTimer` at `0x180008599`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008430`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008479`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000857f`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800085b0`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008430`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008479`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000857f`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800085b0`
- `KERNEL32!GetLastError` at `0x180008406`
- `KERNEL32!GetLastError` at `0x18000844f`
- `KERNEL32!GetLastError` at `0x180008406`
- `KERNEL32!GetLastError` at `0x18000844f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008427`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008470`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008576`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800085a7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008427`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008470`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008576`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800085a7`
- `KERNEL32!SetLastError` at `0x180008438`
- `KERNEL32!SetLastError` at `0x180008481`
- `KERNEL32!SetLastError` at `0x180008438`
- `KERNEL32!SetLastError` at `0x180008481`
- `KERNEL32!HeapFree` at `0x1800084b4`
- `KERNEL32!HeapFree` at `0x180008504`
- `KERNEL32!HeapFree` at `0x180008544`
- `KERNEL32!HeapFree` at `0x1800084b4`
- `KERNEL32!HeapFree` at `0x180008504`
- `KERNEL32!HeapFree` at `0x180008544`

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
  if ( v8 && qword_18002F0A0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002F0A0[25], qword_18002F0A0, v8);
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
0x1800083e8  mov     [rsp+arg_0], rbx
0x1800083ed  mov     [rsp+arg_8], rsi
0x1800083f2  push    rdi
0x1800083f3  sub     rsp, 20h
0x1800083f7  mov     rdi, rcx
0x1800083fa  mov     byte ptr [rcx], 0
0x1800083fd  mov     rsi, [rcx+30h]
0x180008401  test    rsi, rsi
0x180008404  jz      short loc_18000843E
0x180008406  call    cs:__imp_GetLastError
0x18000840c  mov     ebx, eax
0x18000840e  xor     r9d, r9d; msWindowLength
0x180008411  xor     r8d, r8d; msPeriod
0x180008414  xor     edx, edx; pftDueTime
0x180008416  mov     rcx, rsi; pti
0x180008419  call    cs:__imp_SetThreadpoolTimer
0x18000841f  mov     edx, 1; fCancelPendingCallbacks
0x180008424  mov     rcx, rsi; pti
0x180008427  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000842d  mov     rcx, rsi; pti
0x180008430  call    cs:__imp_CloseThreadpoolTimer
0x180008436  mov     ecx, ebx; dwErrCode
0x180008438  call    cs:__imp_SetLastError
0x18000843e  mov     qword ptr [rdi+30h], 0
0x180008446  mov     rsi, [rdi+38h]
0x18000844a  test    rsi, rsi
0x18000844d  jz      short loc_180008487
0x18000844f  call    cs:__imp_GetLastError
0x180008455  mov     ebx, eax
0x180008457  xor     r9d, r9d; msWindowLength
0x18000845a  xor     r8d, r8d; msPeriod
0x18000845d  xor     edx, edx; pftDueTime
0x18000845f  mov     rcx, rsi; pti
0x180008462  call    cs:__imp_SetThreadpoolTimer
0x180008468  mov     edx, 1; fCancelPendingCallbacks
0x18000846d  mov     rcx, rsi; pti
0x180008470  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008476  mov     rcx, rsi; pti
0x180008479  call    cs:__imp_CloseThreadpoolTimer
0x18000847f  mov     ecx, ebx; dwErrCode
0x180008481  call    cs:__imp_SetLastError
0x180008487  mov     qword ptr [rdi+38h], 0
0x18000848f  mov     rbx, [rdi+100h]
0x180008496  mov     qword ptr [rdi+100h], 0
0x1800084a1  test    rbx, rbx
0x1800084a4  jz      short loc_1800084BA
0x1800084a6  call    cs:__imp_GetProcessHeap
0x1800084ac  mov     rcx, rax; hHeap
0x1800084af  mov     r8, rbx; lpMem
0x1800084b2  xor     edx, edx; dwFlags
0x1800084b4  call    cs:__imp_HeapFree
0x1800084ba  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800084c1  test    r8, r8
0x1800084c4  jz      short loc_1800084DE
0x1800084c6  mov     rdx, cs:qword_18002F0A0; SRWLock
0x1800084cd  test    rdx, rdx
0x1800084d0  jz      short loc_1800084DE
0x1800084d2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800084d9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800084de  lea     rbx, [rdi+98h]
0x1800084e5  mov     rsi, [rbx+40h]
0x1800084e9  mov     qword ptr [rbx+40h], 0
0x1800084f1  test    rsi, rsi
0x1800084f4  jz      short loc_18000850A
0x1800084f6  call    cs:__imp_GetProcessHeap
0x1800084fc  mov     rcx, rax; hHeap
0x1800084ff  mov     r8, rsi; lpMem
0x180008502  xor     edx, edx; dwFlags
0x180008504  call    cs:__imp_HeapFree
0x18000850a  mov     rcx, rbx; lpCriticalSection
0x18000850d  call    cs:__imp_DeleteCriticalSection
0x180008513  lea     rcx, [rdi+90h]
0x18000851a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000851f  mov     rsi, [rdi+88h]
0x180008526  mov     qword ptr [rdi+88h], 0
0x180008531  test    rsi, rsi
0x180008534  jz      short loc_18000854A
0x180008536  call    cs:__imp_GetProcessHeap
0x18000853c  mov     rcx, rax; hHeap
0x18000853f  mov     r8, rsi; lpMem
0x180008542  xor     edx, edx; dwFlags
0x180008544  call    cs:__imp_HeapFree
0x18000854a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000854e  call    cs:__imp_DeleteCriticalSection
0x180008554  mov     rbx, [rdi+38h]
0x180008558  test    rbx, rbx
0x18000855b  jz      short loc_180008585
0x18000855d  xor     r9d, r9d; msWindowLength
0x180008560  xor     r8d, r8d; msPeriod
0x180008563  xor     edx, edx; pftDueTime
0x180008565  mov     rcx, rbx; pti
0x180008568  call    cs:__imp_SetThreadpoolTimer
0x18000856e  mov     edx, 1; fCancelPendingCallbacks
0x180008573  mov     rcx, rbx; pti
0x180008576  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000857c  mov     rcx, rbx; pti
0x18000857f  call    cs:__imp_CloseThreadpoolTimer
0x180008585  mov     rbx, [rdi+30h]
0x180008589  test    rbx, rbx
0x18000858c  jz      short loc_1800085B7
0x18000858e  xor     r9d, r9d; msWindowLength
0x180008591  xor     r8d, r8d; msPeriod
0x180008594  xor     edx, edx; pftDueTime
0x180008596  mov     rcx, rbx; pti
0x180008599  call    cs:__imp_SetThreadpoolTimer
0x18000859f  mov     edx, 1; fCancelPendingCallbacks
0x1800085a4  mov     rcx, rbx; pti
0x1800085a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800085ad  mov     rcx, rbx; pti
0x1800085b0  call    cs:__imp_CloseThreadpoolTimer
0x1800085b6  nop
0x1800085b7  mov     rcx, [rdi+10h]; lpMem
0x1800085bb  test    rcx, rcx
0x1800085be  jz      short loc_1800085C6
0x1800085c0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800085c5  nop
0x1800085c6  mov     rbx, [rsp+28h+arg_0]
0x1800085cb  mov     rsi, [rsp+28h+arg_8]
0x1800085d0  add     rsp, 20h
0x1800085d4  pop     rdi
0x1800085d5  retn
```
