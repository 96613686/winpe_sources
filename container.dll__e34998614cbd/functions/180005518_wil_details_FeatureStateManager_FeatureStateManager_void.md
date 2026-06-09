# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005518`
- end: `0x1800056dc`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180033710`

## callees

- `0x180005518`
- `0x180009cbc`
- `0x18000b78c`
- `0x18000b800`
- `0x18000c100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000562e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000562e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000560a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000560a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000556b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000561e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000556b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000561e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005664`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005664`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005653`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005693`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005653`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005693`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005673`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005673`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v4; // r8
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  struct _TP_TIMER *v11; // rdi
  struct _TP_TIMER *v12; // rdi
  void *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && SRWLock )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&SRWLock[25], SRWLock, v4);
  v5 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 18);
  if ( v8 )
    wil::details::UnregisterWilFeatureConfigurationChange(v8, v7);
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x180005518  push    rbx
0x18000551a  push    rsi
0x18000551b  push    rdi
0x18000551c  push    r14
0x18000551e  push    r15
0x180005520  sub     rsp, 20h
0x180005524  mov     rbx, rcx
0x180005527  mov     byte ptr [rcx], 0
0x18000552a  xor     edx, edx
0x18000552c  add     rcx, 30h ; '0'
0x180005530  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005535  xor     edx, edx
0x180005537  lea     rcx, [rbx+38h]
0x18000553b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005540  mov     rdi, [rbx+100h]
0x180005547  mov     qword ptr [rbx+100h], 0
0x180005552  test    rdi, rdi
0x180005555  jz      short loc_180005577
0x180005557  call    cs:__imp_GetProcessHeap
0x18000555e  nop     dword ptr [rax+rax+00h]
0x180005563  mov     rcx, rax; hHeap
0x180005566  mov     r8, rdi; lpMem
0x180005569  xor     edx, edx; dwFlags
0x18000556b  call    cs:__imp_HeapFree
0x180005572  nop     dword ptr [rax+rax+00h]
0x180005577  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000557e  test    r8, r8
0x180005581  jz      short loc_18000559B
0x180005583  mov     rdx, cs:SRWLock; SRWLock
0x18000558a  test    rdx, rdx
0x18000558d  jz      short loc_18000559B
0x18000558f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005596  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000559b  lea     rdi, [rbx+98h]
0x1800055a2  mov     rsi, [rdi+40h]
0x1800055a6  mov     qword ptr [rdi+40h], 0
0x1800055ae  test    rsi, rsi
0x1800055b1  jz      short loc_1800055D3
0x1800055b3  call    cs:__imp_GetProcessHeap
0x1800055ba  nop     dword ptr [rax+rax+00h]
0x1800055bf  mov     rcx, rax; hHeap
0x1800055c2  mov     r8, rsi; lpMem
0x1800055c5  xor     edx, edx; dwFlags
0x1800055c7  call    cs:__imp_HeapFree
0x1800055ce  nop     dword ptr [rax+rax+00h]
0x1800055d3  mov     rcx, rdi; lpCriticalSection
0x1800055d6  call    cs:__imp_DeleteCriticalSection
0x1800055dd  nop     dword ptr [rax+rax+00h]
0x1800055e2  mov     rcx, [rbx+90h]; this
0x1800055e9  test    rcx, rcx
0x1800055ec  jz      short loc_1800055F3
0x1800055ee  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800055f3  mov     rsi, [rbx+88h]
0x1800055fa  mov     qword ptr [rbx+88h], 0
0x180005605  test    rsi, rsi
0x180005608  jz      short loc_18000562A
0x18000560a  call    cs:__imp_GetProcessHeap
0x180005611  nop     dword ptr [rax+rax+00h]
0x180005616  mov     rcx, rax; hHeap
0x180005619  mov     r8, rsi; lpMem
0x18000561c  xor     edx, edx; dwFlags
0x18000561e  call    cs:__imp_HeapFree
0x180005625  nop     dword ptr [rax+rax+00h]
0x18000562a  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000562e  call    cs:__imp_DeleteCriticalSection
0x180005635  nop     dword ptr [rax+rax+00h]
0x18000563a  mov     rdi, [rbx+38h]
0x18000563e  mov     esi, 1
0x180005643  test    rdi, rdi
0x180005646  jz      short loc_18000567F
0x180005648  xor     r9d, r9d; msWindowLength
0x18000564b  xor     r8d, r8d; msPeriod
0x18000564e  xor     edx, edx; pftDueTime
0x180005650  mov     rcx, rdi; pti
0x180005653  call    cs:__imp_SetThreadpoolTimer
0x18000565a  nop     dword ptr [rax+rax+00h]
0x18000565f  mov     edx, esi; fCancelPendingCallbacks
0x180005661  mov     rcx, rdi; pti
0x180005664  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000566b  nop     dword ptr [rax+rax+00h]
0x180005670  mov     rcx, rdi; pti
0x180005673  call    cs:__imp_CloseThreadpoolTimer
0x18000567a  nop     dword ptr [rax+rax+00h]
0x18000567f  mov     rdi, [rbx+30h]
0x180005683  test    rdi, rdi
0x180005686  jz      short loc_1800056C0
0x180005688  xor     r9d, r9d; msWindowLength
0x18000568b  xor     r8d, r8d; msPeriod
0x18000568e  xor     edx, edx; pftDueTime
0x180005690  mov     rcx, rdi; pti
0x180005693  call    cs:__imp_SetThreadpoolTimer
0x18000569a  nop     dword ptr [rax+rax+00h]
0x18000569f  mov     edx, esi; fCancelPendingCallbacks
0x1800056a1  mov     rcx, rdi; pti
0x1800056a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800056ab  nop     dword ptr [rax+rax+00h]
0x1800056b0  mov     rcx, rdi; pti
0x1800056b3  call    cs:__imp_CloseThreadpoolTimer
0x1800056ba  nop     dword ptr [rax+rax+00h]
0x1800056bf  nop
0x1800056c0  mov     rcx, [rbx+10h]; lpMem
0x1800056c4  test    rcx, rcx
0x1800056c7  jz      short loc_1800056CF
0x1800056c9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800056ce  nop
0x1800056cf  add     rsp, 20h
0x1800056d3  pop     r15
0x1800056d5  pop     r14
0x1800056d7  pop     rdi
0x1800056d8  pop     rsi
0x1800056d9  pop     rbx
0x1800056da  retn
```
