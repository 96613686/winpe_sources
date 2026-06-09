# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180008198`
- end: `0x180008247`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800050b4`
- `0x180058a10`

## callees

- `0x180008198`
- `0x180008624`
- `0x18000b8a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000820c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000820c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008220`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008220`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000822f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000822f`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rax
  struct _TP_TIMER *v4; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  pti = Ptr;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v4 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
}

```

## disassembly

```asm
0x180008198  mov     [rsp+arg_8], rbx
0x18000819d  push    rdi
0x18000819e  sub     rsp, 20h
0x1800081a2  mov     dword ptr [rcx], 0
0x1800081a8  lea     rdi, [rcx+8]
0x1800081ac  mov     rax, [rcx+10h]
0x1800081b0  mov     rbx, rcx
0x1800081b3  mov     qword ptr [rcx+10h], 0
0x1800081bb  mov     rcx, rdi; SRWLock
0x1800081be  mov     [rsp+28h+pti], rax
0x1800081c3  call    cs:__imp_AcquireSRWLockExclusive
0x1800081ca  nop     dword ptr [rax+rax+00h]
0x1800081cf  mov     rcx, rbx
0x1800081d2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800081d7  test    rdi, rdi
0x1800081da  jz      short loc_1800081EB
0x1800081dc  mov     rcx, rdi; SRWLock
0x1800081df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081e6  nop     dword ptr [rax+rax+00h]
0x1800081eb  xor     edx, edx
0x1800081ed  lea     rcx, [rsp+28h+pti]
0x1800081f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800081f7  mov     rbx, [rsp+28h+pti]
0x1800081fc  test    rbx, rbx
0x1800081ff  jz      short loc_18000823B
0x180008201  xor     r9d, r9d; msWindowLength
0x180008204  xor     r8d, r8d; msPeriod
0x180008207  xor     edx, edx; pftDueTime
0x180008209  mov     rcx, rbx; pti
0x18000820c  call    cs:__imp_SetThreadpoolTimer
0x180008213  nop     dword ptr [rax+rax+00h]
0x180008218  mov     edx, 1; fCancelPendingCallbacks
0x18000821d  mov     rcx, rbx; pti
0x180008220  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008227  nop     dword ptr [rax+rax+00h]
0x18000822c  mov     rcx, rbx; pti
0x18000822f  call    cs:__imp_CloseThreadpoolTimer
0x180008236  nop     dword ptr [rax+rax+00h]
0x18000823b  mov     rbx, [rsp+28h+arg_8]
0x180008240  add     rsp, 20h
0x180008244  pop     rdi
0x180008245  retn
```
