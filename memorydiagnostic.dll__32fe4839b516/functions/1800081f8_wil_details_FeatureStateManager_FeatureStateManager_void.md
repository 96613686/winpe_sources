# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800081f8`
- end: `0x1800083cf`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `471`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800237c0`

## callees

- `0x1800081f8`
- `0x180010918`
- `0x1800155a0`
- `0x180015614`
- `0x180018824`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008241`
- `KERNEL32!GetProcessHeap` at `0x18000829a`
- `KERNEL32!GetProcessHeap` at `0x1800082ee`
- `KERNEL32!GetProcessHeap` at `0x180008241`
- `KERNEL32!GetProcessHeap` at `0x18000829a`
- `KERNEL32!GetProcessHeap` at `0x1800082ee`
- `KERNEL32!DeleteCriticalSection` at `0x1800082bd`
- `KERNEL32!DeleteCriticalSection` at `0x180008312`
- `KERNEL32!DeleteCriticalSection` at `0x1800082bd`
- `KERNEL32!DeleteCriticalSection` at `0x180008312`
- `KERNEL32!SetThreadpoolTimer` at `0x180008337`
- `KERNEL32!SetThreadpoolTimer` at `0x180008377`
- `KERNEL32!SetThreadpoolTimer` at `0x180008337`
- `KERNEL32!SetThreadpoolTimer` at `0x180008377`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008357`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008397`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008357`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008397`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008348`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008388`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008348`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008388`
- `KERNEL32!HeapFree` at `0x180008255`
- `KERNEL32!HeapFree` at `0x1800082ae`
- `KERNEL32!HeapFree` at `0x180008302`
- `KERNEL32!HeapFree` at `0x180008255`
- `KERNEL32!HeapFree` at `0x1800082ae`
- `KERNEL32!HeapFree` at `0x180008302`

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
  if ( v4 && qword_1800300A0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800300A0[25], qword_1800300A0, v4);
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
0x1800081f8  mov     rax, rsp
0x1800081fb  mov     [rax+8], rbx
0x1800081ff  mov     [rax+10h], rsi
0x180008203  mov     [rax+18h], rdi
0x180008207  mov     [rax+20h], r14
0x18000820b  push    r15
0x18000820d  sub     rsp, 20h
0x180008211  mov     rbx, rcx
0x180008214  mov     byte ptr [rcx], 0
0x180008217  xor     edx, edx
0x180008219  add     rcx, 30h ; '0'
0x18000821d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008222  xor     edx, edx
0x180008224  lea     rcx, [rbx+38h]
0x180008228  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000822d  mov     rdi, [rbx+100h]
0x180008234  and     qword ptr [rbx+100h], 0
0x18000823c  test    rdi, rdi
0x18000823f  jz      short loc_180008261
0x180008241  call    cs:__imp_GetProcessHeap
0x180008248  nop     dword ptr [rax+rax+00h]
0x18000824d  mov     rcx, rax; hHeap
0x180008250  mov     r8, rdi; lpMem
0x180008253  xor     edx, edx; dwFlags
0x180008255  call    cs:__imp_HeapFree
0x18000825c  nop     dword ptr [rax+rax+00h]
0x180008261  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008268  test    r8, r8
0x18000826b  jz      short loc_180008285
0x18000826d  mov     rdx, cs:qword_1800300A0; SRWLock
0x180008274  test    rdx, rdx
0x180008277  jz      short loc_180008285
0x180008279  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008280  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008285  lea     rdi, [rbx+98h]
0x18000828c  mov     rsi, [rdi+40h]
0x180008290  and     qword ptr [rdi+40h], 0
0x180008295  test    rsi, rsi
0x180008298  jz      short loc_1800082BA
0x18000829a  call    cs:__imp_GetProcessHeap
0x1800082a1  nop     dword ptr [rax+rax+00h]
0x1800082a6  mov     rcx, rax; hHeap
0x1800082a9  mov     r8, rsi; lpMem
0x1800082ac  xor     edx, edx; dwFlags
0x1800082ae  call    cs:__imp_HeapFree
0x1800082b5  nop     dword ptr [rax+rax+00h]
0x1800082ba  mov     rcx, rdi; lpCriticalSection
0x1800082bd  call    cs:__imp_DeleteCriticalSection
0x1800082c4  nop     dword ptr [rax+rax+00h]
0x1800082c9  mov     rcx, [rbx+90h]; this
0x1800082d0  test    rcx, rcx
0x1800082d3  jz      short loc_1800082DA
0x1800082d5  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800082da  mov     rsi, [rbx+88h]
0x1800082e1  and     qword ptr [rbx+88h], 0
0x1800082e9  test    rsi, rsi
0x1800082ec  jz      short loc_18000830E
0x1800082ee  call    cs:__imp_GetProcessHeap
0x1800082f5  nop     dword ptr [rax+rax+00h]
0x1800082fa  mov     rcx, rax; hHeap
0x1800082fd  mov     r8, rsi; lpMem
0x180008300  xor     edx, edx; dwFlags
0x180008302  call    cs:__imp_HeapFree
0x180008309  nop     dword ptr [rax+rax+00h]
0x18000830e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180008312  call    cs:__imp_DeleteCriticalSection
0x180008319  nop     dword ptr [rax+rax+00h]
0x18000831e  mov     rdi, [rbx+38h]
0x180008322  mov     esi, 1
0x180008327  test    rdi, rdi
0x18000832a  jz      short loc_180008363
0x18000832c  xor     r9d, r9d; msWindowLength
0x18000832f  xor     r8d, r8d; msPeriod
0x180008332  xor     edx, edx; pftDueTime
0x180008334  mov     rcx, rdi; pti
0x180008337  call    cs:__imp_SetThreadpoolTimer
0x18000833e  nop     dword ptr [rax+rax+00h]
0x180008343  mov     edx, esi; fCancelPendingCallbacks
0x180008345  mov     rcx, rdi; pti
0x180008348  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000834f  nop     dword ptr [rax+rax+00h]
0x180008354  mov     rcx, rdi; pti
0x180008357  call    cs:__imp_CloseThreadpoolTimer
0x18000835e  nop     dword ptr [rax+rax+00h]
0x180008363  mov     rdi, [rbx+30h]
0x180008367  test    rdi, rdi
0x18000836a  jz      short loc_1800083A4
0x18000836c  xor     r9d, r9d; msWindowLength
0x18000836f  xor     r8d, r8d; msPeriod
0x180008372  xor     edx, edx; pftDueTime
0x180008374  mov     rcx, rdi; pti
0x180008377  call    cs:__imp_SetThreadpoolTimer
0x18000837e  nop     dword ptr [rax+rax+00h]
0x180008383  mov     edx, esi; fCancelPendingCallbacks
0x180008385  mov     rcx, rdi; pti
0x180008388  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000838f  nop     dword ptr [rax+rax+00h]
0x180008394  mov     rcx, rdi; pti
0x180008397  call    cs:__imp_CloseThreadpoolTimer
0x18000839e  nop     dword ptr [rax+rax+00h]
0x1800083a3  nop
0x1800083a4  mov     rcx, [rbx+10h]; lpMem
0x1800083a8  test    rcx, rcx
0x1800083ab  jz      short loc_1800083B3
0x1800083ad  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800083b2  nop
0x1800083b3  mov     rbx, [rsp+28h+arg_0]
0x1800083b8  mov     rsi, [rsp+28h+arg_8]
0x1800083bd  mov     rdi, [rsp+28h+arg_10]
0x1800083c2  mov     r14, [rsp+28h+arg_18]
0x1800083c7  add     rsp, 20h
0x1800083cb  pop     r15
0x1800083cd  retn
```
