# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140010e9c`
- end: `0x140010f30`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e358`
- `0x14003da20`

## callees

- `0x140010e9c`
- `0x140011330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010edd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ec7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010f12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010f12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010f09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010f09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010efb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010efb`

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
0x140010e9c  mov     [rsp+arg_0], rbx
0x140010ea1  mov     [rsp+arg_8], rsi
0x140010ea6  push    rdi
0x140010ea7  sub     rsp, 20h
0x140010eab  mov     dword ptr [rcx], 0
0x140010eb1  lea     rdi, [rcx+8]
0x140010eb5  mov     rsi, [rcx+10h]
0x140010eb9  mov     rbx, rcx
0x140010ebc  mov     qword ptr [rcx+10h], 0
0x140010ec4  mov     rcx, rdi; SRWLock
0x140010ec7  call    cs:__imp_AcquireSRWLockExclusive
0x140010ecd  mov     rcx, rbx
0x140010ed0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140010ed5  test    rdi, rdi
0x140010ed8  jz      short loc_140010EE3
0x140010eda  mov     rcx, rdi; SRWLock
0x140010edd  call    cs:__imp_ReleaseSRWLockExclusive
0x140010ee3  test    rsi, rsi
0x140010ee6  jz      short loc_140010F20
0x140010ee8  call    cs:__imp_GetLastError
0x140010eee  xor     r9d, r9d; msWindowLength
0x140010ef1  xor     r8d, r8d; msPeriod
0x140010ef4  xor     edx, edx; pftDueTime
0x140010ef6  mov     rcx, rsi; pti
0x140010ef9  mov     ebx, eax
0x140010efb  call    cs:__imp_SetThreadpoolTimer
0x140010f01  mov     edx, 1; fCancelPendingCallbacks
0x140010f06  mov     rcx, rsi; pti
0x140010f09  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010f0f  mov     rcx, rsi; pti
0x140010f12  call    cs:__imp_CloseThreadpoolTimer
0x140010f18  mov     ecx, ebx; dwErrCode
0x140010f1a  call    cs:__imp_SetLastError
0x140010f20  mov     rbx, [rsp+28h+arg_0]
0x140010f25  mov     rsi, [rsp+28h+arg_8]
0x140010f2a  add     rsp, 20h
0x140010f2e  pop     rdi
0x140010f2f  retn
```
