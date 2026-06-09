# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180025dd0`
- end: `0x180025e5e`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f810`

## callees

- `0x180025dd0`
- `0x1800263b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025df5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025df5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025e48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025e29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025e29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025e37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025e37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025e40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025e40`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _TP_TIMER *Ptr; // rdi
  DWORD LastError; // ebx

  v1 = this + 1;
  LODWORD(this->Ptr) = 0;
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
0x180025dd0  mov     [rsp+arg_8], rbx
0x180025dd5  mov     [rsp+arg_10], rsi
0x180025dda  push    rdi
0x180025ddb  sub     rsp, 20h
0x180025ddf  xor     eax, eax
0x180025de1  lea     rsi, [rcx+8]
0x180025de5  mov     [rcx], eax
0x180025de7  mov     rbx, rcx
0x180025dea  mov     rdi, [rcx+10h]
0x180025dee  mov     [rcx+10h], rax
0x180025df2  mov     rcx, rsi; SRWLock
0x180025df5  call    cs:__imp_AcquireSRWLockExclusive
0x180025dfb  mov     rcx, rbx
0x180025dfe  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180025e03  test    rsi, rsi
0x180025e06  jz      short loc_180025E11
0x180025e08  mov     rcx, rsi; SRWLock
0x180025e0b  call    cs:__imp_ReleaseSRWLockExclusive
0x180025e11  test    rdi, rdi
0x180025e14  jz      short loc_180025E4E
0x180025e16  call    cs:__imp_GetLastError
0x180025e1c  xor     r9d, r9d; msWindowLength
0x180025e1f  xor     r8d, r8d; msPeriod
0x180025e22  xor     edx, edx; pftDueTime
0x180025e24  mov     rcx, rdi; pti
0x180025e27  mov     ebx, eax
0x180025e29  call    cs:__imp_SetThreadpoolTimer
0x180025e2f  mov     edx, 1; fCancelPendingCallbacks
0x180025e34  mov     rcx, rdi; pti
0x180025e37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025e3d  mov     rcx, rdi; pti
0x180025e40  call    cs:__imp_CloseThreadpoolTimer
0x180025e46  mov     ecx, ebx; dwErrCode
0x180025e48  call    cs:__imp_SetLastError
0x180025e4e  mov     rbx, [rsp+28h+arg_8]
0x180025e53  mov     rsi, [rsp+28h+arg_10]
0x180025e58  add     rsp, 20h
0x180025e5c  pop     rdi
0x180025e5d  retn
```
