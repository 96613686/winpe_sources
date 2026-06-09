# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003d5c`
- end: `0x180003f48`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c110`

## callees

- `0x180003c18`
- `0x180003d5c`
- `0x1800072d0`
- `0x180007edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ec2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003dd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003edc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003dd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003edc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003da4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ded`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ef3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003da4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ded`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ef3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003de4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003de4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003df5`

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
  if ( v8 && qword_180015038 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180015038[25], qword_180015038, v8);
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
0x180003d5c  mov     [rsp+arg_0], rbx
0x180003d61  mov     [rsp+arg_8], rsi
0x180003d66  push    rdi
0x180003d67  sub     rsp, 20h
0x180003d6b  mov     byte ptr [rcx], 0
0x180003d6e  mov     rdi, rcx
0x180003d71  mov     rsi, [rcx+30h]
0x180003d75  test    rsi, rsi
0x180003d78  jz      short loc_180003DB2
0x180003d7a  call    cs:__imp_GetLastError
0x180003d80  xor     r9d, r9d; msWindowLength
0x180003d83  xor     r8d, r8d; msPeriod
0x180003d86  xor     edx, edx; pftDueTime
0x180003d88  mov     rcx, rsi; pti
0x180003d8b  mov     ebx, eax
0x180003d8d  call    cs:__imp_SetThreadpoolTimer
0x180003d93  mov     edx, 1; fCancelPendingCallbacks
0x180003d98  mov     rcx, rsi; pti
0x180003d9b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003da1  mov     rcx, rsi; pti
0x180003da4  call    cs:__imp_CloseThreadpoolTimer
0x180003daa  mov     ecx, ebx; dwErrCode
0x180003dac  call    cs:__imp_SetLastError
0x180003db2  mov     qword ptr [rdi+30h], 0
0x180003dba  mov     rsi, [rdi+38h]
0x180003dbe  test    rsi, rsi
0x180003dc1  jz      short loc_180003DFB
0x180003dc3  call    cs:__imp_GetLastError
0x180003dc9  xor     r9d, r9d; msWindowLength
0x180003dcc  xor     r8d, r8d; msPeriod
0x180003dcf  xor     edx, edx; pftDueTime
0x180003dd1  mov     rcx, rsi; pti
0x180003dd4  mov     ebx, eax
0x180003dd6  call    cs:__imp_SetThreadpoolTimer
0x180003ddc  mov     edx, 1; fCancelPendingCallbacks
0x180003de1  mov     rcx, rsi; pti
0x180003de4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003dea  mov     rcx, rsi; pti
0x180003ded  call    cs:__imp_CloseThreadpoolTimer
0x180003df3  mov     ecx, ebx; dwErrCode
0x180003df5  call    cs:__imp_SetLastError
0x180003dfb  mov     qword ptr [rdi+38h], 0
0x180003e03  mov     rbx, [rdi+100h]
0x180003e0a  mov     qword ptr [rdi+100h], 0
0x180003e15  test    rbx, rbx
0x180003e18  jz      short loc_180003E2E
0x180003e1a  call    cs:__imp_GetProcessHeap
0x180003e20  mov     r8, rbx; lpMem
0x180003e23  xor     edx, edx; dwFlags
0x180003e25  mov     rcx, rax; hHeap
0x180003e28  call    cs:__imp_HeapFree
0x180003e2e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003e35  test    r8, r8
0x180003e38  jz      short loc_180003E52
0x180003e3a  mov     rdx, cs:qword_180015038; SRWLock
0x180003e41  test    rdx, rdx
0x180003e44  jz      short loc_180003E52
0x180003e46  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003e4d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003e52  lea     rbx, [rdi+98h]
0x180003e59  mov     rsi, [rbx+40h]
0x180003e5d  mov     qword ptr [rbx+40h], 0
0x180003e65  test    rsi, rsi
0x180003e68  jz      short loc_180003E7E
0x180003e6a  call    cs:__imp_GetProcessHeap
0x180003e70  mov     r8, rsi; lpMem
0x180003e73  xor     edx, edx; dwFlags
0x180003e75  mov     rcx, rax; hHeap
0x180003e78  call    cs:__imp_HeapFree
0x180003e7e  mov     rcx, rbx; lpCriticalSection
0x180003e81  call    cs:__imp_DeleteCriticalSection
0x180003e87  lea     rcx, [rdi+90h]
0x180003e8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003e93  mov     rsi, [rdi+88h]
0x180003e9a  mov     qword ptr [rdi+88h], 0
0x180003ea5  test    rsi, rsi
0x180003ea8  jz      short loc_180003EBE
0x180003eaa  call    cs:__imp_GetProcessHeap
0x180003eb0  mov     r8, rsi; lpMem
0x180003eb3  xor     edx, edx; dwFlags
0x180003eb5  mov     rcx, rax; hHeap
0x180003eb8  call    cs:__imp_HeapFree
0x180003ebe  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003ec2  call    cs:__imp_DeleteCriticalSection
0x180003ec8  mov     rbx, [rdi+38h]
0x180003ecc  test    rbx, rbx
0x180003ecf  jz      short loc_180003EF9
0x180003ed1  xor     r9d, r9d; msWindowLength
0x180003ed4  xor     r8d, r8d; msPeriod
0x180003ed7  xor     edx, edx; pftDueTime
0x180003ed9  mov     rcx, rbx; pti
0x180003edc  call    cs:__imp_SetThreadpoolTimer
0x180003ee2  mov     edx, 1; fCancelPendingCallbacks
0x180003ee7  mov     rcx, rbx; pti
0x180003eea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003ef0  mov     rcx, rbx; pti
0x180003ef3  call    cs:__imp_CloseThreadpoolTimer
0x180003ef9  mov     rbx, [rdi+30h]
0x180003efd  test    rbx, rbx
0x180003f00  jz      short loc_180003F2A
0x180003f02  xor     r9d, r9d; msWindowLength
0x180003f05  xor     r8d, r8d; msPeriod
0x180003f08  xor     edx, edx; pftDueTime
0x180003f0a  mov     rcx, rbx; pti
0x180003f0d  call    cs:__imp_SetThreadpoolTimer
0x180003f13  mov     edx, 1; fCancelPendingCallbacks
0x180003f18  mov     rcx, rbx; pti
0x180003f1b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003f21  mov     rcx, rbx; pti
0x180003f24  call    cs:__imp_CloseThreadpoolTimer
0x180003f2a  mov     rcx, [rdi+10h]; lpMem
0x180003f2e  test    rcx, rcx
0x180003f31  jz      short loc_180003F38
0x180003f33  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003f38  mov     rbx, [rsp+28h+arg_0]
0x180003f3d  mov     rsi, [rsp+28h+arg_8]
0x180003f42  add     rsp, 20h
0x180003f46  pop     rdi
0x180003f47  retn
```
