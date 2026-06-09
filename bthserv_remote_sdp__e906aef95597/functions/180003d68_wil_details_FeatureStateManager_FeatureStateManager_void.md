# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003d68`
- end: `0x180003f3f`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `471`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180035b50`

## callees

- `0x180003d68`
- `0x180007c50`
- `0x180009314`
- `0x180009388`
- `0x180009c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ec7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ec7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f07`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ef8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ef8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ea7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ee7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ea7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ee7`

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
  if ( v4 && qword_180046070 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180046070[25], qword_180046070, v4);
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
0x180003d68  mov     rax, rsp
0x180003d6b  mov     [rax+8], rbx
0x180003d6f  mov     [rax+10h], rsi
0x180003d73  mov     [rax+18h], rdi
0x180003d77  mov     [rax+20h], r14
0x180003d7b  push    r15
0x180003d7d  sub     rsp, 20h
0x180003d81  mov     rbx, rcx
0x180003d84  mov     byte ptr [rcx], 0
0x180003d87  xor     edx, edx
0x180003d89  add     rcx, 30h ; '0'
0x180003d8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003d92  xor     edx, edx
0x180003d94  lea     rcx, [rbx+38h]
0x180003d98  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003d9d  mov     rdi, [rbx+100h]
0x180003da4  and     qword ptr [rbx+100h], 0
0x180003dac  test    rdi, rdi
0x180003daf  jz      short loc_180003DD1
0x180003db1  call    cs:__imp_GetProcessHeap
0x180003db8  nop     dword ptr [rax+rax+00h]
0x180003dbd  mov     rcx, rax; hHeap
0x180003dc0  mov     r8, rdi; lpMem
0x180003dc3  xor     edx, edx; dwFlags
0x180003dc5  call    cs:__imp_HeapFree
0x180003dcc  nop     dword ptr [rax+rax+00h]
0x180003dd1  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003dd8  test    r8, r8
0x180003ddb  jz      short loc_180003DF5
0x180003ddd  mov     rdx, cs:qword_180046070; SRWLock
0x180003de4  test    rdx, rdx
0x180003de7  jz      short loc_180003DF5
0x180003de9  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003df0  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003df5  lea     rdi, [rbx+98h]
0x180003dfc  mov     rsi, [rdi+40h]
0x180003e00  and     qword ptr [rdi+40h], 0
0x180003e05  test    rsi, rsi
0x180003e08  jz      short loc_180003E2A
0x180003e0a  call    cs:__imp_GetProcessHeap
0x180003e11  nop     dword ptr [rax+rax+00h]
0x180003e16  mov     rcx, rax; hHeap
0x180003e19  mov     r8, rsi; lpMem
0x180003e1c  xor     edx, edx; dwFlags
0x180003e1e  call    cs:__imp_HeapFree
0x180003e25  nop     dword ptr [rax+rax+00h]
0x180003e2a  mov     rcx, rdi; lpCriticalSection
0x180003e2d  call    cs:__imp_DeleteCriticalSection
0x180003e34  nop     dword ptr [rax+rax+00h]
0x180003e39  mov     rcx, [rbx+90h]; this
0x180003e40  test    rcx, rcx
0x180003e43  jz      short loc_180003E4A
0x180003e45  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180003e4a  mov     rsi, [rbx+88h]
0x180003e51  and     qword ptr [rbx+88h], 0
0x180003e59  test    rsi, rsi
0x180003e5c  jz      short loc_180003E7E
0x180003e5e  call    cs:__imp_GetProcessHeap
0x180003e65  nop     dword ptr [rax+rax+00h]
0x180003e6a  mov     rcx, rax; hHeap
0x180003e6d  mov     r8, rsi; lpMem
0x180003e70  xor     edx, edx; dwFlags
0x180003e72  call    cs:__imp_HeapFree
0x180003e79  nop     dword ptr [rax+rax+00h]
0x180003e7e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180003e82  call    cs:__imp_DeleteCriticalSection
0x180003e89  nop     dword ptr [rax+rax+00h]
0x180003e8e  mov     rdi, [rbx+38h]
0x180003e92  mov     esi, 1
0x180003e97  test    rdi, rdi
0x180003e9a  jz      short loc_180003ED3
0x180003e9c  xor     r9d, r9d; msWindowLength
0x180003e9f  xor     r8d, r8d; msPeriod
0x180003ea2  xor     edx, edx; pftDueTime
0x180003ea4  mov     rcx, rdi; pti
0x180003ea7  call    cs:__imp_SetThreadpoolTimer
0x180003eae  nop     dword ptr [rax+rax+00h]
0x180003eb3  mov     edx, esi; fCancelPendingCallbacks
0x180003eb5  mov     rcx, rdi; pti
0x180003eb8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003ebf  nop     dword ptr [rax+rax+00h]
0x180003ec4  mov     rcx, rdi; pti
0x180003ec7  call    cs:__imp_CloseThreadpoolTimer
0x180003ece  nop     dword ptr [rax+rax+00h]
0x180003ed3  mov     rdi, [rbx+30h]
0x180003ed7  test    rdi, rdi
0x180003eda  jz      short loc_180003F14
0x180003edc  xor     r9d, r9d; msWindowLength
0x180003edf  xor     r8d, r8d; msPeriod
0x180003ee2  xor     edx, edx; pftDueTime
0x180003ee4  mov     rcx, rdi; pti
0x180003ee7  call    cs:__imp_SetThreadpoolTimer
0x180003eee  nop     dword ptr [rax+rax+00h]
0x180003ef3  mov     edx, esi; fCancelPendingCallbacks
0x180003ef5  mov     rcx, rdi; pti
0x180003ef8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003eff  nop     dword ptr [rax+rax+00h]
0x180003f04  mov     rcx, rdi; pti
0x180003f07  call    cs:__imp_CloseThreadpoolTimer
0x180003f0e  nop     dword ptr [rax+rax+00h]
0x180003f13  nop
0x180003f14  mov     rcx, [rbx+10h]; lpMem
0x180003f18  test    rcx, rcx
0x180003f1b  jz      short loc_180003F23
0x180003f1d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003f22  nop
0x180003f23  mov     rbx, [rsp+28h+arg_0]
0x180003f28  mov     rsi, [rsp+28h+arg_8]
0x180003f2d  mov     rdi, [rsp+28h+arg_10]
0x180003f32  mov     r14, [rsp+28h+arg_18]
0x180003f37  add     rsp, 20h
0x180003f3b  pop     r15
0x180003f3d  retn
```
