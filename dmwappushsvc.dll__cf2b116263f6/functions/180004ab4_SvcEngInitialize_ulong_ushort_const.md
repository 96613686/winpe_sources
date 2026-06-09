# SvcEngInitialize(ulong,ushort * * const)

- ea: `0x180004ab4`
- end: `0x180004be3`
- name: `?SvcEngInitialize@@YAJKQEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006124`

## callees

- `0x180001b40`
- `0x180003e90`
- `0x1800049c0`
- `0x180004ab4`
- `0x180004f74`
- `0x180005a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004b54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004b54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004ba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004ba7`
- `dmpushroutercore!PrSvcSetMessageCount` at `0x180004b95`
- `dmpushroutercore!PrSvcSetMessageCount` at `0x180004b95`
- `dmpushroutercore!InitializePushRouter` at `0x180004bb9`
- `dmpushroutercore!InitializePushRouter` at `0x180004bb9`

## pseudocode

```c
__int64 __fastcall SvcEngInitialize(__int64 a1, unsigned __int16 **const a2)
{
  __int64 result; // rax
  char *v3; // rax
  SmsWapMsgHandler *v4; // rbx
  DmWapPushSvcStopStart *v5; // rcx
  unsigned int DmWapIdleWaitTime; // eax
  __int64 v7; // rcx
  DmWapPushSvcStopStart *v8; // rcx
  SmsWapMsgHandler *v9; // rcx

  if ( spSmsWapMsgHandler )
    return 2147549183LL;
  v3 = (char *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = (SmsWapMsgHandler *)v3;
  if ( v3 )
  {
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    *(_OWORD *)(v3 + 56) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *(_OWORD *)(v3 + 72) = 0;
    *((_DWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *(_OWORD *)(v3 + 88) = 0;
    *((_QWORD *)v3 + 13) = 0;
    *((_QWORD *)v3 + 20) = 0;
    *((_WORD *)v3 + 84) = 0;
    *((_QWORD *)v3 + 19) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 112));
    spSmsWapMsgHandler = v4;
    if ( !DmWapPushSvcStopStart::g_hTimer )
    {
      DmWapIdleWaitTime = DmWapPushSvcStopStart::GetDmWapIdleWaitTime(v5);
      DmWapPushSvcStopStart::g_IdleStopPeriod = DmWapIdleWaitTime;
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
        McTemplateU0d_EventWriteTransfer(v7, PushRouterDmWapPushServiceGetIdleTimeOut, DmWapIdleWaitTime);
      PrSvcSetMessageCount(0);
      DmWapPushSvcStopStart::g_hTimer = CreateThreadpoolTimer(DmWapPushSvcStopStart::TimerCallback, 0, 0);
      DmWapPushSvcStopStart::SetShutdownTimer(v8);
    }
    result = InitializePushRouter();
    if ( (int)result >= 0 )
      return SmsWapMsgHandler::RegisterForWNF(v9);
  }
  else
  {
    spSmsWapMsgHandler = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004ab4  push    rbx
0x180004ab6  sub     rsp, 20h
0x180004aba  cmp     cs:?spSmsWapMsgHandler@@3PEAVSmsWapMsgHandler@@EA, 0; SmsWapMsgHandler * spSmsWapMsgHandler
0x180004ac2  jz      short loc_180004ACE
0x180004ac4  mov     eax, 8000FFFFh
0x180004ac9  jmp     loc_180004BDD
0x180004ace  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004ad5  mov     ecx, 0B0h; unsigned __int64
0x180004ada  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004adf  mov     [rsp+28h+arg_8], rax
0x180004ae4  mov     rbx, rax
0x180004ae7  test    rax, rax
0x180004aea  jz      loc_180004BCD
0x180004af0  mov     qword ptr [rax], 0
0x180004af7  lea     rcx, [rbx+70h]; lpCriticalSection
0x180004afb  mov     qword ptr [rax+8], 0
0x180004b03  xorps   xmm0, xmm0
0x180004b06  movups  xmmword ptr [rbx+38h], xmm0
0x180004b0a  mov     qword ptr [rax+10h], 0
0x180004b12  movups  xmmword ptr [rbx+48h], xmm0
0x180004b16  mov     dword ptr [rax+18h], 0
0x180004b1d  mov     qword ptr [rax+20h], 0
0x180004b25  mov     qword ptr [rax+28h], 0
0x180004b2d  mov     qword ptr [rax+30h], 0
0x180004b35  xor     eax, eax
0x180004b37  movups  xmmword ptr [rbx+58h], xmm0
0x180004b3b  mov     [rbx+68h], rax
0x180004b3f  mov     [rbx+0A0h], rax
0x180004b46  mov     [rbx+0A8h], ax
0x180004b4d  mov     [rbx+98h], rax
0x180004b54  call    cs:__imp_InitializeCriticalSection
0x180004b5a  mov     cs:?spSmsWapMsgHandler@@3PEAVSmsWapMsgHandler@@EA, rbx; SmsWapMsgHandler * spSmsWapMsgHandler
0x180004b61  test    rbx, rbx
0x180004b64  jz      short loc_180004BD8
0x180004b66  cmp     cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DmWapPushSvcStopStart::g_hTimer
0x180004b6e  jnz     short loc_180004BB9
0x180004b70  call    ?GetDmWapIdleWaitTime@DmWapPushSvcStopStart@@YAKXZ; DmWapPushSvcStopStart::GetDmWapIdleWaitTime(void)
0x180004b75  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180004b7c  mov     cs:?g_IdleStopPeriod@DmWapPushSvcStopStart@@3KA, eax; ulong DmWapPushSvcStopStart::g_IdleStopPeriod
0x180004b82  jz      short loc_180004B93
0x180004b84  mov     r8d, eax
0x180004b87  lea     rdx, PushRouterDmWapPushServiceGetIdleTimeOut
0x180004b8e  call    McTemplateU0d_EventWriteTransfer
0x180004b93  xor     ecx, ecx
0x180004b95  call    cs:__imp_?PrSvcSetMessageCount@@YAKK@Z; PrSvcSetMessageCount(ulong)
0x180004b9b  xor     r8d, r8d; pcbe
0x180004b9e  lea     rcx, ?TimerCallback@DmWapPushSvcStopStart@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004ba5  xor     edx, edx; pv
0x180004ba7  call    cs:__imp_CreateThreadpoolTimer
0x180004bad  mov     cs:?g_hTimer@DmWapPushSvcStopStart@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * DmWapPushSvcStopStart::g_hTimer
0x180004bb4  call    ?SetShutdownTimer@DmWapPushSvcStopStart@@YAHXZ; DmWapPushSvcStopStart::SetShutdownTimer(void)
0x180004bb9  call    cs:__imp_InitializePushRouter
0x180004bbf  test    eax, eax
0x180004bc1  js      short loc_180004BDD
0x180004bc3  add     rsp, 20h
0x180004bc7  pop     rbx
0x180004bc8  jmp     ?RegisterForWNF@SmsWapMsgHandler@@QEAAJXZ; SmsWapMsgHandler::RegisterForWNF(void)
0x180004bcd  mov     cs:?spSmsWapMsgHandler@@3PEAVSmsWapMsgHandler@@EA, 0; SmsWapMsgHandler * spSmsWapMsgHandler
0x180004bd8  mov     eax, 8007000Eh
0x180004bdd  add     rsp, 20h
0x180004be1  pop     rbx
0x180004be2  retn
```
