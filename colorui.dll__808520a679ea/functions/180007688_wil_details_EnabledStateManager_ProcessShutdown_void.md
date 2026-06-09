# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180007688`
- end: `0x18000771c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030bc`
- `0x180018960`

## callees

- `0x180007688`
- `0x180007ba4`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800076f5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800076f5`
- `KERNEL32!GetLastError` at `0x1800076d4`
- `KERNEL32!GetLastError` at `0x1800076d4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800076c9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800076c9`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800076fe`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800076fe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800076b3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800076b3`
- `KERNEL32!SetThreadpoolTimer` at `0x1800076e7`
- `KERNEL32!SetThreadpoolTimer` at `0x1800076e7`
- `KERNEL32!SetLastError` at `0x180007706`
- `KERNEL32!SetLastError` at `0x180007706`

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
0x180007688  mov     [rsp+arg_0], rbx
0x18000768d  mov     [rsp+arg_8], rsi
0x180007692  push    rdi
0x180007693  sub     rsp, 20h
0x180007697  mov     dword ptr [rcx], 0
0x18000769d  lea     rdi, [rcx+8]
0x1800076a1  mov     rsi, [rcx+10h]
0x1800076a5  mov     rbx, rcx
0x1800076a8  mov     qword ptr [rcx+10h], 0
0x1800076b0  mov     rcx, rdi; SRWLock
0x1800076b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800076b9  mov     rcx, rbx
0x1800076bc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800076c1  test    rdi, rdi
0x1800076c4  jz      short loc_1800076CF
0x1800076c6  mov     rcx, rdi; SRWLock
0x1800076c9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800076cf  test    rsi, rsi
0x1800076d2  jz      short loc_18000770C
0x1800076d4  call    cs:__imp_GetLastError
0x1800076da  xor     r9d, r9d; msWindowLength
0x1800076dd  xor     r8d, r8d; msPeriod
0x1800076e0  xor     edx, edx; pftDueTime
0x1800076e2  mov     rcx, rsi; pti
0x1800076e5  mov     ebx, eax
0x1800076e7  call    cs:__imp_SetThreadpoolTimer
0x1800076ed  mov     edx, 1; fCancelPendingCallbacks
0x1800076f2  mov     rcx, rsi; pti
0x1800076f5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800076fb  mov     rcx, rsi; pti
0x1800076fe  call    cs:__imp_CloseThreadpoolTimer
0x180007704  mov     ecx, ebx; dwErrCode
0x180007706  call    cs:__imp_SetLastError
0x18000770c  mov     rbx, [rsp+28h+arg_0]
0x180007711  mov     rsi, [rsp+28h+arg_8]
0x180007716  add     rsp, 20h
0x18000771a  pop     rdi
0x18000771b  retn
```
