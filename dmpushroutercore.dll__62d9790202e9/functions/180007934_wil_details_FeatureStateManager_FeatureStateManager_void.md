# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180007934`
- end: `0x180007b22`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180039c90`

## callees

- `0x180007690`
- `0x180007934`
- `0x18000b78c`
- `0x18000cd5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000799b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000799b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a9a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000797c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007acb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007afc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000797c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007acb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007afc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007973`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ac2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007af3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007973`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ac2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007af3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007965`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ab4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ae5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007965`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ab4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ae5`

## pseudocode

```c
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
  if ( v8 && qword_1800502C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800502C8[25], qword_1800502C8, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
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
0x180007934  mov     [rsp+arg_0], rbx
0x180007939  mov     [rsp+arg_8], rsi
0x18000793e  push    rdi
0x18000793f  sub     rsp, 20h
0x180007943  mov     rdi, rcx
0x180007946  mov     byte ptr [rcx], 0
0x180007949  mov     rsi, [rcx+30h]
0x18000794d  test    rsi, rsi
0x180007950  jz      short loc_18000798A
0x180007952  call    cs:__imp_GetLastError
0x180007958  mov     ebx, eax
0x18000795a  xor     r9d, r9d; msWindowLength
0x18000795d  xor     r8d, r8d; msPeriod
0x180007960  xor     edx, edx; pftDueTime
0x180007962  mov     rcx, rsi; pti
0x180007965  call    cs:__imp_SetThreadpoolTimer
0x18000796b  mov     edx, 1; fCancelPendingCallbacks
0x180007970  mov     rcx, rsi; pti
0x180007973  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007979  mov     rcx, rsi; pti
0x18000797c  call    cs:__imp_CloseThreadpoolTimer
0x180007982  mov     ecx, ebx; dwErrCode
0x180007984  call    cs:__imp_SetLastError
0x18000798a  mov     qword ptr [rdi+30h], 0
0x180007992  mov     rsi, [rdi+38h]
0x180007996  test    rsi, rsi
0x180007999  jz      short loc_1800079D3
0x18000799b  call    cs:__imp_GetLastError
0x1800079a1  mov     ebx, eax
0x1800079a3  xor     r9d, r9d; msWindowLength
0x1800079a6  xor     r8d, r8d; msPeriod
0x1800079a9  xor     edx, edx; pftDueTime
0x1800079ab  mov     rcx, rsi; pti
0x1800079ae  call    cs:__imp_SetThreadpoolTimer
0x1800079b4  mov     edx, 1; fCancelPendingCallbacks
0x1800079b9  mov     rcx, rsi; pti
0x1800079bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079c2  mov     rcx, rsi; pti
0x1800079c5  call    cs:__imp_CloseThreadpoolTimer
0x1800079cb  mov     ecx, ebx; dwErrCode
0x1800079cd  call    cs:__imp_SetLastError
0x1800079d3  mov     qword ptr [rdi+38h], 0
0x1800079db  mov     rbx, [rdi+100h]
0x1800079e2  mov     qword ptr [rdi+100h], 0
0x1800079ed  test    rbx, rbx
0x1800079f0  jz      short loc_180007A06
0x1800079f2  call    cs:__imp_GetProcessHeap
0x1800079f8  mov     rcx, rax; hHeap
0x1800079fb  mov     r8, rbx; lpMem
0x1800079fe  xor     edx, edx; dwFlags
0x180007a00  call    cs:__imp_HeapFree
0x180007a06  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180007a0d  test    r8, r8
0x180007a10  jz      short loc_180007A2A
0x180007a12  mov     rdx, cs:qword_1800502C8; SRWLock
0x180007a19  test    rdx, rdx
0x180007a1c  jz      short loc_180007A2A
0x180007a1e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007a25  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180007a2a  lea     rbx, [rdi+98h]
0x180007a31  mov     rsi, [rbx+40h]
0x180007a35  mov     qword ptr [rbx+40h], 0
0x180007a3d  test    rsi, rsi
0x180007a40  jz      short loc_180007A56
0x180007a42  call    cs:__imp_GetProcessHeap
0x180007a48  mov     rcx, rax; hHeap
0x180007a4b  mov     r8, rsi; lpMem
0x180007a4e  xor     edx, edx; dwFlags
0x180007a50  call    cs:__imp_HeapFree
0x180007a56  mov     rcx, rbx; lpCriticalSection
0x180007a59  call    cs:__imp_DeleteCriticalSection
0x180007a5f  lea     rcx, [rdi+90h]
0x180007a66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007a6b  mov     rsi, [rdi+88h]
0x180007a72  mov     qword ptr [rdi+88h], 0
0x180007a7d  test    rsi, rsi
0x180007a80  jz      short loc_180007A96
0x180007a82  call    cs:__imp_GetProcessHeap
0x180007a88  mov     rcx, rax; hHeap
0x180007a8b  mov     r8, rsi; lpMem
0x180007a8e  xor     edx, edx; dwFlags
0x180007a90  call    cs:__imp_HeapFree
0x180007a96  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007a9a  call    cs:__imp_DeleteCriticalSection
0x180007aa0  mov     rbx, [rdi+38h]
0x180007aa4  test    rbx, rbx
0x180007aa7  jz      short loc_180007AD1
0x180007aa9  xor     r9d, r9d; msWindowLength
0x180007aac  xor     r8d, r8d; msPeriod
0x180007aaf  xor     edx, edx; pftDueTime
0x180007ab1  mov     rcx, rbx; pti
0x180007ab4  call    cs:__imp_SetThreadpoolTimer
0x180007aba  mov     edx, 1; fCancelPendingCallbacks
0x180007abf  mov     rcx, rbx; pti
0x180007ac2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007ac8  mov     rcx, rbx; pti
0x180007acb  call    cs:__imp_CloseThreadpoolTimer
0x180007ad1  mov     rbx, [rdi+30h]
0x180007ad5  test    rbx, rbx
0x180007ad8  jz      short loc_180007B03
0x180007ada  xor     r9d, r9d; msWindowLength
0x180007add  xor     r8d, r8d; msPeriod
0x180007ae0  xor     edx, edx; pftDueTime
0x180007ae2  mov     rcx, rbx; pti
0x180007ae5  call    cs:__imp_SetThreadpoolTimer
0x180007aeb  mov     edx, 1; fCancelPendingCallbacks
0x180007af0  mov     rcx, rbx; pti
0x180007af3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007af9  mov     rcx, rbx; pti
0x180007afc  call    cs:__imp_CloseThreadpoolTimer
0x180007b02  nop
0x180007b03  mov     rcx, [rdi+10h]; lpMem
0x180007b07  test    rcx, rcx
0x180007b0a  jz      short loc_180007B12
0x180007b0c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180007b11  nop
0x180007b12  mov     rbx, [rsp+28h+arg_0]
0x180007b17  mov     rsi, [rsp+28h+arg_8]
0x180007b1c  add     rsp, 20h
0x180007b20  pop     rdi
0x180007b21  retn
```
