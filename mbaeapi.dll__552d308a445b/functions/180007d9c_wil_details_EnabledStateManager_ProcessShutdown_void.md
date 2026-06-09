# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180007d9c`
- end: `0x180007e30`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054bc`
- `0x18005b470`

## callees

- `0x180007d9c`
- `0x180008230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007dc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007dc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ddd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007dfb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007dfb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007e12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007e12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007e09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007e09`

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
0x180007d9c  mov     [rsp+arg_0], rbx
0x180007da1  mov     [rsp+arg_8], rsi
0x180007da6  push    rdi
0x180007da7  sub     rsp, 20h
0x180007dab  mov     dword ptr [rcx], 0
0x180007db1  lea     rdi, [rcx+8]
0x180007db5  mov     rsi, [rcx+10h]
0x180007db9  mov     rbx, rcx
0x180007dbc  mov     qword ptr [rcx+10h], 0
0x180007dc4  mov     rcx, rdi; SRWLock
0x180007dc7  call    cs:__imp_AcquireSRWLockExclusive
0x180007dcd  mov     rcx, rbx
0x180007dd0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180007dd5  test    rdi, rdi
0x180007dd8  jz      short loc_180007DE3
0x180007dda  mov     rcx, rdi; SRWLock
0x180007ddd  call    cs:__imp_ReleaseSRWLockExclusive
0x180007de3  test    rsi, rsi
0x180007de6  jz      short loc_180007E20
0x180007de8  call    cs:__imp_GetLastError
0x180007dee  xor     r9d, r9d; msWindowLength
0x180007df1  xor     r8d, r8d; msPeriod
0x180007df4  xor     edx, edx; pftDueTime
0x180007df6  mov     rcx, rsi; pti
0x180007df9  mov     ebx, eax
0x180007dfb  call    cs:__imp_SetThreadpoolTimer
0x180007e01  mov     edx, 1; fCancelPendingCallbacks
0x180007e06  mov     rcx, rsi; pti
0x180007e09  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007e0f  mov     rcx, rsi; pti
0x180007e12  call    cs:__imp_CloseThreadpoolTimer
0x180007e18  mov     ecx, ebx; dwErrCode
0x180007e1a  call    cs:__imp_SetLastError
0x180007e20  mov     rbx, [rsp+28h+arg_0]
0x180007e25  mov     rsi, [rsp+28h+arg_8]
0x180007e2a  add     rsp, 20h
0x180007e2e  pop     rdi
0x180007e2f  retn
```
