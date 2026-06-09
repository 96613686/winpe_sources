# PAL_System_WinCommon_StopThreadpoolTimer

- ea: `0x14001887c`
- end: `0x1400188a7`
- name: `PAL_System_WinCommon_StopThreadpoolTimer`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140020280`
- `0x1400202d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400188a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001888d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001888d`

## pseudocode

```c
void __fastcall PAL_System_WinCommon_StopThreadpoolTimer(struct _TP_TIMER *a1)
{
  SetThreadpoolTimer(a1, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(a1, 1);
}

```

## disassembly

```asm
0x14001887c  push    rbx
0x14001887e  sub     rsp, 20h
0x140018882  xor     r9d, r9d; msWindowLength
0x140018885  xor     r8d, r8d; msPeriod
0x140018888  xor     edx, edx; pftDueTime
0x14001888a  mov     rbx, rcx
0x14001888d  call    cs:__imp_SetThreadpoolTimer
0x140018893  mov     edx, 1
0x140018898  mov     rcx, rbx
0x14001889b  add     rsp, 20h
0x14001889f  pop     rbx
0x1400188a0  jmp     cs:__imp_WaitForThreadpoolTimerCallbacks
```
