# HbEvtpInitEventLog

- ea: `0x1400115a0`
- end: `0x140011757`
- name: `HbEvtpInitEventLog`
- size: `439`
- prototype: `BOOLEAN __fastcall(char *DeferredContext)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14000e6fc`

## callees

- `0x1400020f8`
- `0x140002134`
- `0x1400027e4`
- `0x140002ae0`
- `0x1400115a0`
- `0x140011760`
- `0x140012658`
- `0x14001274c`
- `0x1400129f4`
- `0x140013074`
- `0x140013510`
- `0x140014810`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140011640`
- `ntoskrnl!KeInitializeEvent` at `0x140011640`
- `ntoskrnl!KeInitializeDpc` at `0x140011711`
- `ntoskrnl!KeInitializeDpc` at `0x140011711`
- `ntoskrnl!KeSetTimerEx` at `0x140011733`
- `ntoskrnl!KeSetTimerEx` at `0x140011733`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001160b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001160b`
- `winhvr!WinHvSetEventLogGroupSources` at `0x1400116da`
- `winhvr!WinHvSetEventLogGroupSources` at `0x1400116da`

## pseudocode

```c
BOOLEAN __fastcall HbEvtpInitEventLog(char *DeferredContext)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  BOOLEAN result; // al
  _BYTE v5[20]; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)v5 = 0;
  HviGetEnlightenmentInformation(v5);
  byte_140009048 = (*(_DWORD *)v5 & 0x4000000) == 0;
  v2 = 0;
  do
  {
    if ( HbpIsCpuManagementPartition || (_DWORD)v2 == 2 )
    {
      v3 = 18 * v2;
      ExInitializeRundownProtection(&stru_1400092E8 + 18 * v2);
      LODWORD(HbEvtpEventLog[v3 + 7]) = 1;
      HbEvtpEventLog[v3 + 8] = 0;
      LODWORD(HbEvtpEventLog[v3 + 9]) = 0;
      KeInitializeEvent((PRKEVENT)&qword_1400092F0[18 * v2 + 6], SynchronizationEvent, 0);
    }
    v2 = (unsigned int)(v2 + 1);
  }
  while ( (unsigned int)v2 <= 2 );
  if ( HbpIsCpuManagementPartition )
  {
    McGenEventRegister_EtwRegister();
    HbEvtpRegisterLocalDiagnosticsEtwProvider(DeferredContext);
    HbEvtpLogProcessorFeatures(0);
    HbEvtpLogSecFwStatus();
    HbEvtpLogHwWatchdogBootStatus();
    HbEvtpTraceMinrootConfig();
    *(_DWORD *)v5 = 4;
    *(_QWORD *)&v5[4] = 0x300004000LL;
    *(_QWORD *)&v5[12] = 1;
    if ( (int)HbEvtpCreateEventLog(DeferredContext, 0, 0, v5) >= 0 )
    {
      byte_14000904A = 1;
      WinHvSetEventLogGroupSources(0, -1);
    }
    else
    {
      HbEvtpWriteEventLog(&HV_EVENTLOG_CREATE_GLOBAL_FAILED, 0, 0);
    }
  }
  result = HbEvtpInitializeSystemDiagLog(DeferredContext);
  if ( byte_140009049 || byte_14000904A )
  {
    KeInitializeDpc(&HbEvtpPeriodicTimerDpc, HbEvtpTracePeriodicTimerDpcRoutine, DeferredContext);
    return KeSetTimerEx((PKTIMER)(DeferredContext + 96), (LARGE_INTEGER)64771072LL, 30000, &HbEvtpPeriodicTimerDpc);
  }
  return result;
}

```

## disassembly

