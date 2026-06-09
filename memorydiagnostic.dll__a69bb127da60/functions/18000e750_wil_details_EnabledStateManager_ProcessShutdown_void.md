# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000e750`
- end: `0x18000e7e4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800081b0`
- `0x180022150`

## callees

- `0x18000e750`
- `0x18000f09c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18000e7af`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e7af`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e77b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e77b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e7c6`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e7c6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e791`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e791`
- `KERNEL32!GetLastError` at `0x18000e79c`
- `KERNEL32!GetLastError` at `0x18000e79c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e7bd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e7bd`
- `KERNEL32!SetLastError` at `0x18000e7ce`
- `KERNEL32!SetLastError` at `0x18000e7ce`

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
0x18000e750  mov     [rsp+arg_0], rbx
0x18000e755  mov     [rsp+arg_8], rsi
0x18000e75a  push    rdi
0x18000e75b  sub     rsp, 20h
0x18000e75f  mov     dword ptr [rcx], 0
0x18000e765  lea     rdi, [rcx+8]
0x18000e769  mov     rsi, [rcx+10h]
0x18000e76d  mov     rbx, rcx
0x18000e770  mov     qword ptr [rcx+10h], 0
0x18000e778  mov     rcx, rdi; SRWLock
0x18000e77b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e781  mov     rcx, rbx
0x18000e784  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000e789  test    rdi, rdi
0x18000e78c  jz      short loc_18000E797
0x18000e78e  mov     rcx, rdi; SRWLock
0x18000e791  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e797  test    rsi, rsi
0x18000e79a  jz      short loc_18000E7D4
0x18000e79c  call    cs:__imp_GetLastError
0x18000e7a2  xor     r9d, r9d; msWindowLength
0x18000e7a5  xor     r8d, r8d; msPeriod
0x18000e7a8  xor     edx, edx; pftDueTime
0x18000e7aa  mov     rcx, rsi; pti
0x18000e7ad  mov     ebx, eax
0x18000e7af  call    cs:__imp_SetThreadpoolTimer
0x18000e7b5  mov     edx, 1; fCancelPendingCallbacks
0x18000e7ba  mov     rcx, rsi; pti
0x18000e7bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e7c3  mov     rcx, rsi; pti
0x18000e7c6  call    cs:__imp_CloseThreadpoolTimer
0x18000e7cc  mov     ecx, ebx; dwErrCode
0x18000e7ce  call    cs:__imp_SetLastError
0x18000e7d4  mov     rbx, [rsp+28h+arg_0]
0x18000e7d9  mov     rsi, [rsp+28h+arg_8]
0x18000e7de  add     rsp, 20h
0x18000e7e2  pop     rdi
0x18000e7e3  retn
```
