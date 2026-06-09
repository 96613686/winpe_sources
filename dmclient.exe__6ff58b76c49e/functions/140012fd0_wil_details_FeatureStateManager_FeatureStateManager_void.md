# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140012fd0`
- end: `0x1400131be`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018f20`

## callees

- `0x140012e8c`
- `0x140012fd0`
- `0x14001594c`
- `0x14001674c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400130f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140013136`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400130f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140013136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001308e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400130de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001311e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001308e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400130de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001311e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001309c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400130ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001312c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001309c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400130ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001312c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013037`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013069`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013069`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001300f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013058`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001315e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001318f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001300f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013058`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001315e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001318f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013001`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001304a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013150`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013181`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013001`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001304a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013150`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013181`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013018`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013061`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013167`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013198`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013018`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013061`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013167`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013198`

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
  if ( v8 && qword_1400270F0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400270F0[25], qword_1400270F0, v8);
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
0x140012fd0  mov     [rsp+arg_0], rbx
0x140012fd5  mov     [rsp+arg_8], rsi
0x140012fda  push    rdi
0x140012fdb  sub     rsp, 20h
0x140012fdf  mov     rdi, rcx
0x140012fe2  mov     byte ptr [rcx], 0
0x140012fe5  mov     rsi, [rcx+30h]
0x140012fe9  test    rsi, rsi
0x140012fec  jz      short loc_140013026
0x140012fee  call    cs:__imp_GetLastError
0x140012ff4  mov     ebx, eax
0x140012ff6  xor     r9d, r9d; msWindowLength
0x140012ff9  xor     r8d, r8d; msPeriod
0x140012ffc  xor     edx, edx; pftDueTime
0x140012ffe  mov     rcx, rsi; pti
0x140013001  call    cs:__imp_SetThreadpoolTimer
0x140013007  mov     edx, 1; fCancelPendingCallbacks
0x14001300c  mov     rcx, rsi; pti
0x14001300f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013015  mov     rcx, rsi; pti
0x140013018  call    cs:__imp_CloseThreadpoolTimer
0x14001301e  mov     ecx, ebx; dwErrCode
0x140013020  call    cs:__imp_SetLastError
0x140013026  mov     qword ptr [rdi+30h], 0
0x14001302e  mov     rsi, [rdi+38h]
0x140013032  test    rsi, rsi
0x140013035  jz      short loc_14001306F
0x140013037  call    cs:__imp_GetLastError
0x14001303d  mov     ebx, eax
0x14001303f  xor     r9d, r9d; msWindowLength
0x140013042  xor     r8d, r8d; msPeriod
0x140013045  xor     edx, edx; pftDueTime
0x140013047  mov     rcx, rsi; pti
0x14001304a  call    cs:__imp_SetThreadpoolTimer
0x140013050  mov     edx, 1; fCancelPendingCallbacks
0x140013055  mov     rcx, rsi; pti
0x140013058  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001305e  mov     rcx, rsi; pti
0x140013061  call    cs:__imp_CloseThreadpoolTimer
0x140013067  mov     ecx, ebx; dwErrCode
0x140013069  call    cs:__imp_SetLastError
0x14001306f  mov     qword ptr [rdi+38h], 0
0x140013077  mov     rbx, [rdi+100h]
0x14001307e  mov     qword ptr [rdi+100h], 0
0x140013089  test    rbx, rbx
0x14001308c  jz      short loc_1400130A2
0x14001308e  call    cs:__imp_GetProcessHeap
0x140013094  mov     rcx, rax; hHeap
0x140013097  mov     r8, rbx; lpMem
0x14001309a  xor     edx, edx; dwFlags
0x14001309c  call    cs:__imp_HeapFree
0x1400130a2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400130a9  test    r8, r8
0x1400130ac  jz      short loc_1400130C6
0x1400130ae  mov     rdx, cs:qword_1400270F0; SRWLock
0x1400130b5  test    rdx, rdx
0x1400130b8  jz      short loc_1400130C6
0x1400130ba  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400130c1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400130c6  lea     rbx, [rdi+98h]
0x1400130cd  mov     rsi, [rbx+40h]
0x1400130d1  mov     qword ptr [rbx+40h], 0
0x1400130d9  test    rsi, rsi
0x1400130dc  jz      short loc_1400130F2
0x1400130de  call    cs:__imp_GetProcessHeap
0x1400130e4  mov     rcx, rax; hHeap
0x1400130e7  mov     r8, rsi; lpMem
0x1400130ea  xor     edx, edx; dwFlags
0x1400130ec  call    cs:__imp_HeapFree
0x1400130f2  mov     rcx, rbx; lpCriticalSection
0x1400130f5  call    cs:__imp_DeleteCriticalSection
0x1400130fb  lea     rcx, [rdi+90h]
0x140013102  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140013107  mov     rsi, [rdi+88h]
0x14001310e  mov     qword ptr [rdi+88h], 0
0x140013119  test    rsi, rsi
0x14001311c  jz      short loc_140013132
0x14001311e  call    cs:__imp_GetProcessHeap
0x140013124  mov     rcx, rax; hHeap
0x140013127  mov     r8, rsi; lpMem
0x14001312a  xor     edx, edx; dwFlags
0x14001312c  call    cs:__imp_HeapFree
0x140013132  lea     rcx, [rdi+48h]; lpCriticalSection
0x140013136  call    cs:__imp_DeleteCriticalSection
0x14001313c  mov     rbx, [rdi+38h]
0x140013140  test    rbx, rbx
0x140013143  jz      short loc_14001316D
0x140013145  xor     r9d, r9d; msWindowLength
0x140013148  xor     r8d, r8d; msPeriod
0x14001314b  xor     edx, edx; pftDueTime
0x14001314d  mov     rcx, rbx; pti
0x140013150  call    cs:__imp_SetThreadpoolTimer
0x140013156  mov     edx, 1; fCancelPendingCallbacks
0x14001315b  mov     rcx, rbx; pti
0x14001315e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013164  mov     rcx, rbx; pti
0x140013167  call    cs:__imp_CloseThreadpoolTimer
0x14001316d  mov     rbx, [rdi+30h]
0x140013171  test    rbx, rbx
0x140013174  jz      short loc_14001319F
0x140013176  xor     r9d, r9d; msWindowLength
0x140013179  xor     r8d, r8d; msPeriod
0x14001317c  xor     edx, edx; pftDueTime
0x14001317e  mov     rcx, rbx; pti
0x140013181  call    cs:__imp_SetThreadpoolTimer
0x140013187  mov     edx, 1; fCancelPendingCallbacks
0x14001318c  mov     rcx, rbx; pti
0x14001318f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013195  mov     rcx, rbx; pti
0x140013198  call    cs:__imp_CloseThreadpoolTimer
0x14001319e  nop
0x14001319f  mov     rcx, [rdi+10h]; lpMem
0x1400131a3  test    rcx, rcx
0x1400131a6  jz      short loc_1400131AE
0x1400131a8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400131ad  nop
0x1400131ae  mov     rbx, [rsp+28h+arg_0]
0x1400131b3  mov     rsi, [rsp+28h+arg_8]
0x1400131b8  add     rsp, 20h
0x1400131bc  pop     rdi
0x1400131bd  retn
```
