# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000b7bc`
- end: `0x18000b850`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086c8`
- `0x180115180`

## callees

- `0x18000b7bc`
- `0x18000bdc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b83a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b808`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b829`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b829`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b81b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b81b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b832`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b832`

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
0x18000b7bc  mov     [rsp+arg_0], rbx
0x18000b7c1  mov     [rsp+arg_8], rsi
0x18000b7c6  push    rdi
0x18000b7c7  sub     rsp, 20h
0x18000b7cb  mov     dword ptr [rcx], 0
0x18000b7d1  lea     rdi, [rcx+8]
0x18000b7d5  mov     rsi, [rcx+10h]
0x18000b7d9  mov     rbx, rcx
0x18000b7dc  mov     qword ptr [rcx+10h], 0
0x18000b7e4  mov     rcx, rdi; SRWLock
0x18000b7e7  call    cs:__imp_AcquireSRWLockExclusive
0x18000b7ed  mov     rcx, rbx
0x18000b7f0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000b7f5  test    rdi, rdi
0x18000b7f8  jz      short loc_18000B803
0x18000b7fa  mov     rcx, rdi; SRWLock
0x18000b7fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b803  test    rsi, rsi
0x18000b806  jz      short loc_18000B840
0x18000b808  call    cs:__imp_GetLastError
0x18000b80e  xor     r9d, r9d; msWindowLength
0x18000b811  xor     r8d, r8d; msPeriod
0x18000b814  xor     edx, edx; pftDueTime
0x18000b816  mov     rcx, rsi; pti
0x18000b819  mov     ebx, eax
0x18000b81b  call    cs:__imp_SetThreadpoolTimer
0x18000b821  mov     edx, 1; fCancelPendingCallbacks
0x18000b826  mov     rcx, rsi; pti
0x18000b829  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b82f  mov     rcx, rsi; pti
0x18000b832  call    cs:__imp_CloseThreadpoolTimer
0x18000b838  mov     ecx, ebx; dwErrCode
0x18000b83a  call    cs:__imp_SetLastError
0x18000b840  mov     rbx, [rsp+28h+arg_0]
0x18000b845  mov     rsi, [rsp+28h+arg_8]
0x18000b84a  add     rsp, 20h
0x18000b84e  pop     rdi
0x18000b84f  retn
```
