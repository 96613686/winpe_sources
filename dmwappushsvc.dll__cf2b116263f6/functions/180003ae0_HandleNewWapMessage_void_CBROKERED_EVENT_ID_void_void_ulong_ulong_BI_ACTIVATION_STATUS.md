# HandleNewWapMessage(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)

- ea: `0x180003ae0`
- end: `0x180003c04`
- name: `?HandleNewWapMessage@@YAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `292`
- prototype: `unsigned int __fastcall(__int64, __int64, SmsWapMsgHandler *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001158`
- `0x180001a70`
- `0x180003ae0`
- `0x180003d3c`
- `0x180004968`
- `0x180005a1c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bdb`
- `dmpushroutercore!PrSvcGetMessageCount` at `0x180003ba4`
- `dmpushroutercore!PrSvcGetMessageCount` at `0x180003ba4`
- `dmpushroutercore!PrSvcDecMessageCount` at `0x180003be1`
- `dmpushroutercore!PrSvcDecMessageCount` at `0x180003be1`
- `dmpushroutercore!PrSvcIncMessageCount` at `0x180003b64`
- `dmpushroutercore!PrSvcIncMessageCount` at `0x180003b64`

## pseudocode

```c
unsigned int __fastcall HandleNewWapMessage(__int64 a1, __int64 a2, SmsWapMsgHandler *a3, void *a4)
{
  unsigned int result; // eax
  DmWapPushSvcStopStart *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-38h] BYREF

  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, PushRouterDmWapPushServiceHandleNewWapMessage, a3, 1, &pftDueTime);
  if ( (unsigned int)dword_18001C048 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C048, byte_1800161A1, 0, 0, 2, &pftDueTime);
  if ( DmWapPushSvcStopStart::g_hTimer && PrSvcIncMessageCount() )
  {
    pftDueTime = 0;
    SetThreadpoolTimer(DmWapPushSvcStopStart::g_hTimer, &pftDueTime, 0, 0);
  }
  result = SmsWapMsgHandler::ProcessNewWapMessage(a3, a4);
  if ( DmWapPushSvcStopStart::g_hTimer )
  {
    result = PrSvcGetMessageCount();
    if ( result )
    {
      pftDueTime = 0;
      SetThreadpoolTimer(DmWapPushSvcStopStart::g_hTimer, &pftDueTime, 0, 0);
      WaitForThreadpoolTimerCallbacks(DmWapPushSvcStopStart::g_hTimer, 1);
      PrSvcDecMessageCount();
      return DmWapPushSvcStopStart::SetShutdownTimer(v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ae0  mov     [rsp+arg_0], rbx
0x180003ae5  push    rdi
0x180003ae6  sub     rsp, 60h
0x180003aea  mov     rax, cs:__security_cookie
0x180003af1  xor     rax, rsp
0x180003af4  mov     [rsp+68h+var_18], rax
0x180003af9  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180003b00  mov     rdi, r9
0x180003b03  mov     rbx, r8
0x180003b06  jz      short loc_180003B24
0x180003b08  lea     rax, [rsp+68h+pftDueTime]
0x180003b0d  mov     r9d, 1
0x180003b13  lea     rdx, PushRouterDmWapPushServiceHandleNewWapMessage
0x180003b1a  mov     [rsp+68h+var_48], rax
0x180003b1f  call    McGenEventWrite_EventWriteTransfer
0x180003b24  mov     eax, cs:dword_18001C048
0x180003b2a  cmp     eax, 5
0x180003b2d  jbe     short loc_180003B5A
0x180003b2f  lea     rax, [rsp+68h+pftDueTime]
0x180003b34  xor     r9d, r9d
0x180003b37  mov     [rsp+68h+var_40], rax
0x180003b3c  lea     rdx, byte_1800161A1
0x180003b43  xor     r8d, r8d
0x180003b46  mov     dword ptr [rsp+68h+var_48], 2
0x180003b4e  lea     rcx, dword_18001C048
0x180003b55  call    _tlgWriteTransfer_EventWriteTransfer
0x180003b5a  cmp     cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DmWapPushSvcStopStart::g_hTimer
0x180003b62  jz      short loc_180003B8F
0x180003b64  call    cs:__imp_?PrSvcIncMessageCount@@YAHXZ; PrSvcIncMessageCount(void)
0x180003b6a  test    eax, eax
0x180003b6c  jz      short loc_180003B8F
0x180003b6e  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180003b75  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180003b7a  xor     r9d, r9d; msWindowLength
0x180003b7d  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x180003b86  xor     r8d, r8d; msPeriod
0x180003b89  call    cs:__imp_SetThreadpoolTimer
0x180003b8f  mov     rdx, rdi; void *
0x180003b92  mov     rcx, rbx; this
0x180003b95  call    ?ProcessNewWapMessage@SmsWapMsgHandler@@QEAAJPEAX@Z; SmsWapMsgHandler::ProcessNewWapMessage(void *)
0x180003b9a  cmp     cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DmWapPushSvcStopStart::g_hTimer
0x180003ba2  jz      short loc_180003BEC
0x180003ba4  call    cs:__imp_?PrSvcGetMessageCount@@YAKXZ; PrSvcGetMessageCount(void)
0x180003baa  test    eax, eax
0x180003bac  jz      short loc_180003BEC
0x180003bae  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180003bb5  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180003bba  xor     r9d, r9d; msWindowLength
0x180003bbd  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x180003bc6  xor     r8d, r8d; msPeriod
0x180003bc9  call    cs:__imp_SetThreadpoolTimer
0x180003bcf  mov     rcx, cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA; pti
0x180003bd6  mov     edx, 1; fCancelPendingCallbacks
0x180003bdb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003be1  call    cs:__imp_?PrSvcDecMessageCount@@YAHXZ; PrSvcDecMessageCount(void)
0x180003be7  call    ?SetShutdownTimer@DmWapPushSvcStopStart@@YAHXZ; DmWapPushSvcStopStart::SetShutdownTimer(void)
0x180003bec  mov     rcx, [rsp+68h+var_18]
0x180003bf1  xor     rcx, rsp; StackCookie
0x180003bf4  call    __security_check_cookie
0x180003bf9  mov     rbx, [rsp+68h+arg_0]
0x180003bfe  add     rsp, 60h
0x180003c02  pop     rdi
0x180003c03  retn
```
