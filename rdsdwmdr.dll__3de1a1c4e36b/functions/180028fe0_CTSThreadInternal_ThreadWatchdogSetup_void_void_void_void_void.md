# CTSThreadInternal::ThreadWatchdogSetup(void (*)(void *),void (*)(void *),void *)

- ea: `0x180028fe0`
- end: `0x18002906b`
- name: `?ThreadWatchdogSetup@CTSThreadInternal@@UEAAJP6AXPEAX@Z10@Z`
- size: `139`
- prototype: `__int64 __fastcall(PVOID pv, void (*)(void *), void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028d8c`

## callees

- `0x18001f00c`
- `0x18001f450`
- `0x180028fe0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002904c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002904c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029007`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029007`

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
0x180028fe0  push    rbx
0x180028fe2  push    rbp
0x180028fe3  push    rsi
0x180028fe4  push    rdi
0x180028fe5  sub     rsp, 28h
0x180028fe9  mov     rbx, rcx
0x180028fec  mov     rsi, r9
0x180028fef  mov     rcx, [rcx+38h]
0x180028ff3  mov     rbp, r8
0x180028ff6  mov     rdi, rdx
0x180028ff9  test    rcx, rcx
0x180028ffc  jz      short loc_180029015
0x180028ffe  call    PAL_System_WinCommon_StopThreadpoolTimer
0x180029003  mov     rcx, [rbx+38h]; pti
0x180029007  call    cs:__imp_CloseThreadpoolTimer
0x18002900d  mov     qword ptr [rbx+38h], 0
0x180029015  test    rdi, rdi
0x180029018  jnz     short loc_18002902A
0x18002901a  mov     [rbx+40h], rdi
0x18002901e  xor     eax, eax
0x180029020  mov     [rbx+48h], rdi
0x180029024  mov     [rbx+50h], rdi
0x180029028  jmp     short loc_180029062
0x18002902a  lea     rcx, [rbx+58h]
0x18002902e  mov     [rbx+40h], rdi
0x180029032  mov     [rbx+48h], rbp
0x180029036  mov     [rbx+50h], rsi
0x18002903a  call    PAL_System_AtomicExchange
0x18002903f  xor     r8d, r8d; pcbe
0x180029042  lea     rcx, ?TimerCallbackMultiplex@CTSThreadInternal@@CAXPEAX00@Z; pfnti
0x180029049  mov     rdx, rbx; pv
0x18002904c  call    cs:__imp_CreateThreadpoolTimer
0x180029052  mov     [rbx+38h], rax
0x180029056  neg     rax
0x180029059  sbb     eax, eax
0x18002905b  not     eax
0x18002905d  and     eax, 80004005h
0x180029062  add     rsp, 28h
0x180029066  pop     rdi
0x180029067  pop     rsi
0x180029068  pop     rbp
0x180029069  pop     rbx
0x18002906a  retn
```
