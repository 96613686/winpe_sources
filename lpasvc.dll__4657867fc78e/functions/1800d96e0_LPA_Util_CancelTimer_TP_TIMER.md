# LPA::Util::CancelTimer(_TP_TIMER * &)

- ea: `0x1800d96e0`
- end: `0x1800d9723`
- name: `?CancelTimer@Util@LPA@@YAXAEAPEAU_TP_TIMER@@@Z`
- size: `67`
- prototype: `void __fastcall(LPA::Util *__hidden this, struct _TP_TIMER **)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180065a48`
- `0x18006a5f0`
- `0x180076c20`
- `0x180085c34`
- `0x180088704`
- `0x180088b48`
- `0x180095df0`
- `0x1800a807c`
- `0x1800adc8c`
- `0x1800d7a58`
- `0x1800d8244`
- `0x1800d9864`

## callees

- `0x1800d96e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d96f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d96f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d9710`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d9710`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d9707`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d9707`

## pseudocode

```c
void __fastcall LPA::Util::CancelTimer(PTP_TIMER *this, struct _TP_TIMER **a2)
{
  struct _TP_TIMER *v3; // rcx

  v3 = *this;
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x1800d96e0  push    rbx
0x1800d96e2  sub     rsp, 20h
0x1800d96e6  mov     rbx, rcx
0x1800d96e9  mov     rcx, [rcx]; pti
0x1800d96ec  test    rcx, rcx
0x1800d96ef  jz      short loc_1800D971D
0x1800d96f1  xor     r9d, r9d; msWindowLength
0x1800d96f4  xor     r8d, r8d; msPeriod
0x1800d96f7  xor     edx, edx; pftDueTime
0x1800d96f9  call    cs:__imp_SetThreadpoolTimer
0x1800d96ff  mov     rcx, [rbx]; pti
0x1800d9702  mov     edx, 1; fCancelPendingCallbacks
0x1800d9707  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800d970d  mov     rcx, [rbx]; pti
0x1800d9710  call    cs:__imp_CloseThreadpoolTimer
0x1800d9716  mov     qword ptr [rbx], 0
0x1800d971d  add     rsp, 20h
0x1800d9721  pop     rbx
0x1800d9722  retn
```
