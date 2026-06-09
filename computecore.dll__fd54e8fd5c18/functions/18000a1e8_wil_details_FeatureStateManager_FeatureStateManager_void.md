# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000a1e8`
- end: `0x18000a3c3`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a19a0`

## callees

- `0x180009fb0`
- `0x18000a1e8`
- `0x18000ebf0`
- `0x180010460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a33b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a33b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a281`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a24f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a230`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a279`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a36c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a39d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a230`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a279`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a36c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a39d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a227`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a270`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a363`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a394`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a227`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a270`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a363`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a394`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a219`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a262`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a355`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a386`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a219`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a262`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a355`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a386`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x18000a1e8  mov     [rsp+arg_0], rbx
0x18000a1ed  mov     [rsp+arg_8], rsi
0x18000a1f2  push    rdi
0x18000a1f3  sub     rsp, 20h
0x18000a1f7  mov     rdi, rcx
0x18000a1fa  mov     byte ptr [rcx], 0
0x18000a1fd  mov     rsi, [rcx+30h]
0x18000a201  test    rsi, rsi
0x18000a204  jz      short loc_18000A23E
0x18000a206  call    cs:__imp_GetLastError
0x18000a20c  mov     ebx, eax
0x18000a20e  xor     r9d, r9d; msWindowLength
0x18000a211  xor     r8d, r8d; msPeriod
0x18000a214  xor     edx, edx; pftDueTime
0x18000a216  mov     rcx, rsi; pti
0x18000a219  call    cs:__imp_SetThreadpoolTimer
0x18000a21f  mov     edx, 1; fCancelPendingCallbacks
0x18000a224  mov     rcx, rsi; pti
0x18000a227  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a22d  mov     rcx, rsi; pti
0x18000a230  call    cs:__imp_CloseThreadpoolTimer
0x18000a236  mov     ecx, ebx; dwErrCode
0x18000a238  call    cs:__imp_SetLastError
0x18000a23e  mov     qword ptr [rdi+30h], 0
0x18000a246  mov     rsi, [rdi+38h]
0x18000a24a  test    rsi, rsi
0x18000a24d  jz      short loc_18000A287
0x18000a24f  call    cs:__imp_GetLastError
0x18000a255  mov     ebx, eax
0x18000a257  xor     r9d, r9d; msWindowLength
0x18000a25a  xor     r8d, r8d; msPeriod
0x18000a25d  xor     edx, edx; pftDueTime
0x18000a25f  mov     rcx, rsi; pti
0x18000a262  call    cs:__imp_SetThreadpoolTimer
0x18000a268  mov     edx, 1; fCancelPendingCallbacks
0x18000a26d  mov     rcx, rsi; pti
0x18000a270  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a276  mov     rcx, rsi; pti
0x18000a279  call    cs:__imp_CloseThreadpoolTimer
0x18000a27f  mov     ecx, ebx; dwErrCode
0x18000a281  call    cs:__imp_SetLastError
0x18000a287  mov     qword ptr [rdi+38h], 0
0x18000a28f  mov     rbx, [rdi+100h]
0x18000a296  mov     qword ptr [rdi+100h], 0
0x18000a2a1  test    rbx, rbx
0x18000a2a4  jz      short loc_18000A2BA
0x18000a2a6  call    cs:__imp_GetProcessHeap
0x18000a2ac  mov     rcx, rax; hHeap
0x18000a2af  mov     r8, rbx; lpMem
0x18000a2b2  xor     edx, edx; dwFlags
0x18000a2b4  call    cs:__imp_HeapFree
0x18000a2ba  mov     rcx, [rdi+0E0h]; this
0x18000a2c1  test    rcx, rcx
0x18000a2c4  jz      short loc_18000A2CB
0x18000a2c6  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000a2cb  lea     rbx, [rdi+98h]
0x18000a2d2  mov     rsi, [rbx+40h]
0x18000a2d6  mov     qword ptr [rbx+40h], 0
0x18000a2de  test    rsi, rsi
0x18000a2e1  jz      short loc_18000A2F7
0x18000a2e3  call    cs:__imp_GetProcessHeap
0x18000a2e9  mov     rcx, rax; hHeap
0x18000a2ec  mov     r8, rsi; lpMem
0x18000a2ef  xor     edx, edx; dwFlags
0x18000a2f1  call    cs:__imp_HeapFree
0x18000a2f7  mov     rcx, rbx; lpCriticalSection
0x18000a2fa  call    cs:__imp_DeleteCriticalSection
0x18000a300  lea     rcx, [rdi+90h]
0x18000a307  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000a30c  mov     rsi, [rdi+88h]
0x18000a313  mov     qword ptr [rdi+88h], 0
0x18000a31e  test    rsi, rsi
0x18000a321  jz      short loc_18000A337
0x18000a323  call    cs:__imp_GetProcessHeap
0x18000a329  mov     rcx, rax; hHeap
0x18000a32c  mov     r8, rsi; lpMem
0x18000a32f  xor     edx, edx; dwFlags
0x18000a331  call    cs:__imp_HeapFree
0x18000a337  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000a33b  call    cs:__imp_DeleteCriticalSection
0x18000a341  mov     rbx, [rdi+38h]
0x18000a345  test    rbx, rbx
0x18000a348  jz      short loc_18000A372
0x18000a34a  xor     r9d, r9d; msWindowLength
0x18000a34d  xor     r8d, r8d; msPeriod
0x18000a350  xor     edx, edx; pftDueTime
0x18000a352  mov     rcx, rbx; pti
0x18000a355  call    cs:__imp_SetThreadpoolTimer
0x18000a35b  mov     edx, 1; fCancelPendingCallbacks
0x18000a360  mov     rcx, rbx; pti
0x18000a363  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a369  mov     rcx, rbx; pti
0x18000a36c  call    cs:__imp_CloseThreadpoolTimer
0x18000a372  mov     rbx, [rdi+30h]
0x18000a376  test    rbx, rbx
0x18000a379  jz      short loc_18000A3A4
0x18000a37b  xor     r9d, r9d; msWindowLength
0x18000a37e  xor     r8d, r8d; msPeriod
0x18000a381  xor     edx, edx; pftDueTime
0x18000a383  mov     rcx, rbx; pti
0x18000a386  call    cs:__imp_SetThreadpoolTimer
0x18000a38c  mov     edx, 1; fCancelPendingCallbacks
0x18000a391  mov     rcx, rbx; pti
0x18000a394  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a39a  mov     rcx, rbx; pti
0x18000a39d  call    cs:__imp_CloseThreadpoolTimer
0x18000a3a3  nop
0x18000a3a4  mov     rcx, [rdi+10h]; lpMem
0x18000a3a8  test    rcx, rcx
0x18000a3ab  jz      short loc_18000A3B3
0x18000a3ad  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000a3b2  nop
0x18000a3b3  mov     rbx, [rsp+28h+arg_0]
0x18000a3b8  mov     rsi, [rsp+28h+arg_8]
0x18000a3bd  add     rsp, 20h
0x18000a3c1  pop     rdi
0x18000a3c2  retn
```
