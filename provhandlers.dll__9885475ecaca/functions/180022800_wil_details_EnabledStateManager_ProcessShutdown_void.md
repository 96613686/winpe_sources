# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180022800`
- end: `0x180022894`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001601c`
- `0x18003e270`

## callees

- `0x180022800`
- `0x180022dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002282b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002282b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022841`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002284c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002284c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002287e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002287e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002285f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002285f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002286d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002286d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022876`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022876`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180022800  mov     [rsp+arg_0], rbx
0x180022805  mov     [rsp+arg_8], rsi
0x18002280a  push    rdi
0x18002280b  sub     rsp, 20h
0x18002280f  mov     dword ptr [rcx], 0
0x180022815  lea     rdi, [rcx+8]
0x180022819  mov     rsi, [rcx+10h]
0x18002281d  mov     rbx, rcx
0x180022820  mov     qword ptr [rcx+10h], 0
0x180022828  mov     rcx, rdi; SRWLock
0x18002282b  call    cs:__imp_AcquireSRWLockExclusive
0x180022831  mov     rcx, rbx
0x180022834  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180022839  test    rdi, rdi
0x18002283c  jz      short loc_180022847
0x18002283e  mov     rcx, rdi; SRWLock
0x180022841  call    cs:__imp_ReleaseSRWLockExclusive
0x180022847  test    rsi, rsi
0x18002284a  jz      short loc_180022884
0x18002284c  call    cs:__imp_GetLastError
0x180022852  xor     r9d, r9d; msWindowLength
0x180022855  xor     r8d, r8d; msPeriod
0x180022858  xor     edx, edx; pftDueTime
0x18002285a  mov     rcx, rsi; pti
0x18002285d  mov     ebx, eax
0x18002285f  call    cs:__imp_SetThreadpoolTimer
0x180022865  mov     edx, 1; fCancelPendingCallbacks
0x18002286a  mov     rcx, rsi; pti
0x18002286d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022873  mov     rcx, rsi; pti
0x180022876  call    cs:__imp_CloseThreadpoolTimer
0x18002287c  mov     ecx, ebx; dwErrCode
0x18002287e  call    cs:__imp_SetLastError
0x180022884  mov     rbx, [rsp+28h+arg_0]
0x180022889  mov     rsi, [rsp+28h+arg_8]
0x18002288e  add     rsp, 20h
0x180022892  pop     rdi
0x180022893  retn
```
