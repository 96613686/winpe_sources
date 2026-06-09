# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18001c004`
- end: `0x18001c135`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `305`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800314a0`

## callees

- `0x18001c004`
- `0x180023a74`
- `0x1800265e4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c0f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c0f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c118`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c118`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c109`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c109`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c03d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c06b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c03d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c06b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c07f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c07f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  struct _TP_TIMER *v6; // rcx
  __int64 v7; // rdx
  void (*v8)(void); // rax
  struct _TP_TIMER *v9; // rbx

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
  v6 = this[5];
  v7 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( v6 )
  {
    if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      ((void (__fastcall *)(struct _TP_TIMER *, __int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification)(
        v6,
        g_wil_details_internalUnsubscribeFeatureStateChangeNotification);
    }
    else
    {
      v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_12;
      ((void (__fastcall *)(struct _TP_TIMER *, _QWORD))g_wil_details_apiUnsubscribeFeatureStateChangeNotification)(
        v6,
        0);
    }
    v7 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( v7 )
  {
    v8 = (void (*)(void))v7;
  }
  else if ( !v8 )
  {
    goto LABEL_17;
  }
  v8();
LABEL_17:
  v9 = this[2];
  if ( v9 )
  {
    SetThreadpoolTimer(v9, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v9, 1);
    CloseThreadpoolTimer(v9);
  }
}

```

## disassembly

```asm
0x18001c004  mov     [rsp+arg_0], rbx
0x18001c009  mov     [rsp+arg_8], rsi
0x18001c00e  push    rdi
0x18001c00f  sub     rsp, 20h
0x18001c013  mov     rbx, rcx
0x18001c016  mov     byte ptr [rcx], 0
0x18001c019  add     rcx, 10h
0x18001c01d  xor     edx, edx
0x18001c01f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c024  mov     rcx, rbx; this
0x18001c027  mov     byte ptr [rbx], 0
0x18001c02a  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18001c02f  mov     rdi, [rbx+68h]
0x18001c033  and     qword ptr [rbx+68h], 0
0x18001c038  test    rdi, rdi
0x18001c03b  jz      short loc_18001C05D
0x18001c03d  call    cs:__imp_GetProcessHeap
0x18001c044  nop     dword ptr [rax+rax+00h]
0x18001c049  mov     r8, rdi; lpMem
0x18001c04c  xor     edx, edx; dwFlags
0x18001c04e  mov     rcx, rax; hHeap
0x18001c051  call    cs:__imp_HeapFree
0x18001c058  nop     dword ptr [rax+rax+00h]
0x18001c05d  mov     rdi, [rbx+48h]
0x18001c061  and     qword ptr [rbx+48h], 0
0x18001c066  test    rdi, rdi
0x18001c069  jz      short loc_18001C08B
0x18001c06b  call    cs:__imp_GetProcessHeap
0x18001c072  nop     dword ptr [rax+rax+00h]
0x18001c077  mov     r8, rdi; lpMem
0x18001c07a  xor     edx, edx; dwFlags
0x18001c07c  mov     rcx, rax; hHeap
0x18001c07f  call    cs:__imp_HeapFree
0x18001c086  nop     dword ptr [rax+rax+00h]
0x18001c08b  mov     rcx, [rbx+28h]
0x18001c08f  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001c096  test    rcx, rcx
0x18001c099  jz      short loc_18001C0BD
0x18001c09b  test    rdx, rdx
0x18001c09e  jz      short loc_18001C0A5
0x18001c0a0  mov     rax, rdx
0x18001c0a3  jmp     short loc_18001C0B1
0x18001c0a5  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001c0ac  test    rax, rax
0x18001c0af  jz      short loc_18001C0C4
0x18001c0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b6  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001c0bd  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001c0c4  mov     rcx, [rbx+20h]
0x18001c0c8  test    rcx, rcx
0x18001c0cb  jz      short loc_18001C0E1
0x18001c0cd  test    rdx, rdx
0x18001c0d0  jz      short loc_18001C0D7
0x18001c0d2  mov     rax, rdx
0x18001c0d5  jmp     short loc_18001C0DC
0x18001c0d7  test    rax, rax
0x18001c0da  jz      short loc_18001C0E1
0x18001c0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0e1  mov     rbx, [rbx+10h]
0x18001c0e5  test    rbx, rbx
0x18001c0e8  jz      short loc_18001C124
0x18001c0ea  xor     r9d, r9d; msWindowLength
0x18001c0ed  xor     r8d, r8d; msPeriod
0x18001c0f0  xor     edx, edx; pftDueTime
0x18001c0f2  mov     rcx, rbx; pti
0x18001c0f5  call    cs:__imp_SetThreadpoolTimer
0x18001c0fc  nop     dword ptr [rax+rax+00h]
0x18001c101  mov     edx, 1; fCancelPendingCallbacks
0x18001c106  mov     rcx, rbx; pti
0x18001c109  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c110  nop     dword ptr [rax+rax+00h]
0x18001c115  mov     rcx, rbx; pti
0x18001c118  call    cs:__imp_CloseThreadpoolTimer
0x18001c11f  nop     dword ptr [rax+rax+00h]
0x18001c124  mov     rbx, [rsp+28h+arg_0]
0x18001c129  mov     rsi, [rsp+28h+arg_8]
0x18001c12e  add     rsp, 20h
0x18001c132  pop     rdi
0x18001c133  retn
```
