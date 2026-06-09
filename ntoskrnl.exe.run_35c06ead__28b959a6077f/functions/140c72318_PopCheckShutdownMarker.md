# PopCheckShutdownMarker

- ea: `0x140c72318`
- end: `0x140c729fa`
- name: `PopCheckShutdownMarker`
- size: `1762`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140c70a9c`

## callees

- `0x140307510`
- `0x1404ba12c`
- `0x1404e7c00`
- `0x1406d9d70`
- `0x1406daf50`
- `0x1406dd650`
- `0x1406de4b0`
- `0x140720384`
- `0x140786cc4`
- `0x1407baca0`
- `0x1407bad50`
- `0x140a37360`
- `0x140ac3728`
- `0x140ad71b4`
- `0x140c72318`
- `0x140c72a00`
- `0x140c741e4`
- `0x140c74dc8`

## string_xrefs

- `0x140c72840`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140c7286b`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140c7288d`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\LastCrashdump`

## pseudocode

```c
char __fastcall PopCheckShutdownMarker(__int64 a1)
{
  __int64 v1; // rax
  char v3; // dl
  int SystemBootStatus; // ebx
  __int64 i; // rdx
  unsigned int ULongFromUser; // eax
  __int64 v7; // r9
  __int64 v8; // r8
  char v9; // cl
  char result; // al
  UCHAR Size; // bl
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  UCHAR v15; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+41h] [rbp-BFh] BYREF
  bool v17; // [rsp+42h] [rbp-BEh] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h] BYREF
  char v28[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  int *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  int *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  PVOID *p_SystemArgument1; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  int *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  int *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  int *v43; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+118h] [rbp+18h]
  char *v45; // [rsp+120h] [rbp+20h]
  __int64 v46; // [rsp+128h] [rbp+28h]
  bool *v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+138h] [rbp+38h]
  _DWORD v49[2]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 *p_RelativeTimerBias; // [rsp+148h] [rbp+48h]
  int v51; // [rsp+150h] [rbp+50h]
  int v52; // [rsp+158h] [rbp+58h]
  PVOID *p_SparePtr; // [rsp+160h] [rbp+60h]
  int v54; // [rsp+168h] [rbp+68h]
  int v55; // [rsp+170h] [rbp+70h]
  $E2C6C6C915598FB0034C51775CBCD2CB *v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+180h] [rbp+80h]
  int v58; // [rsp+188h] [rbp+88h]
  unsigned __int8 *v59; // [rsp+190h] [rbp+90h]
  int v60; // [rsp+198h] [rbp+98h]

  v1 = *(_QWORD *)(a1 + 240);
  v15 = 0;
  v18 = 0;
  v26 = 0;
  v19 = 0;
  v27 = 0;
  v3 = *(_BYTE *)(v1 + 132);
  v49[0] = 14;
  p_RelativeTimerBias = &stru_140E4D568.RelativeTimerBias;
  stru_140E4D568.WaitBlockFill6[88] = v3 & 1;
  p_SparePtr = &stru_140E4D568.WaitBlock[0].SparePtr;
  v56 = &stru_140E4D568.216;
  v59 = &stru_140E4D568.WaitBlockFill6[100];
  v51 = 64;
  v52 = 7;
  v54 = 32;
  v55 = 16;
  v57 = 32;
  v58 = 11;
  v60 = 4;
  RtlCheckSystemBootStatusIntegrity(&stru_140E4D568.WaitBlockFill11[89]);
  SystemBootStatus = RtlGetSystemBootStatusEx(v49, 4, &v27);
  if ( SystemBootStatus < 0 )
  {
    for ( i = 0; i != 4; ++i )
    {
      if ( !*(_DWORD *)&v28[4 * i - 16] )
        *(_DWORD *)&stru_140E4D568.WaitBlockFill11[92] |= 1 << LOBYTE(v49[6 * i]);
    }
    ULongFromUser = RtlReadULongFromUser(2147353284);
    LOBYTE(v7) = stru_140E4D568.WaitBlockFill6[89];
    PopDiagTraceInvalidBootStat(
      ULongFromUser,
      *(unsigned int *)&stru_140E4D568.WaitBlockFill11[92],
      (unsigned int)SystemBootStatus,
      v7);
  }
  *(_OWORD *)&stru_140E4D568.SchedulerApcFill5[32] = *(_OWORD *)&stru_140E4D568.RelativeTimerBias;
  *(LIST_ENTRY *)&stru_140E4D568.SchedulerApcFill5[48] = stru_140E4D568.Timer.Header.WaitListHead;
  *(_OWORD *)&stru_140E4D568.SchedulerApcFill5[64] = *(_OWORD *)&stru_140E4D568.Timer.DueTime.LowPart;
  *(_OWORD *)&stru_140E4D568.SchedulerApcFill5[80] = *(_OWORD *)&stru_140E4D568.Timer.TimerListEntry.Blink;
  if ( _mm_srli_si128(*(__m128i *)&stru_140E4D568.RelativeTimerBias, 8).m128i_u32[0]
    && (unsigned int)dword_140E0B718 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_140E0B718, 0x200000000000LL) )
  {
    v20 = *(unsigned __int16 *)&stru_140E4D568.SchedulerApcFill5[44];
    v31 = &v20;
    v33 = &v21;
    p_SystemArgument1 = &stru_140E4D568.SchedulerApc.SystemArgument1;
    v22 = *(unsigned __int16 *)&stru_140E4D568.SchedulerApcFill5[76];
    v37 = &v22;
    v39 = &v23;
    v24 = *(unsigned __int16 *)&stru_140E4D568.SchedulerApcFill5[78];
    v41 = &v24;
    v25 = stru_140E4D568.SchedulerApcFill3[46];
    v43 = &v25;
    v16 = stru_140E4D568.SchedulerApcFill3[47] & 1;
    v29 = v8;
    v45 = &v16;
    v21 = *(_DWORD *)&stru_140E4D568.SchedulerApcFill5[40];
    v47 = &v17;
    v23 = *(_DWORD *)&stru_140E4D568.SchedulerApcFill5[40];
    v17 = (stru_140E4D568.SchedulerApcFill3[47] & 2) != 0;
    v30 = 8;
    v32 = 4;
    v34 = 4;
    v36 = 8;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 1;
    v48 = 1;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140E0B718, &word_1400496B6, 0, 0, 12, v28);
  }
  *(_OWORD *)(&stru_140E4D568.MiscFlags + 1) = *(_OWORD *)&stru_140E4D568.WaitBlockFill11[40];
  *(_OWORD *)&stru_140E4D568.FirstArgument = *(_OWORD *)&stru_140E4D568.WaitBlockFill11[56];
  stru_140E4D568.ApcState.ApcListHead[0] = *(_LIST_ENTRY *)&stru_140E4D568.WaitBlockFill11[40];
  *(_OWORD *)&stru_140E4D568.ApcStateFill[16] = *(_OWORD *)&stru_140E4D568.WaitBlockFill11[56];
  *(_OWORD *)&stru_140E4D568.StackBase = *(_OWORD *)&stru_140E4D568.RelativeTimerBias;
  *(LIST_ENTRY *)&stru_140E4D568.CycleTime = stru_140E4D568.Timer.Header.WaitListHead;
  *(_OWORD *)&stru_140E4D568.KernelStack = *(_OWORD *)&stru_140E4D568.Timer.DueTime.LowPart;
  *(_OWORD *)&stru_140E4D568.SchedulingGroup = *(_OWORD *)&stru_140E4D568.Timer.TimerListEntry.Blink;
  *($E2C6C6C915598FB0034C51775CBCD2CB *)&stru_140E4D568.SchedulerApc.Type = stru_140E4D568.216;
  *(_OWORD *)&stru_140E4D568.SchedulerApcFill5[16] = *(_OWORD *)&stru_140E4D568.Queue;
  *($E2C6C6C915598FB0034C51775CBCD2CB *)&stru_140E4D568.ApcStateFill[32] = stru_140E4D568.216;
  *(_OWORD *)&stru_140E4D568.WaitStatus = *(_OWORD *)&stru_140E4D568.Queue;
  if ( (ExpKeyManipLock.SavedApcStateFill[16] & 4) != 0 )
    LOBYTE(stru_140E4D568.SystemCallNumber) &= ~1u;
  if ( (PopAwaymodeLock.RealtimePriorityFloor & 0x200) != 0 )
    LOBYTE(stru_140E4D568.SystemCallNumber) |= 1u;
  v9 = BYTE2(stru_140E4D568.ReadyTime) & 0xDF;
  BYTE2(stru_140E4D568.ReadyTime) &= ~0x20u;
  if ( *(_DWORD *)&stru_140E4D568.SchedulerApcFill5[40] && (stru_140E4D568.SchedulerApcFill3[47] & 4) != 0 )
  {
    BYTE2(stru_140E4D568.ReadyTime) = v9 | 0x20;
    *($C9C4F79064DE35237E3F199A7D1BD3E1 *)((char *)&stru_140E4D568.116 + 4) = ($C9C4F79064DE35237E3F199A7D1BD3E1)stru_140E4D568.SchedulerApc.Reserved[0];
  }
  stru_140E4D568.WaitBlockFill6[76] = (stru_140E4D568.WaitBlockFill5[54] & 0x10) != 0;
  v26 = WNF_PO_PREVIOUS_SHUTDOWN_STATE;
  v18 = stru_140E4D568.SystemCallNumber & 1;
  result = ZwUpdateWnfStateData(&v26, &v18, 4, 0, 0, 0, 0);
  if ( (PopAwaymodeLock.RealtimePriorityFloor & 0x400) != 0 )
  {
    LOWORD(stru_140E4D568.ReadyTime) = 1;
    result = stru_140E4D568.SystemCallNumber & 0xF | 0x50;
    LOBYTE(stru_140E4D568.SystemCallNumber) = result;
  }
  if ( (PopAwaymodeLock.RealtimePriorityFloor & 0x20000000) != 0 )
  {
    LOBYTE(stru_140E4D568.SystemCallNumber) |= 2u;
    stru_140E4D568.SchedulerApc.ApcListEntry.Blink = (struct _LIST_ENTRY *)1;
  }
  if ( (stru_140E4D568.SystemCallNumber & 1) != 0 )
  {
    v19 = 1;
    if ( (int)ExGetFirmwareEnvironmentVariable(
                (unsigned int)L"*,",
                (unsigned int)SYSTEM_SLEEP_ETW_CHECKPOINT_GUID,
                (unsigned int)&v15,
                (unsigned int)&v19,
                0) < 0 )
    {
      Size = stru_140E4D568.SchedulerApc.Size;
      stru_140E4D568.SchedulerApc.SpareByte0 = stru_140E4D568.SchedulerApc.SpareByte0 & 0xF3 | 8;
      PopRecordSleepCheckpointSource(2);
    }
    else
    {
      Size = v15;
      stru_140E4D568.SchedulerApc.Size = v15;
      stru_140E4D568.SchedulerApc.SpareByte0 = stru_140E4D568.SchedulerApc.SpareByte0 & 0xF3 | 4;
      PopRecordSleepCheckpoint(v15);
      PopRecordSleepCheckpointSource(1);
      LOBYTE(v12) = 1;
      PopClearSystemSleepCheckpoint(v12);
    }
    v13 = *(_QWORD *)(a1 + 240);
    if ( v13 )
    {
      v14 = *(_QWORD *)(v13 + 280);
      if ( v14 )
      {
        *(_DWORD *)&stru_140E4D568.WaitBlockFill11[104] = *(_DWORD *)(v14 + 56);
        *(_OWORD *)&stru_140E4D568.WaitBlockFill11[112] = *(_OWORD *)(v14 + 64);
        *(_OWORD *)&stru_140E4D568.WaitBlockFill11[128] = *(_OWORD *)(v14 + 80);
      }
    }
    LODWORD(stru_140E4D568.Process) = 0;
    PopReadRegKeyValue(
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl",
      L"CrashDumpEnabled",
      4,
      4,
      &stru_140E4D568.Process);
    HIDWORD(stru_140E4D568.Process) = 0;
    PopReadRegKeyValue(
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl",
      L"FilterPages",
      4,
      4,
      (char *)&stru_140E4D568.Process + 4);
    if ( (int)PopReadRegKeyValue(
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\LastCrashdump",
                L"Info",
                48,
                0,
                &stru_140E4D568.UserAffinity) >= 0
      && !*(_DWORD *)&stru_140E4D568.WaitBlockFill11[104]
      && *(_DWORD *)&stru_140E4D568.UserAffinityPrimaryGroup )
    {
      *(_DWORD *)&stru_140E4D568.WaitBlockFill11[104] = *(_DWORD *)&stru_140E4D568.UserAffinityPrimaryGroup;
      *(_QWORD *)&stru_140E4D568.WaitBlockFill11[112] = stru_140E4D568.AffinityVersion;
      *(_DWORD *)&stru_140E4D568.WaitBlockFill11[144] = 1;
    }
    *(_DWORD *)&stru_140E4D568.WaitBlockFill11[96] = RtlReadULongFromUser(2147353284);
    stru_140E4D568.WaitBlockFill11[168] = Size;
    stru_140E4D568.Spare18 = (unsigned __int64)stru_140E4D568.SchedulerApc.Reserved;
    stru_140E4D568.WaitBlock[3].WaitListEntry.Blink = (struct _LIST_ENTRY *)((char *)&stru_140E4D568.116 + 4);
    *(_QWORD *)&stru_140E4D568.WaitBlockFill11[160] = &stru_140E4D568.648;
    LODWORD(stru_140E4D568.LastXStateSaveDebugInfo) = ExBootAppErrorDiagCode;
    HIDWORD(stru_140E4D568.LastXStateSaveDebugInfo) = ExBootAppFailureStatus;
    ZwQuerySystemInformation(90, &stru_140E4D568.512, 32, 0);
    *(_DWORD *)&stru_140E4D568.SavedApcStateFill[8] = 7;
    stru_140E4D568.SavedApcState.ApcListHead[1].Flink = (struct _LIST_ENTRY *)&stru_140E4D568.Timer.Processor;
    if ( (int)ZwQuerySystemInformationEx(
                72,
                &stru_140E4D568.SavedApcStateFill[8],
                4,
                &stru_140E4D568.SavedApcStateFill[8],
                8,
                0) >= 0 )
    {
      LODWORD(stru_140E4D568.SavedApcState.ApcListHead[0].Flink) = *(_DWORD *)&stru_140E4D568.SavedApcStateFill[12];
      if ( *(_DWORD *)&stru_140E4D568.SavedApcStateFill[12] )
      {
        *(_DWORD *)&stru_140E4D568.SavedApcStateFill[8] = 8;
        if ( (int)ZwQuerySystemInformationEx(
                    72,
                    &stru_140E4D568.SavedApcStateFill[8],
                    4,
                    &stru_140E4D568.SavedApcStateFill[8],
                    8,
                    0) >= 0 )
          *(_DWORD *)&stru_140E4D568.SavedApcStateFill[4] = *(_DWORD *)&stru_140E4D568.SavedApcStateFill[12];
      }
    }
    PopReadWheaBootErrorCount(&stru_140E4D568.SavedApcStateFill[24]);
    return PopDiagTraceDirtyTransition(&stru_140E4D568.WaitBlockFill11[88]);
  }
  return result;
}

```

