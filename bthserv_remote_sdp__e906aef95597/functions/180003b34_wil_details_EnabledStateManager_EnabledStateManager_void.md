# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003b34`
- end: `0x180003c77`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180035b00`

## callees

- `0x180003b34`
- `0x180006824`
- `0x180009c50`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003be8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003be8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c59`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c36`

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
0x180003b34  mov     [rsp+arg_0], rbx
0x180003b39  mov     [rsp+arg_8], rsi
0x180003b3e  push    rdi
0x180003b3f  sub     rsp, 20h
0x180003b43  mov     rbx, rcx
0x180003b46  mov     dword ptr [rcx], 0
0x180003b4c  xor     edx, edx
0x180003b4e  add     rcx, 10h
0x180003b52  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003b57  mov     rcx, rbx; this
0x180003b5a  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003b5f  mov     rcx, [rbx+68h]
0x180003b63  test    rcx, rcx
0x180003b66  jz      short loc_180003B9A
0x180003b68  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003b6f  test    rdx, rdx
0x180003b72  jz      short loc_180003B79
0x180003b74  mov     rax, rdx
0x180003b77  jmp     short loc_180003B85
0x180003b79  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003b80  test    rax, rax
0x180003b83  jz      short loc_180003B98
0x180003b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8a  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003b91  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003b98  jmp     short loc_180003BA8
0x180003b9a  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003ba1  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003ba8  mov     rcx, [rbx+60h]
0x180003bac  test    rcx, rcx
0x180003baf  jz      short loc_180003BC6
0x180003bb1  test    rdx, rdx
0x180003bb4  jz      short loc_180003BBB
0x180003bb6  mov     rax, rdx
0x180003bb9  jmp     short loc_180003BC0
0x180003bbb  test    rax, rax
0x180003bbe  jz      short loc_180003BC6
0x180003bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc5  nop
0x180003bc6  mov     rdi, [rbx+58h]
0x180003bca  and     qword ptr [rbx+58h], 0
0x180003bcf  test    rdi, rdi
0x180003bd2  jz      short loc_180003BF4
0x180003bd4  call    cs:__imp_GetProcessHeap
0x180003bdb  nop     dword ptr [rax+rax+00h]
0x180003be0  mov     rcx, rax; hHeap
0x180003be3  mov     r8, rdi; lpMem
0x180003be6  xor     edx, edx; dwFlags
0x180003be8  call    cs:__imp_HeapFree
0x180003bef  nop     dword ptr [rax+rax+00h]
0x180003bf4  mov     rdi, [rbx+38h]
0x180003bf8  and     qword ptr [rbx+38h], 0
0x180003bfd  test    rdi, rdi
0x180003c00  jz      short loc_180003C22
0x180003c02  call    cs:__imp_GetProcessHeap
0x180003c09  nop     dword ptr [rax+rax+00h]
0x180003c0e  mov     rcx, rax; hHeap
0x180003c11  mov     r8, rdi; lpMem
0x180003c14  xor     edx, edx; dwFlags
0x180003c16  call    cs:__imp_HeapFree
0x180003c1d  nop     dword ptr [rax+rax+00h]
0x180003c22  mov     rbx, [rbx+10h]
0x180003c26  test    rbx, rbx
0x180003c29  jz      short loc_180003C66
0x180003c2b  xor     r9d, r9d; msWindowLength
0x180003c2e  xor     r8d, r8d; msPeriod
0x180003c31  xor     edx, edx; pftDueTime
0x180003c33  mov     rcx, rbx; pti
0x180003c36  call    cs:__imp_SetThreadpoolTimer
0x180003c3d  nop     dword ptr [rax+rax+00h]
0x180003c42  mov     edx, 1; fCancelPendingCallbacks
0x180003c47  mov     rcx, rbx; pti
0x180003c4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c51  nop     dword ptr [rax+rax+00h]
0x180003c56  mov     rcx, rbx; pti
0x180003c59  call    cs:__imp_CloseThreadpoolTimer
0x180003c60  nop     dword ptr [rax+rax+00h]
0x180003c65  nop
0x180003c66  mov     rbx, [rsp+28h+arg_0]
0x180003c6b  mov     rsi, [rsp+28h+arg_8]
0x180003c70  add     rsp, 20h
0x180003c74  pop     rdi
0x180003c75  retn
```
