# wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(void)

- ea: `0x180029580`
- end: `0x180029706`
- name: `?destroy@?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@wil@@QEAAXXZ`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f860`

## callees

- `0x1800226a0`
- `0x180027550`
- `0x180028a30`
- `0x180029580`
- `0x180029820`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002963c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002967d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002963c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002967d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800295f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002962f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029673`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800295f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002962f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029665`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029665`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029697`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800296c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029697`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800296c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800296a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800296d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800296a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800296d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800296ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800296df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800296ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800296df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(__int64 a1)
{
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v2; // rdx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  wil::details *v5; // rcx
  void *v6; // rsi
  HANDLE v7; // rax
  void *v8; // rsi
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rdi
  struct _TP_TIMER *v11; // rdi
  void *v12; // rcx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    *(_BYTE *)a1 = 0;
  }
  else
  {
    *(_BYTE *)a1 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      a1 + 48,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      a1 + 56,
      0);
    v3 = *(void **)(a1 + 256);
    *(_QWORD *)(a1 + 256) = 0;
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    v5 = *(wil::details **)(a1 + 224);
    if ( v5 )
      wil::details::UnsubscribeProcessWideUsageFlush(v5, v2);
    v6 = *(void **)(a1 + 216);
    *(_QWORD *)(a1 + 216) = 0;
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(a1 + 144);
    v8 = *(void **)(a1 + 136);
    *(_QWORD *)(a1 + 136) = 0;
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
    v10 = *(struct _TP_TIMER **)(a1 + 56);
    if ( v10 )
    {
      SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 56), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v10, 1);
      CloseThreadpoolTimer(v10);
    }
    v11 = *(struct _TP_TIMER **)(a1 + 48);
    if ( v11 )
    {
      SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 48), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v11, 1);
      CloseThreadpoolTimer(v11);
    }
  }
  v12 = *(void **)(a1 + 16);
  if ( v12 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v12);
}

```

## disassembly

```asm
0x180029580  push    rbx
0x180029582  push    rsi
0x180029583  push    rdi
0x180029584  push    r14
0x180029586  push    r15
0x180029588  sub     rsp, 20h
0x18002958c  mov     rbx, rcx
0x18002958f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180029596  jnz     loc_1800296E8
0x18002959c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800295a3  test    rax, rax
0x1800295a6  jz      short loc_1800295B5
0x1800295a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295ad  test    al, al
0x1800295af  jnz     loc_1800296E8
0x1800295b5  mov     byte ptr [rbx], 0
0x1800295b8  xor     edx, edx
0x1800295ba  lea     rcx, [rbx+30h]
0x1800295be  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800295c3  xor     edx, edx
0x1800295c5  lea     rcx, [rbx+38h]
0x1800295c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800295ce  mov     rdi, [rbx+100h]
0x1800295d5  mov     qword ptr [rbx+100h], 0
0x1800295e0  test    rdi, rdi
0x1800295e3  jz      short loc_1800295F9
0x1800295e5  call    cs:__imp_GetProcessHeap
0x1800295eb  mov     rcx, rax; hHeap
0x1800295ee  mov     r8, rdi; lpMem
0x1800295f1  xor     edx, edx; dwFlags
0x1800295f3  call    cs:__imp_HeapFree
0x1800295f9  mov     rcx, [rbx+0E0h]; this
0x180029600  test    rcx, rcx
0x180029603  jz      short loc_18002960A
0x180029605  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18002960a  mov     rsi, [rbx+0D8h]
0x180029611  mov     qword ptr [rbx+0D8h], 0
0x18002961c  test    rsi, rsi
0x18002961f  jz      short loc_180029635
0x180029621  call    cs:__imp_GetProcessHeap
0x180029627  mov     rcx, rax; hHeap
0x18002962a  mov     r8, rsi; lpMem
0x18002962d  xor     edx, edx; dwFlags
0x18002962f  call    cs:__imp_HeapFree
0x180029635  lea     rcx, [rbx+98h]; lpCriticalSection
0x18002963c  call    cs:__imp_DeleteCriticalSection
0x180029642  lea     rcx, [rbx+90h]
0x180029649  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002964e  mov     rsi, [rbx+88h]
0x180029655  mov     qword ptr [rbx+88h], 0
0x180029660  test    rsi, rsi
0x180029663  jz      short loc_180029679
0x180029665  call    cs:__imp_GetProcessHeap
0x18002966b  mov     rcx, rax; hHeap
0x18002966e  mov     r8, rsi; lpMem
0x180029671  xor     edx, edx; dwFlags
0x180029673  call    cs:__imp_HeapFree
0x180029679  lea     rcx, [rbx+48h]; lpCriticalSection
0x18002967d  call    cs:__imp_DeleteCriticalSection
0x180029683  mov     rdi, [rbx+38h]
0x180029687  test    rdi, rdi
0x18002968a  jz      short loc_1800296B4
0x18002968c  xor     r9d, r9d; msWindowLength
0x18002968f  xor     r8d, r8d; msPeriod
0x180029692  xor     edx, edx; pftDueTime
0x180029694  mov     rcx, rdi; pti
0x180029697  call    cs:__imp_SetThreadpoolTimer
0x18002969d  mov     edx, 1; fCancelPendingCallbacks
0x1800296a2  mov     rcx, rdi; pti
0x1800296a5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800296ab  mov     rcx, rdi; pti
0x1800296ae  call    cs:__imp_CloseThreadpoolTimer
0x1800296b4  mov     rdi, [rbx+30h]
0x1800296b8  test    rdi, rdi
0x1800296bb  jz      short loc_1800296E6
0x1800296bd  xor     r9d, r9d; msWindowLength
0x1800296c0  xor     r8d, r8d; msPeriod
0x1800296c3  xor     edx, edx; pftDueTime
0x1800296c5  mov     rcx, rdi; pti
0x1800296c8  call    cs:__imp_SetThreadpoolTimer
0x1800296ce  mov     edx, 1; fCancelPendingCallbacks
0x1800296d3  mov     rcx, rdi; pti
0x1800296d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800296dc  mov     rcx, rdi; pti
0x1800296df  call    cs:__imp_CloseThreadpoolTimer
0x1800296e5  nop
0x1800296e6  jmp     short loc_1800296EB
0x1800296e8  mov     byte ptr [rbx], 0
0x1800296eb  mov     rcx, [rbx+10h]; lpMem
0x1800296ef  test    rcx, rcx
0x1800296f2  jz      short loc_1800296FA
0x1800296f4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800296f9  nop
0x1800296fa  add     rsp, 20h
0x1800296fe  pop     r15
0x180029700  pop     r14
0x180029702  pop     rdi
0x180029703  pop     rsi
0x180029704  pop     rbx
0x180029705  retn
```
