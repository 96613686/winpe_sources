# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800173cc`
- end: `0x180017511`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800c8900`

## callees

- `0x1800173cc`
- `0x18001d650`
- `0x180021d08`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001747f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800174b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001747f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800174b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001746b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001749c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001746b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001749c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800174d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800174d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800174f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800174f3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800174e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800174e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  void (*v2)(void); // rax
  __int64 v3; // rdx
  struct _TP_TIMER *v4; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v6; // rdi
  HANDLE v7; // rax
  struct _TP_TIMER *v8; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)this);
  if ( !this[13] )
  {
    v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_8;
  }
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_8;
    v2 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v2();
  v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_8:
  if ( !this[12] )
    goto LABEL_13;
  if ( !v2 )
  {
    if ( !v3 )
      goto LABEL_13;
    v2 = (void (*)(void))v3;
  }
  v2();
LABEL_13:
  v4 = this[11];
  this[11] = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = this[7];
  this[7] = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
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
0x1800173cc  mov     [rsp+arg_0], rbx
0x1800173d1  mov     [rsp+arg_8], rsi
0x1800173d6  push    rdi
0x1800173d7  sub     rsp, 20h
0x1800173db  mov     rbx, rcx
0x1800173de  mov     dword ptr [rcx], 0
0x1800173e4  xor     edx, edx
0x1800173e6  add     rcx, 10h
0x1800173ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800173ef  mov     rcx, rbx; this
0x1800173f2  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800173f7  mov     rcx, [rbx+68h]
0x1800173fb  test    rcx, rcx
0x1800173fe  jz      short loc_180017430
0x180017400  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180017407  test    rax, rax
0x18001740a  jnz     short loc_18001741B
0x18001740c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180017413  test    rdx, rdx
0x180017416  jz      short loc_18001742E
0x180017418  mov     rax, rdx
0x18001741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017420  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180017427  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001742e  jmp     short loc_18001743E
0x180017430  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180017437  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001743e  mov     rcx, [rbx+60h]
0x180017442  test    rcx, rcx
0x180017445  jz      short loc_18001745A
0x180017447  test    rax, rax
0x18001744a  jnz     short loc_180017454
0x18001744c  test    rdx, rdx
0x18001744f  jz      short loc_18001745A
0x180017451  mov     rax, rdx
0x180017454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017459  nop
0x18001745a  mov     rdi, [rbx+58h]
0x18001745e  mov     qword ptr [rbx+58h], 0
0x180017466  test    rdi, rdi
0x180017469  jz      short loc_18001748B
0x18001746b  call    cs:__imp_GetProcessHeap
0x180017472  nop     dword ptr [rax+rax+00h]
0x180017477  mov     rcx, rax; hHeap
0x18001747a  mov     r8, rdi; lpMem
0x18001747d  xor     edx, edx; dwFlags
0x18001747f  call    cs:__imp_HeapFree
0x180017486  nop     dword ptr [rax+rax+00h]
0x18001748b  mov     rdi, [rbx+38h]
0x18001748f  mov     qword ptr [rbx+38h], 0
0x180017497  test    rdi, rdi
0x18001749a  jz      short loc_1800174BC
0x18001749c  call    cs:__imp_GetProcessHeap
0x1800174a3  nop     dword ptr [rax+rax+00h]
0x1800174a8  mov     rcx, rax; hHeap
0x1800174ab  mov     r8, rdi; lpMem
0x1800174ae  xor     edx, edx; dwFlags
0x1800174b0  call    cs:__imp_HeapFree
0x1800174b7  nop     dword ptr [rax+rax+00h]
0x1800174bc  mov     rbx, [rbx+10h]
0x1800174c0  test    rbx, rbx
0x1800174c3  jz      short loc_180017500
0x1800174c5  xor     r9d, r9d; msWindowLength
0x1800174c8  xor     r8d, r8d; msPeriod
0x1800174cb  xor     edx, edx; pftDueTime
0x1800174cd  mov     rcx, rbx; pti
0x1800174d0  call    cs:__imp_SetThreadpoolTimer
0x1800174d7  nop     dword ptr [rax+rax+00h]
0x1800174dc  mov     edx, 1; fCancelPendingCallbacks
0x1800174e1  mov     rcx, rbx; pti
0x1800174e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800174eb  nop     dword ptr [rax+rax+00h]
0x1800174f0  mov     rcx, rbx; pti
0x1800174f3  call    cs:__imp_CloseThreadpoolTimer
0x1800174fa  nop     dword ptr [rax+rax+00h]
0x1800174ff  nop
0x180017500  mov     rbx, [rsp+28h+arg_0]
0x180017505  mov     rsi, [rsp+28h+arg_8]
0x18001750a  add     rsp, 20h
0x18001750e  pop     rdi
0x18001750f  retn
```
