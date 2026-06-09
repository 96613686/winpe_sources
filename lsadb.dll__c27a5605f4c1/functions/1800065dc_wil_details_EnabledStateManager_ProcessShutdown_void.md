# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800065dc`
- end: `0x180006670`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003558`
- `0x18003ae90`

## callees

- `0x1800065dc`
- `0x180006a24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006628`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000661d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000661d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006607`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006607`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006652`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006652`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000663b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000663b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006649`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006649`

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
0x1800065dc  mov     [rsp+arg_0], rbx
0x1800065e1  mov     [rsp+arg_8], rsi
0x1800065e6  push    rdi
0x1800065e7  sub     rsp, 20h
0x1800065eb  mov     dword ptr [rcx], 0
0x1800065f1  lea     rdi, [rcx+8]
0x1800065f5  mov     rsi, [rcx+10h]
0x1800065f9  mov     rbx, rcx
0x1800065fc  mov     qword ptr [rcx+10h], 0
0x180006604  mov     rcx, rdi; SRWLock
0x180006607  call    cs:__imp_AcquireSRWLockExclusive
0x18000660d  mov     rcx, rbx
0x180006610  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006615  test    rdi, rdi
0x180006618  jz      short loc_180006623
0x18000661a  mov     rcx, rdi; SRWLock
0x18000661d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006623  test    rsi, rsi
0x180006626  jz      short loc_180006660
0x180006628  call    cs:__imp_GetLastError
0x18000662e  xor     r9d, r9d; msWindowLength
0x180006631  xor     r8d, r8d; msPeriod
0x180006634  xor     edx, edx; pftDueTime
0x180006636  mov     rcx, rsi; pti
0x180006639  mov     ebx, eax
0x18000663b  call    cs:__imp_SetThreadpoolTimer
0x180006641  mov     edx, 1; fCancelPendingCallbacks
0x180006646  mov     rcx, rsi; pti
0x180006649  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000664f  mov     rcx, rsi; pti
0x180006652  call    cs:__imp_CloseThreadpoolTimer
0x180006658  mov     ecx, ebx; dwErrCode
0x18000665a  call    cs:__imp_SetLastError
0x180006660  mov     rbx, [rsp+28h+arg_0]
0x180006665  mov     rsi, [rsp+28h+arg_8]
0x18000666a  add     rsp, 20h
0x18000666e  pop     rdi
0x18000666f  retn
```
