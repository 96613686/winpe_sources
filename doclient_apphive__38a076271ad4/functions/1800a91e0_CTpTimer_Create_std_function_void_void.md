# CTpTimer::Create(std::function<void (void)> &&)

- ea: `0x1800a91e0`
- end: `0x1800a934b`
- name: `?Create@CTpTimer@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bec4`
- `0x18004de5c`
- `0x18007d190`
- `0x18009839c`
- `0x18009a1ec`
- `0x18009a8ec`
- `0x1800a3750`
- `0x1800a3b20`
- `0x1800b8b64`
- `0x1800f0d60`

## callees

- `0x180039b68`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a91e0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a9294`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a9294`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a928c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a928c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a9283`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a9283`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a9275`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a9275`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a9250`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a9250`

## string_xrefs

- `0x1800a9225`: `CTpTimer::Create`

## pseudocode

```c
void __fastcall CTpTimer::Create(_QWORD *pv, _QWORD *a2)
{
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v5; // rdx
  const char *v6; // r9
  struct _TP_TIMER *v7; // r14
  PTP_TIMER v8; // rbp
  DWORD LastError; // ebx
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( pv[8] )
  {
    LogMessage(2u, "CTpTimer::Create", 8u, "TelemetryAssert (%s): %s", "!_tpTimer", "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  ThreadpoolTimer = CreateThreadpoolTimer(CTpTimer::Create_::_2_::_lambda_1_::_lambda_invoker_cdecl_, pv, 0);
  v7 = (struct _TP_TIMER *)pv[8];
  v8 = ThreadpoolTimer;
  if ( v7 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v7, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v7, 1);
    CloseThreadpoolTimer(v7);
    SetLastError(LastError);
  }
  pv[8] = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\TpTimer.cpp",
      v6);
  if ( pv != a2 )
  {
    v10 = (_QWORD *)pv[7];
    if ( v10 )
    {
      LOBYTE(v5) = v10 != pv;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v10 + 32LL))(v10, v5);
      pv[7] = 0;
    }
    v11 = (_QWORD *)a2[7];
    if ( v11 )
    {
      if ( v11 == a2 )
      {
        pv[7] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v11 + 8LL))(v11, pv);
        v13 = (_QWORD *)a2[7];
        if ( !v13 )
          return;
        LOBYTE(v12) = v13 != a2;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v13 + 32LL))(v13, v12);
      }
      else
      {
        pv[7] = v11;
      }
      a2[7] = 0;
    }
  }
}

```

## disassembly

```asm
0x1800a91e0  mov     r11, rsp
0x1800a91e3  mov     [r11+8], rbx
0x1800a91e7  mov     [r11+10h], rbp
0x1800a91eb  mov     [r11+18h], rsi
0x1800a91ef  mov     [r11+20h], rdi
0x1800a91f3  push    r14
0x1800a91f5  sub     rsp, 30h
0x1800a91f9  cmp     qword ptr [rcx+40h], 0
0x1800a91fe  mov     rsi, rdx
0x1800a9201  mov     rdi, rcx
0x1800a9204  jz      short loc_1800A9243
0x1800a9206  mov     r8d, 8; unsigned int
0x1800a920c  lea     rax, aFailed; "Failed"
0x1800a9213  mov     [r11-10h], rax
0x1800a9217  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800a921e  lea     rax, aTptimer; "!_tpTimer"
0x1800a9225  lea     rdx, aCtptimerCreate; "CTpTimer::Create"
0x1800a922c  mov     [r11-18h], rax
0x1800a9230  lea     ecx, [r8-6]; unsigned __int8
0x1800a9234  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800a9239  or      ecx, 0FFFFFFFFh; unsigned int
0x1800a923c  mov     edx, ecx; unsigned int
0x1800a923e  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800a9243  xor     r8d, r8d; pcbe
0x1800a9246  lea     rcx, _CTpTimer__Create____2____lambda_1____lambda_invoker_cdecl_; pfnti
0x1800a924d  mov     rdx, rdi; pv
0x1800a9250  call    cs:__imp_CreateThreadpoolTimer
0x1800a9256  mov     r14, [rdi+40h]
0x1800a925a  mov     rbp, rax
0x1800a925d  test    r14, r14
0x1800a9260  jz      short loc_1800A929A
0x1800a9262  call    cs:__imp_GetLastError
0x1800a9268  xor     r9d, r9d; msWindowLength
0x1800a926b  xor     r8d, r8d; msPeriod
0x1800a926e  xor     edx, edx; pftDueTime
0x1800a9270  mov     rcx, r14; pti
0x1800a9273  mov     ebx, eax
0x1800a9275  call    cs:__imp_SetThreadpoolTimer
0x1800a927b  mov     edx, 1; fCancelPendingCallbacks
0x1800a9280  mov     rcx, r14; pti
0x1800a9283  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800a9289  mov     rcx, r14; pti
0x1800a928c  call    cs:__imp_CloseThreadpoolTimer
0x1800a9292  mov     ecx, ebx; dwErrCode
0x1800a9294  call    cs:__imp_SetLastError
0x1800a929a  mov     [rdi+40h], rbp
0x1800a929e  test    rbp, rbp
0x1800a92a1  jz      loc_1800A9334
0x1800a92a7  cmp     rdi, rsi
0x1800a92aa  jz      short loc_1800A9319
0x1800a92ac  mov     rcx, [rdi+38h]
0x1800a92b0  test    rcx, rcx
0x1800a92b3  jz      short loc_1800A92CF
0x1800a92b5  mov     rax, [rcx]
0x1800a92b8  cmp     rcx, rdi
0x1800a92bb  setnz   dl
0x1800a92be  mov     rax, [rax+20h]
0x1800a92c2  call    _guard_dispatch_icall
0x1800a92c7  mov     qword ptr [rdi+38h], 0
0x1800a92cf  mov     rcx, [rsi+38h]
0x1800a92d3  test    rcx, rcx
0x1800a92d6  jz      short loc_1800A9319
0x1800a92d8  cmp     rcx, rsi
0x1800a92db  jnz     short loc_1800A930D
0x1800a92dd  mov     rax, [rcx]
0x1800a92e0  mov     rdx, rdi
0x1800a92e3  mov     rax, [rax+8]
0x1800a92e7  call    _guard_dispatch_icall
0x1800a92ec  mov     [rdi+38h], rax
0x1800a92f0  mov     rcx, [rsi+38h]
0x1800a92f4  test    rcx, rcx
0x1800a92f7  jz      short loc_1800A9319
0x1800a92f9  mov     rax, [rcx]
0x1800a92fc  cmp     rcx, rsi
0x1800a92ff  setnz   dl
0x1800a9302  mov     rax, [rax+20h]
0x1800a9306  call    _guard_dispatch_icall
0x1800a930b  jmp     short loc_1800A9311
0x1800a930d  mov     [rdi+38h], rcx
0x1800a9311  mov     qword ptr [rsi+38h], 0
0x1800a9319  mov     rbx, [rsp+38h+arg_0]
0x1800a931e  mov     rbp, [rsp+38h+arg_8]
0x1800a9323  mov     rsi, [rsp+38h+arg_10]
0x1800a9328  mov     rdi, [rsp+38h+arg_18]
0x1800a932d  add     rsp, 30h
0x1800a9331  pop     r14
0x1800a9333  retn
0x1800a9334  mov     rcx, [rsp+38h]; this
0x1800a9339  lea     r8, aCW1SSrcDeliver_30; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a9340  mov     edx, 11h; void *
0x1800a9345  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
