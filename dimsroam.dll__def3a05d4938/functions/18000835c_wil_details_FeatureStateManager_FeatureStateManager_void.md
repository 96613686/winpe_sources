# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000835c`
- end: `0x180008548`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000dcc0`

## callees

- `0x180008218`
- `0x18000835c`
- `0x18000b8d0`
- `0x18000c4dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000837a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000837a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008481`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008481`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008428`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008478`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008428`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008478`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000841a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000846a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000841a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000846a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008524`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008524`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000838d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000850d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000838d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000850d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000839b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000851b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000839b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000851b`

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
  if ( v8 && qword_180013038 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180013038[25], qword_180013038, v8);
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
0x18000835c  mov     [rsp+arg_0], rbx
0x180008361  mov     [rsp+arg_8], rsi
0x180008366  push    rdi
0x180008367  sub     rsp, 20h
0x18000836b  mov     byte ptr [rcx], 0
0x18000836e  mov     rdi, rcx
0x180008371  mov     rsi, [rcx+30h]
0x180008375  test    rsi, rsi
0x180008378  jz      short loc_1800083B2
0x18000837a  call    cs:__imp_GetLastError
0x180008380  xor     r9d, r9d; msWindowLength
0x180008383  xor     r8d, r8d; msPeriod
0x180008386  xor     edx, edx; pftDueTime
0x180008388  mov     rcx, rsi; pti
0x18000838b  mov     ebx, eax
0x18000838d  call    cs:__imp_SetThreadpoolTimer
0x180008393  mov     edx, 1; fCancelPendingCallbacks
0x180008398  mov     rcx, rsi; pti
0x18000839b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083a1  mov     rcx, rsi; pti
0x1800083a4  call    cs:__imp_CloseThreadpoolTimer
0x1800083aa  mov     ecx, ebx; dwErrCode
0x1800083ac  call    cs:__imp_SetLastError
0x1800083b2  mov     qword ptr [rdi+30h], 0
0x1800083ba  mov     rsi, [rdi+38h]
0x1800083be  test    rsi, rsi
0x1800083c1  jz      short loc_1800083FB
0x1800083c3  call    cs:__imp_GetLastError
0x1800083c9  xor     r9d, r9d; msWindowLength
0x1800083cc  xor     r8d, r8d; msPeriod
0x1800083cf  xor     edx, edx; pftDueTime
0x1800083d1  mov     rcx, rsi; pti
0x1800083d4  mov     ebx, eax
0x1800083d6  call    cs:__imp_SetThreadpoolTimer
0x1800083dc  mov     edx, 1; fCancelPendingCallbacks
0x1800083e1  mov     rcx, rsi; pti
0x1800083e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083ea  mov     rcx, rsi; pti
0x1800083ed  call    cs:__imp_CloseThreadpoolTimer
0x1800083f3  mov     ecx, ebx; dwErrCode
0x1800083f5  call    cs:__imp_SetLastError
0x1800083fb  mov     qword ptr [rdi+38h], 0
0x180008403  mov     rbx, [rdi+100h]
0x18000840a  mov     qword ptr [rdi+100h], 0
0x180008415  test    rbx, rbx
0x180008418  jz      short loc_18000842E
0x18000841a  call    cs:__imp_GetProcessHeap
0x180008420  mov     r8, rbx; lpMem
0x180008423  xor     edx, edx; dwFlags
0x180008425  mov     rcx, rax; hHeap
0x180008428  call    cs:__imp_HeapFree
0x18000842e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008435  test    r8, r8
0x180008438  jz      short loc_180008452
0x18000843a  mov     rdx, cs:qword_180013038; SRWLock
0x180008441  test    rdx, rdx
0x180008444  jz      short loc_180008452
0x180008446  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000844d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008452  lea     rbx, [rdi+98h]
0x180008459  mov     rsi, [rbx+40h]
0x18000845d  mov     qword ptr [rbx+40h], 0
0x180008465  test    rsi, rsi
0x180008468  jz      short loc_18000847E
0x18000846a  call    cs:__imp_GetProcessHeap
0x180008470  mov     r8, rsi; lpMem
0x180008473  xor     edx, edx; dwFlags
0x180008475  mov     rcx, rax; hHeap
0x180008478  call    cs:__imp_HeapFree
0x18000847e  mov     rcx, rbx; lpCriticalSection
0x180008481  call    cs:__imp_DeleteCriticalSection
0x180008487  lea     rcx, [rdi+90h]
0x18000848e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008493  mov     rsi, [rdi+88h]
0x18000849a  mov     qword ptr [rdi+88h], 0
0x1800084a5  test    rsi, rsi
0x1800084a8  jz      short loc_1800084BE
0x1800084aa  call    cs:__imp_GetProcessHeap
0x1800084b0  mov     r8, rsi; lpMem
0x1800084b3  xor     edx, edx; dwFlags
0x1800084b5  mov     rcx, rax; hHeap
0x1800084b8  call    cs:__imp_HeapFree
0x1800084be  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800084c2  call    cs:__imp_DeleteCriticalSection
0x1800084c8  mov     rbx, [rdi+38h]
0x1800084cc  test    rbx, rbx
0x1800084cf  jz      short loc_1800084F9
0x1800084d1  xor     r9d, r9d; msWindowLength
0x1800084d4  xor     r8d, r8d; msPeriod
0x1800084d7  xor     edx, edx; pftDueTime
0x1800084d9  mov     rcx, rbx; pti
0x1800084dc  call    cs:__imp_SetThreadpoolTimer
0x1800084e2  mov     edx, 1; fCancelPendingCallbacks
0x1800084e7  mov     rcx, rbx; pti
0x1800084ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800084f0  mov     rcx, rbx; pti
0x1800084f3  call    cs:__imp_CloseThreadpoolTimer
0x1800084f9  mov     rbx, [rdi+30h]
0x1800084fd  test    rbx, rbx
0x180008500  jz      short loc_18000852A
0x180008502  xor     r9d, r9d; msWindowLength
0x180008505  xor     r8d, r8d; msPeriod
0x180008508  xor     edx, edx; pftDueTime
0x18000850a  mov     rcx, rbx; pti
0x18000850d  call    cs:__imp_SetThreadpoolTimer
0x180008513  mov     edx, 1; fCancelPendingCallbacks
0x180008518  mov     rcx, rbx; pti
0x18000851b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008521  mov     rcx, rbx; pti
0x180008524  call    cs:__imp_CloseThreadpoolTimer
0x18000852a  mov     rcx, [rdi+10h]; lpMem
0x18000852e  test    rcx, rcx
0x180008531  jz      short loc_180008538
0x180008533  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008538  mov     rbx, [rsp+28h+arg_0]
0x18000853d  mov     rsi, [rsp+28h+arg_8]
0x180008542  add     rsp, 20h
0x180008546  pop     rdi
0x180008547  retn
```
