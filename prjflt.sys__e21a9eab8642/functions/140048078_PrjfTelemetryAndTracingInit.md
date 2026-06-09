# PrjfTelemetryAndTracingInit

- ea: `0x140048078`
- end: `0x1400484da`
- name: `PrjfTelemetryAndTracingInit`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400484e0`

## callees

- `0x14000b0d8`
- `0x14000b1a0`
- `0x14000ba20`
- `0x14000d128`
- `0x140046edc`
- `0x140048078`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048262`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048262`
- `ntoskrnl!RtlInitAnsiString` at `0x1400482a4`
- `ntoskrnl!RtlInitAnsiString` at `0x1400482a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400481e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400481e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400481c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400481c4`
- `ntoskrnl!EtwSetInformation` at `0x140048122`
- `ntoskrnl!EtwSetInformation` at `0x14004813e`
- `ntoskrnl!EtwSetInformation` at `0x140048122`
- `ntoskrnl!EtwSetInformation` at `0x14004813e`
- `ntoskrnl!EtwRegister` at `0x140048108`
- `ntoskrnl!EtwRegister` at `0x140048108`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004821c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004821c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14004822f`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14004822f`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400482c6`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400482c6`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14004824e`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14004824e`
- `WppRecorder!WppAutoLogStart` at `0x14004819d`
- `WppRecorder!WppAutoLogStart` at `0x14004819d`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400482ef`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400482ef`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140048379`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14004840e`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140048379`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14004840e`

## string_xrefs

- `0x140048389`: `Unable to create trace log recorder - default log will be used instead.`
- `0x14004841e`: `Unable to create trace log recorder - default log will be used instead.`

## pseudocode

```c
__int64 __fastcall PrjfTelemetryAndTracingInit(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rcx
  bool v6; // zf
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  const char *v10; // r8
  __int128 *v11; // rcx
  __int64 v12; // rdx
  __int128 *v13; // rax
  void *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  const char *v18; // rax
  __int128 *v19; // rcx
  __int128 *v20; // rax
  void *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 result; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  char EventInformation[8]; // [rsp+60h] [rbp-59h] BYREF
  ULONGLONG RegHandle[2]; // [rsp+68h] [rbp-51h] BYREF
  struct _STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  struct _STRING v32; // [rsp+90h] [rbp-29h] BYREF
  struct _STRING v33; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v35; // [rsp+C0h] [rbp+7h]
  __int128 v36; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v37; // [rsp+E0h] [rbp+27h]
  __int128 v38; // [rsp+E8h] [rbp+2Fh] BYREF

  EventInformation[0] = 1;
  v37 = 0;
  RegHandle[0] = 0;
  FastWppCallbackLock = 0;
  v38 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  g_rgFastWppLevelEnabledFlags = 0;
  xmmword_14001A3D0 = 0;
  xmmword_14001A3E0 = 0;
  FastWppInitState = 1;
  EtwRegister(&FastWppControlGuid, FastWppCallback, 0, RegHandle);
  EtwSetInformation(RegHandle[0], MaxEventInfo, 0, 0);
  EtwSetInformation(RegHandle[0], EventProviderUseDescriptorType, EventInformation, 1u);
  WPP_MAIN_CB = 0;
  qword_14001AC50 = 0;
  qword_14001AC48 = (__int64)WPP_ThisDir_CTLGUID_PrjfltTrace;
  qword_14001AC60 = 0;
  qword_14001AC68 = 1;
  qword_14001AC80 = 0;
  dword_14001AC88 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppAutoLogStart(&WPP_MAIN_CB, a1, a2);
  FastWppRegHandle = RegHandle[0];
  WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  ExAcquirePushLockExclusiveEx(&FastWppCallbackLock, 0);
  FastWppInitState = 2;
  ExReleasePushLockExclusiveEx(&FastWppCallbackLock, 0);
  DestinationString = 0;
  *(_OWORD *)RegHandle = 0;
  if ( !_InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    RtlInitUnicodeString((PUNICODE_STRING)RegHandle, 0);
    if ( (int)IoQueryFullDriverPath(a1, RegHandle) >= 0 )
    {
      v4 = RtlUnicodeStringToAnsiString(&DestinationString, (PCUNICODE_STRING)RegHandle, 1u);
      ExFreePoolWithTag((PVOID)RegHandle[1], 0);
      if ( v4 >= 0 )
      {
        v5 = (unsigned int)DestinationString.Length - 1;
        if ( DestinationString.Length != 1 )
        {
          while ( DestinationString.Buffer[v5] != 92 )
          {
            v6 = (_DWORD)v5 == 1;
            v5 = (unsigned int)(v5 - 1);
            if ( v6 )
              goto LABEL_10;
          }
          if ( (_DWORD)v5 != DestinationString.Length )
          {
            v32 = 0;
            RtlInitAnsiString(&v32, &DestinationString.Buffer[(unsigned int)(v5 + 1)]);
            v33 = v32;
            InitializeTelemetryAssertsKMWorkerInternal(&v33);
          }
        }
LABEL_10:
        RtlFreeAnsiString(&DestinationString);
      }
    }
  }
  v7 = 16;
  *((_QWORD *)&v38 + 1) = 0x200000002LL;
  LODWORD(v38) = 16;
  BYTE4(v38) = 1;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, &v38);
  v8 = 2147483646;
  *(_QWORD *)&v34 = 56;
  v9 = 2147483646;
  LOBYTE(v36) = 0;
  HIDWORD(v35) = 16;
  v10 = "GvTraceLog";
  *(_QWORD *)&v35 = 0;
  v11 = &v36;
  BYTE8(v35) = 0;
  v12 = 16;
  do
  {
    if ( !v9 )
      break;
    if ( !*v10 )
      break;
    *(_BYTE *)v11 = *v10++;
    v11 = (__int128 *)((char *)v11 + 1);
    --v9;
    --v12;
  }
  while ( v12 );
  v13 = (__int128 *)((char *)v11 - 1);
  if ( v12 )
    v13 = v11;
  v14 = WPP_GLOBAL_Control;
  *(_BYTE *)v13 = 0;
  v37 = 0x200000002LL;
  *((_QWORD *)&v34 + 1) = 0xC800001000LL;
  if ( (int)imp_WppRecorderLogCreate(v14, &v34, &PrjfTraceRecorder) < 0 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "Unable to create trace log recorder - default log will be used instead.",
      v15,
      v16,
      v17);
    PrjfTraceRecorder = 0;
  }
  *(_QWORD *)&v34 = 56;
  v18 = "GvEnterLeaveLog";
  LOBYTE(v36) = 0;
  v19 = &v36;
  HIDWORD(v35) = 16;
  *(_QWORD *)&v35 = 0;
  BYTE8(v35) = 0;
  do
  {
    if ( !v8 )
      break;
    if ( !*v18 )
      break;
    *(_BYTE *)v19 = *v18++;
    v19 = (__int128 *)((char *)v19 + 1);
    --v8;
    --v7;
  }
  while ( v7 );
  v20 = (__int128 *)((char *)v19 - 1);
  if ( v7 )
    v20 = v19;
  v21 = WPP_GLOBAL_Control;
  *(_BYTE *)v20 = 0;
  v37 = 0x200000002LL;
  *((_QWORD *)&v34 + 1) = 0xC800001000LL;
  if ( (int)imp_WppRecorderLogCreate(v21, &v34, &PrjfEnterLeaveRecorder) < 0 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "Unable to create trace log recorder - default log will be used instead.",
      v22,
      v23,
      v24);
    PrjfEnterLeaveRecorder = 0;
  }
  result = TlgRegisterAggregateProvider();
  if ( (int)result < 0 )
  {
    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v26) = xmmword_14001A3D0 & 2;
    if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v26,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        10,
        (__int64)WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\telemetry.c",
        190,
        result);
    return MicrosoftTelemetryAssertTriggeredMsgKM("Failed to register telemetry.", v26, v27, v28);
  }
  return result;
}

