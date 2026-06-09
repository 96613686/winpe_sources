# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800032e0`
- end: `0x1800034cc`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800189b0`

## callees

- `0x180002fac`
- `0x1800032e0`
- `0x180009838`
- `0x18000a714`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000331f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003368`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000346e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000349f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000331f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003368`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000346e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000349f`
- `KERNEL32!GetLastError` at `0x1800032fe`
- `KERNEL32!GetLastError` at `0x180003347`
- `KERNEL32!GetLastError` at `0x1800032fe`
- `KERNEL32!GetLastError` at `0x180003347`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003328`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003371`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003477`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800034a8`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003328`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003371`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003477`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800034a8`
- `KERNEL32!SetThreadpoolTimer` at `0x180003311`
- `KERNEL32!SetThreadpoolTimer` at `0x18000335a`
- `KERNEL32!SetThreadpoolTimer` at `0x180003460`
- `KERNEL32!SetThreadpoolTimer` at `0x180003491`
- `KERNEL32!SetThreadpoolTimer` at `0x180003311`
- `KERNEL32!SetThreadpoolTimer` at `0x18000335a`
- `KERNEL32!SetThreadpoolTimer` at `0x180003460`
- `KERNEL32!SetThreadpoolTimer` at `0x180003491`
- `KERNEL32!DeleteCriticalSection` at `0x180003405`
- `KERNEL32!DeleteCriticalSection` at `0x180003446`
- `KERNEL32!DeleteCriticalSection` at `0x180003405`
- `KERNEL32!DeleteCriticalSection` at `0x180003446`
- `KERNEL32!GetProcessHeap` at `0x18000339e`
- `KERNEL32!GetProcessHeap` at `0x1800033ee`
- `KERNEL32!GetProcessHeap` at `0x18000342e`
- `KERNEL32!GetProcessHeap` at `0x18000339e`
- `KERNEL32!GetProcessHeap` at `0x1800033ee`
- `KERNEL32!GetProcessHeap` at `0x18000342e`
- `KERNEL32!HeapFree` at `0x1800033ac`
- `KERNEL32!HeapFree` at `0x1800033fc`
- `KERNEL32!HeapFree` at `0x18000343c`
- `KERNEL32!HeapFree` at `0x1800033ac`
- `KERNEL32!HeapFree` at `0x1800033fc`
- `KERNEL32!HeapFree` at `0x18000343c`
- `KERNEL32!SetLastError` at `0x180003330`
- `KERNEL32!SetLastError` at `0x180003379`
- `KERNEL32!SetLastError` at `0x180003330`
- `KERNEL32!SetLastError` at `0x180003379`

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
  if ( v8 && qword_180021188 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180021188[25], qword_180021188, v8);
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
0x1800032e0  mov     [rsp+arg_0], rbx
0x1800032e5  mov     [rsp+arg_8], rsi
0x1800032ea  push    rdi
0x1800032eb  sub     rsp, 20h
0x1800032ef  mov     byte ptr [rcx], 0
0x1800032f2  mov     rdi, rcx
0x1800032f5  mov     rsi, [rcx+30h]
0x1800032f9  test    rsi, rsi
0x1800032fc  jz      short loc_180003336
0x1800032fe  call    cs:__imp_GetLastError
0x180003304  xor     r9d, r9d; msWindowLength
0x180003307  xor     r8d, r8d; msPeriod
0x18000330a  xor     edx, edx; pftDueTime
0x18000330c  mov     rcx, rsi; pti
0x18000330f  mov     ebx, eax
0x180003311  call    cs:__imp_SetThreadpoolTimer
0x180003317  mov     edx, 1; fCancelPendingCallbacks
0x18000331c  mov     rcx, rsi; pti
0x18000331f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003325  mov     rcx, rsi; pti
0x180003328  call    cs:__imp_CloseThreadpoolTimer
0x18000332e  mov     ecx, ebx; dwErrCode
0x180003330  call    cs:__imp_SetLastError
0x180003336  mov     qword ptr [rdi+30h], 0
0x18000333e  mov     rsi, [rdi+38h]
0x180003342  test    rsi, rsi
0x180003345  jz      short loc_18000337F
0x180003347  call    cs:__imp_GetLastError
0x18000334d  xor     r9d, r9d; msWindowLength
0x180003350  xor     r8d, r8d; msPeriod
0x180003353  xor     edx, edx; pftDueTime
0x180003355  mov     rcx, rsi; pti
0x180003358  mov     ebx, eax
0x18000335a  call    cs:__imp_SetThreadpoolTimer
0x180003360  mov     edx, 1; fCancelPendingCallbacks
0x180003365  mov     rcx, rsi; pti
0x180003368  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000336e  mov     rcx, rsi; pti
0x180003371  call    cs:__imp_CloseThreadpoolTimer
0x180003377  mov     ecx, ebx; dwErrCode
0x180003379  call    cs:__imp_SetLastError
0x18000337f  mov     qword ptr [rdi+38h], 0
0x180003387  mov     rbx, [rdi+100h]
0x18000338e  mov     qword ptr [rdi+100h], 0
0x180003399  test    rbx, rbx
0x18000339c  jz      short loc_1800033B2
0x18000339e  call    cs:__imp_GetProcessHeap
0x1800033a4  mov     r8, rbx; lpMem
0x1800033a7  xor     edx, edx; dwFlags
0x1800033a9  mov     rcx, rax; hHeap
0x1800033ac  call    cs:__imp_HeapFree
0x1800033b2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800033b9  test    r8, r8
0x1800033bc  jz      short loc_1800033D6
0x1800033be  mov     rdx, cs:qword_180021188; SRWLock
0x1800033c5  test    rdx, rdx
0x1800033c8  jz      short loc_1800033D6
0x1800033ca  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800033d1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800033d6  lea     rbx, [rdi+98h]
0x1800033dd  mov     rsi, [rbx+40h]
0x1800033e1  mov     qword ptr [rbx+40h], 0
0x1800033e9  test    rsi, rsi
0x1800033ec  jz      short loc_180003402
0x1800033ee  call    cs:__imp_GetProcessHeap
0x1800033f4  mov     r8, rsi; lpMem
0x1800033f7  xor     edx, edx; dwFlags
0x1800033f9  mov     rcx, rax; hHeap
0x1800033fc  call    cs:__imp_HeapFree
0x180003402  mov     rcx, rbx; lpCriticalSection
0x180003405  call    cs:__imp_DeleteCriticalSection
0x18000340b  lea     rcx, [rdi+90h]
0x180003412  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003417  mov     rsi, [rdi+88h]
0x18000341e  mov     qword ptr [rdi+88h], 0
0x180003429  test    rsi, rsi
0x18000342c  jz      short loc_180003442
0x18000342e  call    cs:__imp_GetProcessHeap
0x180003434  mov     r8, rsi; lpMem
0x180003437  xor     edx, edx; dwFlags
0x180003439  mov     rcx, rax; hHeap
0x18000343c  call    cs:__imp_HeapFree
0x180003442  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003446  call    cs:__imp_DeleteCriticalSection
0x18000344c  mov     rbx, [rdi+38h]
0x180003450  test    rbx, rbx
0x180003453  jz      short loc_18000347D
0x180003455  xor     r9d, r9d; msWindowLength
0x180003458  xor     r8d, r8d; msPeriod
0x18000345b  xor     edx, edx; pftDueTime
0x18000345d  mov     rcx, rbx; pti
0x180003460  call    cs:__imp_SetThreadpoolTimer
0x180003466  mov     edx, 1; fCancelPendingCallbacks
0x18000346b  mov     rcx, rbx; pti
0x18000346e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003474  mov     rcx, rbx; pti
0x180003477  call    cs:__imp_CloseThreadpoolTimer
0x18000347d  mov     rbx, [rdi+30h]
0x180003481  test    rbx, rbx
0x180003484  jz      short loc_1800034AE
0x180003486  xor     r9d, r9d; msWindowLength
0x180003489  xor     r8d, r8d; msPeriod
0x18000348c  xor     edx, edx; pftDueTime
0x18000348e  mov     rcx, rbx; pti
0x180003491  call    cs:__imp_SetThreadpoolTimer
0x180003497  mov     edx, 1; fCancelPendingCallbacks
0x18000349c  mov     rcx, rbx; pti
0x18000349f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800034a5  mov     rcx, rbx; pti
0x1800034a8  call    cs:__imp_CloseThreadpoolTimer
0x1800034ae  mov     rcx, [rdi+10h]; lpMem
0x1800034b2  test    rcx, rcx
0x1800034b5  jz      short loc_1800034BC
0x1800034b7  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800034bc  mov     rbx, [rsp+28h+arg_0]
0x1800034c1  mov     rsi, [rsp+28h+arg_8]
0x1800034c6  add     rsp, 20h
0x1800034ca  pop     rdi
0x1800034cb  retn
```
