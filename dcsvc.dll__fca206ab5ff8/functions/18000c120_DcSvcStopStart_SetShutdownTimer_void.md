# DcSvcStopStart::SetShutdownTimer(void)

- ea: `0x18000c120`
- end: `0x18000c15d`
- name: `?SetShutdownTimer@DcSvcStopStart@@YAHXZ`
- size: `61`
- prototype: `__int64 __fastcall(DcSvcStopStart *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800060b0`
- `0x18000c200`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c14d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c14d`

## pseudocode

```c
__int64 __fastcall DcSvcStopStart::SetShutdownTimer(DcSvcStopStart *this)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = (struct _FILETIME)-(__int64)(10000000 * DcSvcStopStart::g_IdleStopPeriod);
  SetThreadpoolTimer(DcSvcStopStart::g_hTimer, &pftDueTime, 0, 100 * DcSvcStopStart::g_IdleStopPeriod);
  return 1;
}

```

## disassembly

```asm
0x18000c120  sub     rsp, 28h
0x18000c124  imul    ecx, cs:?g_IdleStopPeriod@DcSvcStopStart@@3KA, 989680h; ulong DcSvcStopStart::g_IdleStopPeriod
0x18000c12e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000c133  imul    r9d, cs:?g_IdleStopPeriod@DcSvcStopStart@@3KA, 64h ; 'd'; msWindowLength
0x18000c13b  xor     r8d, r8d; msPeriod
0x18000c13e  neg     rcx
0x18000c141  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rcx
0x18000c146  mov     rcx, cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x18000c14d  call    cs:__imp_SetThreadpoolTimer
0x18000c153  mov     eax, 1
0x18000c158  add     rsp, 28h
0x18000c15c  retn
```
