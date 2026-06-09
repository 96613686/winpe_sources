# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001d650`
- end: `0x18001d6ff`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800173cc`
- `0x1800c8900`

## callees

- `0x18001d650`
- `0x18001dc18`
- `0x180021d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d67b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d67b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d697`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d6c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d6c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d6e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d6e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d6d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d6d8`

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
0x18001d650  mov     [rsp+arg_8], rbx
0x18001d655  push    rdi
0x18001d656  sub     rsp, 20h
0x18001d65a  mov     dword ptr [rcx], 0
0x18001d660  lea     rdi, [rcx+8]
0x18001d664  mov     rax, [rcx+10h]
0x18001d668  mov     rbx, rcx
0x18001d66b  mov     qword ptr [rcx+10h], 0
0x18001d673  mov     rcx, rdi; SRWLock
0x18001d676  mov     [rsp+28h+pti], rax
0x18001d67b  call    cs:__imp_AcquireSRWLockExclusive
0x18001d682  nop     dword ptr [rax+rax+00h]
0x18001d687  mov     rcx, rbx
0x18001d68a  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001d68f  test    rdi, rdi
0x18001d692  jz      short loc_18001D6A3
0x18001d694  mov     rcx, rdi; SRWLock
0x18001d697  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d69e  nop     dword ptr [rax+rax+00h]
0x18001d6a3  xor     edx, edx
0x18001d6a5  lea     rcx, [rsp+28h+pti]
0x18001d6aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d6af  mov     rbx, [rsp+28h+pti]
0x18001d6b4  test    rbx, rbx
0x18001d6b7  jz      short loc_18001D6F3
0x18001d6b9  xor     r9d, r9d; msWindowLength
0x18001d6bc  xor     r8d, r8d; msPeriod
0x18001d6bf  xor     edx, edx; pftDueTime
0x18001d6c1  mov     rcx, rbx; pti
0x18001d6c4  call    cs:__imp_SetThreadpoolTimer
0x18001d6cb  nop     dword ptr [rax+rax+00h]
0x18001d6d0  mov     edx, 1; fCancelPendingCallbacks
0x18001d6d5  mov     rcx, rbx; pti
0x18001d6d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d6df  nop     dword ptr [rax+rax+00h]
0x18001d6e4  mov     rcx, rbx; pti
0x18001d6e7  call    cs:__imp_CloseThreadpoolTimer
0x18001d6ee  nop     dword ptr [rax+rax+00h]
0x18001d6f3  mov     rbx, [rsp+28h+arg_8]
0x18001d6f8  add     rsp, 20h
0x18001d6fc  pop     rdi
0x18001d6fd  retn
```
