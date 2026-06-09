# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000377c`
- end: `0x140003940`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14004bfc0`

## callees

- `0x14000377c`
- `0x1400074a8`
- `0x140008918`
- `0x14000898c`
- `0x140009900`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400037cf`
- `KERNEL32!HeapFree` at `0x14000382b`
- `KERNEL32!HeapFree` at `0x140003882`
- `KERNEL32!HeapFree` at `0x1400037cf`
- `KERNEL32!HeapFree` at `0x14000382b`
- `KERNEL32!HeapFree` at `0x140003882`
- `KERNEL32!GetProcessHeap` at `0x1400037bb`
- `KERNEL32!GetProcessHeap` at `0x140003817`
- `KERNEL32!GetProcessHeap` at `0x14000386e`
- `KERNEL32!GetProcessHeap` at `0x1400037bb`
- `KERNEL32!GetProcessHeap` at `0x140003817`
- `KERNEL32!GetProcessHeap` at `0x14000386e`
- `KERNEL32!DeleteCriticalSection` at `0x14000383a`
- `KERNEL32!DeleteCriticalSection` at `0x140003892`
- `KERNEL32!DeleteCriticalSection` at `0x14000383a`
- `KERNEL32!DeleteCriticalSection` at `0x140003892`
- `KERNEL32!SetThreadpoolTimer` at `0x1400038b7`
- `KERNEL32!SetThreadpoolTimer` at `0x1400038f7`
- `KERNEL32!SetThreadpoolTimer` at `0x1400038b7`
- `KERNEL32!SetThreadpoolTimer` at `0x1400038f7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400038d7`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003917`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400038d7`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003917`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400038c8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003908`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400038c8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003908`

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
  if ( v4 && qword_140063260 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140063260[25], qword_140063260, v4);
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
0x14000377c  push    rbx
0x14000377e  push    rsi
0x14000377f  push    rdi
0x140003780  push    r14
0x140003782  push    r15
0x140003784  sub     rsp, 20h
0x140003788  mov     rbx, rcx
0x14000378b  mov     byte ptr [rcx], 0
0x14000378e  xor     edx, edx
0x140003790  add     rcx, 30h ; '0'
0x140003794  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140003799  xor     edx, edx
0x14000379b  lea     rcx, [rbx+38h]
0x14000379f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400037a4  mov     rdi, [rbx+100h]
0x1400037ab  mov     qword ptr [rbx+100h], 0
0x1400037b6  test    rdi, rdi
0x1400037b9  jz      short loc_1400037DB
0x1400037bb  call    cs:__imp_GetProcessHeap
0x1400037c2  nop     dword ptr [rax+rax+00h]
0x1400037c7  mov     rcx, rax; hHeap
0x1400037ca  mov     r8, rdi; lpMem
0x1400037cd  xor     edx, edx; dwFlags
0x1400037cf  call    cs:__imp_HeapFree
0x1400037d6  nop     dword ptr [rax+rax+00h]
0x1400037db  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400037e2  test    r8, r8
0x1400037e5  jz      short loc_1400037FF
0x1400037e7  mov     rdx, cs:qword_140063260; SRWLock
0x1400037ee  test    rdx, rdx
0x1400037f1  jz      short loc_1400037FF
0x1400037f3  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400037fa  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400037ff  lea     rdi, [rbx+98h]
0x140003806  mov     rsi, [rdi+40h]
0x14000380a  mov     qword ptr [rdi+40h], 0
0x140003812  test    rsi, rsi
0x140003815  jz      short loc_140003837
0x140003817  call    cs:__imp_GetProcessHeap
0x14000381e  nop     dword ptr [rax+rax+00h]
0x140003823  mov     rcx, rax; hHeap
0x140003826  mov     r8, rsi; lpMem
0x140003829  xor     edx, edx; dwFlags
0x14000382b  call    cs:__imp_HeapFree
0x140003832  nop     dword ptr [rax+rax+00h]
0x140003837  mov     rcx, rdi; lpCriticalSection
0x14000383a  call    cs:__imp_DeleteCriticalSection
0x140003841  nop     dword ptr [rax+rax+00h]
0x140003846  mov     rcx, [rbx+90h]; this
0x14000384d  test    rcx, rcx
0x140003850  jz      short loc_140003857
0x140003852  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140003857  mov     rsi, [rbx+88h]
0x14000385e  mov     qword ptr [rbx+88h], 0
0x140003869  test    rsi, rsi
0x14000386c  jz      short loc_14000388E
0x14000386e  call    cs:__imp_GetProcessHeap
0x140003875  nop     dword ptr [rax+rax+00h]
0x14000387a  mov     rcx, rax; hHeap
0x14000387d  mov     r8, rsi; lpMem
0x140003880  xor     edx, edx; dwFlags
0x140003882  call    cs:__imp_HeapFree
0x140003889  nop     dword ptr [rax+rax+00h]
0x14000388e  lea     rcx, [rbx+48h]; lpCriticalSection
0x140003892  call    cs:__imp_DeleteCriticalSection
0x140003899  nop     dword ptr [rax+rax+00h]
0x14000389e  mov     rdi, [rbx+38h]
0x1400038a2  mov     esi, 1
0x1400038a7  test    rdi, rdi
0x1400038aa  jz      short loc_1400038E3
0x1400038ac  xor     r9d, r9d; msWindowLength
0x1400038af  xor     r8d, r8d; msPeriod
0x1400038b2  xor     edx, edx; pftDueTime
0x1400038b4  mov     rcx, rdi; pti
0x1400038b7  call    cs:__imp_SetThreadpoolTimer
0x1400038be  nop     dword ptr [rax+rax+00h]
0x1400038c3  mov     edx, esi; fCancelPendingCallbacks
0x1400038c5  mov     rcx, rdi; pti
0x1400038c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400038cf  nop     dword ptr [rax+rax+00h]
0x1400038d4  mov     rcx, rdi; pti
0x1400038d7  call    cs:__imp_CloseThreadpoolTimer
0x1400038de  nop     dword ptr [rax+rax+00h]
0x1400038e3  mov     rdi, [rbx+30h]
0x1400038e7  test    rdi, rdi
0x1400038ea  jz      short loc_140003924
0x1400038ec  xor     r9d, r9d; msWindowLength
0x1400038ef  xor     r8d, r8d; msPeriod
0x1400038f2  xor     edx, edx; pftDueTime
0x1400038f4  mov     rcx, rdi; pti
0x1400038f7  call    cs:__imp_SetThreadpoolTimer
0x1400038fe  nop     dword ptr [rax+rax+00h]
0x140003903  mov     edx, esi; fCancelPendingCallbacks
0x140003905  mov     rcx, rdi; pti
0x140003908  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000390f  nop     dword ptr [rax+rax+00h]
0x140003914  mov     rcx, rdi; pti
0x140003917  call    cs:__imp_CloseThreadpoolTimer
0x14000391e  nop     dword ptr [rax+rax+00h]
0x140003923  nop
0x140003924  mov     rcx, [rbx+10h]; lpMem
0x140003928  test    rcx, rcx
0x14000392b  jz      short loc_140003933
0x14000392d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140003932  nop
0x140003933  add     rsp, 20h
0x140003937  pop     r15
0x140003939  pop     r14
0x14000393b  pop     rdi
0x14000393c  pop     rsi
0x14000393d  pop     rbx
0x14000393e  retn
```
