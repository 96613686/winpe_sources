# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1000d4f0`
- end: `0x1000d558`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QAEXXZ`
- size: `104`
- prototype: `void __thiscall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1000d370`
- `0x10062970`

## callees

- `0x1000d4f0`
- `0x1000d600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d50b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d50b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d51e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d51e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000d54e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000d54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000d528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000d528`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d537`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d537`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d547`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d547`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d540`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d540`

## pseudocode

```c
void __thiscall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // ebx
  struct _TP_TIMER *Ptr; // esi
  int v3; // ecx
  DWORD LastError; // edi

  this->Ptr = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(v3);
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
0x1000d4f0  mov     edi, edi
0x1000d4f2  push    ebx
0x1000d4f3  push    esi
0x1000d4f4  push    edi
0x1000d4f5  mov     edi, ecx
0x1000d4f7  mov     dword ptr [edi], 0
0x1000d4fd  lea     ebx, [edi+4]
0x1000d500  mov     esi, [edi+8]
0x1000d503  push    ebx; SRWLock
0x1000d504  mov     dword ptr [edi+8], 0
0x1000d50b  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d511  push    ecx
0x1000d512  mov     ecx, edi
0x1000d514  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AAEXABV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_RTL_SRWLOCK@@P6GXPAU1@@Z$1?ReleaseSRWLockExclusive@@YGX0@ZU?$integral_constant@I$00@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<uint,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1000d519  test    ebx, ebx
0x1000d51b  jz      short loc_1000D524
0x1000d51d  push    ebx; SRWLock
0x1000d51e  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d524  test    esi, esi
0x1000d526  jz      short loc_1000D554
0x1000d528  call    ds:__imp__GetLastError@0; GetLastError()
0x1000d52e  push    0; msWindowLength
0x1000d530  push    0; msPeriod
0x1000d532  push    0; pftDueTime
0x1000d534  push    esi; pti
0x1000d535  mov     edi, eax
0x1000d537  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000d53d  push    1; fCancelPendingCallbacks
0x1000d53f  push    esi; pti
0x1000d540  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1000d546  push    esi; pti
0x1000d547  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x1000d54d  push    edi; dwErrCode
0x1000d54e  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000d554  pop     edi
0x1000d555  pop     esi
0x1000d556  pop     ebx
0x1000d557  retn
```
