# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003a80`
- end: `0x140003bc5`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140016130`

## callees

- `0x140003a80`
- `0x1400068b8`
- `0x14000a6e0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003aed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003aed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003b01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003b01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003ba7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003ba7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003b98`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003b98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003b84`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003b84`

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
0x140003a80  mov     [rsp+arg_0], rbx
0x140003a85  mov     [rsp+arg_8], rsi
0x140003a8a  push    rdi
0x140003a8b  sub     rsp, 20h
0x140003a8f  mov     rbx, rcx
0x140003a92  mov     dword ptr [rcx], 0
0x140003a98  xor     edx, edx
0x140003a9a  add     rcx, 10h
0x140003a9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140003aa3  mov     rcx, rbx; this
0x140003aa6  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140003aab  mov     rdi, [rbx+68h]
0x140003aaf  mov     qword ptr [rbx+68h], 0
0x140003ab7  test    rdi, rdi
0x140003aba  jz      short loc_140003ADC
0x140003abc  call    cs:__imp_GetProcessHeap
0x140003ac3  nop     dword ptr [rax+rax+00h]
0x140003ac8  mov     rcx, rax; hHeap
0x140003acb  mov     r8, rdi; lpMem
0x140003ace  xor     edx, edx; dwFlags
0x140003ad0  call    cs:__imp_HeapFree
0x140003ad7  nop     dword ptr [rax+rax+00h]
0x140003adc  mov     rdi, [rbx+48h]
0x140003ae0  mov     qword ptr [rbx+48h], 0
0x140003ae8  test    rdi, rdi
0x140003aeb  jz      short loc_140003B0D
0x140003aed  call    cs:__imp_GetProcessHeap
0x140003af4  nop     dword ptr [rax+rax+00h]
0x140003af9  mov     rcx, rax; hHeap
0x140003afc  mov     r8, rdi; lpMem
0x140003aff  xor     edx, edx; dwFlags
0x140003b01  call    cs:__imp_HeapFree
0x140003b08  nop     dword ptr [rax+rax+00h]
0x140003b0d  mov     rcx, [rbx+28h]
0x140003b11  test    rcx, rcx
0x140003b14  jz      short loc_140003B46
0x140003b16  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003b1d  test    rax, rax
0x140003b20  jnz     short loc_140003B31
0x140003b22  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003b29  test    rdx, rdx
0x140003b2c  jz      short loc_140003B44
0x140003b2e  mov     rax, rdx
0x140003b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b36  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003b3d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003b44  jmp     short loc_140003B54
0x140003b46  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003b4d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003b54  mov     rcx, [rbx+20h]
0x140003b58  test    rcx, rcx
0x140003b5b  jz      short loc_140003B70
0x140003b5d  test    rax, rax
0x140003b60  jnz     short loc_140003B6A
0x140003b62  test    rdx, rdx
0x140003b65  jz      short loc_140003B70
0x140003b67  mov     rax, rdx
0x140003b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b6f  nop
0x140003b70  mov     rbx, [rbx+10h]
0x140003b74  test    rbx, rbx
0x140003b77  jz      short loc_140003BB4
0x140003b79  xor     r9d, r9d; msWindowLength
0x140003b7c  xor     r8d, r8d; msPeriod
0x140003b7f  xor     edx, edx; pftDueTime
0x140003b81  mov     rcx, rbx; pti
0x140003b84  call    cs:__imp_SetThreadpoolTimer
0x140003b8b  nop     dword ptr [rax+rax+00h]
0x140003b90  mov     edx, 1; fCancelPendingCallbacks
0x140003b95  mov     rcx, rbx; pti
0x140003b98  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003b9f  nop     dword ptr [rax+rax+00h]
0x140003ba4  mov     rcx, rbx; pti
0x140003ba7  call    cs:__imp_CloseThreadpoolTimer
0x140003bae  nop     dword ptr [rax+rax+00h]
0x140003bb3  nop
0x140003bb4  mov     rbx, [rsp+28h+arg_0]
0x140003bb9  mov     rsi, [rsp+28h+arg_8]
0x140003bbe  add     rsp, 20h
0x140003bc2  pop     rdi
0x140003bc3  retn
```
