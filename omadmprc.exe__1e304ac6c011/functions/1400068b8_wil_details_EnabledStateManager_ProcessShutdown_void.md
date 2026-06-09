# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1400068b8`
- end: `0x140006967`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003a80`
- `0x140016130`

## callees

- `0x1400068b8`
- `0x140007088`
- `0x14000a6e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400068e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400068e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400068ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400068ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000694f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000694f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006940`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006940`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000692c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000692c`

## pseudocode

```c
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
0x1400068b8  mov     [rsp+arg_8], rbx
0x1400068bd  push    rdi
0x1400068be  sub     rsp, 20h
0x1400068c2  mov     dword ptr [rcx], 0
0x1400068c8  lea     rdi, [rcx+8]
0x1400068cc  mov     rax, [rcx+10h]
0x1400068d0  mov     rbx, rcx
0x1400068d3  mov     qword ptr [rcx+10h], 0
0x1400068db  mov     rcx, rdi; SRWLock
0x1400068de  mov     [rsp+28h+pti], rax
0x1400068e3  call    cs:__imp_AcquireSRWLockExclusive
0x1400068ea  nop     dword ptr [rax+rax+00h]
0x1400068ef  mov     rcx, rbx
0x1400068f2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1400068f7  test    rdi, rdi
0x1400068fa  jz      short loc_14000690B
0x1400068fc  mov     rcx, rdi; SRWLock
0x1400068ff  call    cs:__imp_ReleaseSRWLockExclusive
0x140006906  nop     dword ptr [rax+rax+00h]
0x14000690b  xor     edx, edx
0x14000690d  lea     rcx, [rsp+28h+pti]
0x140006912  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006917  mov     rbx, [rsp+28h+pti]
0x14000691c  test    rbx, rbx
0x14000691f  jz      short loc_14000695B
0x140006921  xor     r9d, r9d; msWindowLength
0x140006924  xor     r8d, r8d; msPeriod
0x140006927  xor     edx, edx; pftDueTime
0x140006929  mov     rcx, rbx; pti
0x14000692c  call    cs:__imp_SetThreadpoolTimer
0x140006933  nop     dword ptr [rax+rax+00h]
0x140006938  mov     edx, 1; fCancelPendingCallbacks
0x14000693d  mov     rcx, rbx; pti
0x140006940  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006947  nop     dword ptr [rax+rax+00h]
0x14000694c  mov     rcx, rbx; pti
0x14000694f  call    cs:__imp_CloseThreadpoolTimer
0x140006956  nop     dword ptr [rax+rax+00h]
0x14000695b  mov     rbx, [rsp+28h+arg_8]
0x140006960  add     rsp, 20h
0x140006964  pop     rdi
0x140006965  retn
```
