# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001c224`
- end: `0x18001c3f9`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800314f0`

## callees

- `0x18001c224`
- `0x1800249c4`
- `0x180025d6c`
- `0x180025de0`
- `0x1800265e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c2e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c33e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c2e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c33e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c363`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c3a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c363`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c383`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c3c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c383`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c3c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c374`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c3b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c374`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c3b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c26d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c2c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c31a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c26d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c2c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c31a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c281`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c2da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c32e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c281`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c2da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c32e`

## pseudocode

```c
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
  if ( v4 && qword_18003A068 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003A068[25], qword_18003A068, v4);
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
0x18001c224  mov     rax, rsp
0x18001c227  mov     [rax+8], rbx
0x18001c22b  mov     [rax+10h], rsi
0x18001c22f  mov     [rax+18h], rdi
0x18001c233  mov     [rax+20h], r14
0x18001c237  push    r15
0x18001c239  sub     rsp, 20h
0x18001c23d  mov     rbx, rcx
0x18001c240  mov     byte ptr [rcx], 0
0x18001c243  add     rcx, 30h ; '0'
0x18001c247  xor     edx, edx
0x18001c249  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c24e  xor     edx, edx
0x18001c250  lea     rcx, [rbx+38h]
0x18001c254  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c259  mov     rdi, [rbx+100h]
0x18001c260  and     qword ptr [rbx+100h], 0
0x18001c268  test    rdi, rdi
0x18001c26b  jz      short loc_18001C28D
0x18001c26d  call    cs:__imp_GetProcessHeap
0x18001c274  nop     dword ptr [rax+rax+00h]
0x18001c279  mov     r8, rdi; lpMem
0x18001c27c  xor     edx, edx; dwFlags
0x18001c27e  mov     rcx, rax; hHeap
0x18001c281  call    cs:__imp_HeapFree
0x18001c288  nop     dword ptr [rax+rax+00h]
0x18001c28d  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18001c294  test    r8, r8
0x18001c297  jz      short loc_18001C2B1
0x18001c299  mov     rdx, cs:qword_18003A068; SRWLock
0x18001c2a0  test    rdx, rdx
0x18001c2a3  jz      short loc_18001C2B1
0x18001c2a5  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001c2ac  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001c2b1  lea     rdi, [rbx+98h]
0x18001c2b8  mov     rsi, [rdi+40h]
0x18001c2bc  and     qword ptr [rdi+40h], 0
0x18001c2c1  test    rsi, rsi
0x18001c2c4  jz      short loc_18001C2E6
0x18001c2c6  call    cs:__imp_GetProcessHeap
0x18001c2cd  nop     dword ptr [rax+rax+00h]
0x18001c2d2  mov     r8, rsi; lpMem
0x18001c2d5  xor     edx, edx; dwFlags
0x18001c2d7  mov     rcx, rax; hHeap
0x18001c2da  call    cs:__imp_HeapFree
0x18001c2e1  nop     dword ptr [rax+rax+00h]
0x18001c2e6  mov     rcx, rdi; lpCriticalSection
0x18001c2e9  call    cs:__imp_DeleteCriticalSection
0x18001c2f0  nop     dword ptr [rax+rax+00h]
0x18001c2f5  mov     rcx, [rbx+90h]; this
0x18001c2fc  test    rcx, rcx
0x18001c2ff  jz      short loc_18001C306
0x18001c301  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18001c306  mov     rsi, [rbx+88h]
0x18001c30d  and     qword ptr [rbx+88h], 0
0x18001c315  test    rsi, rsi
0x18001c318  jz      short loc_18001C33A
0x18001c31a  call    cs:__imp_GetProcessHeap
0x18001c321  nop     dword ptr [rax+rax+00h]
0x18001c326  mov     r8, rsi; lpMem
0x18001c329  xor     edx, edx; dwFlags
0x18001c32b  mov     rcx, rax; hHeap
0x18001c32e  call    cs:__imp_HeapFree
0x18001c335  nop     dword ptr [rax+rax+00h]
0x18001c33a  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001c33e  call    cs:__imp_DeleteCriticalSection
0x18001c345  nop     dword ptr [rax+rax+00h]
0x18001c34a  mov     rdi, [rbx+38h]
0x18001c34e  mov     esi, 1
0x18001c353  test    rdi, rdi
0x18001c356  jz      short loc_18001C38F
0x18001c358  xor     r9d, r9d; msWindowLength
0x18001c35b  xor     r8d, r8d; msPeriod
0x18001c35e  xor     edx, edx; pftDueTime
0x18001c360  mov     rcx, rdi; pti
0x18001c363  call    cs:__imp_SetThreadpoolTimer
0x18001c36a  nop     dword ptr [rax+rax+00h]
0x18001c36f  mov     edx, esi; fCancelPendingCallbacks
0x18001c371  mov     rcx, rdi; pti
0x18001c374  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c37b  nop     dword ptr [rax+rax+00h]
0x18001c380  mov     rcx, rdi; pti
0x18001c383  call    cs:__imp_CloseThreadpoolTimer
0x18001c38a  nop     dword ptr [rax+rax+00h]
0x18001c38f  mov     rdi, [rbx+30h]
0x18001c393  test    rdi, rdi
0x18001c396  jz      short loc_18001C3CF
0x18001c398  xor     r9d, r9d; msWindowLength
0x18001c39b  xor     r8d, r8d; msPeriod
0x18001c39e  xor     edx, edx; pftDueTime
0x18001c3a0  mov     rcx, rdi; pti
0x18001c3a3  call    cs:__imp_SetThreadpoolTimer
0x18001c3aa  nop     dword ptr [rax+rax+00h]
0x18001c3af  mov     edx, esi; fCancelPendingCallbacks
0x18001c3b1  mov     rcx, rdi; pti
0x18001c3b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c3bb  nop     dword ptr [rax+rax+00h]
0x18001c3c0  mov     rcx, rdi; pti
0x18001c3c3  call    cs:__imp_CloseThreadpoolTimer
0x18001c3ca  nop     dword ptr [rax+rax+00h]
0x18001c3cf  mov     rcx, [rbx+10h]; lpMem
0x18001c3d3  test    rcx, rcx
0x18001c3d6  jz      short loc_18001C3DD
0x18001c3d8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18001c3dd  mov     rbx, [rsp+28h+arg_0]
0x18001c3e2  mov     rsi, [rsp+28h+arg_8]
0x18001c3e7  mov     rdi, [rsp+28h+arg_10]
0x18001c3ec  mov     r14, [rsp+28h+arg_18]
0x18001c3f1  add     rsp, 20h
0x18001c3f5  pop     r15
0x18001c3f7  retn
```
