# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180015788`
- end: `0x1800158cb`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800c75e0`

## callees

- `0x180015788`
- `0x18001d008`
- `0x180021468`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015803`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001589e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001589e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001588a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001588a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800158ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800158ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  __int64 v6; // rdx
  void (*v7)(void); // rax
  struct _TP_TIMER *v8; // rbx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)this);
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
    v6 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v7 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v6 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v7 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  else
  {
    v7 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
  }
  v7();
  v7 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v6 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( v6 )
  {
    v7 = (void (*)(void))v6;
  }
  else if ( !v7 )
  {
    goto LABEL_17;
  }
  v7();
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
0x180015788  mov     [rsp+arg_0], rbx
0x18001578d  mov     [rsp+arg_8], rsi
0x180015792  push    rdi
0x180015793  sub     rsp, 20h
0x180015797  mov     rbx, rcx
0x18001579a  mov     byte ptr [rcx], 0
0x18001579d  xor     edx, edx
0x18001579f  add     rcx, 10h
0x1800157a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800157a8  mov     byte ptr [rbx], 0
0x1800157ab  mov     rcx, rbx; this
0x1800157ae  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x1800157b3  mov     rdi, [rbx+68h]
0x1800157b7  and     qword ptr [rbx+68h], 0
0x1800157bc  test    rdi, rdi
0x1800157bf  jz      short loc_1800157E1
0x1800157c1  call    cs:__imp_GetProcessHeap
0x1800157c8  nop     dword ptr [rax+rax+00h]
0x1800157cd  mov     rcx, rax; hHeap
0x1800157d0  mov     r8, rdi; lpMem
0x1800157d3  xor     edx, edx; dwFlags
0x1800157d5  call    cs:__imp_HeapFree
0x1800157dc  nop     dword ptr [rax+rax+00h]
0x1800157e1  mov     rdi, [rbx+48h]
0x1800157e5  and     qword ptr [rbx+48h], 0
0x1800157ea  test    rdi, rdi
0x1800157ed  jz      short loc_18001580F
0x1800157ef  call    cs:__imp_GetProcessHeap
0x1800157f6  nop     dword ptr [rax+rax+00h]
0x1800157fb  mov     rcx, rax; hHeap
0x1800157fe  mov     r8, rdi; lpMem
0x180015801  xor     edx, edx; dwFlags
0x180015803  call    cs:__imp_HeapFree
0x18001580a  nop     dword ptr [rax+rax+00h]
0x18001580f  mov     rcx, [rbx+28h]
0x180015813  test    rcx, rcx
0x180015816  jz      short loc_18001584A
0x180015818  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001581f  test    rdx, rdx
0x180015822  jz      short loc_180015829
0x180015824  mov     rax, rdx
0x180015827  jmp     short loc_180015835
0x180015829  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180015830  test    rax, rax
0x180015833  jz      short loc_180015848
0x180015835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001583a  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180015841  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180015848  jmp     short loc_180015858
0x18001584a  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180015851  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180015858  mov     rcx, [rbx+20h]
0x18001585c  test    rcx, rcx
0x18001585f  jz      short loc_180015876
0x180015861  test    rdx, rdx
0x180015864  jz      short loc_18001586B
0x180015866  mov     rax, rdx
0x180015869  jmp     short loc_180015870
0x18001586b  test    rax, rax
0x18001586e  jz      short loc_180015876
0x180015870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015875  nop
0x180015876  mov     rbx, [rbx+10h]
0x18001587a  test    rbx, rbx
0x18001587d  jz      short loc_1800158BA
0x18001587f  xor     r9d, r9d; msWindowLength
0x180015882  xor     r8d, r8d; msPeriod
0x180015885  xor     edx, edx; pftDueTime
0x180015887  mov     rcx, rbx; pti
0x18001588a  call    cs:__imp_SetThreadpoolTimer
0x180015891  nop     dword ptr [rax+rax+00h]
0x180015896  mov     edx, 1; fCancelPendingCallbacks
0x18001589b  mov     rcx, rbx; pti
0x18001589e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800158a5  nop     dword ptr [rax+rax+00h]
0x1800158aa  mov     rcx, rbx; pti
0x1800158ad  call    cs:__imp_CloseThreadpoolTimer
0x1800158b4  nop     dword ptr [rax+rax+00h]
0x1800158b9  nop
0x1800158ba  mov     rbx, [rsp+28h+arg_0]
0x1800158bf  mov     rsi, [rsp+28h+arg_8]
0x1800158c4  add     rsp, 20h
0x1800158c8  pop     rdi
0x1800158c9  retn
```
