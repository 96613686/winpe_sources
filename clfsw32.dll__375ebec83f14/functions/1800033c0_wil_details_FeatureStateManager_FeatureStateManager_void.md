# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800033c0`
- end: `0x180003582`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `450`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180015d50`

## callees

- `0x1800033c0`
- `0x180006a90`
- `0x1800078b8`
- `0x18000792c`
- `0x18000803c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000345b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000345b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000346f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000346f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000347e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000347e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000350c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000354c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000350c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000354c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000353b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000353b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000351b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000355b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000351b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000355b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v4; // r8
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  struct _TP_TIMER *v11; // rdi
  struct _TP_TIMER *v12; // rdi
  void *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && SRWLock )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&SRWLock[25], SRWLock, v4);
  v5 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 18);
  if ( v8 )
    wil::details::UnregisterWilFeatureConfigurationChange(v8, v7);
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x1800033c0  push    rbx
0x1800033c2  push    rsi
0x1800033c3  push    rdi
0x1800033c4  push    r14
0x1800033c6  push    r15
0x1800033c8  sub     rsp, 20h
0x1800033cc  mov     rbx, rcx
0x1800033cf  mov     byte ptr [rcx], 0
0x1800033d2  add     rcx, 30h ; '0'
0x1800033d6  xor     edx, edx
0x1800033d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800033dd  xor     edx, edx
0x1800033df  lea     rcx, [rbx+38h]
0x1800033e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800033e8  mov     rdi, [rbx+100h]
0x1800033ef  mov     qword ptr [rbx+100h], 0
0x1800033fa  test    rdi, rdi
0x1800033fd  jz      short loc_18000341F
0x1800033ff  call    cs:__imp_GetProcessHeap
0x180003406  nop     dword ptr [rax+rax+00h]
0x18000340b  mov     r8, rdi; lpMem
0x18000340e  xor     edx, edx; dwFlags
0x180003410  mov     rcx, rax; hHeap
0x180003413  call    cs:__imp_HeapFree
0x18000341a  nop     dword ptr [rax+rax+00h]
0x18000341f  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003426  test    r8, r8
0x180003429  jz      short loc_180003443
0x18000342b  mov     rdx, cs:SRWLock; SRWLock
0x180003432  test    rdx, rdx
0x180003435  jz      short loc_180003443
0x180003437  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000343e  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003443  lea     rdi, [rbx+98h]
0x18000344a  mov     rsi, [rdi+40h]
0x18000344e  mov     qword ptr [rdi+40h], 0
0x180003456  test    rsi, rsi
0x180003459  jz      short loc_18000347B
0x18000345b  call    cs:__imp_GetProcessHeap
0x180003462  nop     dword ptr [rax+rax+00h]
0x180003467  mov     r8, rsi; lpMem
0x18000346a  xor     edx, edx; dwFlags
0x18000346c  mov     rcx, rax; hHeap
0x18000346f  call    cs:__imp_HeapFree
0x180003476  nop     dword ptr [rax+rax+00h]
0x18000347b  mov     rcx, rdi; lpCriticalSection
0x18000347e  call    cs:__imp_DeleteCriticalSection
0x180003485  nop     dword ptr [rax+rax+00h]
0x18000348a  mov     rcx, [rbx+90h]; this
0x180003491  test    rcx, rcx
0x180003494  jz      short loc_18000349B
0x180003496  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000349b  mov     rsi, [rbx+88h]
0x1800034a2  mov     qword ptr [rbx+88h], 0
0x1800034ad  test    rsi, rsi
0x1800034b0  jz      short loc_1800034D2
0x1800034b2  call    cs:__imp_GetProcessHeap
0x1800034b9  nop     dword ptr [rax+rax+00h]
0x1800034be  mov     r8, rsi; lpMem
0x1800034c1  xor     edx, edx; dwFlags
0x1800034c3  mov     rcx, rax; hHeap
0x1800034c6  call    cs:__imp_HeapFree
0x1800034cd  nop     dword ptr [rax+rax+00h]
0x1800034d2  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800034d6  call    cs:__imp_DeleteCriticalSection
0x1800034dd  nop     dword ptr [rax+rax+00h]
0x1800034e2  mov     rdi, [rbx+38h]
0x1800034e6  mov     esi, 1
0x1800034eb  test    rdi, rdi
0x1800034ee  jz      short loc_180003527
0x1800034f0  xor     r9d, r9d; msWindowLength
0x1800034f3  xor     r8d, r8d; msPeriod
0x1800034f6  xor     edx, edx; pftDueTime
0x1800034f8  mov     rcx, rdi; pti
0x1800034fb  call    cs:__imp_SetThreadpoolTimer
0x180003502  nop     dword ptr [rax+rax+00h]
0x180003507  mov     edx, esi; fCancelPendingCallbacks
0x180003509  mov     rcx, rdi; pti
0x18000350c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003513  nop     dword ptr [rax+rax+00h]
0x180003518  mov     rcx, rdi; pti
0x18000351b  call    cs:__imp_CloseThreadpoolTimer
0x180003522  nop     dword ptr [rax+rax+00h]
0x180003527  mov     rdi, [rbx+30h]
0x18000352b  test    rdi, rdi
0x18000352e  jz      short loc_180003567
0x180003530  xor     r9d, r9d; msWindowLength
0x180003533  xor     r8d, r8d; msPeriod
0x180003536  xor     edx, edx; pftDueTime
0x180003538  mov     rcx, rdi; pti
0x18000353b  call    cs:__imp_SetThreadpoolTimer
0x180003542  nop     dword ptr [rax+rax+00h]
0x180003547  mov     edx, esi; fCancelPendingCallbacks
0x180003549  mov     rcx, rdi; pti
0x18000354c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003553  nop     dword ptr [rax+rax+00h]
0x180003558  mov     rcx, rdi; pti
0x18000355b  call    cs:__imp_CloseThreadpoolTimer
0x180003562  nop     dword ptr [rax+rax+00h]
0x180003567  mov     rcx, [rbx+10h]; lpMem
0x18000356b  test    rcx, rcx
0x18000356e  jz      short loc_180003575
0x180003570  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003575  add     rsp, 20h
0x180003579  pop     r15
0x18000357b  pop     r14
0x18000357d  pop     rdi
0x18000357e  pop     rsi
0x18000357f  pop     rbx
0x180003580  retn
```
