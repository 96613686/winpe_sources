# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000a57c`
- end: `0x18000a610`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009370`
- `0x180032a30`

## callees

- `0x18000a57c`
- `0x18000ab0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a5bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a5bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a5a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5e9`

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
0x18000a57c  mov     [rsp+arg_0], rbx
0x18000a581  mov     [rsp+arg_8], rsi
0x18000a586  push    rdi
0x18000a587  sub     rsp, 20h
0x18000a58b  mov     dword ptr [rcx], 0
0x18000a591  lea     rdi, [rcx+8]
0x18000a595  mov     rsi, [rcx+10h]
0x18000a599  mov     rbx, rcx
0x18000a59c  mov     qword ptr [rcx+10h], 0
0x18000a5a4  mov     rcx, rdi; SRWLock
0x18000a5a7  call    cs:__imp_AcquireSRWLockExclusive
0x18000a5ad  mov     rcx, rbx
0x18000a5b0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000a5b5  test    rdi, rdi
0x18000a5b8  jz      short loc_18000A5C3
0x18000a5ba  mov     rcx, rdi; SRWLock
0x18000a5bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a5c3  test    rsi, rsi
0x18000a5c6  jz      short loc_18000A600
0x18000a5c8  call    cs:__imp_GetLastError
0x18000a5ce  xor     r9d, r9d; msWindowLength
0x18000a5d1  xor     r8d, r8d; msPeriod
0x18000a5d4  xor     edx, edx; pftDueTime
0x18000a5d6  mov     rcx, rsi; pti
0x18000a5d9  mov     ebx, eax
0x18000a5db  call    cs:__imp_SetThreadpoolTimer
0x18000a5e1  mov     edx, 1; fCancelPendingCallbacks
0x18000a5e6  mov     rcx, rsi; pti
0x18000a5e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a5ef  mov     rcx, rsi; pti
0x18000a5f2  call    cs:__imp_CloseThreadpoolTimer
0x18000a5f8  mov     ecx, ebx; dwErrCode
0x18000a5fa  call    cs:__imp_SetLastError
0x18000a600  mov     rbx, [rsp+28h+arg_0]
0x18000a605  mov     rsi, [rsp+28h+arg_8]
0x18000a60a  add     rsp, 20h
0x18000a60e  pop     rdi
0x18000a60f  retn
```
