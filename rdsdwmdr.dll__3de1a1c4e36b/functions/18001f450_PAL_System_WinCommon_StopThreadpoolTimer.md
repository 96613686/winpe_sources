# PAL_System_WinCommon_StopThreadpoolTimer

- ea: `0x18001f450`
- end: `0x18001f47b`
- name: `PAL_System_WinCommon_StopThreadpoolTimer`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180028f90`
- `0x180028fe0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f474`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f461`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f461`

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
0x18001f450  push    rbx
0x18001f452  sub     rsp, 20h
0x18001f456  xor     r9d, r9d; msWindowLength
0x18001f459  xor     r8d, r8d; msPeriod
0x18001f45c  xor     edx, edx; pftDueTime
0x18001f45e  mov     rbx, rcx
0x18001f461  call    cs:__imp_SetThreadpoolTimer
0x18001f467  mov     edx, 1
0x18001f46c  mov     rcx, rbx
0x18001f46f  add     rsp, 20h
0x18001f473  pop     rbx
0x18001f474  jmp     cs:__imp_WaitForThreadpoolTimerCallbacks
```
