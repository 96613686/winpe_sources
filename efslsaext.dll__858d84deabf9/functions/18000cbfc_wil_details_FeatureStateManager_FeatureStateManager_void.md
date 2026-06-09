# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000cbfc`
- end: `0x18000cde8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800125b0`

## callees

- `0x18000cab8`
- `0x18000cbfc`
- `0x180010bb0`
- `0x1800110d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cd21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cd62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cd21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cd62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdc4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc76`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cdad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc76`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cdad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc84`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cd8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdbb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc84`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cd8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ccc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ccc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd58`

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
  if ( v8 && qword_18001E0D0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001E0D0[25], qword_18001E0D0, v8);
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
0x18000cbfc  mov     [rsp+arg_0], rbx
0x18000cc01  mov     [rsp+arg_8], rsi
0x18000cc06  push    rdi
0x18000cc07  sub     rsp, 20h
0x18000cc0b  mov     byte ptr [rcx], 0
0x18000cc0e  mov     rdi, rcx
0x18000cc11  mov     rsi, [rcx+30h]
0x18000cc15  test    rsi, rsi
0x18000cc18  jz      short loc_18000CC52
0x18000cc1a  call    cs:__imp_GetLastError
0x18000cc20  xor     r9d, r9d; msWindowLength
0x18000cc23  xor     r8d, r8d; msPeriod
0x18000cc26  xor     edx, edx; pftDueTime
0x18000cc28  mov     rcx, rsi; pti
0x18000cc2b  mov     ebx, eax
0x18000cc2d  call    cs:__imp_SetThreadpoolTimer
0x18000cc33  mov     edx, 1; fCancelPendingCallbacks
0x18000cc38  mov     rcx, rsi; pti
0x18000cc3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cc41  mov     rcx, rsi; pti
0x18000cc44  call    cs:__imp_CloseThreadpoolTimer
0x18000cc4a  mov     ecx, ebx; dwErrCode
0x18000cc4c  call    cs:__imp_SetLastError
0x18000cc52  mov     qword ptr [rdi+30h], 0
0x18000cc5a  mov     rsi, [rdi+38h]
0x18000cc5e  test    rsi, rsi
0x18000cc61  jz      short loc_18000CC9B
0x18000cc63  call    cs:__imp_GetLastError
0x18000cc69  xor     r9d, r9d; msWindowLength
0x18000cc6c  xor     r8d, r8d; msPeriod
0x18000cc6f  xor     edx, edx; pftDueTime
0x18000cc71  mov     rcx, rsi; pti
0x18000cc74  mov     ebx, eax
0x18000cc76  call    cs:__imp_SetThreadpoolTimer
0x18000cc7c  mov     edx, 1; fCancelPendingCallbacks
0x18000cc81  mov     rcx, rsi; pti
0x18000cc84  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cc8a  mov     rcx, rsi; pti
0x18000cc8d  call    cs:__imp_CloseThreadpoolTimer
0x18000cc93  mov     ecx, ebx; dwErrCode
0x18000cc95  call    cs:__imp_SetLastError
0x18000cc9b  mov     qword ptr [rdi+38h], 0
0x18000cca3  mov     rbx, [rdi+100h]
0x18000ccaa  mov     qword ptr [rdi+100h], 0
0x18000ccb5  test    rbx, rbx
0x18000ccb8  jz      short loc_18000CCCE
0x18000ccba  call    cs:__imp_GetProcessHeap
0x18000ccc0  mov     r8, rbx; lpMem
0x18000ccc3  xor     edx, edx; dwFlags
0x18000ccc5  mov     rcx, rax; hHeap
0x18000ccc8  call    cs:__imp_HeapFree
0x18000ccce  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000ccd5  test    r8, r8
0x18000ccd8  jz      short loc_18000CCF2
0x18000ccda  mov     rdx, cs:qword_18001E0D0; SRWLock
0x18000cce1  test    rdx, rdx
0x18000cce4  jz      short loc_18000CCF2
0x18000cce6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000cced  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000ccf2  lea     rbx, [rdi+98h]
0x18000ccf9  mov     rsi, [rbx+40h]
0x18000ccfd  mov     qword ptr [rbx+40h], 0
0x18000cd05  test    rsi, rsi
0x18000cd08  jz      short loc_18000CD1E
0x18000cd0a  call    cs:__imp_GetProcessHeap
0x18000cd10  mov     r8, rsi; lpMem
0x18000cd13  xor     edx, edx; dwFlags
0x18000cd15  mov     rcx, rax; hHeap
0x18000cd18  call    cs:__imp_HeapFree
0x18000cd1e  mov     rcx, rbx; lpCriticalSection
0x18000cd21  call    cs:__imp_DeleteCriticalSection
0x18000cd27  lea     rcx, [rdi+90h]
0x18000cd2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cd33  mov     rsi, [rdi+88h]
0x18000cd3a  mov     qword ptr [rdi+88h], 0
0x18000cd45  test    rsi, rsi
0x18000cd48  jz      short loc_18000CD5E
0x18000cd4a  call    cs:__imp_GetProcessHeap
0x18000cd50  mov     r8, rsi; lpMem
0x18000cd53  xor     edx, edx; dwFlags
0x18000cd55  mov     rcx, rax; hHeap
0x18000cd58  call    cs:__imp_HeapFree
0x18000cd5e  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000cd62  call    cs:__imp_DeleteCriticalSection
0x18000cd68  mov     rbx, [rdi+38h]
0x18000cd6c  test    rbx, rbx
0x18000cd6f  jz      short loc_18000CD99
0x18000cd71  xor     r9d, r9d; msWindowLength
0x18000cd74  xor     r8d, r8d; msPeriod
0x18000cd77  xor     edx, edx; pftDueTime
0x18000cd79  mov     rcx, rbx; pti
0x18000cd7c  call    cs:__imp_SetThreadpoolTimer
0x18000cd82  mov     edx, 1; fCancelPendingCallbacks
0x18000cd87  mov     rcx, rbx; pti
0x18000cd8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cd90  mov     rcx, rbx; pti
0x18000cd93  call    cs:__imp_CloseThreadpoolTimer
0x18000cd99  mov     rbx, [rdi+30h]
0x18000cd9d  test    rbx, rbx
0x18000cda0  jz      short loc_18000CDCA
0x18000cda2  xor     r9d, r9d; msWindowLength
0x18000cda5  xor     r8d, r8d; msPeriod
0x18000cda8  xor     edx, edx; pftDueTime
0x18000cdaa  mov     rcx, rbx; pti
0x18000cdad  call    cs:__imp_SetThreadpoolTimer
0x18000cdb3  mov     edx, 1; fCancelPendingCallbacks
0x18000cdb8  mov     rcx, rbx; pti
0x18000cdbb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cdc1  mov     rcx, rbx; pti
0x18000cdc4  call    cs:__imp_CloseThreadpoolTimer
0x18000cdca  mov     rcx, [rdi+10h]; lpMem
0x18000cdce  test    rcx, rcx
0x18000cdd1  jz      short loc_18000CDD8
0x18000cdd3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000cdd8  mov     rbx, [rsp+28h+arg_0]
0x18000cddd  mov     rsi, [rsp+28h+arg_8]
0x18000cde2  add     rsp, 20h
0x18000cde6  pop     rdi
0x18000cde7  retn
```
