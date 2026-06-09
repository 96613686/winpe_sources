# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800baa68`
- end: `0x1800bab17`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800b4850`
- `0x1800ea030`

## callees

- `0x1800baa68`
- `0x1800bb2f8`
- `0x1800be088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800baaaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800baaaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800baa93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800baa93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800baadc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800baadc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800baaf0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800baaf0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800baaff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800baaff`

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
0x1800baa68  mov     [rsp+arg_8], rbx
0x1800baa6d  push    rdi
0x1800baa6e  sub     rsp, 20h
0x1800baa72  mov     dword ptr [rcx], 0
0x1800baa78  lea     rdi, [rcx+8]
0x1800baa7c  mov     rax, [rcx+10h]
0x1800baa80  mov     rbx, rcx
0x1800baa83  mov     qword ptr [rcx+10h], 0
0x1800baa8b  mov     rcx, rdi; SRWLock
0x1800baa8e  mov     [rsp+28h+pti], rax
0x1800baa93  call    cs:__imp_AcquireSRWLockExclusive
0x1800baa9a  nop     dword ptr [rax+rax+00h]
0x1800baa9f  mov     rcx, rbx
0x1800baaa2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800baaa7  test    rdi, rdi
0x1800baaaa  jz      short loc_1800BAABB
0x1800baaac  mov     rcx, rdi; SRWLock
0x1800baaaf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800baab6  nop     dword ptr [rax+rax+00h]
0x1800baabb  xor     edx, edx
0x1800baabd  lea     rcx, [rsp+28h+pti]
0x1800baac2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800baac7  mov     rbx, [rsp+28h+pti]
0x1800baacc  test    rbx, rbx
0x1800baacf  jz      short loc_1800BAB0B
0x1800baad1  xor     r9d, r9d; msWindowLength
0x1800baad4  xor     r8d, r8d; msPeriod
0x1800baad7  xor     edx, edx; pftDueTime
0x1800baad9  mov     rcx, rbx; pti
0x1800baadc  call    cs:__imp_SetThreadpoolTimer
0x1800baae3  nop     dword ptr [rax+rax+00h]
0x1800baae8  mov     edx, 1; fCancelPendingCallbacks
0x1800baaed  mov     rcx, rbx; pti
0x1800baaf0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800baaf7  nop     dword ptr [rax+rax+00h]
0x1800baafc  mov     rcx, rbx; pti
0x1800baaff  call    cs:__imp_CloseThreadpoolTimer
0x1800bab06  nop     dword ptr [rax+rax+00h]
0x1800bab0b  mov     rbx, [rsp+28h+arg_8]
0x1800bab10  add     rsp, 20h
0x1800bab14  pop     rdi
0x1800bab15  retn
```
