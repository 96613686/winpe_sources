# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140015c3c`
- end: `0x140015e00`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140019d60`

## callees

- `0x140015c3c`
- `0x140017c4c`
- `0x140018310`
- `0x140018384`
- `0x140018a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015cfa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015d52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015cfa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015cd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015cd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ceb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ceb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d42`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015d88`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015dc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015d88`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015dc8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015d77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015db7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015d77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015db7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015d97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015dd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015d97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015dd7`

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
0x140015c3c  push    rbx
0x140015c3e  push    rsi
0x140015c3f  push    rdi
0x140015c40  push    r14
0x140015c42  push    r15
0x140015c44  sub     rsp, 20h
0x140015c48  mov     rbx, rcx
0x140015c4b  mov     byte ptr [rcx], 0
0x140015c4e  xor     edx, edx
0x140015c50  add     rcx, 30h ; '0'
0x140015c54  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140015c59  xor     edx, edx
0x140015c5b  lea     rcx, [rbx+38h]
0x140015c5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140015c64  mov     rdi, [rbx+100h]
0x140015c6b  mov     qword ptr [rbx+100h], 0
0x140015c76  test    rdi, rdi
0x140015c79  jz      short loc_140015C9B
0x140015c7b  call    cs:__imp_GetProcessHeap
0x140015c82  nop     dword ptr [rax+rax+00h]
0x140015c87  mov     rcx, rax; hHeap
0x140015c8a  mov     r8, rdi; lpMem
0x140015c8d  xor     edx, edx; dwFlags
0x140015c8f  call    cs:__imp_HeapFree
0x140015c96  nop     dword ptr [rax+rax+00h]
0x140015c9b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140015ca2  test    r8, r8
0x140015ca5  jz      short loc_140015CBF
0x140015ca7  mov     rdx, cs:SRWLock; SRWLock
0x140015cae  test    rdx, rdx
0x140015cb1  jz      short loc_140015CBF
0x140015cb3  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140015cba  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140015cbf  lea     rdi, [rbx+98h]
0x140015cc6  mov     rsi, [rdi+40h]
0x140015cca  mov     qword ptr [rdi+40h], 0
0x140015cd2  test    rsi, rsi
0x140015cd5  jz      short loc_140015CF7
0x140015cd7  call    cs:__imp_GetProcessHeap
0x140015cde  nop     dword ptr [rax+rax+00h]
0x140015ce3  mov     rcx, rax; hHeap
0x140015ce6  mov     r8, rsi; lpMem
0x140015ce9  xor     edx, edx; dwFlags
0x140015ceb  call    cs:__imp_HeapFree
0x140015cf2  nop     dword ptr [rax+rax+00h]
0x140015cf7  mov     rcx, rdi; lpCriticalSection
0x140015cfa  call    cs:__imp_DeleteCriticalSection
0x140015d01  nop     dword ptr [rax+rax+00h]
0x140015d06  mov     rcx, [rbx+90h]; this
0x140015d0d  test    rcx, rcx
0x140015d10  jz      short loc_140015D17
0x140015d12  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140015d17  mov     rsi, [rbx+88h]
0x140015d1e  mov     qword ptr [rbx+88h], 0
0x140015d29  test    rsi, rsi
0x140015d2c  jz      short loc_140015D4E
0x140015d2e  call    cs:__imp_GetProcessHeap
0x140015d35  nop     dword ptr [rax+rax+00h]
0x140015d3a  mov     rcx, rax; hHeap
0x140015d3d  mov     r8, rsi; lpMem
0x140015d40  xor     edx, edx; dwFlags
0x140015d42  call    cs:__imp_HeapFree
0x140015d49  nop     dword ptr [rax+rax+00h]
0x140015d4e  lea     rcx, [rbx+48h]; lpCriticalSection
0x140015d52  call    cs:__imp_DeleteCriticalSection
0x140015d59  nop     dword ptr [rax+rax+00h]
0x140015d5e  mov     rdi, [rbx+38h]
0x140015d62  mov     esi, 1
0x140015d67  test    rdi, rdi
0x140015d6a  jz      short loc_140015DA3
0x140015d6c  xor     r9d, r9d; msWindowLength
0x140015d6f  xor     r8d, r8d; msPeriod
0x140015d72  xor     edx, edx; pftDueTime
0x140015d74  mov     rcx, rdi; pti
0x140015d77  call    cs:__imp_SetThreadpoolTimer
0x140015d7e  nop     dword ptr [rax+rax+00h]
0x140015d83  mov     edx, esi; fCancelPendingCallbacks
0x140015d85  mov     rcx, rdi; pti
0x140015d88  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015d8f  nop     dword ptr [rax+rax+00h]
0x140015d94  mov     rcx, rdi; pti
0x140015d97  call    cs:__imp_CloseThreadpoolTimer
0x140015d9e  nop     dword ptr [rax+rax+00h]
0x140015da3  mov     rdi, [rbx+30h]
0x140015da7  test    rdi, rdi
0x140015daa  jz      short loc_140015DE4
0x140015dac  xor     r9d, r9d; msWindowLength
0x140015daf  xor     r8d, r8d; msPeriod
0x140015db2  xor     edx, edx; pftDueTime
0x140015db4  mov     rcx, rdi; pti
0x140015db7  call    cs:__imp_SetThreadpoolTimer
0x140015dbe  nop     dword ptr [rax+rax+00h]
0x140015dc3  mov     edx, esi; fCancelPendingCallbacks
0x140015dc5  mov     rcx, rdi; pti
0x140015dc8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015dcf  nop     dword ptr [rax+rax+00h]
0x140015dd4  mov     rcx, rdi; pti
0x140015dd7  call    cs:__imp_CloseThreadpoolTimer
0x140015dde  nop     dword ptr [rax+rax+00h]
0x140015de3  nop
0x140015de4  mov     rcx, [rbx+10h]; lpMem
0x140015de8  test    rcx, rcx
0x140015deb  jz      short loc_140015DF3
0x140015ded  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140015df2  nop
0x140015df3  add     rsp, 20h
0x140015df7  pop     r15
0x140015df9  pop     r14
0x140015dfb  pop     rdi
0x140015dfc  pop     rsi
0x140015dfd  pop     rbx
0x140015dfe  retn
```
