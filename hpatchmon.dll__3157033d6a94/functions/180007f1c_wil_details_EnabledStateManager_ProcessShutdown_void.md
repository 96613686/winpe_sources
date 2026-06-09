# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180007f1c`
- end: `0x180007fb0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040c0`
- `0x180014560`

## callees

- `0x180007f1c`
- `0x180008528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f89`

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
0x180007f1c  mov     [rsp+arg_0], rbx
0x180007f21  mov     [rsp+arg_8], rsi
0x180007f26  push    rdi
0x180007f27  sub     rsp, 20h
0x180007f2b  mov     dword ptr [rcx], 0
0x180007f31  lea     rdi, [rcx+8]
0x180007f35  mov     rsi, [rcx+10h]
0x180007f39  mov     rbx, rcx
0x180007f3c  mov     qword ptr [rcx+10h], 0
0x180007f44  mov     rcx, rdi; SRWLock
0x180007f47  call    cs:__imp_AcquireSRWLockExclusive
0x180007f4d  mov     rcx, rbx
0x180007f50  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180007f55  test    rdi, rdi
0x180007f58  jz      short loc_180007F63
0x180007f5a  mov     rcx, rdi; SRWLock
0x180007f5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f63  test    rsi, rsi
0x180007f66  jz      short loc_180007FA0
0x180007f68  call    cs:__imp_GetLastError
0x180007f6e  xor     r9d, r9d; msWindowLength
0x180007f71  xor     r8d, r8d; msPeriod
0x180007f74  xor     edx, edx; pftDueTime
0x180007f76  mov     rcx, rsi; pti
0x180007f79  mov     ebx, eax
0x180007f7b  call    cs:__imp_SetThreadpoolTimer
0x180007f81  mov     edx, 1; fCancelPendingCallbacks
0x180007f86  mov     rcx, rsi; pti
0x180007f89  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007f8f  mov     rcx, rsi; pti
0x180007f92  call    cs:__imp_CloseThreadpoolTimer
0x180007f98  mov     ecx, ebx; dwErrCode
0x180007f9a  call    cs:__imp_SetLastError
0x180007fa0  mov     rbx, [rsp+28h+arg_0]
0x180007fa5  mov     rsi, [rsp+28h+arg_8]
0x180007faa  add     rsp, 20h
0x180007fae  pop     rdi
0x180007faf  retn
```
