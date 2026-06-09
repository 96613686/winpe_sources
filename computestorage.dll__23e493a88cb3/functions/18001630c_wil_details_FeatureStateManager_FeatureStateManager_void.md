# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001630c`
- end: `0x1800164d0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044ef0`

## callees

- `0x18001630c`
- `0x1800188f0`
- `0x180018f50`
- `0x180018fc4`
- `0x180019f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016422`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001634b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001634b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001635f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001635f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016412`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016458`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016498`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016458`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016498`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016447`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016487`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016447`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016487`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016467`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800164a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016467`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800164a7`

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
0x18001630c  push    rbx
0x18001630e  push    rsi
0x18001630f  push    rdi
0x180016310  push    r14
0x180016312  push    r15
0x180016314  sub     rsp, 20h
0x180016318  mov     rbx, rcx
0x18001631b  mov     byte ptr [rcx], 0
0x18001631e  xor     edx, edx
0x180016320  add     rcx, 30h ; '0'
0x180016324  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016329  xor     edx, edx
0x18001632b  lea     rcx, [rbx+38h]
0x18001632f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016334  mov     rdi, [rbx+100h]
0x18001633b  mov     qword ptr [rbx+100h], 0
0x180016346  test    rdi, rdi
0x180016349  jz      short loc_18001636B
0x18001634b  call    cs:__imp_GetProcessHeap
0x180016352  nop     dword ptr [rax+rax+00h]
0x180016357  mov     rcx, rax; hHeap
0x18001635a  mov     r8, rdi; lpMem
0x18001635d  xor     edx, edx; dwFlags
0x18001635f  call    cs:__imp_HeapFree
0x180016366  nop     dword ptr [rax+rax+00h]
0x18001636b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180016372  test    r8, r8
0x180016375  jz      short loc_18001638F
0x180016377  mov     rdx, cs:SRWLock; SRWLock
0x18001637e  test    rdx, rdx
0x180016381  jz      short loc_18001638F
0x180016383  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001638a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001638f  lea     rdi, [rbx+98h]
0x180016396  mov     rsi, [rdi+40h]
0x18001639a  mov     qword ptr [rdi+40h], 0
0x1800163a2  test    rsi, rsi
0x1800163a5  jz      short loc_1800163C7
0x1800163a7  call    cs:__imp_GetProcessHeap
0x1800163ae  nop     dword ptr [rax+rax+00h]
0x1800163b3  mov     rcx, rax; hHeap
0x1800163b6  mov     r8, rsi; lpMem
0x1800163b9  xor     edx, edx; dwFlags
0x1800163bb  call    cs:__imp_HeapFree
0x1800163c2  nop     dword ptr [rax+rax+00h]
0x1800163c7  mov     rcx, rdi; lpCriticalSection
0x1800163ca  call    cs:__imp_DeleteCriticalSection
0x1800163d1  nop     dword ptr [rax+rax+00h]
0x1800163d6  mov     rcx, [rbx+90h]; this
0x1800163dd  test    rcx, rcx
0x1800163e0  jz      short loc_1800163E7
0x1800163e2  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800163e7  mov     rsi, [rbx+88h]
0x1800163ee  mov     qword ptr [rbx+88h], 0
0x1800163f9  test    rsi, rsi
0x1800163fc  jz      short loc_18001641E
0x1800163fe  call    cs:__imp_GetProcessHeap
0x180016405  nop     dword ptr [rax+rax+00h]
0x18001640a  mov     rcx, rax; hHeap
0x18001640d  mov     r8, rsi; lpMem
0x180016410  xor     edx, edx; dwFlags
0x180016412  call    cs:__imp_HeapFree
0x180016419  nop     dword ptr [rax+rax+00h]
0x18001641e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180016422  call    cs:__imp_DeleteCriticalSection
0x180016429  nop     dword ptr [rax+rax+00h]
0x18001642e  mov     rdi, [rbx+38h]
0x180016432  mov     esi, 1
0x180016437  test    rdi, rdi
0x18001643a  jz      short loc_180016473
0x18001643c  xor     r9d, r9d; msWindowLength
0x18001643f  xor     r8d, r8d; msPeriod
0x180016442  xor     edx, edx; pftDueTime
0x180016444  mov     rcx, rdi; pti
0x180016447  call    cs:__imp_SetThreadpoolTimer
0x18001644e  nop     dword ptr [rax+rax+00h]
0x180016453  mov     edx, esi; fCancelPendingCallbacks
0x180016455  mov     rcx, rdi; pti
0x180016458  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001645f  nop     dword ptr [rax+rax+00h]
0x180016464  mov     rcx, rdi; pti
0x180016467  call    cs:__imp_CloseThreadpoolTimer
0x18001646e  nop     dword ptr [rax+rax+00h]
0x180016473  mov     rdi, [rbx+30h]
0x180016477  test    rdi, rdi
0x18001647a  jz      short loc_1800164B4
0x18001647c  xor     r9d, r9d; msWindowLength
0x18001647f  xor     r8d, r8d; msPeriod
0x180016482  xor     edx, edx; pftDueTime
0x180016484  mov     rcx, rdi; pti
0x180016487  call    cs:__imp_SetThreadpoolTimer
0x18001648e  nop     dword ptr [rax+rax+00h]
0x180016493  mov     edx, esi; fCancelPendingCallbacks
0x180016495  mov     rcx, rdi; pti
0x180016498  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001649f  nop     dword ptr [rax+rax+00h]
0x1800164a4  mov     rcx, rdi; pti
0x1800164a7  call    cs:__imp_CloseThreadpoolTimer
0x1800164ae  nop     dword ptr [rax+rax+00h]
0x1800164b3  nop
0x1800164b4  mov     rcx, [rbx+10h]; lpMem
0x1800164b8  test    rcx, rcx
0x1800164bb  jz      short loc_1800164C3
0x1800164bd  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800164c2  nop
0x1800164c3  add     rsp, 20h
0x1800164c7  pop     r15
0x1800164c9  pop     r14
0x1800164cb  pop     rdi
0x1800164cc  pop     rsi
0x1800164cd  pop     rbx
0x1800164ce  retn
```
