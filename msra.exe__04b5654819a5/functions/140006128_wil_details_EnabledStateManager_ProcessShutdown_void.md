# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140006128`
- end: `0x1400061d7`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003548`
- `0x14004bf70`

## callees

- `0x140006128`
- `0x140006568`
- `0x140009900`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14000619c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000619c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006153`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006153`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400061bf`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400061bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000616f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000616f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400061b0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400061b0`

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
0x140006128  mov     [rsp+arg_8], rbx
0x14000612d  push    rdi
0x14000612e  sub     rsp, 20h
0x140006132  mov     dword ptr [rcx], 0
0x140006138  lea     rdi, [rcx+8]
0x14000613c  mov     rax, [rcx+10h]
0x140006140  mov     rbx, rcx
0x140006143  mov     qword ptr [rcx+10h], 0
0x14000614b  mov     rcx, rdi; SRWLock
0x14000614e  mov     [rsp+28h+pti], rax
0x140006153  call    cs:__imp_AcquireSRWLockExclusive
0x14000615a  nop     dword ptr [rax+rax+00h]
0x14000615f  mov     rcx, rbx
0x140006162  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140006167  test    rdi, rdi
0x14000616a  jz      short loc_14000617B
0x14000616c  mov     rcx, rdi; SRWLock
0x14000616f  call    cs:__imp_ReleaseSRWLockExclusive
0x140006176  nop     dword ptr [rax+rax+00h]
0x14000617b  xor     edx, edx
0x14000617d  lea     rcx, [rsp+28h+pti]
0x140006182  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006187  mov     rbx, [rsp+28h+pti]
0x14000618c  test    rbx, rbx
0x14000618f  jz      short loc_1400061CB
0x140006191  xor     r9d, r9d; msWindowLength
0x140006194  xor     r8d, r8d; msPeriod
0x140006197  xor     edx, edx; pftDueTime
0x140006199  mov     rcx, rbx; pti
0x14000619c  call    cs:__imp_SetThreadpoolTimer
0x1400061a3  nop     dword ptr [rax+rax+00h]
0x1400061a8  mov     edx, 1; fCancelPendingCallbacks
0x1400061ad  mov     rcx, rbx; pti
0x1400061b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400061b7  nop     dword ptr [rax+rax+00h]
0x1400061bc  mov     rcx, rbx; pti
0x1400061bf  call    cs:__imp_CloseThreadpoolTimer
0x1400061c6  nop     dword ptr [rax+rax+00h]
0x1400061cb  mov     rbx, [rsp+28h+arg_8]
0x1400061d0  add     rsp, 20h
0x1400061d4  pop     rdi
0x1400061d5  retn
```
