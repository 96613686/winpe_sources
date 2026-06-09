# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180015a90`
- end: `0x180015c67`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `471`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800c7630`

## callees

- `0x180015a90`
- `0x18001dda8`
- `0x18001f9d4`
- `0x18001fa48`
- `0x180021468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015baa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015baa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015aed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015aed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015be0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015c20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015be0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015c20`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015bcf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015c0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015bcf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015c0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015bef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015c2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015bef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015c2f`

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
  if ( v4 && qword_180106108 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180106108[25], qword_180106108, v4);
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
0x180015a90  mov     rax, rsp
0x180015a93  mov     [rax+8], rbx
0x180015a97  mov     [rax+10h], rsi
0x180015a9b  mov     [rax+18h], rdi
0x180015a9f  mov     [rax+20h], r14
0x180015aa3  push    r15
0x180015aa5  sub     rsp, 20h
0x180015aa9  mov     rbx, rcx
0x180015aac  mov     byte ptr [rcx], 0
0x180015aaf  xor     edx, edx
0x180015ab1  add     rcx, 30h ; '0'
0x180015ab5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180015aba  xor     edx, edx
0x180015abc  lea     rcx, [rbx+38h]
0x180015ac0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180015ac5  mov     rdi, [rbx+100h]
0x180015acc  and     qword ptr [rbx+100h], 0
0x180015ad4  test    rdi, rdi
0x180015ad7  jz      short loc_180015AF9
0x180015ad9  call    cs:__imp_GetProcessHeap
0x180015ae0  nop     dword ptr [rax+rax+00h]
0x180015ae5  mov     rcx, rax; hHeap
0x180015ae8  mov     r8, rdi; lpMem
0x180015aeb  xor     edx, edx; dwFlags
0x180015aed  call    cs:__imp_HeapFree
0x180015af4  nop     dword ptr [rax+rax+00h]
0x180015af9  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180015b00  test    r8, r8
0x180015b03  jz      short loc_180015B1D
0x180015b05  mov     rdx, cs:qword_180106108; SRWLock
0x180015b0c  test    rdx, rdx
0x180015b0f  jz      short loc_180015B1D
0x180015b11  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180015b18  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180015b1d  lea     rdi, [rbx+98h]
0x180015b24  mov     rsi, [rdi+40h]
0x180015b28  and     qword ptr [rdi+40h], 0
0x180015b2d  test    rsi, rsi
0x180015b30  jz      short loc_180015B52
0x180015b32  call    cs:__imp_GetProcessHeap
0x180015b39  nop     dword ptr [rax+rax+00h]
0x180015b3e  mov     rcx, rax; hHeap
0x180015b41  mov     r8, rsi; lpMem
0x180015b44  xor     edx, edx; dwFlags
0x180015b46  call    cs:__imp_HeapFree
0x180015b4d  nop     dword ptr [rax+rax+00h]
0x180015b52  mov     rcx, rdi; lpCriticalSection
0x180015b55  call    cs:__imp_DeleteCriticalSection
0x180015b5c  nop     dword ptr [rax+rax+00h]
0x180015b61  mov     rcx, [rbx+90h]; this
0x180015b68  test    rcx, rcx
0x180015b6b  jz      short loc_180015B72
0x180015b6d  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180015b72  mov     rsi, [rbx+88h]
0x180015b79  and     qword ptr [rbx+88h], 0
0x180015b81  test    rsi, rsi
0x180015b84  jz      short loc_180015BA6
0x180015b86  call    cs:__imp_GetProcessHeap
0x180015b8d  nop     dword ptr [rax+rax+00h]
0x180015b92  mov     rcx, rax; hHeap
0x180015b95  mov     r8, rsi; lpMem
0x180015b98  xor     edx, edx; dwFlags
0x180015b9a  call    cs:__imp_HeapFree
0x180015ba1  nop     dword ptr [rax+rax+00h]
0x180015ba6  lea     rcx, [rbx+48h]; lpCriticalSection
0x180015baa  call    cs:__imp_DeleteCriticalSection
0x180015bb1  nop     dword ptr [rax+rax+00h]
0x180015bb6  mov     rdi, [rbx+38h]
0x180015bba  mov     esi, 1
0x180015bbf  test    rdi, rdi
0x180015bc2  jz      short loc_180015BFB
0x180015bc4  xor     r9d, r9d; msWindowLength
0x180015bc7  xor     r8d, r8d; msPeriod
0x180015bca  xor     edx, edx; pftDueTime
0x180015bcc  mov     rcx, rdi; pti
0x180015bcf  call    cs:__imp_SetThreadpoolTimer
0x180015bd6  nop     dword ptr [rax+rax+00h]
0x180015bdb  mov     edx, esi; fCancelPendingCallbacks
0x180015bdd  mov     rcx, rdi; pti
0x180015be0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015be7  nop     dword ptr [rax+rax+00h]
0x180015bec  mov     rcx, rdi; pti
0x180015bef  call    cs:__imp_CloseThreadpoolTimer
0x180015bf6  nop     dword ptr [rax+rax+00h]
0x180015bfb  mov     rdi, [rbx+30h]
0x180015bff  test    rdi, rdi
0x180015c02  jz      short loc_180015C3C
0x180015c04  xor     r9d, r9d; msWindowLength
0x180015c07  xor     r8d, r8d; msPeriod
0x180015c0a  xor     edx, edx; pftDueTime
0x180015c0c  mov     rcx, rdi; pti
0x180015c0f  call    cs:__imp_SetThreadpoolTimer
0x180015c16  nop     dword ptr [rax+rax+00h]
0x180015c1b  mov     edx, esi; fCancelPendingCallbacks
0x180015c1d  mov     rcx, rdi; pti
0x180015c20  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015c27  nop     dword ptr [rax+rax+00h]
0x180015c2c  mov     rcx, rdi; pti
0x180015c2f  call    cs:__imp_CloseThreadpoolTimer
0x180015c36  nop     dword ptr [rax+rax+00h]
0x180015c3b  nop
0x180015c3c  mov     rcx, [rbx+10h]; lpMem
0x180015c40  test    rcx, rcx
0x180015c43  jz      short loc_180015C4B
0x180015c45  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180015c4a  nop
0x180015c4b  mov     rbx, [rsp+28h+arg_0]
0x180015c50  mov     rsi, [rsp+28h+arg_8]
0x180015c55  mov     rdi, [rsp+28h+arg_10]
0x180015c5a  mov     r14, [rsp+28h+arg_18]
0x180015c5f  add     rsp, 20h
0x180015c63  pop     r15
0x180015c65  retn
```
