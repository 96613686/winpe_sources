# DmWapPushSvcStopStart::SvcDeinitIdleStopStart(void)

- ea: `0x180005bec`
- end: `0x180005c8b`
- name: `?SvcDeinitIdleStopStart@DmWapPushSvcStopStart@@YAHXZ`
- size: `159`
- prototype: `__int64 __fastcall(DmWapPushSvcStopStart *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004bec`

## callees

- `0x180001a70`
- `0x180004968`
- `0x180005bec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c56`

## pseudocode

```c
__int64 __fastcall DmWapPushSvcStopStart::SvcDeinitIdleStopStart(DmWapPushSvcStopStart *this, __int64 a2, __int64 a3)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v5[16]; // [rsp+38h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(this, PushRouterDmWapPushSvcDeinitIdleStopStart, a3, 1, v5);
  if ( DmWapPushSvcStopStart::g_hTimer )
  {
    pftDueTime = 0;
    SetThreadpoolTimer(DmWapPushSvcStopStart::g_hTimer, &pftDueTime, 0, 0);
    WaitForThreadpoolTimerCallbacks(DmWapPushSvcStopStart::g_hTimer, 1);
    CloseThreadpoolTimer(DmWapPushSvcStopStart::g_hTimer);
    DmWapPushSvcStopStart::g_hTimer = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180005bec  sub     rsp, 58h
0x180005bf0  mov     rax, cs:__security_cookie
0x180005bf7  xor     rax, rsp
0x180005bfa  mov     [rsp+58h+var_10], rax
0x180005bff  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180005c06  jz      short loc_180005C24
0x180005c08  lea     rax, [rsp+58h+var_20]
0x180005c0d  mov     r9d, 1
0x180005c13  lea     rdx, PushRouterDmWapPushSvcDeinitIdleStopStart
0x180005c1a  mov     [rsp+58h+var_38], rax
0x180005c1f  call    McGenEventWrite_EventWriteTransfer
0x180005c24  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180005c2b  test    rcx, rcx
0x180005c2e  jz      short loc_180005C74
0x180005c30  xor     r9d, r9d; msWindowLength
0x180005c33  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x180005c3c  xor     r8d, r8d; msPeriod
0x180005c3f  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180005c44  call    cs:__imp_SetThreadpoolTimer
0x180005c4a  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180005c51  mov     edx, 1; fCancelPendingCallbacks
0x180005c56  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c5c  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180005c63  call    cs:__imp_CloseThreadpoolTimer
0x180005c69  mov     cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DmWapPushSvcStopStart::g_hTimer
0x180005c74  mov     eax, 1
0x180005c79  mov     rcx, [rsp+58h+var_10]
0x180005c7e  xor     rcx, rsp; StackCookie
0x180005c81  call    __security_check_cookie
0x180005c86  add     rsp, 58h
0x180005c8a  retn
```
