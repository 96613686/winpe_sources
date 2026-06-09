# ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(void)

- ea: `0x18004e138`
- end: `0x18004e237`
- name: `??0ComCallTracker@Details@Vmwp@ComputeService@@QEAA@XZ`
- size: `255`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004df3c`

## callees

- `0x1800067c0`
- `0x18001017c`
- `0x18004e138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e1cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e203`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e203`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e188`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e188`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e1c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e1c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e1ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e1ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e1ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e1fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e1ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e1fd`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18004e168`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18004e168`

## string_xrefs

- `0x18004e225`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(_DWORD *pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rsi
  const char *v3; // r9
  struct _TP_TIMER *v4; // rbp
  DWORD LastError; // ebx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)pv = 0;
  pv[2] = 0;
  if ( CoEnableCallCancellation(0) >= 0 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ComputeService::Vmwp::Details::ComCallTracker::TimerCallback, pv, 0);
    v4 = *(struct _TP_TIMER **)pv;
    if ( *(_QWORD *)pv )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v4, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v4, 1);
      CloseThreadpoolTimer(v4);
      SetLastError(LastError);
    }
    *(_QWORD *)pv = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
        v3);
    pftDueTime = (struct _FILETIME)-1200000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x1388u);
    pv[2] = GetCurrentThreadId();
  }
  return pv;
}

```

## disassembly

```asm
0x18004e138  push    rbx
0x18004e13a  push    rbp
0x18004e13b  push    rsi
0x18004e13c  push    rdi
0x18004e13d  sub     rsp, 48h
0x18004e141  mov     rax, cs:__security_cookie
0x18004e148  xor     rax, rsp
0x18004e14b  mov     [rsp+68h+var_30], rax
0x18004e150  mov     rdi, rcx
0x18004e153  mov     [rsp+68h+var_40], rcx
0x18004e158  mov     qword ptr [rcx], 0
0x18004e15f  mov     dword ptr [rcx+8], 0
0x18004e166  xor     ecx, ecx; pReserved
0x18004e168  call    cs:__imp_CoEnableCallCancellation
0x18004e16e  test    eax, eax
0x18004e170  js      loc_18004E20C
0x18004e176  mov     [rsp+68h+var_47], 1
0x18004e17b  xor     r8d, r8d; pcbe
0x18004e17e  mov     rdx, rdi; pv
0x18004e181  lea     rcx, ?TimerCallback@ComCallTracker@Details@Vmwp@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004e188  call    cs:__imp_CreateThreadpoolTimer
0x18004e18e  mov     rsi, rax
0x18004e191  mov     rbp, [rdi]
0x18004e194  test    rbp, rbp
0x18004e197  jz      short loc_18004E1D1
0x18004e199  call    cs:__imp_GetLastError
0x18004e19f  mov     ebx, eax
0x18004e1a1  xor     r9d, r9d; msWindowLength
0x18004e1a4  xor     r8d, r8d; msPeriod
0x18004e1a7  xor     edx, edx; pftDueTime
0x18004e1a9  mov     rcx, rbp; pti
0x18004e1ac  call    cs:__imp_SetThreadpoolTimer
0x18004e1b2  mov     edx, 1; fCancelPendingCallbacks
0x18004e1b7  mov     rcx, rbp; pti
0x18004e1ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004e1c0  mov     rcx, rbp; pti
0x18004e1c3  call    cs:__imp_CloseThreadpoolTimer
0x18004e1c9  mov     ecx, ebx; dwErrCode
0x18004e1cb  call    cs:__imp_SetLastError
0x18004e1d1  mov     [rdi], rsi
0x18004e1d4  test    rsi, rsi
0x18004e1d7  setz    al
0x18004e1da  mov     rcx, [rsp+68h]; this
0x18004e1df  test    al, al
0x18004e1e1  jnz     short loc_18004E225
0x18004e1e3  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x18004e1ec  mov     r9d, 1388h; msWindowLength
0x18004e1f2  xor     r8d, r8d; msPeriod
0x18004e1f5  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18004e1fa  mov     rcx, rsi; pti
0x18004e1fd  call    cs:__imp_SetThreadpoolTimer
0x18004e203  call    cs:__imp_GetCurrentThreadId
0x18004e209  mov     [rdi+8], eax
0x18004e20c  mov     rax, rdi
0x18004e20f  mov     rcx, [rsp+68h+var_30]
0x18004e214  xor     rcx, rsp; StackCookie
0x18004e217  call    __security_check_cookie
0x18004e21c  add     rsp, 48h
0x18004e220  pop     rdi
0x18004e221  pop     rsi
0x18004e222  pop     rbp
0x18004e223  pop     rbx
0x18004e224  retn
0x18004e225  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004e22c  mov     edx, 6Ch ; 'l'; void *
0x18004e231  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
