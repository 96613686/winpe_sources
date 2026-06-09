# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006708`
- end: `0x18000684d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004d090`

## callees

- `0x180006708`
- `0x180009728`
- `0x18000cfb4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006789`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006775`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000682f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000682f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000680c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000680c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006820`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006820`

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
0x180006708  mov     [rsp+arg_0], rbx
0x18000670d  mov     [rsp+arg_8], rsi
0x180006712  push    rdi
0x180006713  sub     rsp, 20h
0x180006717  mov     rbx, rcx
0x18000671a  mov     dword ptr [rcx], 0
0x180006720  xor     edx, edx
0x180006722  add     rcx, 10h
0x180006726  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000672b  mov     rcx, rbx; this
0x18000672e  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180006733  mov     rdi, [rbx+68h]
0x180006737  mov     qword ptr [rbx+68h], 0
0x18000673f  test    rdi, rdi
0x180006742  jz      short loc_180006764
0x180006744  call    cs:__imp_GetProcessHeap
0x18000674b  nop     dword ptr [rax+rax+00h]
0x180006750  mov     rcx, rax; hHeap
0x180006753  mov     r8, rdi; lpMem
0x180006756  xor     edx, edx; dwFlags
0x180006758  call    cs:__imp_HeapFree
0x18000675f  nop     dword ptr [rax+rax+00h]
0x180006764  mov     rdi, [rbx+48h]
0x180006768  mov     qword ptr [rbx+48h], 0
0x180006770  test    rdi, rdi
0x180006773  jz      short loc_180006795
0x180006775  call    cs:__imp_GetProcessHeap
0x18000677c  nop     dword ptr [rax+rax+00h]
0x180006781  mov     rcx, rax; hHeap
0x180006784  mov     r8, rdi; lpMem
0x180006787  xor     edx, edx; dwFlags
0x180006789  call    cs:__imp_HeapFree
0x180006790  nop     dword ptr [rax+rax+00h]
0x180006795  mov     rcx, [rbx+28h]
0x180006799  test    rcx, rcx
0x18000679c  jz      short loc_1800067CE
0x18000679e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067a5  test    rax, rax
0x1800067a8  jnz     short loc_1800067B9
0x1800067aa  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067b1  test    rdx, rdx
0x1800067b4  jz      short loc_1800067CC
0x1800067b6  mov     rax, rdx
0x1800067b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067be  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067c5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067cc  jmp     short loc_1800067DC
0x1800067ce  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800067d5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800067dc  mov     rcx, [rbx+20h]
0x1800067e0  test    rcx, rcx
0x1800067e3  jz      short loc_1800067F8
0x1800067e5  test    rax, rax
0x1800067e8  jnz     short loc_1800067F2
0x1800067ea  test    rdx, rdx
0x1800067ed  jz      short loc_1800067F8
0x1800067ef  mov     rax, rdx
0x1800067f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f7  nop
0x1800067f8  mov     rbx, [rbx+10h]
0x1800067fc  test    rbx, rbx
0x1800067ff  jz      short loc_18000683C
0x180006801  xor     r9d, r9d; msWindowLength
0x180006804  xor     r8d, r8d; msPeriod
0x180006807  xor     edx, edx; pftDueTime
0x180006809  mov     rcx, rbx; pti
0x18000680c  call    cs:__imp_SetThreadpoolTimer
0x180006813  nop     dword ptr [rax+rax+00h]
0x180006818  mov     edx, 1; fCancelPendingCallbacks
0x18000681d  mov     rcx, rbx; pti
0x180006820  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006827  nop     dword ptr [rax+rax+00h]
0x18000682c  mov     rcx, rbx; pti
0x18000682f  call    cs:__imp_CloseThreadpoolTimer
0x180006836  nop     dword ptr [rax+rax+00h]
0x18000683b  nop
0x18000683c  mov     rbx, [rsp+28h+arg_0]
0x180006841  mov     rsi, [rsp+28h+arg_8]
0x180006846  add     rsp, 20h
0x18000684a  pop     rdi
0x18000684b  retn
```
