# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180008ea8`
- end: `0x180008f3c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006508`
- `0x180060600`

## callees

- `0x180008ea8`
- `0x18000933c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ee9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ee9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ed3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ef4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f15`

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
0x180008ea8  mov     [rsp+arg_0], rbx
0x180008ead  mov     [rsp+arg_8], rsi
0x180008eb2  push    rdi
0x180008eb3  sub     rsp, 20h
0x180008eb7  mov     dword ptr [rcx], 0
0x180008ebd  lea     rdi, [rcx+8]
0x180008ec1  mov     rsi, [rcx+10h]
0x180008ec5  mov     rbx, rcx
0x180008ec8  mov     qword ptr [rcx+10h], 0
0x180008ed0  mov     rcx, rdi; SRWLock
0x180008ed3  call    cs:__imp_AcquireSRWLockExclusive
0x180008ed9  mov     rcx, rbx
0x180008edc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180008ee1  test    rdi, rdi
0x180008ee4  jz      short loc_180008EEF
0x180008ee6  mov     rcx, rdi; SRWLock
0x180008ee9  call    cs:__imp_ReleaseSRWLockExclusive
0x180008eef  test    rsi, rsi
0x180008ef2  jz      short loc_180008F2C
0x180008ef4  call    cs:__imp_GetLastError
0x180008efa  xor     r9d, r9d; msWindowLength
0x180008efd  xor     r8d, r8d; msPeriod
0x180008f00  xor     edx, edx; pftDueTime
0x180008f02  mov     rcx, rsi; pti
0x180008f05  mov     ebx, eax
0x180008f07  call    cs:__imp_SetThreadpoolTimer
0x180008f0d  mov     edx, 1; fCancelPendingCallbacks
0x180008f12  mov     rcx, rsi; pti
0x180008f15  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008f1b  mov     rcx, rsi; pti
0x180008f1e  call    cs:__imp_CloseThreadpoolTimer
0x180008f24  mov     ecx, ebx; dwErrCode
0x180008f26  call    cs:__imp_SetLastError
0x180008f2c  mov     rbx, [rsp+28h+arg_0]
0x180008f31  mov     rsi, [rsp+28h+arg_8]
0x180008f36  add     rsp, 20h
0x180008f3a  pop     rdi
0x180008f3b  retn
```
