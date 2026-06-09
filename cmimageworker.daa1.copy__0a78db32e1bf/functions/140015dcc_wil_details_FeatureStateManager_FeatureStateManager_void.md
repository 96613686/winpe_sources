# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140015dcc`
- end: `0x140015f90`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002f2f0`

## callees

- `0x140015dcc`
- `0x14001d8e0`
- `0x14001ecb0`
- `0x14001ed24`
- `0x1400204b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015e8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015ee2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015e8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015ee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ebe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ed2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015f47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015f47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015f18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015f58`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015f18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015f58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015f27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015f67`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015f27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015f67`

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
  if ( v4 && qword_14003E198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14003E198[25], qword_14003E198, v4);
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
0x140015dcc  push    rbx
0x140015dce  push    rsi
0x140015dcf  push    rdi
0x140015dd0  push    r14
0x140015dd2  push    r15
0x140015dd4  sub     rsp, 20h
0x140015dd8  mov     rbx, rcx
0x140015ddb  mov     byte ptr [rcx], 0
0x140015dde  xor     edx, edx
0x140015de0  add     rcx, 30h ; '0'
0x140015de4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140015de9  xor     edx, edx
0x140015deb  lea     rcx, [rbx+38h]
0x140015def  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140015df4  mov     rdi, [rbx+100h]
0x140015dfb  mov     qword ptr [rbx+100h], 0
0x140015e06  test    rdi, rdi
0x140015e09  jz      short loc_140015E2B
0x140015e0b  call    cs:__imp_GetProcessHeap
0x140015e12  nop     dword ptr [rax+rax+00h]
0x140015e17  mov     rcx, rax; hHeap
0x140015e1a  mov     r8, rdi; lpMem
0x140015e1d  xor     edx, edx; dwFlags
0x140015e1f  call    cs:__imp_HeapFree
0x140015e26  nop     dword ptr [rax+rax+00h]
0x140015e2b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140015e32  test    r8, r8
0x140015e35  jz      short loc_140015E4F
0x140015e37  mov     rdx, cs:qword_14003E198; SRWLock
0x140015e3e  test    rdx, rdx
0x140015e41  jz      short loc_140015E4F
0x140015e43  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140015e4a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140015e4f  lea     rdi, [rbx+98h]
0x140015e56  mov     rsi, [rdi+40h]
0x140015e5a  mov     qword ptr [rdi+40h], 0
0x140015e62  test    rsi, rsi
0x140015e65  jz      short loc_140015E87
0x140015e67  call    cs:__imp_GetProcessHeap
0x140015e6e  nop     dword ptr [rax+rax+00h]
0x140015e73  mov     rcx, rax; hHeap
0x140015e76  mov     r8, rsi; lpMem
0x140015e79  xor     edx, edx; dwFlags
0x140015e7b  call    cs:__imp_HeapFree
0x140015e82  nop     dword ptr [rax+rax+00h]
0x140015e87  mov     rcx, rdi; lpCriticalSection
0x140015e8a  call    cs:__imp_DeleteCriticalSection
0x140015e91  nop     dword ptr [rax+rax+00h]
0x140015e96  mov     rcx, [rbx+90h]; this
0x140015e9d  test    rcx, rcx
0x140015ea0  jz      short loc_140015EA7
0x140015ea2  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140015ea7  mov     rsi, [rbx+88h]
0x140015eae  mov     qword ptr [rbx+88h], 0
0x140015eb9  test    rsi, rsi
0x140015ebc  jz      short loc_140015EDE
0x140015ebe  call    cs:__imp_GetProcessHeap
0x140015ec5  nop     dword ptr [rax+rax+00h]
0x140015eca  mov     rcx, rax; hHeap
0x140015ecd  mov     r8, rsi; lpMem
0x140015ed0  xor     edx, edx; dwFlags
0x140015ed2  call    cs:__imp_HeapFree
0x140015ed9  nop     dword ptr [rax+rax+00h]
0x140015ede  lea     rcx, [rbx+48h]; lpCriticalSection
0x140015ee2  call    cs:__imp_DeleteCriticalSection
0x140015ee9  nop     dword ptr [rax+rax+00h]
0x140015eee  mov     rdi, [rbx+38h]
0x140015ef2  mov     esi, 1
0x140015ef7  test    rdi, rdi
0x140015efa  jz      short loc_140015F33
0x140015efc  xor     r9d, r9d; msWindowLength
0x140015eff  xor     r8d, r8d; msPeriod
0x140015f02  xor     edx, edx; pftDueTime
0x140015f04  mov     rcx, rdi; pti
0x140015f07  call    cs:__imp_SetThreadpoolTimer
0x140015f0e  nop     dword ptr [rax+rax+00h]
0x140015f13  mov     edx, esi; fCancelPendingCallbacks
0x140015f15  mov     rcx, rdi; pti
0x140015f18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015f1f  nop     dword ptr [rax+rax+00h]
0x140015f24  mov     rcx, rdi; pti
0x140015f27  call    cs:__imp_CloseThreadpoolTimer
0x140015f2e  nop     dword ptr [rax+rax+00h]
0x140015f33  mov     rdi, [rbx+30h]
0x140015f37  test    rdi, rdi
0x140015f3a  jz      short loc_140015F74
0x140015f3c  xor     r9d, r9d; msWindowLength
0x140015f3f  xor     r8d, r8d; msPeriod
0x140015f42  xor     edx, edx; pftDueTime
0x140015f44  mov     rcx, rdi; pti
0x140015f47  call    cs:__imp_SetThreadpoolTimer
0x140015f4e  nop     dword ptr [rax+rax+00h]
0x140015f53  mov     edx, esi; fCancelPendingCallbacks
0x140015f55  mov     rcx, rdi; pti
0x140015f58  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015f5f  nop     dword ptr [rax+rax+00h]
0x140015f64  mov     rcx, rdi; pti
0x140015f67  call    cs:__imp_CloseThreadpoolTimer
0x140015f6e  nop     dword ptr [rax+rax+00h]
0x140015f73  nop
0x140015f74  mov     rcx, [rbx+10h]; lpMem
0x140015f78  test    rcx, rcx
0x140015f7b  jz      short loc_140015F83
0x140015f7d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140015f82  nop
0x140015f83  add     rsp, 20h
0x140015f87  pop     r15
0x140015f89  pop     r14
0x140015f8b  pop     rdi
0x140015f8c  pop     rsi
0x140015f8d  pop     rbx
0x140015f8e  retn
```
