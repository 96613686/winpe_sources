# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000a0d8`
- end: `0x18000a21d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800234e0`

## callees

- `0x18000a0d8`
- `0x180010168`
- `0x1800142b8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a128`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a128`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a145`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1ff`

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
0x18000a0d8  mov     [rsp+arg_0], rbx
0x18000a0dd  mov     [rsp+arg_8], rsi
0x18000a0e2  push    rdi
0x18000a0e3  sub     rsp, 20h
0x18000a0e7  mov     rbx, rcx
0x18000a0ea  mov     dword ptr [rcx], 0
0x18000a0f0  xor     edx, edx
0x18000a0f2  add     rcx, 10h
0x18000a0f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a0fb  mov     rcx, rbx; this
0x18000a0fe  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000a103  mov     rdi, [rbx+68h]
0x18000a107  mov     qword ptr [rbx+68h], 0
0x18000a10f  test    rdi, rdi
0x18000a112  jz      short loc_18000A134
0x18000a114  call    cs:__imp_GetProcessHeap
0x18000a11b  nop     dword ptr [rax+rax+00h]
0x18000a120  mov     rcx, rax; hHeap
0x18000a123  mov     r8, rdi; lpMem
0x18000a126  xor     edx, edx; dwFlags
0x18000a128  call    cs:__imp_HeapFree
0x18000a12f  nop     dword ptr [rax+rax+00h]
0x18000a134  mov     rdi, [rbx+48h]
0x18000a138  mov     qword ptr [rbx+48h], 0
0x18000a140  test    rdi, rdi
0x18000a143  jz      short loc_18000A165
0x18000a145  call    cs:__imp_GetProcessHeap
0x18000a14c  nop     dword ptr [rax+rax+00h]
0x18000a151  mov     rcx, rax; hHeap
0x18000a154  mov     r8, rdi; lpMem
0x18000a157  xor     edx, edx; dwFlags
0x18000a159  call    cs:__imp_HeapFree
0x18000a160  nop     dword ptr [rax+rax+00h]
0x18000a165  mov     rcx, [rbx+28h]
0x18000a169  test    rcx, rcx
0x18000a16c  jz      short loc_18000A19E
0x18000a16e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a175  test    rax, rax
0x18000a178  jnz     short loc_18000A189
0x18000a17a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a181  test    rdx, rdx
0x18000a184  jz      short loc_18000A19C
0x18000a186  mov     rax, rdx
0x18000a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a195  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a19c  jmp     short loc_18000A1AC
0x18000a19e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a1a5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a1ac  mov     rcx, [rbx+20h]
0x18000a1b0  test    rcx, rcx
0x18000a1b3  jz      short loc_18000A1C8
0x18000a1b5  test    rax, rax
0x18000a1b8  jnz     short loc_18000A1C2
0x18000a1ba  test    rdx, rdx
0x18000a1bd  jz      short loc_18000A1C8
0x18000a1bf  mov     rax, rdx
0x18000a1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c7  nop
0x18000a1c8  mov     rbx, [rbx+10h]
0x18000a1cc  test    rbx, rbx
0x18000a1cf  jz      short loc_18000A20C
0x18000a1d1  xor     r9d, r9d; msWindowLength
0x18000a1d4  xor     r8d, r8d; msPeriod
0x18000a1d7  xor     edx, edx; pftDueTime
0x18000a1d9  mov     rcx, rbx; pti
0x18000a1dc  call    cs:__imp_SetThreadpoolTimer
0x18000a1e3  nop     dword ptr [rax+rax+00h]
0x18000a1e8  mov     edx, 1; fCancelPendingCallbacks
0x18000a1ed  mov     rcx, rbx; pti
0x18000a1f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a1f7  nop     dword ptr [rax+rax+00h]
0x18000a1fc  mov     rcx, rbx; pti
0x18000a1ff  call    cs:__imp_CloseThreadpoolTimer
0x18000a206  nop     dword ptr [rax+rax+00h]
0x18000a20b  nop
0x18000a20c  mov     rbx, [rsp+28h+arg_0]
0x18000a211  mov     rsi, [rsp+28h+arg_8]
0x18000a216  add     rsp, 20h
0x18000a21a  pop     rdi
0x18000a21b  retn
```
