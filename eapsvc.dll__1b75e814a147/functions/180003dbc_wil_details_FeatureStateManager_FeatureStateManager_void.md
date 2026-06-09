# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003dbc`
- end: `0x180003faa`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016030`

## callees

- `0x180003a3c`
- `0x180003dbc`
- `0x180007c80`
- `0x180009410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ee1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f22`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ee1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ded`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003ded`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003f6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f84`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003f84`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003dfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f7b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003dfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003f7b`

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
  if ( v8 && qword_1800200A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800200A8[25], qword_1800200A8, v8);
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
0x180003dbc  mov     [rsp+arg_0], rbx
0x180003dc1  mov     [rsp+arg_8], rsi
0x180003dc6  push    rdi
0x180003dc7  sub     rsp, 20h
0x180003dcb  mov     rdi, rcx
0x180003dce  mov     byte ptr [rcx], 0
0x180003dd1  mov     rsi, [rcx+30h]
0x180003dd5  test    rsi, rsi
0x180003dd8  jz      short loc_180003E12
0x180003dda  call    cs:__imp_GetLastError
0x180003de0  mov     ebx, eax
0x180003de2  xor     r9d, r9d; msWindowLength
0x180003de5  xor     r8d, r8d; msPeriod
0x180003de8  xor     edx, edx; pftDueTime
0x180003dea  mov     rcx, rsi; pti
0x180003ded  call    cs:__imp_SetThreadpoolTimer
0x180003df3  mov     edx, 1; fCancelPendingCallbacks
0x180003df8  mov     rcx, rsi; pti
0x180003dfb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e01  mov     rcx, rsi; pti
0x180003e04  call    cs:__imp_CloseThreadpoolTimer
0x180003e0a  mov     ecx, ebx; dwErrCode
0x180003e0c  call    cs:__imp_SetLastError
0x180003e12  mov     qword ptr [rdi+30h], 0
0x180003e1a  mov     rsi, [rdi+38h]
0x180003e1e  test    rsi, rsi
0x180003e21  jz      short loc_180003E5B
0x180003e23  call    cs:__imp_GetLastError
0x180003e29  mov     ebx, eax
0x180003e2b  xor     r9d, r9d; msWindowLength
0x180003e2e  xor     r8d, r8d; msPeriod
0x180003e31  xor     edx, edx; pftDueTime
0x180003e33  mov     rcx, rsi; pti
0x180003e36  call    cs:__imp_SetThreadpoolTimer
0x180003e3c  mov     edx, 1; fCancelPendingCallbacks
0x180003e41  mov     rcx, rsi; pti
0x180003e44  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e4a  mov     rcx, rsi; pti
0x180003e4d  call    cs:__imp_CloseThreadpoolTimer
0x180003e53  mov     ecx, ebx; dwErrCode
0x180003e55  call    cs:__imp_SetLastError
0x180003e5b  mov     qword ptr [rdi+38h], 0
0x180003e63  mov     rbx, [rdi+100h]
0x180003e6a  mov     qword ptr [rdi+100h], 0
0x180003e75  test    rbx, rbx
0x180003e78  jz      short loc_180003E8E
0x180003e7a  call    cs:__imp_GetProcessHeap
0x180003e80  mov     rcx, rax; hHeap
0x180003e83  mov     r8, rbx; lpMem
0x180003e86  xor     edx, edx; dwFlags
0x180003e88  call    cs:__imp_HeapFree
0x180003e8e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003e95  test    r8, r8
0x180003e98  jz      short loc_180003EB2
0x180003e9a  mov     rdx, cs:qword_1800200A8; SRWLock
0x180003ea1  test    rdx, rdx
0x180003ea4  jz      short loc_180003EB2
0x180003ea6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003ead  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003eb2  lea     rbx, [rdi+98h]
0x180003eb9  mov     rsi, [rbx+40h]
0x180003ebd  mov     qword ptr [rbx+40h], 0
0x180003ec5  test    rsi, rsi
0x180003ec8  jz      short loc_180003EDE
0x180003eca  call    cs:__imp_GetProcessHeap
0x180003ed0  mov     rcx, rax; hHeap
0x180003ed3  mov     r8, rsi; lpMem
0x180003ed6  xor     edx, edx; dwFlags
0x180003ed8  call    cs:__imp_HeapFree
0x180003ede  mov     rcx, rbx; lpCriticalSection
0x180003ee1  call    cs:__imp_DeleteCriticalSection
0x180003ee7  lea     rcx, [rdi+90h]
0x180003eee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003ef3  mov     rsi, [rdi+88h]
0x180003efa  mov     qword ptr [rdi+88h], 0
0x180003f05  test    rsi, rsi
0x180003f08  jz      short loc_180003F1E
0x180003f0a  call    cs:__imp_GetProcessHeap
0x180003f10  mov     rcx, rax; hHeap
0x180003f13  mov     r8, rsi; lpMem
0x180003f16  xor     edx, edx; dwFlags
0x180003f18  call    cs:__imp_HeapFree
0x180003f1e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003f22  call    cs:__imp_DeleteCriticalSection
0x180003f28  mov     rbx, [rdi+38h]
0x180003f2c  test    rbx, rbx
0x180003f2f  jz      short loc_180003F59
0x180003f31  xor     r9d, r9d; msWindowLength
0x180003f34  xor     r8d, r8d; msPeriod
0x180003f37  xor     edx, edx; pftDueTime
0x180003f39  mov     rcx, rbx; pti
0x180003f3c  call    cs:__imp_SetThreadpoolTimer
0x180003f42  mov     edx, 1; fCancelPendingCallbacks
0x180003f47  mov     rcx, rbx; pti
0x180003f4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003f50  mov     rcx, rbx; pti
0x180003f53  call    cs:__imp_CloseThreadpoolTimer
0x180003f59  mov     rbx, [rdi+30h]
0x180003f5d  test    rbx, rbx
0x180003f60  jz      short loc_180003F8B
0x180003f62  xor     r9d, r9d; msWindowLength
0x180003f65  xor     r8d, r8d; msPeriod
0x180003f68  xor     edx, edx; pftDueTime
0x180003f6a  mov     rcx, rbx; pti
0x180003f6d  call    cs:__imp_SetThreadpoolTimer
0x180003f73  mov     edx, 1; fCancelPendingCallbacks
0x180003f78  mov     rcx, rbx; pti
0x180003f7b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003f81  mov     rcx, rbx; pti
0x180003f84  call    cs:__imp_CloseThreadpoolTimer
0x180003f8a  nop
0x180003f8b  mov     rcx, [rdi+10h]; lpMem
0x180003f8f  test    rcx, rcx
0x180003f92  jz      short loc_180003F9A
0x180003f94  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003f99  nop
0x180003f9a  mov     rbx, [rsp+28h+arg_0]
0x180003f9f  mov     rsi, [rsp+28h+arg_8]
0x180003fa4  add     rsp, 20h
0x180003fa8  pop     rdi
0x180003fa9  retn
```
