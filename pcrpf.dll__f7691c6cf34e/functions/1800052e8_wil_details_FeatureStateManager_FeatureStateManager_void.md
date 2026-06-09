# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800052e8`
- end: `0x1800054ac`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180058a60`

## callees

- `0x1800052e8`
- `0x180009600`
- `0x18000aec4`
- `0x18000af38`
- `0x18000b8a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000533b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000533b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005423`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005423`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005463`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005434`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005474`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005434`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005474`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005443`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005483`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005443`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005483`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
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
  if ( v4 && qword_180072360 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180072360[25], qword_180072360, v4);
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
0x1800052e8  push    rbx
0x1800052ea  push    rsi
0x1800052eb  push    rdi
0x1800052ec  push    r14
0x1800052ee  push    r15
0x1800052f0  sub     rsp, 20h
0x1800052f4  mov     rbx, rcx
0x1800052f7  mov     byte ptr [rcx], 0
0x1800052fa  xor     edx, edx
0x1800052fc  add     rcx, 30h ; '0'
0x180005300  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005305  xor     edx, edx
0x180005307  lea     rcx, [rbx+38h]
0x18000530b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005310  mov     rdi, [rbx+100h]
0x180005317  mov     qword ptr [rbx+100h], 0
0x180005322  test    rdi, rdi
0x180005325  jz      short loc_180005347
0x180005327  call    cs:__imp_GetProcessHeap
0x18000532e  nop     dword ptr [rax+rax+00h]
0x180005333  mov     rcx, rax; hHeap
0x180005336  mov     r8, rdi; lpMem
0x180005339  xor     edx, edx; dwFlags
0x18000533b  call    cs:__imp_HeapFree
0x180005342  nop     dword ptr [rax+rax+00h]
0x180005347  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000534e  test    r8, r8
0x180005351  jz      short loc_18000536B
0x180005353  mov     rdx, cs:qword_180072360; SRWLock
0x18000535a  test    rdx, rdx
0x18000535d  jz      short loc_18000536B
0x18000535f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005366  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000536b  lea     rdi, [rbx+98h]
0x180005372  mov     rsi, [rdi+40h]
0x180005376  mov     qword ptr [rdi+40h], 0
0x18000537e  test    rsi, rsi
0x180005381  jz      short loc_1800053A3
0x180005383  call    cs:__imp_GetProcessHeap
0x18000538a  nop     dword ptr [rax+rax+00h]
0x18000538f  mov     rcx, rax; hHeap
0x180005392  mov     r8, rsi; lpMem
0x180005395  xor     edx, edx; dwFlags
0x180005397  call    cs:__imp_HeapFree
0x18000539e  nop     dword ptr [rax+rax+00h]
0x1800053a3  mov     rcx, rdi; lpCriticalSection
0x1800053a6  call    cs:__imp_DeleteCriticalSection
0x1800053ad  nop     dword ptr [rax+rax+00h]
0x1800053b2  mov     rcx, [rbx+90h]; this
0x1800053b9  test    rcx, rcx
0x1800053bc  jz      short loc_1800053C3
0x1800053be  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800053c3  mov     rsi, [rbx+88h]
0x1800053ca  mov     qword ptr [rbx+88h], 0
0x1800053d5  test    rsi, rsi
0x1800053d8  jz      short loc_1800053FA
0x1800053da  call    cs:__imp_GetProcessHeap
0x1800053e1  nop     dword ptr [rax+rax+00h]
0x1800053e6  mov     rcx, rax; hHeap
0x1800053e9  mov     r8, rsi; lpMem
0x1800053ec  xor     edx, edx; dwFlags
0x1800053ee  call    cs:__imp_HeapFree
0x1800053f5  nop     dword ptr [rax+rax+00h]
0x1800053fa  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800053fe  call    cs:__imp_DeleteCriticalSection
0x180005405  nop     dword ptr [rax+rax+00h]
0x18000540a  mov     rdi, [rbx+38h]
0x18000540e  mov     esi, 1
0x180005413  test    rdi, rdi
0x180005416  jz      short loc_18000544F
0x180005418  xor     r9d, r9d; msWindowLength
0x18000541b  xor     r8d, r8d; msPeriod
0x18000541e  xor     edx, edx; pftDueTime
0x180005420  mov     rcx, rdi; pti
0x180005423  call    cs:__imp_SetThreadpoolTimer
0x18000542a  nop     dword ptr [rax+rax+00h]
0x18000542f  mov     edx, esi; fCancelPendingCallbacks
0x180005431  mov     rcx, rdi; pti
0x180005434  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000543b  nop     dword ptr [rax+rax+00h]
0x180005440  mov     rcx, rdi; pti
0x180005443  call    cs:__imp_CloseThreadpoolTimer
0x18000544a  nop     dword ptr [rax+rax+00h]
0x18000544f  mov     rdi, [rbx+30h]
0x180005453  test    rdi, rdi
0x180005456  jz      short loc_180005490
0x180005458  xor     r9d, r9d; msWindowLength
0x18000545b  xor     r8d, r8d; msPeriod
0x18000545e  xor     edx, edx; pftDueTime
0x180005460  mov     rcx, rdi; pti
0x180005463  call    cs:__imp_SetThreadpoolTimer
0x18000546a  nop     dword ptr [rax+rax+00h]
0x18000546f  mov     edx, esi; fCancelPendingCallbacks
0x180005471  mov     rcx, rdi; pti
0x180005474  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000547b  nop     dword ptr [rax+rax+00h]
0x180005480  mov     rcx, rdi; pti
0x180005483  call    cs:__imp_CloseThreadpoolTimer
0x18000548a  nop     dword ptr [rax+rax+00h]
0x18000548f  nop
0x180005490  mov     rcx, [rbx+10h]; lpMem
0x180005494  test    rcx, rcx
0x180005497  jz      short loc_18000549F
0x180005499  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000549e  nop
0x18000549f  add     rsp, 20h
0x1800054a3  pop     r15
0x1800054a5  pop     r14
0x1800054a7  pop     rdi
0x1800054a8  pop     rsi
0x1800054a9  pop     rbx
0x1800054aa  retn
```
