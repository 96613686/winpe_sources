# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000a35c`
- end: `0x18000a3f0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076fc`
- `0x180039c40`

## callees

- `0x18000a35c`
- `0x18000a87c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a39d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a39d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a387`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a387`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3bb`

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
0x18000a35c  mov     [rsp+arg_0], rbx
0x18000a361  mov     [rsp+arg_8], rsi
0x18000a366  push    rdi
0x18000a367  sub     rsp, 20h
0x18000a36b  mov     dword ptr [rcx], 0
0x18000a371  lea     rdi, [rcx+8]
0x18000a375  mov     rsi, [rcx+10h]
0x18000a379  mov     rbx, rcx
0x18000a37c  mov     qword ptr [rcx+10h], 0
0x18000a384  mov     rcx, rdi; SRWLock
0x18000a387  call    cs:__imp_AcquireSRWLockExclusive
0x18000a38d  mov     rcx, rbx
0x18000a390  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000a395  test    rdi, rdi
0x18000a398  jz      short loc_18000A3A3
0x18000a39a  mov     rcx, rdi; SRWLock
0x18000a39d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a3a3  test    rsi, rsi
0x18000a3a6  jz      short loc_18000A3E0
0x18000a3a8  call    cs:__imp_GetLastError
0x18000a3ae  xor     r9d, r9d; msWindowLength
0x18000a3b1  xor     r8d, r8d; msPeriod
0x18000a3b4  xor     edx, edx; pftDueTime
0x18000a3b6  mov     rcx, rsi; pti
0x18000a3b9  mov     ebx, eax
0x18000a3bb  call    cs:__imp_SetThreadpoolTimer
0x18000a3c1  mov     edx, 1; fCancelPendingCallbacks
0x18000a3c6  mov     rcx, rsi; pti
0x18000a3c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a3cf  mov     rcx, rsi; pti
0x18000a3d2  call    cs:__imp_CloseThreadpoolTimer
0x18000a3d8  mov     ecx, ebx; dwErrCode
0x18000a3da  call    cs:__imp_SetLastError
0x18000a3e0  mov     rbx, [rsp+28h+arg_0]
0x18000a3e5  mov     rsi, [rsp+28h+arg_8]
0x18000a3ea  add     rsp, 20h
0x18000a3ee  pop     rdi
0x18000a3ef  retn
```
