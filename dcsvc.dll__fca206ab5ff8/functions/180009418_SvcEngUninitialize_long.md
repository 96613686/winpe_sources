# SvcEngUninitialize(long)

- ea: `0x180009418`
- end: `0x180009473`
- name: `?SvcEngUninitialize@@YAJJ@Z`
- size: `91`
- prototype: `__int64 __fastcall()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060b0`
- `0x18000993c`

## callees

- `0x180009418`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000943c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000943c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000944e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000944e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000945b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000945b`

## pseudocode

```c
__int64 __fastcall SvcEngUninitialize()
{
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( DcSvcStopStart::g_hTimer )
  {
    pftDueTime = 0;
    SetThreadpoolTimer(DcSvcStopStart::g_hTimer, &pftDueTime, 0, 0);
    WaitForThreadpoolTimerCallbacks(DcSvcStopStart::g_hTimer, 1);
    CloseThreadpoolTimer(DcSvcStopStart::g_hTimer);
    DcSvcStopStart::g_hTimer = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180009418  sub     rsp, 28h
0x18000941c  mov     rcx, cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180009423  test    rcx, rcx
0x180009426  jz      short loc_18000946C
0x180009428  xor     r9d, r9d; msWindowLength
0x18000942b  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x180009434  xor     r8d, r8d; msPeriod
0x180009437  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000943c  call    cs:__imp_SetThreadpoolTimer
0x180009442  mov     rcx, cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180009449  mov     edx, 1; fCancelPendingCallbacks
0x18000944e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009454  mov     rcx, cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x18000945b  call    cs:__imp_CloseThreadpoolTimer
0x180009461  mov     cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DcSvcStopStart::g_hTimer
0x18000946c  xor     eax, eax
0x18000946e  add     rsp, 28h
0x180009472  retn
```
