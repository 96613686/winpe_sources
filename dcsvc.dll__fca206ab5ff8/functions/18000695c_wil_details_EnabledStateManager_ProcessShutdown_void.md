# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000695c`
- end: `0x1800069f0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c38`
- `0x180011f50`

## callees

- `0x18000695c`
- `0x180006da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000699d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000699d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006987`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006987`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800069c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800069c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800069d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800069d2`

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
0x18000695c  mov     [rsp+arg_0], rbx
0x180006961  mov     [rsp+arg_8], rsi
0x180006966  push    rdi
0x180006967  sub     rsp, 20h
0x18000696b  mov     dword ptr [rcx], 0
0x180006971  lea     rdi, [rcx+8]
0x180006975  mov     rsi, [rcx+10h]
0x180006979  mov     rbx, rcx
0x18000697c  mov     qword ptr [rcx+10h], 0
0x180006984  mov     rcx, rdi; SRWLock
0x180006987  call    cs:__imp_AcquireSRWLockExclusive
0x18000698d  mov     rcx, rbx
0x180006990  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006995  test    rdi, rdi
0x180006998  jz      short loc_1800069A3
0x18000699a  mov     rcx, rdi; SRWLock
0x18000699d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800069a3  test    rsi, rsi
0x1800069a6  jz      short loc_1800069E0
0x1800069a8  call    cs:__imp_GetLastError
0x1800069ae  xor     r9d, r9d; msWindowLength
0x1800069b1  xor     r8d, r8d; msPeriod
0x1800069b4  xor     edx, edx; pftDueTime
0x1800069b6  mov     rcx, rsi; pti
0x1800069b9  mov     ebx, eax
0x1800069bb  call    cs:__imp_SetThreadpoolTimer
0x1800069c1  mov     edx, 1; fCancelPendingCallbacks
0x1800069c6  mov     rcx, rsi; pti
0x1800069c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800069cf  mov     rcx, rsi; pti
0x1800069d2  call    cs:__imp_CloseThreadpoolTimer
0x1800069d8  mov     ecx, ebx; dwErrCode
0x1800069da  call    cs:__imp_SetLastError
0x1800069e0  mov     rbx, [rsp+28h+arg_0]
0x1800069e5  mov     rsi, [rsp+28h+arg_8]
0x1800069ea  add     rsp, 20h
0x1800069ee  pop     rdi
0x1800069ef  retn
```
