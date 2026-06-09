# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140015b98`
- end: `0x140015cdd`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002f2a0`

## callees

- `0x140015b98`
- `0x14001bf5c`
- `0x1400204b8`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015c7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015c9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015c9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015cb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015cb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015cbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015cbf`

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
0x140015b98  mov     [rsp+arg_0], rbx
0x140015b9d  mov     [rsp+arg_8], rsi
0x140015ba2  push    rdi
0x140015ba3  sub     rsp, 20h
0x140015ba7  mov     rbx, rcx
0x140015baa  mov     dword ptr [rcx], 0
0x140015bb0  xor     edx, edx
0x140015bb2  add     rcx, 10h
0x140015bb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140015bbb  mov     rcx, rbx; this
0x140015bbe  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140015bc3  mov     rcx, [rbx+68h]
0x140015bc7  test    rcx, rcx
0x140015bca  jz      short loc_140015BFC
0x140015bcc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140015bd3  test    rax, rax
0x140015bd6  jnz     short loc_140015BE7
0x140015bd8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140015bdf  test    rdx, rdx
0x140015be2  jz      short loc_140015BFA
0x140015be4  mov     rax, rdx
0x140015be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015bec  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140015bf3  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140015bfa  jmp     short loc_140015C0A
0x140015bfc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140015c03  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140015c0a  mov     rcx, [rbx+60h]
0x140015c0e  test    rcx, rcx
0x140015c11  jz      short loc_140015C26
0x140015c13  test    rax, rax
0x140015c16  jnz     short loc_140015C20
0x140015c18  test    rdx, rdx
0x140015c1b  jz      short loc_140015C26
0x140015c1d  mov     rax, rdx
0x140015c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015c25  nop
0x140015c26  mov     rdi, [rbx+58h]
0x140015c2a  mov     qword ptr [rbx+58h], 0
0x140015c32  test    rdi, rdi
0x140015c35  jz      short loc_140015C57
0x140015c37  call    cs:__imp_GetProcessHeap
0x140015c3e  nop     dword ptr [rax+rax+00h]
0x140015c43  mov     rcx, rax; hHeap
0x140015c46  mov     r8, rdi; lpMem
0x140015c49  xor     edx, edx; dwFlags
0x140015c4b  call    cs:__imp_HeapFree
0x140015c52  nop     dword ptr [rax+rax+00h]
0x140015c57  mov     rdi, [rbx+38h]
0x140015c5b  mov     qword ptr [rbx+38h], 0
0x140015c63  test    rdi, rdi
0x140015c66  jz      short loc_140015C88
0x140015c68  call    cs:__imp_GetProcessHeap
0x140015c6f  nop     dword ptr [rax+rax+00h]
0x140015c74  mov     rcx, rax; hHeap
0x140015c77  mov     r8, rdi; lpMem
0x140015c7a  xor     edx, edx; dwFlags
0x140015c7c  call    cs:__imp_HeapFree
0x140015c83  nop     dword ptr [rax+rax+00h]
0x140015c88  mov     rbx, [rbx+10h]
0x140015c8c  test    rbx, rbx
0x140015c8f  jz      short loc_140015CCC
0x140015c91  xor     r9d, r9d; msWindowLength
0x140015c94  xor     r8d, r8d; msPeriod
0x140015c97  xor     edx, edx; pftDueTime
0x140015c99  mov     rcx, rbx; pti
0x140015c9c  call    cs:__imp_SetThreadpoolTimer
0x140015ca3  nop     dword ptr [rax+rax+00h]
0x140015ca8  mov     edx, 1; fCancelPendingCallbacks
0x140015cad  mov     rcx, rbx; pti
0x140015cb0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015cb7  nop     dword ptr [rax+rax+00h]
0x140015cbc  mov     rcx, rbx; pti
0x140015cbf  call    cs:__imp_CloseThreadpoolTimer
0x140015cc6  nop     dword ptr [rax+rax+00h]
0x140015ccb  nop
0x140015ccc  mov     rbx, [rsp+28h+arg_0]
0x140015cd1  mov     rsi, [rsp+28h+arg_8]
0x140015cd6  add     rsp, 20h
0x140015cda  pop     rdi
0x140015cdb  retn
```
