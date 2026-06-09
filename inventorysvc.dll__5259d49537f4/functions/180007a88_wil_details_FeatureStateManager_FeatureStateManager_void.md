# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180007a88`
- end: `0x180007c76`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800d08c0`

## callees

- `0x1800076e0`
- `0x180007a88`
- `0x18000e74c`
- `0x1800101c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007bad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007bee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007bad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007bee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ba4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ba4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007be4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ad8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ad8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ab9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007b02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ab9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007b02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007ad0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007b19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007ad0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007b19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ac7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007b10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ac7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007b10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c47`

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
  if ( v8 && qword_1800FE230 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800FE230[25], qword_1800FE230, v8);
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
0x180007a88  mov     [rsp+arg_0], rbx
0x180007a8d  mov     [rsp+arg_8], rsi
0x180007a92  push    rdi
0x180007a93  sub     rsp, 20h
0x180007a97  mov     rdi, rcx
0x180007a9a  mov     byte ptr [rcx], 0
0x180007a9d  mov     rsi, [rcx+30h]
0x180007aa1  test    rsi, rsi
0x180007aa4  jz      short loc_180007ADE
0x180007aa6  call    cs:__imp_GetLastError
0x180007aac  mov     ebx, eax
0x180007aae  xor     r9d, r9d; msWindowLength
0x180007ab1  xor     r8d, r8d; msPeriod
0x180007ab4  xor     edx, edx; pftDueTime
0x180007ab6  mov     rcx, rsi; pti
0x180007ab9  call    cs:__imp_SetThreadpoolTimer
0x180007abf  mov     edx, 1; fCancelPendingCallbacks
0x180007ac4  mov     rcx, rsi; pti
0x180007ac7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007acd  mov     rcx, rsi; pti
0x180007ad0  call    cs:__imp_CloseThreadpoolTimer
0x180007ad6  mov     ecx, ebx; dwErrCode
0x180007ad8  call    cs:__imp_SetLastError
0x180007ade  mov     qword ptr [rdi+30h], 0
0x180007ae6  mov     rsi, [rdi+38h]
0x180007aea  test    rsi, rsi
0x180007aed  jz      short loc_180007B27
0x180007aef  call    cs:__imp_GetLastError
0x180007af5  mov     ebx, eax
0x180007af7  xor     r9d, r9d; msWindowLength
0x180007afa  xor     r8d, r8d; msPeriod
0x180007afd  xor     edx, edx; pftDueTime
0x180007aff  mov     rcx, rsi; pti
0x180007b02  call    cs:__imp_SetThreadpoolTimer
0x180007b08  mov     edx, 1; fCancelPendingCallbacks
0x180007b0d  mov     rcx, rsi; pti
0x180007b10  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007b16  mov     rcx, rsi; pti
0x180007b19  call    cs:__imp_CloseThreadpoolTimer
0x180007b1f  mov     ecx, ebx; dwErrCode
0x180007b21  call    cs:__imp_SetLastError
0x180007b27  mov     qword ptr [rdi+38h], 0
0x180007b2f  mov     rbx, [rdi+100h]
0x180007b36  mov     qword ptr [rdi+100h], 0
0x180007b41  test    rbx, rbx
0x180007b44  jz      short loc_180007B5A
0x180007b46  call    cs:__imp_GetProcessHeap
0x180007b4c  mov     rcx, rax; hHeap
0x180007b4f  mov     r8, rbx; lpMem
0x180007b52  xor     edx, edx; dwFlags
0x180007b54  call    cs:__imp_HeapFree
0x180007b5a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180007b61  test    r8, r8
0x180007b64  jz      short loc_180007B7E
0x180007b66  mov     rdx, cs:qword_1800FE230; SRWLock
0x180007b6d  test    rdx, rdx
0x180007b70  jz      short loc_180007B7E
0x180007b72  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007b79  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180007b7e  lea     rbx, [rdi+98h]
0x180007b85  mov     rsi, [rbx+40h]
0x180007b89  mov     qword ptr [rbx+40h], 0
0x180007b91  test    rsi, rsi
0x180007b94  jz      short loc_180007BAA
0x180007b96  call    cs:__imp_GetProcessHeap
0x180007b9c  mov     rcx, rax; hHeap
0x180007b9f  mov     r8, rsi; lpMem
0x180007ba2  xor     edx, edx; dwFlags
0x180007ba4  call    cs:__imp_HeapFree
0x180007baa  mov     rcx, rbx; lpCriticalSection
0x180007bad  call    cs:__imp_DeleteCriticalSection
0x180007bb3  lea     rcx, [rdi+90h]
0x180007bba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007bbf  mov     rsi, [rdi+88h]
0x180007bc6  mov     qword ptr [rdi+88h], 0
0x180007bd1  test    rsi, rsi
0x180007bd4  jz      short loc_180007BEA
0x180007bd6  call    cs:__imp_GetProcessHeap
0x180007bdc  mov     rcx, rax; hHeap
0x180007bdf  mov     r8, rsi; lpMem
0x180007be2  xor     edx, edx; dwFlags
0x180007be4  call    cs:__imp_HeapFree
0x180007bea  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007bee  call    cs:__imp_DeleteCriticalSection
0x180007bf4  mov     rbx, [rdi+38h]
0x180007bf8  test    rbx, rbx
0x180007bfb  jz      short loc_180007C25
0x180007bfd  xor     r9d, r9d; msWindowLength
0x180007c00  xor     r8d, r8d; msPeriod
0x180007c03  xor     edx, edx; pftDueTime
0x180007c05  mov     rcx, rbx; pti
0x180007c08  call    cs:__imp_SetThreadpoolTimer
0x180007c0e  mov     edx, 1; fCancelPendingCallbacks
0x180007c13  mov     rcx, rbx; pti
0x180007c16  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007c1c  mov     rcx, rbx; pti
0x180007c1f  call    cs:__imp_CloseThreadpoolTimer
0x180007c25  mov     rbx, [rdi+30h]
0x180007c29  test    rbx, rbx
0x180007c2c  jz      short loc_180007C57
0x180007c2e  xor     r9d, r9d; msWindowLength
0x180007c31  xor     r8d, r8d; msPeriod
0x180007c34  xor     edx, edx; pftDueTime
0x180007c36  mov     rcx, rbx; pti
0x180007c39  call    cs:__imp_SetThreadpoolTimer
0x180007c3f  mov     edx, 1; fCancelPendingCallbacks
0x180007c44  mov     rcx, rbx; pti
0x180007c47  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007c4d  mov     rcx, rbx; pti
0x180007c50  call    cs:__imp_CloseThreadpoolTimer
0x180007c56  nop
0x180007c57  mov     rcx, [rdi+10h]; lpMem
0x180007c5b  test    rcx, rcx
0x180007c5e  jz      short loc_180007C66
0x180007c60  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180007c65  nop
0x180007c66  mov     rbx, [rsp+28h+arg_0]
0x180007c6b  mov     rsi, [rsp+28h+arg_8]
0x180007c70  add     rsp, 20h
0x180007c74  pop     rdi
0x180007c75  retn
```
