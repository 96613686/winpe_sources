# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000693c`
- end: `0x180006b00`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004d0e0`

## callees

- `0x18000693c`
- `0x18000acbc`
- `0x18000c5dc`
- `0x18000c650`
- `0x18000cfb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000698f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000698f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000697b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000697b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a2e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006a97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006ad7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006a97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006ad7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006a77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ab7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006a77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ab7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006a88`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ac8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006a88`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ac8`

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
  if ( v4 && qword_1800703F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800703F8[25], qword_1800703F8, v4);
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
0x18000693c  push    rbx
0x18000693e  push    rsi
0x18000693f  push    rdi
0x180006940  push    r14
0x180006942  push    r15
0x180006944  sub     rsp, 20h
0x180006948  mov     rbx, rcx
0x18000694b  mov     byte ptr [rcx], 0
0x18000694e  xor     edx, edx
0x180006950  add     rcx, 30h ; '0'
0x180006954  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006959  xor     edx, edx
0x18000695b  lea     rcx, [rbx+38h]
0x18000695f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006964  mov     rdi, [rbx+100h]
0x18000696b  mov     qword ptr [rbx+100h], 0
0x180006976  test    rdi, rdi
0x180006979  jz      short loc_18000699B
0x18000697b  call    cs:__imp_GetProcessHeap
0x180006982  nop     dword ptr [rax+rax+00h]
0x180006987  mov     rcx, rax; hHeap
0x18000698a  mov     r8, rdi; lpMem
0x18000698d  xor     edx, edx; dwFlags
0x18000698f  call    cs:__imp_HeapFree
0x180006996  nop     dword ptr [rax+rax+00h]
0x18000699b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800069a2  test    r8, r8
0x1800069a5  jz      short loc_1800069BF
0x1800069a7  mov     rdx, cs:qword_1800703F8; SRWLock
0x1800069ae  test    rdx, rdx
0x1800069b1  jz      short loc_1800069BF
0x1800069b3  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800069ba  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800069bf  lea     rdi, [rbx+98h]
0x1800069c6  mov     rsi, [rdi+40h]
0x1800069ca  mov     qword ptr [rdi+40h], 0
0x1800069d2  test    rsi, rsi
0x1800069d5  jz      short loc_1800069F7
0x1800069d7  call    cs:__imp_GetProcessHeap
0x1800069de  nop     dword ptr [rax+rax+00h]
0x1800069e3  mov     rcx, rax; hHeap
0x1800069e6  mov     r8, rsi; lpMem
0x1800069e9  xor     edx, edx; dwFlags
0x1800069eb  call    cs:__imp_HeapFree
0x1800069f2  nop     dword ptr [rax+rax+00h]
0x1800069f7  mov     rcx, rdi; lpCriticalSection
0x1800069fa  call    cs:__imp_DeleteCriticalSection
0x180006a01  nop     dword ptr [rax+rax+00h]
0x180006a06  mov     rcx, [rbx+90h]; this
0x180006a0d  test    rcx, rcx
0x180006a10  jz      short loc_180006A17
0x180006a12  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180006a17  mov     rsi, [rbx+88h]
0x180006a1e  mov     qword ptr [rbx+88h], 0
0x180006a29  test    rsi, rsi
0x180006a2c  jz      short loc_180006A4E
0x180006a2e  call    cs:__imp_GetProcessHeap
0x180006a35  nop     dword ptr [rax+rax+00h]
0x180006a3a  mov     rcx, rax; hHeap
0x180006a3d  mov     r8, rsi; lpMem
0x180006a40  xor     edx, edx; dwFlags
0x180006a42  call    cs:__imp_HeapFree
0x180006a49  nop     dword ptr [rax+rax+00h]
0x180006a4e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180006a52  call    cs:__imp_DeleteCriticalSection
0x180006a59  nop     dword ptr [rax+rax+00h]
0x180006a5e  mov     rdi, [rbx+38h]
0x180006a62  mov     esi, 1
0x180006a67  test    rdi, rdi
0x180006a6a  jz      short loc_180006AA3
0x180006a6c  xor     r9d, r9d; msWindowLength
0x180006a6f  xor     r8d, r8d; msPeriod
0x180006a72  xor     edx, edx; pftDueTime
0x180006a74  mov     rcx, rdi; pti
0x180006a77  call    cs:__imp_SetThreadpoolTimer
0x180006a7e  nop     dword ptr [rax+rax+00h]
0x180006a83  mov     edx, esi; fCancelPendingCallbacks
0x180006a85  mov     rcx, rdi; pti
0x180006a88  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006a8f  nop     dword ptr [rax+rax+00h]
0x180006a94  mov     rcx, rdi; pti
0x180006a97  call    cs:__imp_CloseThreadpoolTimer
0x180006a9e  nop     dword ptr [rax+rax+00h]
0x180006aa3  mov     rdi, [rbx+30h]
0x180006aa7  test    rdi, rdi
0x180006aaa  jz      short loc_180006AE4
0x180006aac  xor     r9d, r9d; msWindowLength
0x180006aaf  xor     r8d, r8d; msPeriod
0x180006ab2  xor     edx, edx; pftDueTime
0x180006ab4  mov     rcx, rdi; pti
0x180006ab7  call    cs:__imp_SetThreadpoolTimer
0x180006abe  nop     dword ptr [rax+rax+00h]
0x180006ac3  mov     edx, esi; fCancelPendingCallbacks
0x180006ac5  mov     rcx, rdi; pti
0x180006ac8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006acf  nop     dword ptr [rax+rax+00h]
0x180006ad4  mov     rcx, rdi; pti
0x180006ad7  call    cs:__imp_CloseThreadpoolTimer
0x180006ade  nop     dword ptr [rax+rax+00h]
0x180006ae3  nop
0x180006ae4  mov     rcx, [rbx+10h]; lpMem
0x180006ae8  test    rcx, rcx
0x180006aeb  jz      short loc_180006AF3
0x180006aed  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180006af2  nop
0x180006af3  add     rsp, 20h
0x180006af7  pop     r15
0x180006af9  pop     r14
0x180006afb  pop     rdi
0x180006afc  pop     rsi
0x180006afd  pop     rbx
0x180006afe  retn
```
