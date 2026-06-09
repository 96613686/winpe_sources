# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000f090`
- end: `0x18000f13c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `172`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007fc4`
- `0x180023730`

## callees

- `0x18000f090`
- `0x18000f97c`
- `0x180018824`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18000f101`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f101`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f0b8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f0b8`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f124`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f124`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f0d4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f0d4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f115`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f115`

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
0x18000f090  mov     [rsp+arg_8], rbx
0x18000f095  push    rdi
0x18000f096  sub     rsp, 20h
0x18000f09a  mov     dword ptr [rcx], 0
0x18000f0a0  lea     rdi, [rcx+8]
0x18000f0a4  mov     rax, [rcx+10h]
0x18000f0a8  mov     rbx, rcx
0x18000f0ab  and     qword ptr [rcx+10h], 0
0x18000f0b0  mov     rcx, rdi; SRWLock
0x18000f0b3  mov     [rsp+28h+pti], rax
0x18000f0b8  call    cs:__imp_AcquireSRWLockExclusive
0x18000f0bf  nop     dword ptr [rax+rax+00h]
0x18000f0c4  mov     rcx, rbx
0x18000f0c7  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000f0cc  test    rdi, rdi
0x18000f0cf  jz      short loc_18000F0E0
0x18000f0d1  mov     rcx, rdi; SRWLock
0x18000f0d4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f0db  nop     dword ptr [rax+rax+00h]
0x18000f0e0  xor     edx, edx
0x18000f0e2  lea     rcx, [rsp+28h+pti]
0x18000f0e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f0ec  mov     rbx, [rsp+28h+pti]
0x18000f0f1  test    rbx, rbx
0x18000f0f4  jz      short loc_18000F130
0x18000f0f6  xor     r9d, r9d; msWindowLength
0x18000f0f9  xor     r8d, r8d; msPeriod
0x18000f0fc  xor     edx, edx; pftDueTime
0x18000f0fe  mov     rcx, rbx; pti
0x18000f101  call    cs:__imp_SetThreadpoolTimer
0x18000f108  nop     dword ptr [rax+rax+00h]
0x18000f10d  mov     edx, 1; fCancelPendingCallbacks
0x18000f112  mov     rcx, rbx; pti
0x18000f115  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f11c  nop     dword ptr [rax+rax+00h]
0x18000f121  mov     rcx, rbx; pti
0x18000f124  call    cs:__imp_CloseThreadpoolTimer
0x18000f12b  nop     dword ptr [rax+rax+00h]
0x18000f130  mov     rbx, [rsp+28h+arg_8]
0x18000f135  add     rsp, 20h
0x18000f139  pop     rdi
0x18000f13a  retn
```
