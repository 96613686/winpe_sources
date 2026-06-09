# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180010168`
- end: `0x180010217`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a0d8`
- `0x1800234e0`

## callees

- `0x180010168`
- `0x180010720`
- `0x1800142b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800101af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800101af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010193`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010193`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800101f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800101f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800101dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800101dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800101ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800101ff`

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
0x180010168  mov     [rsp+arg_8], rbx
0x18001016d  push    rdi
0x18001016e  sub     rsp, 20h
0x180010172  mov     dword ptr [rcx], 0
0x180010178  lea     rdi, [rcx+8]
0x18001017c  mov     rax, [rcx+10h]
0x180010180  mov     rbx, rcx
0x180010183  mov     qword ptr [rcx+10h], 0
0x18001018b  mov     rcx, rdi; SRWLock
0x18001018e  mov     [rsp+28h+pti], rax
0x180010193  call    cs:__imp_AcquireSRWLockExclusive
0x18001019a  nop     dword ptr [rax+rax+00h]
0x18001019f  mov     rcx, rbx
0x1800101a2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800101a7  test    rdi, rdi
0x1800101aa  jz      short loc_1800101BB
0x1800101ac  mov     rcx, rdi; SRWLock
0x1800101af  call    cs:__imp_ReleaseSRWLockExclusive
0x1800101b6  nop     dword ptr [rax+rax+00h]
0x1800101bb  xor     edx, edx
0x1800101bd  lea     rcx, [rsp+28h+pti]
0x1800101c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800101c7  mov     rbx, [rsp+28h+pti]
0x1800101cc  test    rbx, rbx
0x1800101cf  jz      short loc_18001020B
0x1800101d1  xor     r9d, r9d; msWindowLength
0x1800101d4  xor     r8d, r8d; msPeriod
0x1800101d7  xor     edx, edx; pftDueTime
0x1800101d9  mov     rcx, rbx; pti
0x1800101dc  call    cs:__imp_SetThreadpoolTimer
0x1800101e3  nop     dword ptr [rax+rax+00h]
0x1800101e8  mov     edx, 1; fCancelPendingCallbacks
0x1800101ed  mov     rcx, rbx; pti
0x1800101f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800101f7  nop     dword ptr [rax+rax+00h]
0x1800101fc  mov     rcx, rbx; pti
0x1800101ff  call    cs:__imp_CloseThreadpoolTimer
0x180010206  nop     dword ptr [rax+rax+00h]
0x18001020b  mov     rbx, [rsp+28h+arg_8]
0x180010210  add     rsp, 20h
0x180010214  pop     rdi
0x180010215  retn
```
