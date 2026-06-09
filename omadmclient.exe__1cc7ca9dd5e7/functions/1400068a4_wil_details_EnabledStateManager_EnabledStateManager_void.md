# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1400068a4`
- end: `0x1400069e9`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140068210`

## callees

- `0x1400068a4`
- `0x140009888`
- `0x14000d1a4`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006925`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400069a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400069a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400069bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400069bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400069cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400069cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  void (*v6)(void); // rax
  __int64 v7; // rdx
  struct _TP_TIMER *v8; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)this);
  v2 = this[13];
  this[13] = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = this[9];
  this[9] = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  if ( !this[5] )
  {
    v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
    v6 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v6();
  v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_17;
    v6 = (void (*)(void))v7;
  }
  v6();
LABEL_17:
  v8 = this[2];
  if ( v8 )
  {
    SetThreadpoolTimer(v8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
}

```

## disassembly

```asm
0x1400068a4  mov     [rsp+arg_0], rbx
0x1400068a9  mov     [rsp+arg_8], rsi
0x1400068ae  push    rdi
0x1400068af  sub     rsp, 20h
0x1400068b3  mov     rbx, rcx
0x1400068b6  mov     dword ptr [rcx], 0
0x1400068bc  xor     edx, edx
0x1400068be  add     rcx, 10h
0x1400068c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400068c7  mov     rcx, rbx; this
0x1400068ca  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1400068cf  mov     rdi, [rbx+68h]
0x1400068d3  mov     qword ptr [rbx+68h], 0
0x1400068db  test    rdi, rdi
0x1400068de  jz      short loc_140006900
0x1400068e0  call    cs:__imp_GetProcessHeap
0x1400068e7  nop     dword ptr [rax+rax+00h]
0x1400068ec  mov     rcx, rax; hHeap
0x1400068ef  mov     r8, rdi; lpMem
0x1400068f2  xor     edx, edx; dwFlags
0x1400068f4  call    cs:__imp_HeapFree
0x1400068fb  nop     dword ptr [rax+rax+00h]
0x140006900  mov     rdi, [rbx+48h]
0x140006904  mov     qword ptr [rbx+48h], 0
0x14000690c  test    rdi, rdi
0x14000690f  jz      short loc_140006931
0x140006911  call    cs:__imp_GetProcessHeap
0x140006918  nop     dword ptr [rax+rax+00h]
0x14000691d  mov     rcx, rax; hHeap
0x140006920  mov     r8, rdi; lpMem
0x140006923  xor     edx, edx; dwFlags
0x140006925  call    cs:__imp_HeapFree
0x14000692c  nop     dword ptr [rax+rax+00h]
0x140006931  mov     rcx, [rbx+28h]
0x140006935  test    rcx, rcx
0x140006938  jz      short loc_14000696A
0x14000693a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140006941  test    rax, rax
0x140006944  jnz     short loc_140006955
0x140006946  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000694d  test    rdx, rdx
0x140006950  jz      short loc_140006968
0x140006952  mov     rax, rdx
0x140006955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000695a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140006961  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140006968  jmp     short loc_140006978
0x14000696a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140006971  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140006978  mov     rcx, [rbx+20h]
0x14000697c  test    rcx, rcx
0x14000697f  jz      short loc_140006994
0x140006981  test    rax, rax
0x140006984  jnz     short loc_14000698E
0x140006986  test    rdx, rdx
0x140006989  jz      short loc_140006994
0x14000698b  mov     rax, rdx
0x14000698e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006993  nop
0x140006994  mov     rbx, [rbx+10h]
0x140006998  test    rbx, rbx
0x14000699b  jz      short loc_1400069D8
0x14000699d  xor     r9d, r9d; msWindowLength
0x1400069a0  xor     r8d, r8d; msPeriod
0x1400069a3  xor     edx, edx; pftDueTime
0x1400069a5  mov     rcx, rbx; pti
0x1400069a8  call    cs:__imp_SetThreadpoolTimer
0x1400069af  nop     dword ptr [rax+rax+00h]
0x1400069b4  mov     edx, 1; fCancelPendingCallbacks
0x1400069b9  mov     rcx, rbx; pti
0x1400069bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400069c3  nop     dword ptr [rax+rax+00h]
0x1400069c8  mov     rcx, rbx; pti
0x1400069cb  call    cs:__imp_CloseThreadpoolTimer
0x1400069d2  nop     dword ptr [rax+rax+00h]
0x1400069d7  nop
0x1400069d8  mov     rbx, [rsp+28h+arg_0]
0x1400069dd  mov     rsi, [rsp+28h+arg_8]
0x1400069e2  add     rsp, 20h
0x1400069e6  pop     rdi
0x1400069e7  retn
```
