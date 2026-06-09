# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800052a0`
- end: `0x180005334`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039cc`
- `0x1800124d0`

## callees

- `0x1800052a0`
- `0x18000533c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000531e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000531e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800052cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800052cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005316`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005316`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800052ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800052ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000530d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000530d`

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
0x1800052a0  mov     [rsp+arg_0], rbx
0x1800052a5  mov     [rsp+arg_8], rsi
0x1800052aa  push    rdi
0x1800052ab  sub     rsp, 20h
0x1800052af  mov     dword ptr [rcx], 0
0x1800052b5  lea     rdi, [rcx+8]
0x1800052b9  mov     rsi, [rcx+10h]
0x1800052bd  mov     rbx, rcx
0x1800052c0  mov     qword ptr [rcx+10h], 0
0x1800052c8  mov     rcx, rdi; SRWLock
0x1800052cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800052d1  mov     rcx, rbx
0x1800052d4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800052d9  test    rdi, rdi
0x1800052dc  jz      short loc_1800052E7
0x1800052de  mov     rcx, rdi; SRWLock
0x1800052e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800052e7  test    rsi, rsi
0x1800052ea  jz      short loc_180005324
0x1800052ec  call    cs:__imp_GetLastError
0x1800052f2  xor     r9d, r9d; msWindowLength
0x1800052f5  xor     r8d, r8d; msPeriod
0x1800052f8  xor     edx, edx; pftDueTime
0x1800052fa  mov     rcx, rsi; pti
0x1800052fd  mov     ebx, eax
0x1800052ff  call    cs:__imp_SetThreadpoolTimer
0x180005305  mov     edx, 1; fCancelPendingCallbacks
0x18000530a  mov     rcx, rsi; pti
0x18000530d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005313  mov     rcx, rsi; pti
0x180005316  call    cs:__imp_CloseThreadpoolTimer
0x18000531c  mov     ecx, ebx; dwErrCode
0x18000531e  call    cs:__imp_SetLastError
0x180005324  mov     rbx, [rsp+28h+arg_0]
0x180005329  mov     rsi, [rsp+28h+arg_8]
0x18000532e  add     rsp, 20h
0x180005332  pop     rdi
0x180005333  retn
```
