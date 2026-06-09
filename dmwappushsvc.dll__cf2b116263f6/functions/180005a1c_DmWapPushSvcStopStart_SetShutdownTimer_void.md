# DmWapPushSvcStopStart::SetShutdownTimer(void)

- ea: `0x180005a1c`
- end: `0x180005a7e`
- name: `?SetShutdownTimer@DmWapPushSvcStopStart@@YAHXZ`
- size: `98`
- prototype: `__int64 __fastcall(DmWapPushSvcStopStart *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ae0`
- `0x180004ab4`
- `0x180005d00`

## callees

- `0x1800049c0`
- `0x180005a1c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a6e`

## pseudocode

```c
__int64 __fastcall DmWapPushSvcStopStart::SetShutdownTimer(DmWapPushSvcStopStart *this)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = 0;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McTemplateU0d_EventWriteTransfer(
      this,
      PushRouterDmWapPushSetServiceTimerToFire,
      DmWapPushSvcStopStart::g_IdleStopPeriod);
  pftDueTime = (struct _FILETIME)-(__int64)(10000000 * DmWapPushSvcStopStart::g_IdleStopPeriod);
  SetThreadpoolTimer(DmWapPushSvcStopStart::g_hTimer, &pftDueTime, 0, 100 * DmWapPushSvcStopStart::g_IdleStopPeriod);
  return 1;
}

```

## disassembly

```asm
0x180005a1c  sub     rsp, 28h
0x180005a20  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180005a27  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x180005a30  jz      short loc_180005A45
0x180005a32  mov     r8d, cs:?g_IdleStopPeriod@DmWapPushSvcStopStart@@3KA; ulong DmWapPushSvcStopStart::g_IdleStopPeriod
0x180005a39  lea     rdx, PushRouterDmWapPushSetServiceTimerToFire
0x180005a40  call    McTemplateU0d_EventWriteTransfer
0x180005a45  imul    ecx, cs:?g_IdleStopPeriod@DmWapPushSvcStopStart@@3KA, 989680h; ulong DmWapPushSvcStopStart::g_IdleStopPeriod
0x180005a4f  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180005a54  imul    r9d, cs:?g_IdleStopPeriod@DmWapPushSvcStopStart@@3KA, 64h ; 'd'; msWindowLength
0x180005a5c  xor     r8d, r8d; msPeriod
0x180005a5f  neg     rcx
0x180005a62  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rcx
0x180005a67  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180005a6e  call    cs:__imp_SetThreadpoolTimer
0x180005a74  mov     eax, 1
0x180005a79  add     rsp, 28h
0x180005a7d  retn
```