```asm
0x1400115a0  push    rbx
0x1400115a2  push    rsi
0x1400115a3  push    rdi
0x1400115a4  push    r15
0x1400115a6  sub     rsp, 48h
0x1400115aa  mov     rax, cs:__security_cookie
0x1400115b1  xor     rax, rsp
0x1400115b4  mov     [rsp+68h+var_30], rax
0x1400115b9  mov     rsi, rcx
0x1400115bc  xorps   xmm0, xmm0
0x1400115bf  lea     rcx, [rsp+68h+var_48]
0x1400115c4  movups  [rsp+68h+var_48], xmm0
0x1400115c9  call    HviGetEnlightenmentInformation
0x1400115ce  mov     r11d, dword ptr [rsp+68h+var_48]
0x1400115d3  lea     r15, HbEvtpEventLog
0x1400115da  shr     r11d, 1Ah
0x1400115de  not     r11b
0x1400115e1  and     r11b, 1
0x1400115e5  mov     cs:byte_140009048, r11b
0x1400115ec  xor     edi, edi
0x1400115ee  cmp     cs:HbpIsCpuManagementPartition, 0
0x1400115f5  jnz     short loc_1400115FC
0x1400115f7  cmp     edi, 2
0x1400115fa  jnz     short loc_14001164C
0x1400115fc  lea     rbx, [rdi+rdi*8]
0x140011600  shl     rbx, 4
0x140011604  lea     rcx, [r15+18h]
0x140011608  add     rcx, rbx; RunRef
0x14001160b  call    cs:__imp_ExInitializeRundownProtection
0x140011612  nop     dword ptr [rax+rax+00h]
0x140011617  xor     r8d, r8d; State
0x14001161a  mov     dword ptr [rbx+r15+38h], 1
0x140011623  lea     rcx, [r15+50h]
0x140011627  mov     qword ptr [rbx+r15+40h], 0
0x140011630  add     rcx, rbx; Event
0x140011633  mov     dword ptr [rbx+r15+48h], 0
0x14001163c  lea     edx, [r8+1]; Type
0x140011640  call    cs:__imp_KeInitializeEvent
0x140011647  nop     dword ptr [rax+rax+00h]
0x14001164c  inc     edi
0x14001164e  cmp     edi, 2
0x140011651  jbe     short loc_1400115EE
0x140011653  cmp     cs:HbpIsCpuManagementPartition, 0
0x14001165a  jz      loc_1400116E6
0x140011660  call    McGenEventRegister_EtwRegister
0x140011665  mov     rcx, rsi
0x140011668  call    HbEvtpRegisterLocalDiagnosticsEtwProvider
0x14001166d  xor     ecx, ecx
0x14001166f  call    HbEvtpLogProcessorFeatures
0x140011674  call    HbEvtpLogSecFwStatus
0x140011679  call    HbEvtpLogHwWatchdogBootStatus
0x14001167e  call    HbEvtpTraceMinrootConfig
0x140011683  lea     r9, [rsp+68h+var_48]
0x140011688  mov     dword ptr [rsp+68h+var_48+8], 3
0x140011690  xor     r8d, r8d
0x140011693  mov     dword ptr [rsp+68h+var_48], 4
0x14001169b  xor     edx, edx
0x14001169d  mov     dword ptr [rsp+68h+var_48+4], 4000h
0x1400116a5  mov     rcx, rsi; DeferredContext
0x1400116a8  mov     qword ptr [rsp+68h+var_48+0Ch], 1
0x1400116b1  call    HbEvtpCreateEventLog
0x1400116b6  test    eax, eax
0x1400116b8  jns     short loc_1400116CD
0x1400116ba  xor     r8d, r8d; UserData
0x1400116bd  lea     rcx, HV_EVENTLOG_CREATE_GLOBAL_FAILED; EventDescriptor
0x1400116c4  xor     edx, edx; UserDataCount
0x1400116c6  call    HbEvtpWriteEventLog
0x1400116cb  jmp     short loc_1400116E6
0x1400116cd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400116d1  mov     cs:byte_14000904A, 1
0x1400116d8  xor     ecx, ecx
0x1400116da  call    cs:__imp_WinHvSetEventLogGroupSources
0x1400116e1  nop     dword ptr [rax+rax+00h]
0x1400116e6  mov     rcx, rsi
0x1400116e9  call    HbEvtpInitializeSystemDiagLog
0x1400116ee  cmp     cs:byte_140009049, 0
0x1400116f5  jnz     short loc_140011700
0x1400116f7  cmp     cs:byte_14000904A, 0
0x1400116fe  jz      short loc_14001173F
0x140011700  mov     r8, rsi; DeferredContext
0x140011703  lea     rdx, HbEvtpTracePeriodicTimerDpcRoutine; DeferredRoutine
0x14001170a  lea     rcx, HbEvtpPeriodicTimerDpc; Dpc
0x140011711  call    cs:__imp_KeInitializeDpc
0x140011718  nop     dword ptr [rax+rax+00h]
0x14001171d  lea     rcx, [rsi+60h]; Timer
0x140011721  mov     edx, 3DC5400h; DueTime
0x140011726  lea     r9, HbEvtpPeriodicTimerDpc; Dpc
0x14001172d  mov     r8d, 7530h; Period
0x140011733  call    cs:__imp_KeSetTimerEx
0x14001173a  nop     dword ptr [rax+rax+00h]
0x14001173f  mov     rcx, [rsp+68h+var_30]
0x140011744  xor     rcx, rsp; StackCookie
0x140011747  call    __security_check_cookie
0x14001174c  add     rsp, 48h
0x140011750  pop     r15
0x140011752  pop     rdi
0x140011753  pop     rsi
0x140011754  pop     rbx
0x140011755  retn
```
