# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140003cb4`
- end: `0x140003e78`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140016180`

## callees

- `0x140003cb4`
- `0x140007f30`
- `0x1400096f8`
- `0x14000976c`
- `0x14000a6e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003d4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003da6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003d4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003da6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003dba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003dba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003d72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003dca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003d72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003dca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003e0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003e4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003e0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003e4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003e00`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003e40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003e00`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003e40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003def`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003e2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003def`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003e2f`

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
  if ( v4 && qword_140023190 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140023190[25], qword_140023190, v4);
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
0x140003cb4  push    rbx
0x140003cb6  push    rsi
0x140003cb7  push    rdi
0x140003cb8  push    r14
0x140003cba  push    r15
0x140003cbc  sub     rsp, 20h
0x140003cc0  mov     rbx, rcx
0x140003cc3  mov     byte ptr [rcx], 0
0x140003cc6  xor     edx, edx
0x140003cc8  add     rcx, 30h ; '0'
0x140003ccc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140003cd1  xor     edx, edx
0x140003cd3  lea     rcx, [rbx+38h]
0x140003cd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140003cdc  mov     rdi, [rbx+100h]
0x140003ce3  mov     qword ptr [rbx+100h], 0
0x140003cee  test    rdi, rdi
0x140003cf1  jz      short loc_140003D13
0x140003cf3  call    cs:__imp_GetProcessHeap
0x140003cfa  nop     dword ptr [rax+rax+00h]
0x140003cff  mov     rcx, rax; hHeap
0x140003d02  mov     r8, rdi; lpMem
0x140003d05  xor     edx, edx; dwFlags
0x140003d07  call    cs:__imp_HeapFree
0x140003d0e  nop     dword ptr [rax+rax+00h]
0x140003d13  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140003d1a  test    r8, r8
0x140003d1d  jz      short loc_140003D37
0x140003d1f  mov     rdx, cs:qword_140023190; SRWLock
0x140003d26  test    rdx, rdx
0x140003d29  jz      short loc_140003D37
0x140003d2b  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140003d32  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140003d37  lea     rdi, [rbx+98h]
0x140003d3e  mov     rsi, [rdi+40h]
0x140003d42  mov     qword ptr [rdi+40h], 0
0x140003d4a  test    rsi, rsi
0x140003d4d  jz      short loc_140003D6F
0x140003d4f  call    cs:__imp_GetProcessHeap
0x140003d56  nop     dword ptr [rax+rax+00h]
0x140003d5b  mov     rcx, rax; hHeap
0x140003d5e  mov     r8, rsi; lpMem
0x140003d61  xor     edx, edx; dwFlags
0x140003d63  call    cs:__imp_HeapFree
0x140003d6a  nop     dword ptr [rax+rax+00h]
0x140003d6f  mov     rcx, rdi; lpCriticalSection
0x140003d72  call    cs:__imp_DeleteCriticalSection
0x140003d79  nop     dword ptr [rax+rax+00h]
0x140003d7e  mov     rcx, [rbx+90h]; this
0x140003d85  test    rcx, rcx
0x140003d88  jz      short loc_140003D8F
0x140003d8a  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140003d8f  mov     rsi, [rbx+88h]
0x140003d96  mov     qword ptr [rbx+88h], 0
0x140003da1  test    rsi, rsi
0x140003da4  jz      short loc_140003DC6
0x140003da6  call    cs:__imp_GetProcessHeap
0x140003dad  nop     dword ptr [rax+rax+00h]
0x140003db2  mov     rcx, rax; hHeap
0x140003db5  mov     r8, rsi; lpMem
0x140003db8  xor     edx, edx; dwFlags
0x140003dba  call    cs:__imp_HeapFree
0x140003dc1  nop     dword ptr [rax+rax+00h]
0x140003dc6  lea     rcx, [rbx+48h]; lpCriticalSection
0x140003dca  call    cs:__imp_DeleteCriticalSection
0x140003dd1  nop     dword ptr [rax+rax+00h]
0x140003dd6  mov     rdi, [rbx+38h]
0x140003dda  mov     esi, 1
0x140003ddf  test    rdi, rdi
0x140003de2  jz      short loc_140003E1B
0x140003de4  xor     r9d, r9d; msWindowLength
0x140003de7  xor     r8d, r8d; msPeriod
0x140003dea  xor     edx, edx; pftDueTime
0x140003dec  mov     rcx, rdi; pti
0x140003def  call    cs:__imp_SetThreadpoolTimer
0x140003df6  nop     dword ptr [rax+rax+00h]
0x140003dfb  mov     edx, esi; fCancelPendingCallbacks
0x140003dfd  mov     rcx, rdi; pti
0x140003e00  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003e07  nop     dword ptr [rax+rax+00h]
0x140003e0c  mov     rcx, rdi; pti
0x140003e0f  call    cs:__imp_CloseThreadpoolTimer
0x140003e16  nop     dword ptr [rax+rax+00h]
0x140003e1b  mov     rdi, [rbx+30h]
0x140003e1f  test    rdi, rdi
0x140003e22  jz      short loc_140003E5C
0x140003e24  xor     r9d, r9d; msWindowLength
0x140003e27  xor     r8d, r8d; msPeriod
0x140003e2a  xor     edx, edx; pftDueTime
0x140003e2c  mov     rcx, rdi; pti
0x140003e2f  call    cs:__imp_SetThreadpoolTimer
0x140003e36  nop     dword ptr [rax+rax+00h]
0x140003e3b  mov     edx, esi; fCancelPendingCallbacks
0x140003e3d  mov     rcx, rdi; pti
0x140003e40  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003e47  nop     dword ptr [rax+rax+00h]
0x140003e4c  mov     rcx, rdi; pti
0x140003e4f  call    cs:__imp_CloseThreadpoolTimer
0x140003e56  nop     dword ptr [rax+rax+00h]
0x140003e5b  nop
0x140003e5c  mov     rcx, [rbx+10h]; lpMem
0x140003e60  test    rcx, rcx
0x140003e63  jz      short loc_140003E6B
0x140003e65  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140003e6a  nop
0x140003e6b  add     rsp, 20h
0x140003e6f  pop     r15
0x140003e71  pop     r14
0x140003e73  pop     rdi
0x140003e74  pop     rsi
0x140003e75  pop     rbx
0x140003e76  retn
```
