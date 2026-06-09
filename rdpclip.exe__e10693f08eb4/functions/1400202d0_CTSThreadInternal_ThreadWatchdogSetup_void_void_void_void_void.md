# CTSThreadInternal::ThreadWatchdogSetup(void (*)(void *),void (*)(void *),void *)

- ea: `0x1400202d0`
- end: `0x14002035b`
- name: `?ThreadWatchdogSetup@CTSThreadInternal@@UEAAJP6AXPEAX@Z10@Z`
- size: `139`
- prototype: `__int64 __fastcall(PVOID pv, void (*)(void *), void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002007c`

## callees

- `0x140018438`
- `0x14001887c`
- `0x1400202d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400202f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400202f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002033c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002033c`

## pseudocode

```c
__int64 __fastcall CTSThreadInternal::ThreadWatchdogSetup(
        PTP_TIMER *pv,
        struct _TP_TIMER *a2,
        struct _TP_TIMER *a3,
        struct _TP_TIMER *a4)
{
  __int64 result; // rax
  PTP_TIMER ThreadpoolTimer; // rax

  if ( pv[7] )
  {
    PAL_System_WinCommon_StopThreadpoolTimer();
    CloseThreadpoolTimer(pv[7]);
    pv[7] = 0;
  }
  if ( a2 )
  {
    pv[8] = a2;
    pv[9] = a3;
    pv[10] = a4;
    PAL_System_AtomicExchange(pv + 11);
    ThreadpoolTimer = CreateThreadpoolTimer(CTSThreadInternal::TimerCallbackMultiplex, pv, 0);
    pv[7] = ThreadpoolTimer;
    return ThreadpoolTimer == 0 ? 0x80004005 : 0;
  }
  else
  {
    pv[8] = 0;
    result = 0;
    pv[9] = 0;
    pv[10] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400202d0  push    rbx
0x1400202d2  push    rbp
0x1400202d3  push    rsi
0x1400202d4  push    rdi
0x1400202d5  sub     rsp, 28h
0x1400202d9  mov     rbx, rcx
0x1400202dc  mov     rsi, r9
0x1400202df  mov     rcx, [rcx+38h]
0x1400202e3  mov     rbp, r8
0x1400202e6  mov     rdi, rdx
0x1400202e9  test    rcx, rcx
0x1400202ec  jz      short loc_140020305
0x1400202ee  call    PAL_System_WinCommon_StopThreadpoolTimer
0x1400202f3  mov     rcx, [rbx+38h]; pti
0x1400202f7  call    cs:__imp_CloseThreadpoolTimer
0x1400202fd  mov     qword ptr [rbx+38h], 0
0x140020305  test    rdi, rdi
0x140020308  jnz     short loc_14002031A
0x14002030a  mov     [rbx+40h], rdi
0x14002030e  xor     eax, eax
0x140020310  mov     [rbx+48h], rdi
0x140020314  mov     [rbx+50h], rdi
0x140020318  jmp     short loc_140020352
0x14002031a  lea     rcx, [rbx+58h]
0x14002031e  mov     [rbx+40h], rdi
0x140020322  mov     [rbx+48h], rbp
0x140020326  mov     [rbx+50h], rsi
0x14002032a  call    PAL_System_AtomicExchange
0x14002032f  xor     r8d, r8d; pcbe
0x140020332  lea     rcx, ?TimerCallbackMultiplex@CTSThreadInternal@@CAXPEAX00@Z; pfnti
0x140020339  mov     rdx, rbx; pv
0x14002033c  call    cs:__imp_CreateThreadpoolTimer
0x140020342  mov     [rbx+38h], rax
0x140020346  neg     rax
0x140020349  sbb     eax, eax
0x14002034b  not     eax
0x14002034d  and     eax, 80004005h
0x140020352  add     rsp, 28h
0x140020356  pop     rdi
0x140020357  pop     rsi
0x140020358  pop     rbp
0x140020359  pop     rbx
0x14002035a  retn
```
