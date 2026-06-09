# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800b4a74`
- end: `0x1800b4c36`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `450`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800ea080`

## callees

- `0x1800b4a74`
- `0x1800bc22c`
- `0x1800bd57c`
- `0x1800bd5f0`
- `0x1800be088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b4b32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b4b8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b4b32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b4b8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4ac7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4b7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4ac7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4b7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4ab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4b0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4b66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4ab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4b0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4b66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4baf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4bef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4baf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4bef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4bc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4c00`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4bc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4c00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4bcf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4c0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4bcf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4c0f`

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
  if ( v4 && qword_18010B238 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18010B238[25], qword_18010B238, v4);
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
0x1800b4a74  push    rbx
0x1800b4a76  push    rsi
0x1800b4a77  push    rdi
0x1800b4a78  push    r14
0x1800b4a7a  push    r15
0x1800b4a7c  sub     rsp, 20h
0x1800b4a80  mov     rbx, rcx
0x1800b4a83  mov     byte ptr [rcx], 0
0x1800b4a86  add     rcx, 30h ; '0'
0x1800b4a8a  xor     edx, edx
0x1800b4a8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800b4a91  xor     edx, edx
0x1800b4a93  lea     rcx, [rbx+38h]
0x1800b4a97  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800b4a9c  mov     rdi, [rbx+100h]
0x1800b4aa3  mov     qword ptr [rbx+100h], 0
0x1800b4aae  test    rdi, rdi
0x1800b4ab1  jz      short loc_1800B4AD3
0x1800b4ab3  call    cs:__imp_GetProcessHeap
0x1800b4aba  nop     dword ptr [rax+rax+00h]
0x1800b4abf  mov     r8, rdi; lpMem
0x1800b4ac2  xor     edx, edx; dwFlags
0x1800b4ac4  mov     rcx, rax; hHeap
0x1800b4ac7  call    cs:__imp_HeapFree
0x1800b4ace  nop     dword ptr [rax+rax+00h]
0x1800b4ad3  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800b4ada  test    r8, r8
0x1800b4add  jz      short loc_1800B4AF7
0x1800b4adf  mov     rdx, cs:qword_18010B238; SRWLock
0x1800b4ae6  test    rdx, rdx
0x1800b4ae9  jz      short loc_1800B4AF7
0x1800b4aeb  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800b4af2  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800b4af7  lea     rdi, [rbx+98h]
0x1800b4afe  mov     rsi, [rdi+40h]
0x1800b4b02  mov     qword ptr [rdi+40h], 0
0x1800b4b0a  test    rsi, rsi
0x1800b4b0d  jz      short loc_1800B4B2F
0x1800b4b0f  call    cs:__imp_GetProcessHeap
0x1800b4b16  nop     dword ptr [rax+rax+00h]
0x1800b4b1b  mov     r8, rsi; lpMem
0x1800b4b1e  xor     edx, edx; dwFlags
0x1800b4b20  mov     rcx, rax; hHeap
0x1800b4b23  call    cs:__imp_HeapFree
0x1800b4b2a  nop     dword ptr [rax+rax+00h]
0x1800b4b2f  mov     rcx, rdi; lpCriticalSection
0x1800b4b32  call    cs:__imp_DeleteCriticalSection
0x1800b4b39  nop     dword ptr [rax+rax+00h]
0x1800b4b3e  mov     rcx, [rbx+90h]; this
0x1800b4b45  test    rcx, rcx
0x1800b4b48  jz      short loc_1800B4B4F
0x1800b4b4a  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800b4b4f  mov     rsi, [rbx+88h]
0x1800b4b56  mov     qword ptr [rbx+88h], 0
0x1800b4b61  test    rsi, rsi
0x1800b4b64  jz      short loc_1800B4B86
0x1800b4b66  call    cs:__imp_GetProcessHeap
0x1800b4b6d  nop     dword ptr [rax+rax+00h]
0x1800b4b72  mov     r8, rsi; lpMem
0x1800b4b75  xor     edx, edx; dwFlags
0x1800b4b77  mov     rcx, rax; hHeap
0x1800b4b7a  call    cs:__imp_HeapFree
0x1800b4b81  nop     dword ptr [rax+rax+00h]
0x1800b4b86  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800b4b8a  call    cs:__imp_DeleteCriticalSection
0x1800b4b91  nop     dword ptr [rax+rax+00h]
0x1800b4b96  mov     rdi, [rbx+38h]
0x1800b4b9a  mov     esi, 1
0x1800b4b9f  test    rdi, rdi
0x1800b4ba2  jz      short loc_1800B4BDB
0x1800b4ba4  xor     r9d, r9d; msWindowLength
0x1800b4ba7  xor     r8d, r8d; msPeriod
0x1800b4baa  xor     edx, edx; pftDueTime
0x1800b4bac  mov     rcx, rdi; pti
0x1800b4baf  call    cs:__imp_SetThreadpoolTimer
0x1800b4bb6  nop     dword ptr [rax+rax+00h]
0x1800b4bbb  mov     edx, esi; fCancelPendingCallbacks
0x1800b4bbd  mov     rcx, rdi; pti
0x1800b4bc0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b4bc7  nop     dword ptr [rax+rax+00h]
0x1800b4bcc  mov     rcx, rdi; pti
0x1800b4bcf  call    cs:__imp_CloseThreadpoolTimer
0x1800b4bd6  nop     dword ptr [rax+rax+00h]
0x1800b4bdb  mov     rdi, [rbx+30h]
0x1800b4bdf  test    rdi, rdi
0x1800b4be2  jz      short loc_1800B4C1B
0x1800b4be4  xor     r9d, r9d; msWindowLength
0x1800b4be7  xor     r8d, r8d; msPeriod
0x1800b4bea  xor     edx, edx; pftDueTime
0x1800b4bec  mov     rcx, rdi; pti
0x1800b4bef  call    cs:__imp_SetThreadpoolTimer
0x1800b4bf6  nop     dword ptr [rax+rax+00h]
0x1800b4bfb  mov     edx, esi; fCancelPendingCallbacks
0x1800b4bfd  mov     rcx, rdi; pti
0x1800b4c00  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b4c07  nop     dword ptr [rax+rax+00h]
0x1800b4c0c  mov     rcx, rdi; pti
0x1800b4c0f  call    cs:__imp_CloseThreadpoolTimer
0x1800b4c16  nop     dword ptr [rax+rax+00h]
0x1800b4c1b  mov     rcx, [rbx+10h]; lpMem
0x1800b4c1f  test    rcx, rcx
0x1800b4c22  jz      short loc_1800B4C29
0x1800b4c24  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800b4c29  add     rsp, 20h
0x1800b4c2d  pop     r15
0x1800b4c2f  pop     r14
0x1800b4c31  pop     rdi
0x1800b4c32  pop     rsi
0x1800b4c33  pop     rbx
0x1800b4c34  retn
```
