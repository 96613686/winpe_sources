# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004a98`
- end: `0x180004c86`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016f50`

## callees

- `0x1800047f4`
- `0x180004a98`
- `0x180008800`
- `0x180009d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004bbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004bfe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004bbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004bfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004be6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004be6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bf4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004aff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004ac9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004ac9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004ae0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004ae0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004ad7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c57`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004ad7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c57`

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
  if ( v8 && qword_180021178 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180021178[25], qword_180021178, v8);
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
0x180004a98  mov     [rsp+arg_0], rbx
0x180004a9d  mov     [rsp+arg_8], rsi
0x180004aa2  push    rdi
0x180004aa3  sub     rsp, 20h
0x180004aa7  mov     rdi, rcx
0x180004aaa  mov     byte ptr [rcx], 0
0x180004aad  mov     rsi, [rcx+30h]
0x180004ab1  test    rsi, rsi
0x180004ab4  jz      short loc_180004AEE
0x180004ab6  call    cs:__imp_GetLastError
0x180004abc  mov     ebx, eax
0x180004abe  xor     r9d, r9d; msWindowLength
0x180004ac1  xor     r8d, r8d; msPeriod
0x180004ac4  xor     edx, edx; pftDueTime
0x180004ac6  mov     rcx, rsi; pti
0x180004ac9  call    cs:__imp_SetThreadpoolTimer
0x180004acf  mov     edx, 1; fCancelPendingCallbacks
0x180004ad4  mov     rcx, rsi; pti
0x180004ad7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004add  mov     rcx, rsi; pti
0x180004ae0  call    cs:__imp_CloseThreadpoolTimer
0x180004ae6  mov     ecx, ebx; dwErrCode
0x180004ae8  call    cs:__imp_SetLastError
0x180004aee  mov     qword ptr [rdi+30h], 0
0x180004af6  mov     rsi, [rdi+38h]
0x180004afa  test    rsi, rsi
0x180004afd  jz      short loc_180004B37
0x180004aff  call    cs:__imp_GetLastError
0x180004b05  mov     ebx, eax
0x180004b07  xor     r9d, r9d; msWindowLength
0x180004b0a  xor     r8d, r8d; msPeriod
0x180004b0d  xor     edx, edx; pftDueTime
0x180004b0f  mov     rcx, rsi; pti
0x180004b12  call    cs:__imp_SetThreadpoolTimer
0x180004b18  mov     edx, 1; fCancelPendingCallbacks
0x180004b1d  mov     rcx, rsi; pti
0x180004b20  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b26  mov     rcx, rsi; pti
0x180004b29  call    cs:__imp_CloseThreadpoolTimer
0x180004b2f  mov     ecx, ebx; dwErrCode
0x180004b31  call    cs:__imp_SetLastError
0x180004b37  mov     qword ptr [rdi+38h], 0
0x180004b3f  mov     rbx, [rdi+100h]
0x180004b46  mov     qword ptr [rdi+100h], 0
0x180004b51  test    rbx, rbx
0x180004b54  jz      short loc_180004B6A
0x180004b56  call    cs:__imp_GetProcessHeap
0x180004b5c  mov     rcx, rax; hHeap
0x180004b5f  mov     r8, rbx; lpMem
0x180004b62  xor     edx, edx; dwFlags
0x180004b64  call    cs:__imp_HeapFree
0x180004b6a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180004b71  test    r8, r8
0x180004b74  jz      short loc_180004B8E
0x180004b76  mov     rdx, cs:qword_180021178; SRWLock
0x180004b7d  test    rdx, rdx
0x180004b80  jz      short loc_180004B8E
0x180004b82  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180004b89  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004b8e  lea     rbx, [rdi+98h]
0x180004b95  mov     rsi, [rbx+40h]
0x180004b99  mov     qword ptr [rbx+40h], 0
0x180004ba1  test    rsi, rsi
0x180004ba4  jz      short loc_180004BBA
0x180004ba6  call    cs:__imp_GetProcessHeap
0x180004bac  mov     rcx, rax; hHeap
0x180004baf  mov     r8, rsi; lpMem
0x180004bb2  xor     edx, edx; dwFlags
0x180004bb4  call    cs:__imp_HeapFree
0x180004bba  mov     rcx, rbx; lpCriticalSection
0x180004bbd  call    cs:__imp_DeleteCriticalSection
0x180004bc3  lea     rcx, [rdi+90h]
0x180004bca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004bcf  mov     rsi, [rdi+88h]
0x180004bd6  mov     qword ptr [rdi+88h], 0
0x180004be1  test    rsi, rsi
0x180004be4  jz      short loc_180004BFA
0x180004be6  call    cs:__imp_GetProcessHeap
0x180004bec  mov     rcx, rax; hHeap
0x180004bef  mov     r8, rsi; lpMem
0x180004bf2  xor     edx, edx; dwFlags
0x180004bf4  call    cs:__imp_HeapFree
0x180004bfa  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004bfe  call    cs:__imp_DeleteCriticalSection
0x180004c04  mov     rbx, [rdi+38h]
0x180004c08  test    rbx, rbx
0x180004c0b  jz      short loc_180004C35
0x180004c0d  xor     r9d, r9d; msWindowLength
0x180004c10  xor     r8d, r8d; msPeriod
0x180004c13  xor     edx, edx; pftDueTime
0x180004c15  mov     rcx, rbx; pti
0x180004c18  call    cs:__imp_SetThreadpoolTimer
0x180004c1e  mov     edx, 1; fCancelPendingCallbacks
0x180004c23  mov     rcx, rbx; pti
0x180004c26  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c2c  mov     rcx, rbx; pti
0x180004c2f  call    cs:__imp_CloseThreadpoolTimer
0x180004c35  mov     rbx, [rdi+30h]
0x180004c39  test    rbx, rbx
0x180004c3c  jz      short loc_180004C67
0x180004c3e  xor     r9d, r9d; msWindowLength
0x180004c41  xor     r8d, r8d; msPeriod
0x180004c44  xor     edx, edx; pftDueTime
0x180004c46  mov     rcx, rbx; pti
0x180004c49  call    cs:__imp_SetThreadpoolTimer
0x180004c4f  mov     edx, 1; fCancelPendingCallbacks
0x180004c54  mov     rcx, rbx; pti
0x180004c57  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c5d  mov     rcx, rbx; pti
0x180004c60  call    cs:__imp_CloseThreadpoolTimer
0x180004c66  nop
0x180004c67  mov     rcx, [rdi+10h]; lpMem
0x180004c6b  test    rcx, rcx
0x180004c6e  jz      short loc_180004C76
0x180004c70  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004c75  nop
0x180004c76  mov     rbx, [rsp+28h+arg_0]
0x180004c7b  mov     rsi, [rsp+28h+arg_8]
0x180004c80  add     rsp, 20h
0x180004c84  pop     rdi
0x180004c85  retn
```
