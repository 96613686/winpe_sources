# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001017c`
- end: `0x180010210`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cfc8`
- `0x18018cb10`

## callees

- `0x18001017c`
- `0x1800107d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800101bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800101bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800101fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800101fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800101db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800101db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800101f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800101f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800101e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800101e9`

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
0x18001017c  mov     [rsp+arg_0], rbx
0x180010181  mov     [rsp+arg_8], rsi
0x180010186  push    rdi
0x180010187  sub     rsp, 20h
0x18001018b  mov     dword ptr [rcx], 0
0x180010191  lea     rdi, [rcx+8]
0x180010195  mov     rsi, [rcx+10h]
0x180010199  mov     rbx, rcx
0x18001019c  mov     qword ptr [rcx+10h], 0
0x1800101a4  mov     rcx, rdi; SRWLock
0x1800101a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800101ad  mov     rcx, rbx
0x1800101b0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800101b5  test    rdi, rdi
0x1800101b8  jz      short loc_1800101C3
0x1800101ba  mov     rcx, rdi; SRWLock
0x1800101bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800101c3  test    rsi, rsi
0x1800101c6  jz      short loc_180010200
0x1800101c8  call    cs:__imp_GetLastError
0x1800101ce  xor     r9d, r9d; msWindowLength
0x1800101d1  xor     r8d, r8d; msPeriod
0x1800101d4  xor     edx, edx; pftDueTime
0x1800101d6  mov     rcx, rsi; pti
0x1800101d9  mov     ebx, eax
0x1800101db  call    cs:__imp_SetThreadpoolTimer
0x1800101e1  mov     edx, 1; fCancelPendingCallbacks
0x1800101e6  mov     rcx, rsi; pti
0x1800101e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800101ef  mov     rcx, rsi; pti
0x1800101f2  call    cs:__imp_CloseThreadpoolTimer
0x1800101f8  mov     ecx, ebx; dwErrCode
0x1800101fa  call    cs:__imp_SetLastError
0x180010200  mov     rbx, [rsp+28h+arg_0]
0x180010205  mov     rsi, [rsp+28h+arg_8]
0x18001020a  add     rsp, 20h
0x18001020e  pop     rdi
0x18001020f  retn
```