## disassembly

```asm
0x140c72318  push    rbp
0x140c7231a  push    rbx
0x140c7231b  push    rsi
0x140c7231c  push    rdi
0x140c7231d  push    r12
0x140c7231f  push    r14
0x140c72321  push    r15
0x140c72323  lea     rbp, [rsp-0B0h]
0x140c7232b  sub     rsp, 1B0h
0x140c72332  mov     rax, cs:__security_cookie
0x140c72339  xor     rax, rsp
0x140c7233c  mov     [rbp+0E0h+var_40], rax
0x140c72343  mov     rax, [rcx+0F0h]
0x140c7234a  xor     esi, esi
0x140c7234c  xorps   xmm0, xmm0
0x140c7234f  mov     [rsp+1E0h+var_1A0], sil
0x140c72354  mov     [rsp+1E0h+var_19C], esi
0x140c72358  mov     rdi, rcx
0x140c7235b  mov     [rsp+1E0h+var_178], rsi
0x140c72360  lea     rcx, stru_140E4D568.___u33+59h
0x140c72367  mov     [rsp+1E0h+var_198], esi
0x140c7236b  lea     r14d, [rsi+1]
0x140c7236f  movups  [rsp+1E0h+var_170], xmm0
0x140c72374  mov     dl, [rax+84h]
0x140c7237a  lea     r15d, [rsi+4]
0x140c7237e  lea     rax, stru_140E4D568.RelativeTimerBias
0x140c72385  mov     [rbp+0E0h+var_A0], 0Eh
0x140c7238c  mov     [rbp+0E0h+var_98], rax
0x140c72390  and     dl, r14b
0x140c72393  lea     rax, stru_140E4D568.___u33+28h
0x140c7239a  mov     byte ptr cs:stru_140E4D568.___u33+58h, dl
0x140c723a0  mov     [rbp+0E0h+var_80], rax
0x140c723a4  lea     rax, stru_140E4D568.___u28
0x140c723ab  mov     [rbp+0E0h+var_68], rax
0x140c723af  lea     rax, stru_140E4D568.___u33+64h
0x140c723b6  mov     [rbp+0E0h+var_50], rax
0x140c723bd  mov     [rbp+0E0h+var_90], 40h ; '@'
0x140c723c4  mov     [rbp+0E0h+var_88], 7
0x140c723cb  mov     [rbp+0E0h+var_78], 20h ; ' '
0x140c723d2  mov     [rbp+0E0h+var_70], 10h
0x140c723d9  mov     [rbp+0E0h+var_60], 20h ; ' '
0x140c723e3  mov     [rbp+0E0h+var_58], 0Bh
0x140c723ed  mov     [rbp+0E0h+var_48], r15d
0x140c723f4  call    RtlCheckSystemBootStatusIntegrity
0x140c723f9  lea     r8, [rsp+1E0h+var_170]
0x140c723fe  mov     edx, r15d
0x140c72401  lea     rcx, [rbp+0E0h+var_A0]
0x140c72405  call    RtlGetSystemBootStatusEx
0x140c7240a  mov     ebx, eax
0x140c7240c  test    eax, eax
0x140c7240e  jns     short loc_140C72458
0x140c72410  mov     edx, esi
0x140c72412  cmp     dword ptr [rsp+rdx*4+1E0h+var_170], esi
0x140c72416  jnz     short loc_140C7242F
0x140c72418  mov     ecx, dword ptr cs:stru_140E4D568.___u33+5Ch
0x140c7241e  lea     rax, [rdx+rdx*2]
0x140c72422  mov     eax, [rbp+rax*8+0E0h+var_A0]
0x140c72426  bts     ecx, eax
0x140c72429  mov     dword ptr cs:stru_140E4D568.___u33+5Ch, ecx
0x140c7242f  add     rdx, r14
0x140c72432  cmp     rdx, r15
0x140c72435  jnz     short loc_140C72412
0x140c72437  mov     ecx, 7FFE02C4h
0x140c7243c  call    RtlReadULongFromUser
0x140c72441  mov     r9b, byte ptr cs:stru_140E4D568.___u33+59h
0x140c72448  mov     r8d, ebx
0x140c7244b  mov     edx, dword ptr cs:stru_140E4D568.___u33+5Ch
0x140c72451  mov     ecx, eax
0x140c72453  call    PopDiagTraceInvalidBootStat
0x140c72458  movaps  xmm2, xmmword ptr cs:stru_140E4D568.RelativeTimerBias
0x140c7245f  lea     r8, stru_140E4D568.___u58+20h
0x140c72466  movaps  xmm0, xmmword ptr cs:stru_140E4D568.Timer.Header.WaitListHead.Flink
0x140c7246d  mov     r12d, 8
0x140c72473  movaps  xmm1, xmmword ptr cs:stru_140E4D568.Timer.DueTime
0x140c7247a  movaps  xmmword ptr cs:stru_140E4D568.___u58+20h, xmm2
0x140c72481  psrldq  xmm2, 8
0x140c72486  movq    rax, xmm2
0x140c7248b  movaps  xmmword ptr cs:stru_140E4D568.___u58+30h, xmm0
0x140c72492  movaps  xmm0, xmmword ptr cs:stru_140E4D568.Timer.TimerListEntry.Blink
0x140c72499  movaps  xmmword ptr cs:stru_140E4D568.___u58+40h, xmm1
0x140c724a0  movaps  xmmword ptr cs:stru_140E4D568.___u58+50h, xmm0
0x140c724a7  test    eax, eax
0x140c724a9  jz      loc_140C725D7
0x140c724af  mov     eax, cs:dword_140E0B718
0x140c724b5  cmp     eax, 5
0x140c724b8  jbe     loc_140C725D7
0x140c724be  mov     rdx, 200000000000h
0x140c724c8  lea     rcx, dword_140E0B718
0x140c724cf  call    _tlgKeywordOn
0x140c724d4  test    al, al
0x140c724d6  jz      loc_140C725D7
0x140c724dc  mov     dl, byte ptr cs:stru_140E4D568.___u58+2Fh
0x140c724e2  xor     r9d, r9d
0x140c724e5  movzx   eax, word ptr cs:stru_140E4D568.___u58+2Ch
0x140c724ec  mov     ecx, dword ptr cs:stru_140E4D568.___u58+28h
0x140c724f2  mov     [rsp+1E0h+var_194], eax
0x140c724f6  lea     rax, [rsp+1E0h+var_194]
0x140c724fb  mov     [rbp+0E0h+var_130], rax
0x140c724ff  lea     rax, [rsp+1E0h+var_190]
0x140c72504  mov     [rbp+0E0h+var_120], rax
0x140c72508  lea     rax, stru_140E4D568.___u58+40h
0x140c7250f  mov     [rbp+0E0h+var_110], rax
0x140c72513  movzx   eax, word ptr cs:stru_140E4D568.___u58+4Ch
0x140c7251a  mov     [rsp+1E0h+var_18C], eax
0x140c7251e  lea     rax, [rsp+1E0h+var_18C]
0x140c72523  mov     [rbp+0E0h+var_100], rax
0x140c72527  lea     rax, [rsp+1E0h+var_188]
0x140c7252c  mov     [rbp+0E0h+var_F0], rax
0x140c72530  movzx   eax, word ptr cs:stru_140E4D568.___u58+4Eh
0x140c72537  mov     [rsp+1E0h+var_184], eax
0x140c7253b  lea     rax, [rsp+1E0h+var_184]
0x140c72540  mov     [rbp+0E0h+var_E0], rax
0x140c72544  movzx   eax, byte ptr cs:stru_140E4D568.___u58+2Eh
0x140c7254b  mov     [rsp+1E0h+var_180], eax
0x140c7254f  lea     rax, [rsp+1E0h+var_180]
0x140c72554  mov     [rbp+0E0h+var_D0], rax
0x140c72558  mov     al, dl
0x140c7255a  and     al, r14b
0x140c7255d  shr     dl, 1
0x140c7255f  mov     [rsp+1E0h+var_19F], al
0x140c72563  and     dl, r14b
0x140c72566  lea     rax, [rsp+1E0h+var_19F]
0x140c7256b  mov     [rbp+0E0h+var_140], r8
0x140c7256f  mov     [rbp+0E0h+var_C0], rax
0x140c72573  xor     r8d, r8d
0x140c72576  lea     rax, [rsp+1E0h+var_19E]
0x140c7257b  mov     [rsp+1E0h+var_190], ecx
0x140c7257f  mov     [rbp+0E0h+var_B0], rax
0x140c72583  lea     rax, [rbp+0E0h+var_160]
0x140c72587  mov     [rsp+1E0h+var_188], ecx
0x140c7258b  lea     rcx, dword_140E0B718
0x140c72592  mov     [rsp+1E0h+var_19E], dl
0x140c72596  lea     rdx, word_1400496B6
0x140c7259d  mov     [rsp+1E0h+var_1B8], rax
0x140c725a2  mov     dword ptr [rsp+1E0h+var_1C0], 0Ch
0x140c725aa  mov     [rbp+0E0h+var_138], r12
0x140c725ae  mov     [rbp+0E0h+var_128], r15
0x140c725b2  mov     [rbp+0E0h+var_118], r15
0x140c725b6  mov     [rbp+0E0h+var_108], r12
0x140c725ba  mov     [rbp+0E0h+var_F8], r15
0x140c725be  mov     [rbp+0E0h+var_E8], r15
0x140c725c2  mov     [rbp+0E0h+var_D8], r15
0x140c725c6  mov     [rbp+0E0h+var_C8], r15
0x140c725ca  mov     [rbp+0E0h+var_B8], r14
0x140c725ce  mov     [rbp+0E0h+var_A8], r14
0x140c725d2  call    _tlgWriteTransfer_EtwWriteTransfer
0x140c725d7  test    byte ptr cs:ExpKeyManipLock.___u57+10h, r15b
0x140c725de  movups  xmm1, xmmword ptr cs:stru_140E4D568.___u33+28h
0x140c725e5  movups  xmm0, xmmword ptr cs:stru_140E4D568.___u33+38h
0x140c725ec  movups  xmm3, xmmword ptr cs:stru_140E4D568.___u28
0x140c725f3  movups  xmm2, xmmword ptr cs:stru_140E4D568.Queue
0x140c725fa  movups  xmmword ptr cs:stru_140E4D568.___u16+4, xmm1
0x140c72601  movups  xmmword ptr cs:stru_140E4D568.FirstArgument, xmm0
0x140c72608  movups  xmmword ptr cs:stru_140E4D568.___u25, xmm1
0x140c7260f  movaps  xmm1, xmmword ptr cs:stru_140E4D568.Timer.Header.WaitListHead.Flink
0x140c72616  movups  xmmword ptr cs:stru_140E4D568.___u25+10h, xmm0
0x140c7261d  movaps  xmm0, xmmword ptr cs:stru_140E4D568.RelativeTimerBias
0x140c72624  movaps  xmmword ptr cs:stru_140E4D568.StackBase, xmm0
0x140c7262b  movaps  xmm0, xmmword ptr cs:stru_140E4D568.Timer.DueTime
0x140c72632  movaps  xmmword ptr cs:stru_140E4D568.CycleTime, xmm1
0x140c72639  movaps  xmm1, xmmword ptr cs:stru_140E4D568.Timer.TimerListEntry.Blink
0x140c72640  movaps  xmmword ptr cs:stru_140E4D568.KernelStack, xmm0
0x140c72647  movaps  xmmword ptr cs:stru_140E4D568.SchedulingGroup, xmm1
0x140c7264e  movups  xmmword ptr cs:stru_140E4D568.___u58, xmm3
0x140c72655  movups  xmmword ptr cs:stru_140E4D568.___u58+10h, xmm2
0x140c7265c  movups  xmmword ptr cs:stru_140E4D568.___u25+20h, xmm3
0x140c72663  movups  xmmword ptr cs:stru_140E4D568.WaitStatus, xmm2
0x140c7266a  jz      short loc_140C72673
0x140c7266c  and     byte ptr cs:stru_140E4D568.SystemCallNumber, 0FEh
0x140c72673  test    cs:PopAwaymodeLock.RealtimePriorityFloor, 200h
0x140c7267d  jz      short loc_140C72686
0x140c7267f  or      byte ptr cs:stru_140E4D568.SystemCallNumber, r14b
0x140c72686  mov     cl, byte ptr cs:stru_140E4D568.ReadyTime+2
0x140c7268c  and     cl, 0DFh
0x140c7268f  cmp     dword ptr cs:stru_140E4D568.___u58+28h, esi
0x140c72695  mov     byte ptr cs:stru_140E4D568.ReadyTime+2, cl
0x140c7269b  jz      short loc_140C726BD
0x140c7269d  test    byte ptr cs:stru_140E4D568.___u58+2Fh, r15b
0x140c726a4  jz      short loc_140C726BD
0x140c726a6  mov     rax, qword ptr cs:stru_140E4D568.___u58+20h
0x140c726ad  or      cl, 20h
0x140c726b0  mov     byte ptr cs:stru_140E4D568.ReadyTime+2, cl
0x140c726b6  mov     qword ptr cs:stru_140E4D568.___u16+4, rax
0x140c726bd  mov     al, byte ptr cs:stru_140E4D568.___u33+36h
0x140c726c3  lea     rdx, [rsp+1E0h+var_19C]
0x140c726c8  shr     al, 4
0x140c726cb  lea     rcx, [rsp+1E0h+var_178]
0x140c726d0  and     al, r14b
0x140c726d3  mov     [rsp+1E0h+var_1B0], esi
0x140c726d7  mov     byte ptr cs:stru_140E4D568.___u33+4Ch, al
0x140c726dd  xor     r9d, r9d
0x140c726e0  mov     rax, cs:WNF_PO_PREVIOUS_SHUTDOWN_STATE
0x140c726e7  mov     r8d, r15d
0x140c726ea  mov     [rsp+1E0h+var_178], rax
0x140c726ef  movzx   eax, byte ptr cs:stru_140E4D568.SystemCallNumber
0x140c726f6  and     eax, r14d
0x140c726f9  mov     dword ptr [rsp+1E0h+var_1B8], esi
0x140c726fd  mov     [rsp+1E0h+var_19C], eax
0x140c72701  mov     [rsp+1E0h+var_1C0], rsi
0x140c72706  call    ZwUpdateWnfStateData
0x140c7270b  mov     ecx, cs:PopAwaymodeLock.RealtimePriorityFloor
0x140c72711  bt      ecx, 0Ah
0x140c72715  jnb     short loc_140C7272F
0x140c72717  mov     al, byte ptr cs:stru_140E4D568.SystemCallNumber
0x140c7271d  and     al, 0Fh
0x140c7271f  mov     word ptr cs:stru_140E4D568.ReadyTime, r14w
0x140c72727  or      al, 50h
0x140c72729  mov     byte ptr cs:stru_140E4D568.SystemCallNumber, al
0x140c7272f  bt      ecx, 1Dh
0x140c72733  jnb     short loc_140C72743
0x140c72735  or      byte ptr cs:stru_140E4D568.SystemCallNumber, 2
0x140c7273c  mov     qword ptr cs:stru_140E4D568.___u58+18h, r14
0x140c72743  test    byte ptr cs:stru_140E4D568.SystemCallNumber, r14b
0x140c7274a  jz      loc_140C729D8
0x140c72750  lea     r9, [rsp+1E0h+var_198]
0x140c72755  mov     [rsp+1E0h+var_198], r14d
0x140c7275a  lea     r8, [rsp+1E0h+var_1A0]
0x140c7275f  mov     [rsp+1E0h+var_1C0], rsi
0x140c72764  lea     rdx, SYSTEM_SLEEP_ETW_CHECKPOINT_GUID
0x140c7276b  lea     rcx, PopCheckpointSystemSleepVariable; "*,"
0x140c72772  call    ExGetFirmwareEnvironmentVariable
0x140c72777  test    eax, eax
0x140c72779  js      short loc_140C727B2
0x140c7277b  movzx   eax, [rsp+1E0h+var_1A0]
0x140c72780  mov     ebx, eax
0x140c72782  mov     byte ptr cs:stru_140E4D568.___u58+2, al
0x140c72788  mov     al, byte ptr cs:stru_140E4D568.___u58+1
0x140c7278e  mov     ecx, ebx
0x140c72790  and     al, 0F7h
0x140c72792  or      al, r15b
0x140c72795  mov     byte ptr cs:stru_140E4D568.___u58+1, al
0x140c7279b  call    PopRecordSleepCheckpoint
0x140c727a0  mov     ecx, r14d
0x140c727a3  call    PopRecordSleepCheckpointSource
0x140c727a8  mov     cl, r14b
0x140c727ab  call    PopClearSystemSleepCheckpoint
0x140c727b0  jmp     short loc_140C727D4
0x140c727b2  mov     al, byte ptr cs:stru_140E4D568.___u58+1
0x140c727b8  mov     ecx, 2
0x140c727bd  movzx   ebx, byte ptr cs:stru_140E4D568.___u58+2
0x140c727c4  and     al, 0FBh
0x140c727c6  or      al, r12b
0x140c727c9  mov     byte ptr cs:stru_140E4D568.___u58+1, al
0x140c727cf  call    PopRecordSleepCheckpointSource
0x140c727d4  mov     rcx, [rdi+0F0h]
0x140c727db  test    rcx, rcx
0x140c727de  jz      short loc_140C72821
0x140c727e0  mov     rcx, [rcx+118h]
0x140c727e7  test    rcx, rcx
0x140c727ea  jz      short loc_140C72821
0x140c727ec  mov     eax, [rcx+38h]
0x140c727ef  mov     dword ptr cs:stru_140E4D568.___u33+68h, eax
0x140c727f5  mov     rax, [rcx+40h]
0x140c727f9  mov     qword ptr cs:stru_140E4D568.___u33+70h, rax
0x140c72800  mov     rax, [rcx+48h]
0x140c72804  mov     qword ptr cs:stru_140E4D568.___u33+78h, rax
0x140c7280b  mov     rax, [rcx+50h]
0x140c7280f  mov     qword ptr cs:stru_140E4D568.___u33+80h, rax
0x140c72816  mov     rax, [rcx+58h]
0x140c7281a  mov     qword ptr cs:stru_140E4D568.___u33+88h, rax
0x140c72821  lea     rax, stru_140E4D568.Process
0x140c72828  mov     dword ptr cs:stru_140E4D568.Process, esi
0x140c7282e  mov     r9d, r15d
0x140c72831  mov     [rsp+1E0h+var_1C0], rax
0x140c72836  mov     r8, r15
0x140c72839  lea     rdx, aCrashdumpenabl_0; "CrashDumpEnabled"
0x140c72840  lea     rcx, aRegistryMachin_146; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c72847  call    PopReadRegKeyValue
0x140c7284c  lea     rax, stru_140E4D568.Process+4
0x140c72853  mov     dword ptr cs:stru_140E4D568.Process+4, esi
0x140c72859  mov     r9d, r15d
0x140c7285c  mov     [rsp+1E0h+var_1C0], rax
0x140c72861  mov     r8, r15
0x140c72864  lea     rdx, aFilterpages; "FilterPages"
0x140c7286b  lea     rcx, aRegistryMachin_146; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c72872  call    PopReadRegKeyValue
0x140c72877  xor     r9d, r9d
0x140c7287a  lea     rax, stru_140E4D568.UserAffinity
0x140c72881  lea     rdx, aInfo; "Info"
0x140c72888  mov     [rsp+1E0h+var_1C0], rax
0x140c7288d  lea     rcx, aRegistryMachin_110; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c72894  lea     r8d, [r9+30h]
0x140c72898  call    PopReadRegKeyValue
0x140c7289d  test    eax, eax
0x140c7289f  js      short loc_140C728CE
0x140c728a1  cmp     dword ptr cs:stru_140E4D568.___u33+68h, esi
0x140c728a7  jnz     short loc_140C728CE
0x140c728a9  mov     eax, dword ptr cs:stru_140E4D568.UserAffinityPrimaryGroup
0x140c728af  test    eax, eax
0x140c728b1  jz      short loc_140C728CE
0x140c728b3  mov     dword ptr cs:stru_140E4D568.___u33+68h, eax
0x140c728b9  mov     rax, cs:stru_140E4D568.AffinityVersion
0x140c728c0  mov     qword ptr cs:stru_140E4D568.___u33+70h, rax
0x140c728c7  mov     dword ptr cs:stru_140E4D568.___u33+90h, r14d
0x140c728ce  mov     ecx, 7FFE02C4h
0x140c728d3  call    RtlReadULongFromUser
0x140c728d8  mov     dword ptr cs:stru_140E4D568.___u33+60h, eax
0x140c728de  lea     rdx, stru_140E4D568.___u34
0x140c728e5  xor     r9d, r9d
0x140c728e8  mov     byte ptr cs:stru_140E4D568.___u33+0A8h, bl
  ... truncated ...
```
