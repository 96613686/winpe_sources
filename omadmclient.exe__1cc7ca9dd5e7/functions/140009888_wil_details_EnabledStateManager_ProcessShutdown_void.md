# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140009888`
- end: `0x140009937`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400068a4`
- `0x140068210`

## callees

- `0x140009888`
- `0x140009d14`
- `0x14000d1a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400098cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400098cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400098b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400098b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400098fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400098fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009910`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009910`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000991f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000991f`

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
0x140009888  mov     [rsp+arg_8], rbx
0x14000988d  push    rdi
0x14000988e  sub     rsp, 20h
0x140009892  mov     dword ptr [rcx], 0
0x140009898  lea     rdi, [rcx+8]
0x14000989c  mov     rax, [rcx+10h]
0x1400098a0  mov     rbx, rcx
0x1400098a3  mov     qword ptr [rcx+10h], 0
0x1400098ab  mov     rcx, rdi; SRWLock
0x1400098ae  mov     [rsp+28h+pti], rax
0x1400098b3  call    cs:__imp_AcquireSRWLockExclusive
0x1400098ba  nop     dword ptr [rax+rax+00h]
0x1400098bf  mov     rcx, rbx
0x1400098c2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1400098c7  test    rdi, rdi
0x1400098ca  jz      short loc_1400098DB
0x1400098cc  mov     rcx, rdi; SRWLock
0x1400098cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1400098d6  nop     dword ptr [rax+rax+00h]
0x1400098db  xor     edx, edx
0x1400098dd  lea     rcx, [rsp+28h+pti]
0x1400098e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400098e7  mov     rbx, [rsp+28h+pti]
0x1400098ec  test    rbx, rbx
0x1400098ef  jz      short loc_14000992B
0x1400098f1  xor     r9d, r9d; msWindowLength
0x1400098f4  xor     r8d, r8d; msPeriod
0x1400098f7  xor     edx, edx; pftDueTime
0x1400098f9  mov     rcx, rbx; pti
0x1400098fc  call    cs:__imp_SetThreadpoolTimer
0x140009903  nop     dword ptr [rax+rax+00h]
0x140009908  mov     edx, 1; fCancelPendingCallbacks
0x14000990d  mov     rcx, rbx; pti
0x140009910  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009917  nop     dword ptr [rax+rax+00h]
0x14000991c  mov     rcx, rbx; pti
0x14000991f  call    cs:__imp_CloseThreadpoolTimer
0x140009926  nop     dword ptr [rax+rax+00h]
0x14000992b  mov     rbx, [rsp+28h+arg_8]
0x140009930  add     rsp, 20h
0x140009934  pop     rdi
0x140009935  retn
```
