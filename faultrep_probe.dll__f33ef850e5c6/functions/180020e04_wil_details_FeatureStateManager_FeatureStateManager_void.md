# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180020e04`
- end: `0x180020ff2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004a140`

## callees

- `0x180020cc0`
- `0x180020e04`
- `0x180023938`
- `0x180024350`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ed0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ed0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f6a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020e43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020e8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020f92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020fc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020e43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020e8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020f92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020fc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020e4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020e95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020f9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020fcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020e4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020e95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020f9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020fcc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020e35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020e7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020f84`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020fb5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020e35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020e7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020f84`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_180062590 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180062590[25], qword_180062590, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x180020e04  mov     [rsp+arg_0], rbx
0x180020e09  mov     [rsp+arg_8], rsi
0x180020e0e  push    rdi
0x180020e0f  sub     rsp, 20h
0x180020e13  mov     rdi, rcx
0x180020e16  mov     byte ptr [rcx], 0
0x180020e19  mov     rsi, [rcx+30h]
0x180020e1d  test    rsi, rsi
0x180020e20  jz      short loc_180020E5A
0x180020e22  call    cs:__imp_GetLastError
0x180020e28  mov     ebx, eax
0x180020e2a  xor     r9d, r9d; msWindowLength
0x180020e2d  xor     r8d, r8d; msPeriod
0x180020e30  xor     edx, edx; pftDueTime
0x180020e32  mov     rcx, rsi; pti
0x180020e35  call    cs:__imp_SetThreadpoolTimer
0x180020e3b  mov     edx, 1; fCancelPendingCallbacks
0x180020e40  mov     rcx, rsi; pti
0x180020e43  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020e49  mov     rcx, rsi; pti
0x180020e4c  call    cs:__imp_CloseThreadpoolTimer
0x180020e52  mov     ecx, ebx; dwErrCode
0x180020e54  call    cs:__imp_SetLastError
0x180020e5a  mov     qword ptr [rdi+30h], 0
0x180020e62  mov     rsi, [rdi+38h]
0x180020e66  test    rsi, rsi
0x180020e69  jz      short loc_180020EA3
0x180020e6b  call    cs:__imp_GetLastError
0x180020e71  mov     ebx, eax
0x180020e73  xor     r9d, r9d; msWindowLength
0x180020e76  xor     r8d, r8d; msPeriod
0x180020e79  xor     edx, edx; pftDueTime
0x180020e7b  mov     rcx, rsi; pti
0x180020e7e  call    cs:__imp_SetThreadpoolTimer
0x180020e84  mov     edx, 1; fCancelPendingCallbacks
0x180020e89  mov     rcx, rsi; pti
0x180020e8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020e92  mov     rcx, rsi; pti
0x180020e95  call    cs:__imp_CloseThreadpoolTimer
0x180020e9b  mov     ecx, ebx; dwErrCode
0x180020e9d  call    cs:__imp_SetLastError
0x180020ea3  mov     qword ptr [rdi+38h], 0
0x180020eab  mov     rbx, [rdi+100h]
0x180020eb2  mov     qword ptr [rdi+100h], 0
0x180020ebd  test    rbx, rbx
0x180020ec0  jz      short loc_180020ED6
0x180020ec2  call    cs:__imp_GetProcessHeap
0x180020ec8  mov     rcx, rax; hHeap
0x180020ecb  mov     r8, rbx; lpMem
0x180020ece  xor     edx, edx; dwFlags
0x180020ed0  call    cs:__imp_HeapFree
0x180020ed6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180020edd  test    r8, r8
0x180020ee0  jz      short loc_180020EFA
0x180020ee2  mov     rdx, cs:qword_180062590; SRWLock
0x180020ee9  test    rdx, rdx
0x180020eec  jz      short loc_180020EFA
0x180020eee  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180020ef5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180020efa  lea     rbx, [rdi+98h]
0x180020f01  mov     rsi, [rbx+40h]
0x180020f05  mov     qword ptr [rbx+40h], 0
0x180020f0d  test    rsi, rsi
0x180020f10  jz      short loc_180020F26
0x180020f12  call    cs:__imp_GetProcessHeap
0x180020f18  mov     rcx, rax; hHeap
0x180020f1b  mov     r8, rsi; lpMem
0x180020f1e  xor     edx, edx; dwFlags
0x180020f20  call    cs:__imp_HeapFree
0x180020f26  mov     rcx, rbx; lpCriticalSection
0x180020f29  call    cs:__imp_DeleteCriticalSection
0x180020f2f  lea     rcx, [rdi+90h]
0x180020f36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020f3b  mov     rsi, [rdi+88h]
0x180020f42  mov     qword ptr [rdi+88h], 0
0x180020f4d  test    rsi, rsi
0x180020f50  jz      short loc_180020F66
0x180020f52  call    cs:__imp_GetProcessHeap
0x180020f58  mov     rcx, rax; hHeap
0x180020f5b  mov     r8, rsi; lpMem
0x180020f5e  xor     edx, edx; dwFlags
0x180020f60  call    cs:__imp_HeapFree
0x180020f66  lea     rcx, [rdi+48h]; lpCriticalSection
0x180020f6a  call    cs:__imp_DeleteCriticalSection
0x180020f70  mov     rbx, [rdi+38h]
0x180020f74  test    rbx, rbx
0x180020f77  jz      short loc_180020FA1
0x180020f79  xor     r9d, r9d; msWindowLength
0x180020f7c  xor     r8d, r8d; msPeriod
0x180020f7f  xor     edx, edx; pftDueTime
0x180020f81  mov     rcx, rbx; pti
0x180020f84  call    cs:__imp_SetThreadpoolTimer
0x180020f8a  mov     edx, 1; fCancelPendingCallbacks
0x180020f8f  mov     rcx, rbx; pti
0x180020f92  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020f98  mov     rcx, rbx; pti
0x180020f9b  call    cs:__imp_CloseThreadpoolTimer
0x180020fa1  mov     rbx, [rdi+30h]
0x180020fa5  test    rbx, rbx
0x180020fa8  jz      short loc_180020FD3
0x180020faa  xor     r9d, r9d; msWindowLength
0x180020fad  xor     r8d, r8d; msPeriod
0x180020fb0  xor     edx, edx; pftDueTime
0x180020fb2  mov     rcx, rbx; pti
0x180020fb5  call    cs:__imp_SetThreadpoolTimer
0x180020fbb  mov     edx, 1; fCancelPendingCallbacks
0x180020fc0  mov     rcx, rbx; pti
0x180020fc3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020fc9  mov     rcx, rbx; pti
0x180020fcc  call    cs:__imp_CloseThreadpoolTimer
0x180020fd2  nop
0x180020fd3  mov     rcx, [rdi+10h]; lpMem
0x180020fd7  test    rcx, rcx
0x180020fda  jz      short loc_180020FE2
0x180020fdc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180020fe1  nop
0x180020fe2  mov     rbx, [rsp+28h+arg_0]
0x180020fe7  mov     rsi, [rsp+28h+arg_8]
0x180020fec  add     rsp, 20h
0x180020ff0  pop     rdi
0x180020ff1  retn
```
