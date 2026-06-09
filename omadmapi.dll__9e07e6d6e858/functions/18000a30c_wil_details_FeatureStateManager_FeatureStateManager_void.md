# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000a30c`
- end: `0x18000a4d0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180023530`

## callees

- `0x18000a30c`
- `0x1800116a4`
- `0x180013740`
- `0x1800137b4`
- `0x1800142b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a35f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a35f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a34b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a34b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a422`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a422`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a458`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a498`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a458`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a498`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a447`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a487`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a447`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a487`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a467`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a4a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a467`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a4a7`

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
  if ( v4 && qword_180032248 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180032248[25], qword_180032248, v4);
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
0x18000a30c  push    rbx
0x18000a30e  push    rsi
0x18000a30f  push    rdi
0x18000a310  push    r14
0x18000a312  push    r15
0x18000a314  sub     rsp, 20h
0x18000a318  mov     rbx, rcx
0x18000a31b  mov     byte ptr [rcx], 0
0x18000a31e  xor     edx, edx
0x18000a320  add     rcx, 30h ; '0'
0x18000a324  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a329  xor     edx, edx
0x18000a32b  lea     rcx, [rbx+38h]
0x18000a32f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a334  mov     rdi, [rbx+100h]
0x18000a33b  mov     qword ptr [rbx+100h], 0
0x18000a346  test    rdi, rdi
0x18000a349  jz      short loc_18000A36B
0x18000a34b  call    cs:__imp_GetProcessHeap
0x18000a352  nop     dword ptr [rax+rax+00h]
0x18000a357  mov     rcx, rax; hHeap
0x18000a35a  mov     r8, rdi; lpMem
0x18000a35d  xor     edx, edx; dwFlags
0x18000a35f  call    cs:__imp_HeapFree
0x18000a366  nop     dword ptr [rax+rax+00h]
0x18000a36b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000a372  test    r8, r8
0x18000a375  jz      short loc_18000A38F
0x18000a377  mov     rdx, cs:qword_180032248; SRWLock
0x18000a37e  test    rdx, rdx
0x18000a381  jz      short loc_18000A38F
0x18000a383  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a38a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000a38f  lea     rdi, [rbx+98h]
0x18000a396  mov     rsi, [rdi+40h]
0x18000a39a  mov     qword ptr [rdi+40h], 0
0x18000a3a2  test    rsi, rsi
0x18000a3a5  jz      short loc_18000A3C7
0x18000a3a7  call    cs:__imp_GetProcessHeap
0x18000a3ae  nop     dword ptr [rax+rax+00h]
0x18000a3b3  mov     rcx, rax; hHeap
0x18000a3b6  mov     r8, rsi; lpMem
0x18000a3b9  xor     edx, edx; dwFlags
0x18000a3bb  call    cs:__imp_HeapFree
0x18000a3c2  nop     dword ptr [rax+rax+00h]
0x18000a3c7  mov     rcx, rdi; lpCriticalSection
0x18000a3ca  call    cs:__imp_DeleteCriticalSection
0x18000a3d1  nop     dword ptr [rax+rax+00h]
0x18000a3d6  mov     rcx, [rbx+90h]; this
0x18000a3dd  test    rcx, rcx
0x18000a3e0  jz      short loc_18000A3E7
0x18000a3e2  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000a3e7  mov     rsi, [rbx+88h]
0x18000a3ee  mov     qword ptr [rbx+88h], 0
0x18000a3f9  test    rsi, rsi
0x18000a3fc  jz      short loc_18000A41E
0x18000a3fe  call    cs:__imp_GetProcessHeap
0x18000a405  nop     dword ptr [rax+rax+00h]
0x18000a40a  mov     rcx, rax; hHeap
0x18000a40d  mov     r8, rsi; lpMem
0x18000a410  xor     edx, edx; dwFlags
0x18000a412  call    cs:__imp_HeapFree
0x18000a419  nop     dword ptr [rax+rax+00h]
0x18000a41e  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000a422  call    cs:__imp_DeleteCriticalSection
0x18000a429  nop     dword ptr [rax+rax+00h]
0x18000a42e  mov     rdi, [rbx+38h]
0x18000a432  mov     esi, 1
0x18000a437  test    rdi, rdi
0x18000a43a  jz      short loc_18000A473
0x18000a43c  xor     r9d, r9d; msWindowLength
0x18000a43f  xor     r8d, r8d; msPeriod
0x18000a442  xor     edx, edx; pftDueTime
0x18000a444  mov     rcx, rdi; pti
0x18000a447  call    cs:__imp_SetThreadpoolTimer
0x18000a44e  nop     dword ptr [rax+rax+00h]
0x18000a453  mov     edx, esi; fCancelPendingCallbacks
0x18000a455  mov     rcx, rdi; pti
0x18000a458  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a45f  nop     dword ptr [rax+rax+00h]
0x18000a464  mov     rcx, rdi; pti
0x18000a467  call    cs:__imp_CloseThreadpoolTimer
0x18000a46e  nop     dword ptr [rax+rax+00h]
0x18000a473  mov     rdi, [rbx+30h]
0x18000a477  test    rdi, rdi
0x18000a47a  jz      short loc_18000A4B4
0x18000a47c  xor     r9d, r9d; msWindowLength
0x18000a47f  xor     r8d, r8d; msPeriod
0x18000a482  xor     edx, edx; pftDueTime
0x18000a484  mov     rcx, rdi; pti
0x18000a487  call    cs:__imp_SetThreadpoolTimer
0x18000a48e  nop     dword ptr [rax+rax+00h]
0x18000a493  mov     edx, esi; fCancelPendingCallbacks
0x18000a495  mov     rcx, rdi; pti
0x18000a498  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a49f  nop     dword ptr [rax+rax+00h]
0x18000a4a4  mov     rcx, rdi; pti
0x18000a4a7  call    cs:__imp_CloseThreadpoolTimer
0x18000a4ae  nop     dword ptr [rax+rax+00h]
0x18000a4b3  nop
0x18000a4b4  mov     rcx, [rbx+10h]; lpMem
0x18000a4b8  test    rcx, rcx
0x18000a4bb  jz      short loc_18000A4C3
0x18000a4bd  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000a4c2  nop
0x18000a4c3  add     rsp, 20h
0x18000a4c7  pop     r15
0x18000a4c9  pop     r14
0x18000a4cb  pop     rdi
0x18000a4cc  pop     rsi
0x18000a4cd  pop     rbx
0x18000a4ce  retn
```
