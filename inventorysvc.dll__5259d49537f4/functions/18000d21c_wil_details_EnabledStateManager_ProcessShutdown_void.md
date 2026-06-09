# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000d21c`
- end: `0x18000d2b0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007850`
- `0x1800d0870`

## callees

- `0x18000d21c`
- `0x18000d828`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d247`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d25d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d25d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d29a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d27b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d27b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d292`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d292`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d289`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d289`

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
0x18000d21c  mov     [rsp+arg_0], rbx
0x18000d221  mov     [rsp+arg_8], rsi
0x18000d226  push    rdi
0x18000d227  sub     rsp, 20h
0x18000d22b  mov     dword ptr [rcx], 0
0x18000d231  lea     rdi, [rcx+8]
0x18000d235  mov     rsi, [rcx+10h]
0x18000d239  mov     rbx, rcx
0x18000d23c  mov     qword ptr [rcx+10h], 0
0x18000d244  mov     rcx, rdi; SRWLock
0x18000d247  call    cs:__imp_AcquireSRWLockExclusive
0x18000d24d  mov     rcx, rbx
0x18000d250  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000d255  test    rdi, rdi
0x18000d258  jz      short loc_18000D263
0x18000d25a  mov     rcx, rdi; SRWLock
0x18000d25d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d263  test    rsi, rsi
0x18000d266  jz      short loc_18000D2A0
0x18000d268  call    cs:__imp_GetLastError
0x18000d26e  xor     r9d, r9d; msWindowLength
0x18000d271  xor     r8d, r8d; msPeriod
0x18000d274  xor     edx, edx; pftDueTime
0x18000d276  mov     rcx, rsi; pti
0x18000d279  mov     ebx, eax
0x18000d27b  call    cs:__imp_SetThreadpoolTimer
0x18000d281  mov     edx, 1; fCancelPendingCallbacks
0x18000d286  mov     rcx, rsi; pti
0x18000d289  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d28f  mov     rcx, rsi; pti
0x18000d292  call    cs:__imp_CloseThreadpoolTimer
0x18000d298  mov     ecx, ebx; dwErrCode
0x18000d29a  call    cs:__imp_SetLastError
0x18000d2a0  mov     rbx, [rsp+28h+arg_0]
0x18000d2a5  mov     rsi, [rsp+28h+arg_8]
0x18000d2aa  add     rsp, 20h
0x18000d2ae  pop     rdi
0x18000d2af  retn
```