```

## disassembly

```asm
0x140048078  mov     [rsp-8+arg_10], rbx
0x14004807d  mov     [rsp-8+arg_18], rsi
0x140048082  push    rbp
0x140048083  push    rdi
0x140048084  push    r14
0x140048086  lea     rbp, [rsp-47h]
0x14004808b  sub     rsp, 100h
0x140048092  mov     rax, cs:__security_cookie
0x140048099  xor     rax, rsp
0x14004809c  mov     [rbp+57h+var_18], rax
0x1400480a0  xorps   xmm0, xmm0
0x1400480a3  mov     [rbp+57h+EventInformation], 1
0x1400480a7  xorps   xmm1, xmm1
0x1400480aa  xor     eax, eax
0x1400480ac  xor     r14d, r14d
0x1400480af  mov     [rbp+57h+var_30], rax
0x1400480b3  mov     [rbp+57h+RegHandle], r14
0x1400480b7  mov     rbx, rdx
0x1400480ba  mov     cs:FastWppCallbackLock, r14
0x1400480c1  mov     rdi, rcx
0x1400480c4  movups  [rbp+57h+var_28], xmm0
0x1400480c8  movups  [rbp+57h+var_60], xmm1
0x1400480cc  movups  [rbp+57h+var_50], xmm1
0x1400480d0  movups  [rbp+57h+var_40], xmm1
0x1400480d4  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x1400480db  movups  cs:xmmword_14001A3D0, xmm0
0x1400480e2  movups  cs:xmmword_14001A3E0, xmm0
0x1400480e9  lea     r9, [rbp+57h+RegHandle]; RegHandle
0x1400480ed  mov     cs:FastWppInitState, 1
0x1400480f7  xor     r8d, r8d; CallbackContext
0x1400480fa  lea     rdx, FastWppCallback; EnableCallback
0x140048101  lea     rcx, FastWppControlGuid; ProviderId
0x140048108  call    cs:__imp_EtwRegister
0x14004810f  nop     dword ptr [rax+rax+00h]
0x140048114  mov     rcx, [rbp+57h+RegHandle]; RegHandle
0x140048118  lea     edx, [r14+4]; InformationClass
0x14004811c  xor     r9d, r9d; InformationLength
0x14004811f  xor     r8d, r8d; EventInformation
0x140048122  call    cs:__imp_EtwSetInformation
0x140048129  nop     dword ptr [rax+rax+00h]
0x14004812e  mov     rcx, [rbp+57h+RegHandle]; RegHandle
0x140048132  lea     r9d, [r14+1]; InformationLength
0x140048136  lea     r8, [rbp+57h+EventInformation]; EventInformation
0x14004813a  lea     edx, [r14+3]; InformationClass
0x14004813e  call    cs:__imp_EtwSetInformation
0x140048145  nop     dword ptr [rax+rax+00h]
0x14004814a  lea     rsi, WPP_MAIN_CB
0x140048151  mov     cs:WPP_MAIN_CB, r14
0x140048158  lea     rax, WPP_ThisDir_CTLGUID_PrjfltTrace
0x14004815f  mov     cs:qword_14001AC50, r14
0x140048166  mov     rcx, rsi
0x140048169  mov     cs:qword_14001AC48, rax
0x140048170  mov     r8, rbx
0x140048173  mov     cs:qword_14001AC60, r14
0x14004817a  mov     rdx, rdi
0x14004817d  mov     cs:qword_14001AC68, 1
0x140048188  mov     cs:qword_14001AC80, r14
0x14004818f  mov     cs:dword_14001AC88, r14d
0x140048196  mov     cs:WPP_GLOBAL_Control, rsi
0x14004819d  call    cs:__imp_WppAutoLogStart
0x1400481a4  nop     dword ptr [rax+rax+00h]
0x1400481a9  mov     rax, [rbp+57h+RegHandle]
0x1400481ad  lea     rcx, FastWppCallbackLock
0x1400481b4  xor     edx, edx
0x1400481b6  mov     cs:FastWppRegHandle, rax
0x1400481bd  mov     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400481c4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400481cb  nop     dword ptr [rax+rax+00h]
0x1400481d0  mov     eax, cs:FastWppInitState
0x1400481d6  lea     esi, [r14+2]
0x1400481da  xor     edx, edx
0x1400481dc  mov     cs:FastWppInitState, esi
0x1400481e2  lea     rcx, FastWppCallbackLock
0x1400481e9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400481f0  nop     dword ptr [rax+rax+00h]
0x1400481f5  xorps   xmm0, xmm0
0x1400481f8  xorps   xmm1, xmm1
0x1400481fb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400481ff  mov     eax, r14d
0x140048202  movups  xmmword ptr [rbp+57h+RegHandle], xmm1
0x140048206  lock xadd cs:g_AssertsOperational, eax
0x14004820e  test    eax, eax
0x140048210  jnz     loc_1400482D2
0x140048216  xor     edx, edx; SourceString
0x140048218  lea     rcx, [rbp+57h+RegHandle]; DestinationString
0x14004821c  call    cs:__imp_RtlInitUnicodeString
0x140048223  nop     dword ptr [rax+rax+00h]
0x140048228  lea     rdx, [rbp+57h+RegHandle]
0x14004822c  mov     rcx, rdi
0x14004822f  call    cs:__imp_IoQueryFullDriverPath
0x140048236  nop     dword ptr [rax+rax+00h]
0x14004823b  test    eax, eax
0x14004823d  js      loc_1400482D2
0x140048243  mov     r8b, 1; AllocateDestinationString
0x140048246  lea     rdx, [rbp+57h+RegHandle]; SourceString
0x14004824a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004824e  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140048255  nop     dword ptr [rax+rax+00h]
0x14004825a  mov     rcx, [rbp+57h+RegHandle+8]; P
0x14004825e  xor     edx, edx; Tag
0x140048260  mov     ebx, eax
0x140048262  call    cs:__imp_ExFreePoolWithTag
0x140048269  nop     dword ptr [rax+rax+00h]
0x14004826e  test    ebx, ebx
0x140048270  js      short loc_1400482D2
0x140048272  movzx   edx, [rbp+57h+DestinationString.Length]
0x140048276  lea     ecx, [rdx-1]
0x140048279  test    ecx, ecx
0x14004827b  jz      short loc_1400482C2
0x14004827d  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140048281  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140048286  jz      short loc_14004828F
0x140048288  add     ecx, 0FFFFFFFFh
0x14004828b  jnz     short loc_140048281
0x14004828d  jmp     short loc_1400482C2
0x14004828f  cmp     ecx, edx
0x140048291  jz      short loc_1400482C2
0x140048293  lea     edx, [rcx+1]
0x140048296  xorps   xmm0, xmm0
0x140048299  add     rdx, r8; SourceString
0x14004829c  lea     rcx, [rbp+57h+var_80]; DestinationString
0x1400482a0  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x1400482a4  call    cs:__imp_RtlInitAnsiString
0x1400482ab  nop     dword ptr [rax+rax+00h]
0x1400482b0  movaps  xmm0, xmmword ptr [rbp+57h+var_80.Length]
0x1400482b4  lea     rcx, [rbp+57h+var_70]
0x1400482b8  movdqa  [rbp+57h+var_70], xmm0
0x1400482bd  call    InitializeTelemetryAssertsKMWorkerInternal
0x1400482c2  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x1400482c6  call    cs:__imp_RtlFreeAnsiString
0x1400482cd  nop     dword ptr [rax+rax+00h]
0x1400482d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482d9  lea     rdx, [rbp+57h+var_28]
0x1400482dd  mov     ebx, 10h
0x1400482e2  mov     dword ptr [rbp+57h+var_28+8], esi
0x1400482e5  mov     dword ptr [rbp+57h+var_28], ebx
0x1400482e8  mov     dword ptr [rbp+57h+var_28+0Ch], esi
0x1400482eb  mov     byte ptr [rbp+57h+var_28+4], 1
0x1400482ef  call    cs:__imp_imp_WppRecorderConfigure
0x1400482f6  nop     dword ptr [rax+rax+00h]
0x1400482fb  mov     edi, 7FFFFFFEh
0x140048300  mov     qword ptr [rbp+57h+var_60], 38h ; '8'
0x140048308  mov     eax, edi
0x14004830a  mov     byte ptr [rbp+57h+var_40], r14b
0x14004830e  mov     dword ptr [rbp+57h+var_50+0Ch], ebx
0x140048311  lea     r8, aGvtracelog; "GvTraceLog"
0x140048318  mov     qword ptr [rbp+57h+var_50], r14
0x14004831c  lea     rcx, [rbp+57h+var_40]
0x140048320  mov     byte ptr [rbp+57h+var_50+8], r14b
0x140048324  mov     edx, ebx
0x140048326  test    rax, rax
0x140048329  jz      short loc_140048345
0x14004832b  mov     r9b, [r8]
0x14004832e  test    r9b, r9b
0x140048331  jz      short loc_140048345
0x140048333  mov     [rcx], r9b
0x140048336  inc     r8
0x140048339  inc     rcx
0x14004833c  dec     rax
0x14004833f  sub     rdx, 1
0x140048343  jnz     short loc_140048326
0x140048345  test    rdx, rdx
0x140048348  lea     rax, [rcx-1]
0x14004834c  lea     r8, _PrjfTraceRecorder
0x140048353  cmovnz  rax, rcx
0x140048357  lea     rdx, [rbp+57h+var_60]
0x14004835b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048362  mov     [rax], r14b
0x140048365  mov     dword ptr [rbp+57h+var_30], esi
0x140048368  mov     dword ptr [rbp+57h+var_30+4], esi
0x14004836b  mov     dword ptr [rbp+57h+var_60+8], 1000h
0x140048372  mov     dword ptr [rbp+57h+var_60+0Ch], 0C8h
0x140048379  call    cs:__imp_imp_WppRecorderLogCreate
0x140048380  nop     dword ptr [rax+rax+00h]
0x140048385  test    eax, eax
0x140048387  jns     short loc_14004839C
0x140048389  lea     rcx, aUnableToCreate; "Unable to create trace log recorder - d"...
0x140048390  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140048395  mov     cs:_PrjfTraceRecorder, r14
0x14004839c  mov     qword ptr [rbp+57h+var_60], 38h ; '8'
0x1400483a4  lea     rax, aGventerleavelo; "GvEnterLeaveLog"
0x1400483ab  mov     byte ptr [rbp+57h+var_40], r14b
0x1400483af  lea     rcx, [rbp+57h+var_40]
0x1400483b3  mov     dword ptr [rbp+57h+var_50+0Ch], ebx
0x1400483b6  mov     qword ptr [rbp+57h+var_50], r14
0x1400483ba  mov     byte ptr [rbp+57h+var_50+8], r14b
0x1400483be  test    rdi, rdi
0x1400483c1  jz      short loc_1400483DA
0x1400483c3  mov     dl, [rax]
0x1400483c5  test    dl, dl
0x1400483c7  jz      short loc_1400483DA
0x1400483c9  mov     [rcx], dl
0x1400483cb  inc     rax
0x1400483ce  inc     rcx
0x1400483d1  dec     rdi
0x1400483d4  sub     rbx, 1
0x1400483d8  jnz     short loc_1400483BE
0x1400483da  lea     rax, [rcx-1]
0x1400483de  test    rbx, rbx
0x1400483e1  lea     r8, _PrjfEnterLeaveRecorder
0x1400483e8  cmovnz  rax, rcx
0x1400483ec  lea     rdx, [rbp+57h+var_60]
0x1400483f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483f7  mov     [rax], r14b
0x1400483fa  mov     dword ptr [rbp+57h+var_30], esi
0x1400483fd  mov     dword ptr [rbp+57h+var_30+4], esi
0x140048400  mov     dword ptr [rbp+57h+var_60+8], 1000h
0x140048407  mov     dword ptr [rbp+57h+var_60+0Ch], 0C8h
0x14004840e  call    cs:__imp_imp_WppRecorderLogCreate
0x140048415  nop     dword ptr [rax+rax+00h]
0x14004841a  test    eax, eax
0x14004841c  jns     short loc_140048431
0x14004841e  lea     rcx, aUnableToCreate; "Unable to create trace log recorder - d"...
0x140048425  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004842a  mov     cs:_PrjfEnterLeaveRecorder, r14
0x140048431  call    TlgRegisterAggregateProvider
0x140048436  test    eax, eax
0x140048438  jns     short loc_1400484B5
0x14004843a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140048440  lea     rcx, WPP_RECORDER_INITIALIZED
0x140048447  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14004844e  setnz   r8b
0x140048452  and     dl, sil
0x140048455  jnz     short loc_14004845C
0x140048457  test    r8b, r8b
0x14004845a  jz      short loc_1400484A9
0x14004845c  mov     r9, cs:WPP_GLOBAL_Control
0x140048463  mov     ecx, 201h
0x140048468  mov     [rsp+110h+var_C0], eax
0x14004846c  lea     rax, aOnecoreBaseFsG_4; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048473  mov     [rsp+110h+var_C8], 0BEh
0x14004847b  mov     [rsp+110h+var_D0], rax
0x140048480  lea     rax, WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids
0x140048487  mov     r9, [r9+40h]
0x14004848b  mov     [rsp+110h+var_D8], rax
0x140048490  mov     [rsp+110h+var_E0], 0Ah
0x140048497  mov     [rsp+110h+var_E8], 1
0x14004849f  mov     [rsp+110h+var_F0], sil
0x1400484a4  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400484a9  lea     rcx, aFailedToRegist; "Failed to register telemetry."
0x1400484b0  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400484b5  mov     rcx, [rbp+57h+var_18]
0x1400484b9  xor     rcx, rsp; StackCookie
0x1400484bc  call    __security_check_cookie
0x1400484c1  lea     r11, [rsp+110h+var_10]
0x1400484c9  mov     rbx, [r11+30h]
0x1400484cd  mov     rsi, [r11+38h]
0x1400484d1  mov     rsp, r11
0x1400484d4  pop     r14
0x1400484d6  pop     rdi
0x1400484d7  pop     rbp
0x1400484d8  retn
```
