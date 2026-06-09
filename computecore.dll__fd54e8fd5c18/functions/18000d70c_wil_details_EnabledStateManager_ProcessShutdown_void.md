# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000d70c`
- end: `0x18000d7a0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a01c`
- `0x1800a1950`

## callees

- `0x18000d70c`
- `0x18000dc40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d74d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d74d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d737`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d78a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d758`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d782`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d782`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d779`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d76b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d76b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _TP_TIMER *Ptr; // rdi
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
0x18000d70c  mov     [rsp+arg_8], rbx
0x18000d711  mov     [rsp+arg_10], rsi
0x18000d716  push    rdi
0x18000d717  sub     rsp, 20h
0x18000d71b  mov     dword ptr [rcx], 0
0x18000d721  lea     rsi, [rcx+8]
0x18000d725  mov     rdi, [rcx+10h]
0x18000d729  mov     rbx, rcx
0x18000d72c  mov     qword ptr [rcx+10h], 0
0x18000d734  mov     rcx, rsi; SRWLock
0x18000d737  call    cs:__imp_AcquireSRWLockExclusive
0x18000d73d  mov     rcx, rbx
0x18000d740  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000d745  test    rsi, rsi
0x18000d748  jz      short loc_18000D753
0x18000d74a  mov     rcx, rsi; SRWLock
0x18000d74d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d753  test    rdi, rdi
0x18000d756  jz      short loc_18000D790
0x18000d758  call    cs:__imp_GetLastError
0x18000d75e  xor     r9d, r9d; msWindowLength
0x18000d761  xor     r8d, r8d; msPeriod
0x18000d764  xor     edx, edx; pftDueTime
0x18000d766  mov     rcx, rdi; pti
0x18000d769  mov     ebx, eax
0x18000d76b  call    cs:__imp_SetThreadpoolTimer
0x18000d771  mov     edx, 1; fCancelPendingCallbacks
0x18000d776  mov     rcx, rdi; pti
0x18000d779  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d77f  mov     rcx, rdi; pti
0x18000d782  call    cs:__imp_CloseThreadpoolTimer
0x18000d788  mov     ecx, ebx; dwErrCode
0x18000d78a  call    cs:__imp_SetLastError
0x18000d790  mov     rbx, [rsp+28h+arg_8]
0x18000d795  mov     rsi, [rsp+28h+arg_10]
0x18000d79a  add     rsp, 20h
0x18000d79e  pop     rdi
0x18000d79f  retn
```
