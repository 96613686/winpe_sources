# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800080dc`
- end: `0x180008170`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004748`
- `0x18000d210`

## callees

- `0x1800080dc`
- `0x180008504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000815a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000815a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008128`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008107`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000811d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000811d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000813b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000813b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008152`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008152`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008149`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008149`

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
0x1800080dc  mov     [rsp+arg_0], rbx
0x1800080e1  mov     [rsp+arg_8], rsi
0x1800080e6  push    rdi
0x1800080e7  sub     rsp, 20h
0x1800080eb  mov     dword ptr [rcx], 0
0x1800080f1  lea     rdi, [rcx+8]
0x1800080f5  mov     rsi, [rcx+10h]
0x1800080f9  mov     rbx, rcx
0x1800080fc  mov     qword ptr [rcx+10h], 0
0x180008104  mov     rcx, rdi; SRWLock
0x180008107  call    cs:__imp_AcquireSRWLockExclusive
0x18000810d  mov     rcx, rbx
0x180008110  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180008115  test    rdi, rdi
0x180008118  jz      short loc_180008123
0x18000811a  mov     rcx, rdi; SRWLock
0x18000811d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008123  test    rsi, rsi
0x180008126  jz      short loc_180008160
0x180008128  call    cs:__imp_GetLastError
0x18000812e  xor     r9d, r9d; msWindowLength
0x180008131  xor     r8d, r8d; msPeriod
0x180008134  xor     edx, edx; pftDueTime
0x180008136  mov     rcx, rsi; pti
0x180008139  mov     ebx, eax
0x18000813b  call    cs:__imp_SetThreadpoolTimer
0x180008141  mov     edx, 1; fCancelPendingCallbacks
0x180008146  mov     rcx, rsi; pti
0x180008149  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000814f  mov     rcx, rsi; pti
0x180008152  call    cs:__imp_CloseThreadpoolTimer
0x180008158  mov     ecx, ebx; dwErrCode
0x18000815a  call    cs:__imp_SetLastError
0x180008160  mov     rbx, [rsp+28h+arg_0]
0x180008165  mov     rsi, [rsp+28h+arg_8]
0x18000816a  add     rsp, 20h
0x18000816e  pop     rdi
0x18000816f  retn
```
