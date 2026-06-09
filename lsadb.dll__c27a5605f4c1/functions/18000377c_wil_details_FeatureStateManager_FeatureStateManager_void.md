# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000377c`
- end: `0x180003968`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003aee0`

## callees

- `0x1800034ec`
- `0x18000377c`
- `0x180007904`
- `0x180008634`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000383a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000383a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000379a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000379a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000380d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003913`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003944`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000380d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003913`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003944`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000392d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000392d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003804`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000390a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000393b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003804`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000390a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000393b`

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
  if ( v8 && qword_180047508 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180047508[25], qword_180047508, v8);
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
0x18000377c  mov     [rsp+arg_0], rbx
0x180003781  mov     [rsp+arg_8], rsi
0x180003786  push    rdi
0x180003787  sub     rsp, 20h
0x18000378b  mov     byte ptr [rcx], 0
0x18000378e  mov     rdi, rcx
0x180003791  mov     rsi, [rcx+30h]
0x180003795  test    rsi, rsi
0x180003798  jz      short loc_1800037D2
0x18000379a  call    cs:__imp_GetLastError
0x1800037a0  xor     r9d, r9d; msWindowLength
0x1800037a3  xor     r8d, r8d; msPeriod
0x1800037a6  xor     edx, edx; pftDueTime
0x1800037a8  mov     rcx, rsi; pti
0x1800037ab  mov     ebx, eax
0x1800037ad  call    cs:__imp_SetThreadpoolTimer
0x1800037b3  mov     edx, 1; fCancelPendingCallbacks
0x1800037b8  mov     rcx, rsi; pti
0x1800037bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037c1  mov     rcx, rsi; pti
0x1800037c4  call    cs:__imp_CloseThreadpoolTimer
0x1800037ca  mov     ecx, ebx; dwErrCode
0x1800037cc  call    cs:__imp_SetLastError
0x1800037d2  mov     qword ptr [rdi+30h], 0
0x1800037da  mov     rsi, [rdi+38h]
0x1800037de  test    rsi, rsi
0x1800037e1  jz      short loc_18000381B
0x1800037e3  call    cs:__imp_GetLastError
0x1800037e9  xor     r9d, r9d; msWindowLength
0x1800037ec  xor     r8d, r8d; msPeriod
0x1800037ef  xor     edx, edx; pftDueTime
0x1800037f1  mov     rcx, rsi; pti
0x1800037f4  mov     ebx, eax
0x1800037f6  call    cs:__imp_SetThreadpoolTimer
0x1800037fc  mov     edx, 1; fCancelPendingCallbacks
0x180003801  mov     rcx, rsi; pti
0x180003804  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000380a  mov     rcx, rsi; pti
0x18000380d  call    cs:__imp_CloseThreadpoolTimer
0x180003813  mov     ecx, ebx; dwErrCode
0x180003815  call    cs:__imp_SetLastError
0x18000381b  mov     qword ptr [rdi+38h], 0
0x180003823  mov     rbx, [rdi+100h]
0x18000382a  mov     qword ptr [rdi+100h], 0
0x180003835  test    rbx, rbx
0x180003838  jz      short loc_18000384E
0x18000383a  call    cs:__imp_GetProcessHeap
0x180003840  mov     r8, rbx; lpMem
0x180003843  xor     edx, edx; dwFlags
0x180003845  mov     rcx, rax; hHeap
0x180003848  call    cs:__imp_HeapFree
0x18000384e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003855  test    r8, r8
0x180003858  jz      short loc_180003872
0x18000385a  mov     rdx, cs:qword_180047508; SRWLock
0x180003861  test    rdx, rdx
0x180003864  jz      short loc_180003872
0x180003866  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000386d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003872  lea     rbx, [rdi+98h]
0x180003879  mov     rsi, [rbx+40h]
0x18000387d  mov     qword ptr [rbx+40h], 0
0x180003885  test    rsi, rsi
0x180003888  jz      short loc_18000389E
0x18000388a  call    cs:__imp_GetProcessHeap
0x180003890  mov     r8, rsi; lpMem
0x180003893  xor     edx, edx; dwFlags
0x180003895  mov     rcx, rax; hHeap
0x180003898  call    cs:__imp_HeapFree
0x18000389e  mov     rcx, rbx; lpCriticalSection
0x1800038a1  call    cs:__imp_DeleteCriticalSection
0x1800038a7  lea     rcx, [rdi+90h]
0x1800038ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800038b3  mov     rsi, [rdi+88h]
0x1800038ba  mov     qword ptr [rdi+88h], 0
0x1800038c5  test    rsi, rsi
0x1800038c8  jz      short loc_1800038DE
0x1800038ca  call    cs:__imp_GetProcessHeap
0x1800038d0  mov     r8, rsi; lpMem
0x1800038d3  xor     edx, edx; dwFlags
0x1800038d5  mov     rcx, rax; hHeap
0x1800038d8  call    cs:__imp_HeapFree
0x1800038de  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800038e2  call    cs:__imp_DeleteCriticalSection
0x1800038e8  mov     rbx, [rdi+38h]
0x1800038ec  test    rbx, rbx
0x1800038ef  jz      short loc_180003919
0x1800038f1  xor     r9d, r9d; msWindowLength
0x1800038f4  xor     r8d, r8d; msPeriod
0x1800038f7  xor     edx, edx; pftDueTime
0x1800038f9  mov     rcx, rbx; pti
0x1800038fc  call    cs:__imp_SetThreadpoolTimer
0x180003902  mov     edx, 1; fCancelPendingCallbacks
0x180003907  mov     rcx, rbx; pti
0x18000390a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003910  mov     rcx, rbx; pti
0x180003913  call    cs:__imp_CloseThreadpoolTimer
0x180003919  mov     rbx, [rdi+30h]
0x18000391d  test    rbx, rbx
0x180003920  jz      short loc_18000394A
0x180003922  xor     r9d, r9d; msWindowLength
0x180003925  xor     r8d, r8d; msPeriod
0x180003928  xor     edx, edx; pftDueTime
0x18000392a  mov     rcx, rbx; pti
0x18000392d  call    cs:__imp_SetThreadpoolTimer
0x180003933  mov     edx, 1; fCancelPendingCallbacks
0x180003938  mov     rcx, rbx; pti
0x18000393b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003941  mov     rcx, rbx; pti
0x180003944  call    cs:__imp_CloseThreadpoolTimer
0x18000394a  mov     rcx, [rdi+10h]; lpMem
0x18000394e  test    rcx, rcx
0x180003951  jz      short loc_180003958
0x180003953  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003958  mov     rbx, [rsp+28h+arg_0]
0x18000395d  mov     rsi, [rsp+28h+arg_8]
0x180003962  add     rsp, 20h
0x180003966  pop     rdi
0x180003967  retn
```
