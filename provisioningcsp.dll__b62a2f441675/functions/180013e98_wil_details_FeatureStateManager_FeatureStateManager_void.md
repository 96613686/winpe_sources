# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180013e98`
- end: `0x18001405c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180037ad0`

## callees

- `0x180013e98`
- `0x180021b34`
- `0x18002251c`
- `0x180022590`
- `0x180022a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013f56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013fae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013f56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013fae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013eeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013eeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ed7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013f33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ed7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013f33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013f8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013fe4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014024`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013fe4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014024`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013ff3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014033`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013ff3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014033`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013fd3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014013`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013fd3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014013`

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
  if ( v4 && qword_1800496B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800496B8[25], qword_1800496B8, v4);
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
0x180013e98  push    rbx
0x180013e9a  push    rsi
0x180013e9b  push    rdi
0x180013e9c  push    r14
0x180013e9e  push    r15
0x180013ea0  sub     rsp, 20h
0x180013ea4  mov     rbx, rcx
0x180013ea7  mov     byte ptr [rcx], 0
0x180013eaa  xor     edx, edx
0x180013eac  add     rcx, 30h ; '0'
0x180013eb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013eb5  xor     edx, edx
0x180013eb7  lea     rcx, [rbx+38h]
0x180013ebb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013ec0  mov     rdi, [rbx+100h]
0x180013ec7  mov     qword ptr [rbx+100h], 0
0x180013ed2  test    rdi, rdi
0x180013ed5  jz      short loc_180013EF7
0x180013ed7  call    cs:__imp_GetProcessHeap
0x180013ede  nop     dword ptr [rax+rax+00h]
0x180013ee3  mov     rcx, rax; hHeap
0x180013ee6  mov     r8, rdi; lpMem
0x180013ee9  xor     edx, edx; dwFlags
0x180013eeb  call    cs:__imp_HeapFree
0x180013ef2  nop     dword ptr [rax+rax+00h]
0x180013ef7  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180013efe  test    r8, r8
0x180013f01  jz      short loc_180013F1B
0x180013f03  mov     rdx, cs:qword_1800496B8; SRWLock
0x180013f0a  test    rdx, rdx
0x180013f0d  jz      short loc_180013F1B
0x180013f0f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180013f16  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180013f1b  lea     rdi, [rbx+98h]
0x180013f22  mov     rsi, [rdi+40h]
0x180013f26  mov     qword ptr [rdi+40h], 0
0x180013f2e  test    rsi, rsi
0x180013f31  jz      short loc_180013F53
0x180013f33  call    cs:__imp_GetProcessHeap
0x180013f3a  nop     dword ptr [rax+rax+00h]
0x180013f3f  mov     rcx, rax; hHeap
0x180013f42  mov     r8, rsi; lpMem
0x180013f45  xor     edx, edx; dwFlags
0x180013f47  call    cs:__imp_HeapFree
0x180013f4e  nop     dword ptr [rax+rax+00h]
0x180013f53  mov     rcx, rdi; lpCriticalSection
0x180013f56  call    cs:__imp_DeleteCriticalSection
0x180013f5d  nop     dword ptr [rax+rax+00h]
0x180013f62  mov     rcx, [rbx+90h]; this
0x180013f69  test    rcx, rcx
0x180013f6c  jz      short loc_180013F73
0x180013f6e  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180013f73  mov     rsi, [rbx+88h]
0x180013f7a  mov     qword ptr [rbx+88h], 0
0x180013f85  test    rsi, rsi
0x180013f88  jz      short loc_180013FAA
0x180013f8a  call    cs:__imp_GetProcessHeap
0x180013f91  nop     dword ptr [rax+rax+00h]
0x180013f96  mov     rcx, rax; hHeap
0x180013f99  mov     r8, rsi; lpMem
0x180013f9c  xor     edx, edx; dwFlags
0x180013f9e  call    cs:__imp_HeapFree
0x180013fa5  nop     dword ptr [rax+rax+00h]
0x180013faa  lea     rcx, [rbx+48h]; lpCriticalSection
0x180013fae  call    cs:__imp_DeleteCriticalSection
0x180013fb5  nop     dword ptr [rax+rax+00h]
0x180013fba  mov     rdi, [rbx+38h]
0x180013fbe  mov     esi, 1
0x180013fc3  test    rdi, rdi
0x180013fc6  jz      short loc_180013FFF
0x180013fc8  xor     r9d, r9d; msWindowLength
0x180013fcb  xor     r8d, r8d; msPeriod
0x180013fce  xor     edx, edx; pftDueTime
0x180013fd0  mov     rcx, rdi; pti
0x180013fd3  call    cs:__imp_SetThreadpoolTimer
0x180013fda  nop     dword ptr [rax+rax+00h]
0x180013fdf  mov     edx, esi; fCancelPendingCallbacks
0x180013fe1  mov     rcx, rdi; pti
0x180013fe4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013feb  nop     dword ptr [rax+rax+00h]
0x180013ff0  mov     rcx, rdi; pti
0x180013ff3  call    cs:__imp_CloseThreadpoolTimer
0x180013ffa  nop     dword ptr [rax+rax+00h]
0x180013fff  mov     rdi, [rbx+30h]
0x180014003  test    rdi, rdi
0x180014006  jz      short loc_180014040
0x180014008  xor     r9d, r9d; msWindowLength
0x18001400b  xor     r8d, r8d; msPeriod
0x18001400e  xor     edx, edx; pftDueTime
0x180014010  mov     rcx, rdi; pti
0x180014013  call    cs:__imp_SetThreadpoolTimer
0x18001401a  nop     dword ptr [rax+rax+00h]
0x18001401f  mov     edx, esi; fCancelPendingCallbacks
0x180014021  mov     rcx, rdi; pti
0x180014024  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001402b  nop     dword ptr [rax+rax+00h]
0x180014030  mov     rcx, rdi; pti
0x180014033  call    cs:__imp_CloseThreadpoolTimer
0x18001403a  nop     dword ptr [rax+rax+00h]
0x18001403f  nop
0x180014040  mov     rcx, [rbx+10h]; lpMem
0x180014044  test    rcx, rcx
0x180014047  jz      short loc_18001404F
0x180014049  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18001404e  nop
0x18001404f  add     rsp, 20h
0x180014053  pop     r15
0x180014055  pop     r14
0x180014057  pop     rdi
0x180014058  pop     rsi
0x180014059  pop     rbx
0x18001405a  retn
```
