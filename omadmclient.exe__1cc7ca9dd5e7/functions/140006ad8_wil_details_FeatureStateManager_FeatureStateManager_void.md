# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140006ad8`
- end: `0x140006c9c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140068260`

## callees

- `0x140006ad8`
- `0x14000ad1c`
- `0x14000c794`
- `0x14000c808`
- `0x14000d1a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006b96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006bee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006b96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006bee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006b73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006b73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006bde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006bde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c64`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006c33`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006c73`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006c33`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006c73`

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
  if ( v4 && qword_1400842B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400842B8[25], qword_1400842B8, v4);
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
0x140006ad8  push    rbx
0x140006ada  push    rsi
0x140006adb  push    rdi
0x140006adc  push    r14
0x140006ade  push    r15
0x140006ae0  sub     rsp, 20h
0x140006ae4  mov     rbx, rcx
0x140006ae7  mov     byte ptr [rcx], 0
0x140006aea  xor     edx, edx
0x140006aec  add     rcx, 30h ; '0'
0x140006af0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006af5  xor     edx, edx
0x140006af7  lea     rcx, [rbx+38h]
0x140006afb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006b00  mov     rdi, [rbx+100h]
0x140006b07  mov     qword ptr [rbx+100h], 0
0x140006b12  test    rdi, rdi
0x140006b15  jz      short loc_140006B37
0x140006b17  call    cs:__imp_GetProcessHeap
0x140006b1e  nop     dword ptr [rax+rax+00h]
0x140006b23  mov     rcx, rax; hHeap
0x140006b26  mov     r8, rdi; lpMem
0x140006b29  xor     edx, edx; dwFlags
0x140006b2b  call    cs:__imp_HeapFree
0x140006b32  nop     dword ptr [rax+rax+00h]
0x140006b37  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140006b3e  test    r8, r8
0x140006b41  jz      short loc_140006B5B
0x140006b43  mov     rdx, cs:qword_1400842B8; SRWLock
0x140006b4a  test    rdx, rdx
0x140006b4d  jz      short loc_140006B5B
0x140006b4f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140006b56  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140006b5b  lea     rdi, [rbx+98h]
0x140006b62  mov     rsi, [rdi+40h]
0x140006b66  mov     qword ptr [rdi+40h], 0
0x140006b6e  test    rsi, rsi
0x140006b71  jz      short loc_140006B93
0x140006b73  call    cs:__imp_GetProcessHeap
0x140006b7a  nop     dword ptr [rax+rax+00h]
0x140006b7f  mov     rcx, rax; hHeap
0x140006b82  mov     r8, rsi; lpMem
0x140006b85  xor     edx, edx; dwFlags
0x140006b87  call    cs:__imp_HeapFree
0x140006b8e  nop     dword ptr [rax+rax+00h]
0x140006b93  mov     rcx, rdi; lpCriticalSection
0x140006b96  call    cs:__imp_DeleteCriticalSection
0x140006b9d  nop     dword ptr [rax+rax+00h]
0x140006ba2  mov     rcx, [rbx+90h]; this
0x140006ba9  test    rcx, rcx
0x140006bac  jz      short loc_140006BB3
0x140006bae  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140006bb3  mov     rsi, [rbx+88h]
0x140006bba  mov     qword ptr [rbx+88h], 0
0x140006bc5  test    rsi, rsi
0x140006bc8  jz      short loc_140006BEA
0x140006bca  call    cs:__imp_GetProcessHeap
0x140006bd1  nop     dword ptr [rax+rax+00h]
0x140006bd6  mov     rcx, rax; hHeap
0x140006bd9  mov     r8, rsi; lpMem
0x140006bdc  xor     edx, edx; dwFlags
0x140006bde  call    cs:__imp_HeapFree
0x140006be5  nop     dword ptr [rax+rax+00h]
0x140006bea  lea     rcx, [rbx+48h]; lpCriticalSection
0x140006bee  call    cs:__imp_DeleteCriticalSection
0x140006bf5  nop     dword ptr [rax+rax+00h]
0x140006bfa  mov     rdi, [rbx+38h]
0x140006bfe  mov     esi, 1
0x140006c03  test    rdi, rdi
0x140006c06  jz      short loc_140006C3F
0x140006c08  xor     r9d, r9d; msWindowLength
0x140006c0b  xor     r8d, r8d; msPeriod
0x140006c0e  xor     edx, edx; pftDueTime
0x140006c10  mov     rcx, rdi; pti
0x140006c13  call    cs:__imp_SetThreadpoolTimer
0x140006c1a  nop     dword ptr [rax+rax+00h]
0x140006c1f  mov     edx, esi; fCancelPendingCallbacks
0x140006c21  mov     rcx, rdi; pti
0x140006c24  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006c2b  nop     dword ptr [rax+rax+00h]
0x140006c30  mov     rcx, rdi; pti
0x140006c33  call    cs:__imp_CloseThreadpoolTimer
0x140006c3a  nop     dword ptr [rax+rax+00h]
0x140006c3f  mov     rdi, [rbx+30h]
0x140006c43  test    rdi, rdi
0x140006c46  jz      short loc_140006C80
0x140006c48  xor     r9d, r9d; msWindowLength
0x140006c4b  xor     r8d, r8d; msPeriod
0x140006c4e  xor     edx, edx; pftDueTime
0x140006c50  mov     rcx, rdi; pti
0x140006c53  call    cs:__imp_SetThreadpoolTimer
0x140006c5a  nop     dword ptr [rax+rax+00h]
0x140006c5f  mov     edx, esi; fCancelPendingCallbacks
0x140006c61  mov     rcx, rdi; pti
0x140006c64  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006c6b  nop     dword ptr [rax+rax+00h]
0x140006c70  mov     rcx, rdi; pti
0x140006c73  call    cs:__imp_CloseThreadpoolTimer
0x140006c7a  nop     dword ptr [rax+rax+00h]
0x140006c7f  nop
0x140006c80  mov     rcx, [rbx+10h]; lpMem
0x140006c84  test    rcx, rcx
0x140006c87  jz      short loc_140006C8F
0x140006c89  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140006c8e  nop
0x140006c8f  add     rsp, 20h
0x140006c93  pop     r15
0x140006c95  pop     r14
0x140006c97  pop     rdi
0x140006c98  pop     rsi
0x140006c99  pop     rbx
0x140006c9a  retn
```
