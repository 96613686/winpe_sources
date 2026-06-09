# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800142b0`
- end: `0x180014344`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000df6c`
- `0x180036c60`

## callees

- `0x1800142b0`
- `0x180015034`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800142db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800142db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800142f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800142f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001432e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001432e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001430f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001430f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014326`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014326`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001431d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001431d`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rsi
  DWORD LastError; // ebx

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x1800142b0  mov     [rsp+arg_0], rbx
0x1800142b5  mov     [rsp+arg_8], rsi
0x1800142ba  push    rdi
0x1800142bb  sub     rsp, 20h
0x1800142bf  mov     dword ptr [rcx], 0
0x1800142c5  lea     rdi, [rcx+8]
0x1800142c9  mov     rsi, [rcx+10h]
0x1800142cd  mov     rbx, rcx
0x1800142d0  mov     qword ptr [rcx+10h], 0
0x1800142d8  mov     rcx, rdi; SRWLock
0x1800142db  call    cs:__imp_AcquireSRWLockExclusive
0x1800142e1  mov     rcx, rbx
0x1800142e4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800142e9  test    rdi, rdi
0x1800142ec  jz      short loc_1800142F7
0x1800142ee  mov     rcx, rdi; SRWLock
0x1800142f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800142f7  test    rsi, rsi
0x1800142fa  jz      short loc_180014334
0x1800142fc  call    cs:__imp_GetLastError
0x180014302  xor     r9d, r9d; msWindowLength
0x180014305  xor     r8d, r8d; msPeriod
0x180014308  xor     edx, edx; pftDueTime
0x18001430a  mov     rcx, rsi; pti
0x18001430d  mov     ebx, eax
0x18001430f  call    cs:__imp_SetThreadpoolTimer
0x180014315  mov     edx, 1; fCancelPendingCallbacks
0x18001431a  mov     rcx, rsi; pti
0x18001431d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014323  mov     rcx, rsi; pti
0x180014326  call    cs:__imp_CloseThreadpoolTimer
0x18001432c  mov     ecx, ebx; dwErrCode
0x18001432e  call    cs:__imp_SetLastError
0x180014334  mov     rbx, [rsp+28h+arg_0]
0x180014339  mov     rsi, [rsp+28h+arg_8]
0x18001433e  add     rsp, 20h
0x180014342  pop     rdi
0x180014343  retn
```
