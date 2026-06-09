# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800176d4`
- end: `0x180017898`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800c8950`

## callees

- `0x1800176d4`
- `0x18001e930`
- `0x18002083c`
- `0x1800208b0`
- `0x180021d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017792`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800177ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017792`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800177ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001776f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800177c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001776f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800177c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001780f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001784f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001780f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001784f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001782f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001786f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001782f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001786f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017820`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017860`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017820`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017860`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v4 && qword_1801080D0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1801080D0[25], qword_1801080D0, v4);
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
0x1800176d4  push    rbx
0x1800176d6  push    rsi
0x1800176d7  push    rdi
0x1800176d8  push    r14
0x1800176da  push    r15
0x1800176dc  sub     rsp, 20h
0x1800176e0  mov     rbx, rcx
0x1800176e3  mov     byte ptr [rcx], 0
0x1800176e6  xor     edx, edx
0x1800176e8  add     rcx, 30h ; '0'
0x1800176ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800176f1  xor     edx, edx
0x1800176f3  lea     rcx, [rbx+38h]
0x1800176f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800176fc  mov     rdi, [rbx+100h]
0x180017703  mov     qword ptr [rbx+100h], 0
0x18001770e  test    rdi, rdi
0x180017711  jz      short loc_180017733
0x180017713  call    cs:__imp_GetProcessHeap
0x18001771a  nop     dword ptr [rax+rax+00h]
0x18001771f  mov     rcx, rax; hHeap
0x180017722  mov     r8, rdi; lpMem
0x180017725  xor     edx, edx; dwFlags
0x180017727  call    cs:__imp_HeapFree
0x18001772e  nop     dword ptr [rax+rax+00h]
0x180017733  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18001773a  test    r8, r8
0x18001773d  jz      short loc_180017757
0x18001773f  mov     rdx, cs:qword_1801080D0; SRWLock
0x180017746  test    rdx, rdx
0x180017749  jz      short loc_180017757
0x18001774b  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180017752  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180017757  lea     rdi, [rbx+98h]
0x18001775e  mov     rsi, [rdi+40h]
0x180017762  mov     qword ptr [rdi+40h], 0
0x18001776a  test    rsi, rsi
0x18001776d  jz      short loc_18001778F
0x18001776f  call    cs:__imp_GetProcessHeap
0x180017776  nop     dword ptr [rax+rax+00h]
0x18001777b  mov     rcx, rax; hHeap
0x18001777e  mov     r8, rsi; lpMem
0x180017781  xor     edx, edx; dwFlags
0x180017783  call    cs:__imp_HeapFree
0x18001778a  nop     dword ptr [rax+rax+00h]
0x18001778f  mov     rcx, rdi; lpCriticalSection
0x180017792  call    cs:__imp_DeleteCriticalSection
0x180017799  nop     dword ptr [rax+rax+00h]
0x18001779e  mov     rcx, [rbx+90h]; this
0x1800177a5  test    rcx, rcx
0x1800177a8  jz      short loc_1800177AF
0x1800177aa  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800177af  mov     rsi, [rbx+88h]
0x1800177b6  mov     qword ptr [rbx+88h], 0
0x1800177c1  test    rsi, rsi
0x1800177c4  jz      short loc_1800177E6
0x1800177c6  call    cs:__imp_GetProcessHeap
0x1800177cd  nop     dword ptr [rax+rax+00h]
0x1800177d2  mov     rcx, rax; hHeap
0x1800177d5  mov     r8, rsi; lpMem
0x1800177d8  xor     edx, edx; dwFlags
0x1800177da  call    cs:__imp_HeapFree
0x1800177e1  nop     dword ptr [rax+rax+00h]
0x1800177e6  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800177ea  call    cs:__imp_DeleteCriticalSection
0x1800177f1  nop     dword ptr [rax+rax+00h]
0x1800177f6  mov     rdi, [rbx+38h]
0x1800177fa  mov     esi, 1
0x1800177ff  test    rdi, rdi
0x180017802  jz      short loc_18001783B
0x180017804  xor     r9d, r9d; msWindowLength
0x180017807  xor     r8d, r8d; msPeriod
0x18001780a  xor     edx, edx; pftDueTime
0x18001780c  mov     rcx, rdi; pti
0x18001780f  call    cs:__imp_SetThreadpoolTimer
0x180017816  nop     dword ptr [rax+rax+00h]
0x18001781b  mov     edx, esi; fCancelPendingCallbacks
0x18001781d  mov     rcx, rdi; pti
0x180017820  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017827  nop     dword ptr [rax+rax+00h]
0x18001782c  mov     rcx, rdi; pti
0x18001782f  call    cs:__imp_CloseThreadpoolTimer
0x180017836  nop     dword ptr [rax+rax+00h]
0x18001783b  mov     rdi, [rbx+30h]
0x18001783f  test    rdi, rdi
0x180017842  jz      short loc_18001787C
0x180017844  xor     r9d, r9d; msWindowLength
0x180017847  xor     r8d, r8d; msPeriod
0x18001784a  xor     edx, edx; pftDueTime
0x18001784c  mov     rcx, rdi; pti
0x18001784f  call    cs:__imp_SetThreadpoolTimer
0x180017856  nop     dword ptr [rax+rax+00h]
0x18001785b  mov     edx, esi; fCancelPendingCallbacks
0x18001785d  mov     rcx, rdi; pti
0x180017860  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017867  nop     dword ptr [rax+rax+00h]
0x18001786c  mov     rcx, rdi; pti
0x18001786f  call    cs:__imp_CloseThreadpoolTimer
0x180017876  nop     dword ptr [rax+rax+00h]
0x18001787b  nop
0x18001787c  mov     rcx, [rbx+10h]; lpMem
0x180017880  test    rcx, rcx
0x180017883  jz      short loc_18001788B
0x180017885  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18001788a  nop
0x18001788b  add     rsp, 20h
0x18001788f  pop     r15
0x180017891  pop     r14
0x180017893  pop     rdi
0x180017894  pop     rsi
0x180017895  pop     rbx
0x180017896  retn
```
