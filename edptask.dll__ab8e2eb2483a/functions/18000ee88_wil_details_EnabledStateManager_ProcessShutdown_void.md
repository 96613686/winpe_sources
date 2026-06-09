# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000ee88`
- end: `0x18000ef1c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000769c`
- `0x180013df0`

## callees

- `0x18000ee88`
- `0x18000f464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eec9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eec9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eeb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eeb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eefe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eefe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eef5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eef5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eee7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eee7`

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
0x18000ee88  mov     [rsp+arg_0], rbx
0x18000ee8d  mov     [rsp+arg_8], rsi
0x18000ee92  push    rdi
0x18000ee93  sub     rsp, 20h
0x18000ee97  mov     dword ptr [rcx], 0
0x18000ee9d  lea     rdi, [rcx+8]
0x18000eea1  mov     rsi, [rcx+10h]
0x18000eea5  mov     rbx, rcx
0x18000eea8  mov     qword ptr [rcx+10h], 0
0x18000eeb0  mov     rcx, rdi; SRWLock
0x18000eeb3  call    cs:__imp_AcquireSRWLockExclusive
0x18000eeb9  mov     rcx, rbx
0x18000eebc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000eec1  test    rdi, rdi
0x18000eec4  jz      short loc_18000EECF
0x18000eec6  mov     rcx, rdi; SRWLock
0x18000eec9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eecf  test    rsi, rsi
0x18000eed2  jz      short loc_18000EF0C
0x18000eed4  call    cs:__imp_GetLastError
0x18000eeda  xor     r9d, r9d; msWindowLength
0x18000eedd  xor     r8d, r8d; msPeriod
0x18000eee0  xor     edx, edx; pftDueTime
0x18000eee2  mov     rcx, rsi; pti
0x18000eee5  mov     ebx, eax
0x18000eee7  call    cs:__imp_SetThreadpoolTimer
0x18000eeed  mov     edx, 1; fCancelPendingCallbacks
0x18000eef2  mov     rcx, rsi; pti
0x18000eef5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000eefb  mov     rcx, rsi; pti
0x18000eefe  call    cs:__imp_CloseThreadpoolTimer
0x18000ef04  mov     ecx, ebx; dwErrCode
0x18000ef06  call    cs:__imp_SetLastError
0x18000ef0c  mov     rbx, [rsp+28h+arg_0]
0x18000ef11  mov     rsi, [rsp+28h+arg_8]
0x18000ef16  add     rsp, 20h
0x18000ef1a  pop     rdi
0x18000ef1b  retn
```
