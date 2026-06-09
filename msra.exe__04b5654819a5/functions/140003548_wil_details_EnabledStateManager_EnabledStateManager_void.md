# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003548`
- end: `0x14000368d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14004bf70`

## callees

- `0x140003548`
- `0x140006128`
- `0x140009900`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003598`
- `KERNEL32!HeapFree` at `0x1400035c9`
- `KERNEL32!HeapFree` at `0x140003598`
- `KERNEL32!HeapFree` at `0x1400035c9`
- `KERNEL32!GetProcessHeap` at `0x140003584`
- `KERNEL32!GetProcessHeap` at `0x1400035b5`
- `KERNEL32!GetProcessHeap` at `0x140003584`
- `KERNEL32!GetProcessHeap` at `0x1400035b5`
- `KERNEL32!SetThreadpoolTimer` at `0x14000364c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000364c`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000366f`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000366f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003660`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003660`

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
0x140003548  mov     [rsp+arg_0], rbx
0x14000354d  mov     [rsp+arg_8], rsi
0x140003552  push    rdi
0x140003553  sub     rsp, 20h
0x140003557  mov     rbx, rcx
0x14000355a  mov     dword ptr [rcx], 0
0x140003560  xor     edx, edx
0x140003562  add     rcx, 10h
0x140003566  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000356b  mov     rcx, rbx; this
0x14000356e  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140003573  mov     rdi, [rbx+68h]
0x140003577  mov     qword ptr [rbx+68h], 0
0x14000357f  test    rdi, rdi
0x140003582  jz      short loc_1400035A4
0x140003584  call    cs:__imp_GetProcessHeap
0x14000358b  nop     dword ptr [rax+rax+00h]
0x140003590  mov     rcx, rax; hHeap
0x140003593  mov     r8, rdi; lpMem
0x140003596  xor     edx, edx; dwFlags
0x140003598  call    cs:__imp_HeapFree
0x14000359f  nop     dword ptr [rax+rax+00h]
0x1400035a4  mov     rdi, [rbx+48h]
0x1400035a8  mov     qword ptr [rbx+48h], 0
0x1400035b0  test    rdi, rdi
0x1400035b3  jz      short loc_1400035D5
0x1400035b5  call    cs:__imp_GetProcessHeap
0x1400035bc  nop     dword ptr [rax+rax+00h]
0x1400035c1  mov     rcx, rax; hHeap
0x1400035c4  mov     r8, rdi; lpMem
0x1400035c7  xor     edx, edx; dwFlags
0x1400035c9  call    cs:__imp_HeapFree
0x1400035d0  nop     dword ptr [rax+rax+00h]
0x1400035d5  mov     rcx, [rbx+28h]
0x1400035d9  test    rcx, rcx
0x1400035dc  jz      short loc_14000360E
0x1400035de  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400035e5  test    rax, rax
0x1400035e8  jnz     short loc_1400035F9
0x1400035ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400035f1  test    rdx, rdx
0x1400035f4  jz      short loc_14000360C
0x1400035f6  mov     rax, rdx
0x1400035f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035fe  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003605  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000360c  jmp     short loc_14000361C
0x14000360e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003615  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000361c  mov     rcx, [rbx+20h]
0x140003620  test    rcx, rcx
0x140003623  jz      short loc_140003638
0x140003625  test    rax, rax
0x140003628  jnz     short loc_140003632
0x14000362a  test    rdx, rdx
0x14000362d  jz      short loc_140003638
0x14000362f  mov     rax, rdx
0x140003632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003637  nop
0x140003638  mov     rbx, [rbx+10h]
0x14000363c  test    rbx, rbx
0x14000363f  jz      short loc_14000367C
0x140003641  xor     r9d, r9d; msWindowLength
0x140003644  xor     r8d, r8d; msPeriod
0x140003647  xor     edx, edx; pftDueTime
0x140003649  mov     rcx, rbx; pti
0x14000364c  call    cs:__imp_SetThreadpoolTimer
0x140003653  nop     dword ptr [rax+rax+00h]
0x140003658  mov     edx, 1; fCancelPendingCallbacks
0x14000365d  mov     rcx, rbx; pti
0x140003660  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003667  nop     dword ptr [rax+rax+00h]
0x14000366c  mov     rcx, rbx; pti
0x14000366f  call    cs:__imp_CloseThreadpoolTimer
0x140003676  nop     dword ptr [rax+rax+00h]
0x14000367b  nop
0x14000367c  mov     rbx, [rsp+28h+arg_0]
0x140003681  mov     rsi, [rsp+28h+arg_8]
0x140003686  add     rsp, 20h
0x14000368a  pop     rdi
0x14000368b  retn
```
