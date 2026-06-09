# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800b4850`
- end: `0x1800b4983`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `307`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800ea030`

## callees

- `0x1800b4850`
- `0x1800baa68`
- `0x1800be088`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b48a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b48d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b48a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b48d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b488c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b48bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b488c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b48bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4943`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4943`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4957`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4957`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4966`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b4966`

## pseudocode

```c
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
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( this[5] )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_11;
      v6 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v6();
    v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_11:
  if ( !this[4] )
    goto LABEL_16;
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_16;
    v6 = (void (*)(void))v7;
  }
  v6();
LABEL_16:
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
0x1800b4850  mov     [rsp+arg_0], rbx
0x1800b4855  mov     [rsp+arg_8], rsi
0x1800b485a  push    rdi
0x1800b485b  sub     rsp, 20h
0x1800b485f  mov     rbx, rcx
0x1800b4862  mov     dword ptr [rcx], 0
0x1800b4868  add     rcx, 10h
0x1800b486c  xor     edx, edx
0x1800b486e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800b4873  mov     rcx, rbx; this
0x1800b4876  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800b487b  mov     rdi, [rbx+68h]
0x1800b487f  mov     qword ptr [rbx+68h], 0
0x1800b4887  test    rdi, rdi
0x1800b488a  jz      short loc_1800B48AC
0x1800b488c  call    cs:__imp_GetProcessHeap
0x1800b4893  nop     dword ptr [rax+rax+00h]
0x1800b4898  mov     r8, rdi; lpMem
0x1800b489b  xor     edx, edx; dwFlags
0x1800b489d  mov     rcx, rax; hHeap
0x1800b48a0  call    cs:__imp_HeapFree
0x1800b48a7  nop     dword ptr [rax+rax+00h]
0x1800b48ac  mov     rdi, [rbx+48h]
0x1800b48b0  mov     qword ptr [rbx+48h], 0
0x1800b48b8  test    rdi, rdi
0x1800b48bb  jz      short loc_1800B48DD
0x1800b48bd  call    cs:__imp_GetProcessHeap
0x1800b48c4  nop     dword ptr [rax+rax+00h]
0x1800b48c9  mov     r8, rdi; lpMem
0x1800b48cc  xor     edx, edx; dwFlags
0x1800b48ce  mov     rcx, rax; hHeap
0x1800b48d1  call    cs:__imp_HeapFree
0x1800b48d8  nop     dword ptr [rax+rax+00h]
0x1800b48dd  mov     rcx, [rbx+28h]
0x1800b48e1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800b48e8  test    rcx, rcx
0x1800b48eb  jz      short loc_1800B490D
0x1800b48ed  test    rax, rax
0x1800b48f0  jnz     short loc_1800B4901
0x1800b48f2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800b48f9  test    rdx, rdx
0x1800b48fc  jz      short loc_1800B4914
0x1800b48fe  mov     rax, rdx
0x1800b4901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4906  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800b490d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800b4914  mov     rcx, [rbx+20h]
0x1800b4918  test    rcx, rcx
0x1800b491b  jz      short loc_1800B492F
0x1800b491d  test    rax, rax
0x1800b4920  jnz     short loc_1800B492A
0x1800b4922  test    rdx, rdx
0x1800b4925  jz      short loc_1800B492F
0x1800b4927  mov     rax, rdx
0x1800b492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b492f  mov     rbx, [rbx+10h]
0x1800b4933  test    rbx, rbx
0x1800b4936  jz      short loc_1800B4972
0x1800b4938  xor     r9d, r9d; msWindowLength
0x1800b493b  xor     r8d, r8d; msPeriod
0x1800b493e  xor     edx, edx; pftDueTime
0x1800b4940  mov     rcx, rbx; pti
0x1800b4943  call    cs:__imp_SetThreadpoolTimer
0x1800b494a  nop     dword ptr [rax+rax+00h]
0x1800b494f  mov     edx, 1; fCancelPendingCallbacks
0x1800b4954  mov     rcx, rbx; pti
0x1800b4957  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b495e  nop     dword ptr [rax+rax+00h]
0x1800b4963  mov     rcx, rbx; pti
0x1800b4966  call    cs:__imp_CloseThreadpoolTimer
0x1800b496d  nop     dword ptr [rax+rax+00h]
0x1800b4972  mov     rbx, [rsp+28h+arg_0]
0x1800b4977  mov     rsi, [rsp+28h+arg_8]
0x1800b497c  add     rsp, 20h
0x1800b4980  pop     rdi
0x1800b4981  retn
```
