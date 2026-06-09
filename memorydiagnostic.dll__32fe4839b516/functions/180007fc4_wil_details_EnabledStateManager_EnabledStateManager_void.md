# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180007fc4`
- end: `0x180008107`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023730`

## callees

- `0x180007fc4`
- `0x18000f090`
- `0x180018824`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008064`
- `KERNEL32!GetProcessHeap` at `0x180008092`
- `KERNEL32!GetProcessHeap` at `0x180008064`
- `KERNEL32!GetProcessHeap` at `0x180008092`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080c6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080c6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800080e9`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800080e9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800080da`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800080da`
- `KERNEL32!HeapFree` at `0x180008078`
- `KERNEL32!HeapFree` at `0x1800080a6`
- `KERNEL32!HeapFree` at `0x180008078`
- `KERNEL32!HeapFree` at `0x1800080a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  __int64 v2; // rdx
  void (*v3)(void); // rax
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
    v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_8;
  }
  v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v3 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  else
  {
    v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_8;
  }
  v3();
  v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_8:
  if ( !this[12] )
    goto LABEL_13;
  if ( v2 )
  {
    v3 = (void (*)(void))v2;
  }
  else if ( !v3 )
  {
    goto LABEL_13;
  }
  v3();
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
0x180007fc4  mov     [rsp+arg_0], rbx
0x180007fc9  mov     [rsp+arg_8], rsi
0x180007fce  push    rdi
0x180007fcf  sub     rsp, 20h
0x180007fd3  mov     rbx, rcx
0x180007fd6  mov     dword ptr [rcx], 0
0x180007fdc  xor     edx, edx
0x180007fde  add     rcx, 10h
0x180007fe2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180007fe7  mov     rcx, rbx; this
0x180007fea  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180007fef  mov     rcx, [rbx+68h]
0x180007ff3  test    rcx, rcx
0x180007ff6  jz      short loc_18000802A
0x180007ff8  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007fff  test    rdx, rdx
0x180008002  jz      short loc_180008009
0x180008004  mov     rax, rdx
0x180008007  jmp     short loc_180008015
0x180008009  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008010  test    rax, rax
0x180008013  jz      short loc_180008028
0x180008015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000801a  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008021  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008028  jmp     short loc_180008038
0x18000802a  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008031  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008038  mov     rcx, [rbx+60h]
0x18000803c  test    rcx, rcx
0x18000803f  jz      short loc_180008056
0x180008041  test    rdx, rdx
0x180008044  jz      short loc_18000804B
0x180008046  mov     rax, rdx
0x180008049  jmp     short loc_180008050
0x18000804b  test    rax, rax
0x18000804e  jz      short loc_180008056
0x180008050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008055  nop
0x180008056  mov     rdi, [rbx+58h]
0x18000805a  and     qword ptr [rbx+58h], 0
0x18000805f  test    rdi, rdi
0x180008062  jz      short loc_180008084
0x180008064  call    cs:__imp_GetProcessHeap
0x18000806b  nop     dword ptr [rax+rax+00h]
0x180008070  mov     rcx, rax; hHeap
0x180008073  mov     r8, rdi; lpMem
0x180008076  xor     edx, edx; dwFlags
0x180008078  call    cs:__imp_HeapFree
0x18000807f  nop     dword ptr [rax+rax+00h]
0x180008084  mov     rdi, [rbx+38h]
0x180008088  and     qword ptr [rbx+38h], 0
0x18000808d  test    rdi, rdi
0x180008090  jz      short loc_1800080B2
0x180008092  call    cs:__imp_GetProcessHeap
0x180008099  nop     dword ptr [rax+rax+00h]
0x18000809e  mov     rcx, rax; hHeap
0x1800080a1  mov     r8, rdi; lpMem
0x1800080a4  xor     edx, edx; dwFlags
0x1800080a6  call    cs:__imp_HeapFree
0x1800080ad  nop     dword ptr [rax+rax+00h]
0x1800080b2  mov     rbx, [rbx+10h]
0x1800080b6  test    rbx, rbx
0x1800080b9  jz      short loc_1800080F6
0x1800080bb  xor     r9d, r9d; msWindowLength
0x1800080be  xor     r8d, r8d; msPeriod
0x1800080c1  xor     edx, edx; pftDueTime
0x1800080c3  mov     rcx, rbx; pti
0x1800080c6  call    cs:__imp_SetThreadpoolTimer
0x1800080cd  nop     dword ptr [rax+rax+00h]
0x1800080d2  mov     edx, 1; fCancelPendingCallbacks
0x1800080d7  mov     rcx, rbx; pti
0x1800080da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800080e1  nop     dword ptr [rax+rax+00h]
0x1800080e6  mov     rcx, rbx; pti
0x1800080e9  call    cs:__imp_CloseThreadpoolTimer
0x1800080f0  nop     dword ptr [rax+rax+00h]
0x1800080f5  nop
0x1800080f6  mov     rbx, [rsp+28h+arg_0]
0x1800080fb  mov     rsi, [rsp+28h+arg_8]
0x180008100  add     rsp, 20h
0x180008104  pop     rdi
0x180008105  retn
```
