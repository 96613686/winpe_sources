# I8042MouseInterruptService

- ea: `0x140002610`
- end: `0x140004178`
- name: `I8042MouseInterruptService`
- size: `7016`
- prototype: `KSERVICE_ROUTINE`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140001130`
- `0x140001360`
- `0x1400014e0`
- `0x140002610`
- `0x140004180`
- `0x140004530`
- `0x140005440`
- `0x140005e90`
- `0x140006950`
- `0x140007b10`
- `0x14000c8b4`
- `0x14000daa0`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x1400028d3`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002c24`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002d14`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002d5b`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002ee0`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002fc9`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400036b5`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003901`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000399a`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003bc1`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003cf9`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003f07`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400028d3`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002c24`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002d14`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002d5b`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002ee0`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002fc9`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400036b5`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003901`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000399a`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003bc1`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003cf9`
- `ntoskrnl!KeInsertQueueDpc` at `0x140003f07`
- `HAL!KeStallExecutionProcessor` at `0x140002d8f`
- `HAL!KeStallExecutionProcessor` at `0x14000376b`
- `HAL!KeStallExecutionProcessor` at `0x140002d8f`
- `HAL!KeStallExecutionProcessor` at `0x14000376b`

## pseudocode

```c
BOOLEAN __fastcall I8042MouseInterruptService(struct _KINTERRUPT *Interrupt, char *ServiceContext)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  unsigned __int8 v5; // r14
  __int64 v6; // rdx
  _UNKNOWN **v7; // r8
  __int64 v8; // r9
  int *v9; // rsi
  __int64 v10; // r15
  __int64 v11; // rcx
  _DWORD *v12; // r12
  __int64 (__fastcall *v13)(_QWORD, __int64, __int64, _QWORD, unsigned __int8 *, char *, __int64, __int64); // rax
  BOOLEAN v14; // r13
  BOOLEAN result; // al
  char v16; // cl
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  char v20; // r14
  unsigned __int8 v21; // r15
  unsigned __int64 v22; // r9
  __int64 v23; // rax
  unsigned __int8 v24; // al
  int v25; // edx
  unsigned __int8 v26; // r8
  char v27; // al
  __int64 v28; // r8
  __int16 v29; // ax
  __int64 v30; // rdx
  struct _KDPC *v31; // rcx
  void *v32; // rdx
  __int64 v33; // r8
  int v34; // edx
  _UNKNOWN **v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // eax
  unsigned __int8 v38; // al
  __int16 v39; // cx
  char v40; // cl
  __int16 v41; // ax
  __int16 v42; // ax
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // al
  char v45; // al
  __int16 v46; // ax
  int v47; // eax
  int v48; // eax
  char v49; // al
  unsigned __int8 v50; // [rsp+98h] [rbp+38h] BYREF
  char v51; // [rsp+A0h] [rbp+40h] BYREF
  int v52; // [rsp+A8h] [rbp+48h]

  v50 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)ServiceContext,
      29,
      10,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  v3 = *((_QWORD *)ServiceContext + 8);
  if ( *(_DWORD *)(v3 + 80) != 1 )
    return 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                                 + 216LL));
  if ( (v5 & 0x21) != 0x21 )
  {
    KeStallExecutionProcessor(0xAu);
    v5 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 216LL));
    if ( (v5 & 0x21) != 0x21 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v34,
          31,
          11,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      return 0;
    }
  }
  LOBYTE(v4) = 2;
  I8xGetByteAsynchronous(v4, &v50);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      30,
      12,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v50);
  v9 = (int *)(v3 + 1004);
  v10 = MEMORY[0xFFFFF78000000320];
  if ( *(_DWORD *)(v3 + 1004) == 1100 )
    return 1;
  v11 = v50;
  v12 = (_DWORD *)(v3 + 1000);
  if ( *(_DWORD *)(v3 + 1000) == 5 && v50 == 0xFC )
  {
    *(_BYTE *)(v3 + 1104) = -4;
    v14 = 1;
    goto LABEL_36;
  }
  v13 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned __int8 *, char *, __int64, __int64))(v3 + 1064);
  v14 = 1;
  if ( v13 )
  {
    v51 = 0;
    result = v13(*(_QWORD *)(v3 + 1072), v3 + 976, v3 + 512, v5, &v50, &v51, v3 + 1000, v3 + 1004);
    v14 = result;
    if ( !v51 )
      return result;
    v11 = v50;
  }
  if ( *(_BYTE *)(v3 + 1104) == 0xAA && (!(_BYTE)v11 || (_BYTE)v11 == 3) )
  {
    v35 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        30,
        13,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v11);
      v35 = &WPP_RECORDER_INITIALIZED;
    }
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 600), 0, 0) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          30,
          14,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      goto LABEL_38;
    }
    LOBYTE(v35) = -44;
    LOBYTE(v11) = 1;
    I8xPutByteAsynchronous(v11, v35);
    LOBYTE(v36) = -14;
    I8xPutByteAsynchronous(0, v36);
    *v12 = 5;
    *v9 = 2;
    *(_BYTE *)(v3 + 1104) = v50;
    *(_WORD *)(v3 + 560) = 0;
    return 1;
  }
  if ( !*v12 && *(_DWORD *)(v3 + 528) && *((_QWORD *)ServiceContext + 4) )
  {
    if ( (_BYTE)v11 == 0xFE )
    {
      if ( *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) )
      {
        *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = -1;
        v25 = *(__int16 *)(v3 + 560);
        if ( v25 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 70LL) )
        {
          *(_DWORD *)(v3 + 528) = 0;
          KeInsertQueueDpc((PRKDPC)(v3 + 168), *((PVOID *)ServiceContext + 4), 0);
          return 1;
        }
        --*(_DWORD *)(v3 + 520);
        *(_WORD *)(v3 + 560) = v25 + 1;
        I8xInitiateIo(ServiceContext);
        LOBYTE(v11) = v50;
        goto LABEL_27;
      }
    }
    else
    {
      if ( (_BYTE)v11 != 0xFA )
        goto LABEL_27;
      if ( *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) )
      {
        *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = -1;
        v37 = *(_DWORD *)(v3 + 520);
        *(_WORD *)(v3 + 560) = 0;
        if ( v37 >= *(_DWORD *)(v3 + 524) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              30,
              16,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
          *(_DWORD *)(v3 + 528) = 0;
          KeInsertQueueDpc((PRKDPC)(ServiceContext + 200), *((PVOID *)ServiceContext + 4), (PVOID)2);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              30,
              15,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              v37);
          I8xInitiateIo(ServiceContext);
        }
        return 1;
      }
    }
    return 0;
  }
LABEL_27:
  *(_BYTE *)(v3 + 1104) = v11;
  v19 = (unsigned int)*v12;
  if ( (v19 & 0xFFFFFFFA) != 0 || (_DWORD)v19 == 1 )
  {
    v23 = v10 - *(_QWORD *)(v3 + 1016);
    if ( (unsigned int)v23 >= *(_DWORD *)(v3 + 1024) || HIDWORD(v23) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          30,
          17,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v19);
      goto LABEL_36;
    }
  }
  *(_QWORD *)(v3 + 1016) = v10;
  v20 = 0;
  v21 = 0;
  LOBYTE(v52) = 0;
  if ( (_DWORD)v19 == 2 )
  {
    v7 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        30,
        20,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      v7 = &WPP_RECORDER_INITIALIZED;
    }
    v16 = *(_BYTE *)(v3 + 1014);
    if ( v16 < 0 )
    {
      v49 = *(_BYTE *)(v3 + 1015);
      if ( v49 < 0 && (((unsigned __int8)v16 ^ (unsigned __int8)v49) & 0x20) != 0 )
      {
        v16 ^= 0x20u;
        *(_BYTE *)(v3 + 1014) = v16;
      }
      v18 = 255;
      if ( (v16 & 0x20) == 0 )
        v18 = -256;
    }
    else
    {
      v17 = v50;
      *(_DWORD *)(v3 + 992) = v50;
      if ( (v16 & 0x20) != 0 )
      {
        v17 |= 0xFFFFFF00;
        *(_DWORD *)(v3 + 992) = v17;
      }
      v18 = -v17;
    }
    *(_DWORD *)(v3 + 992) = v18;
    *(_BYTE *)(v3 + 1015) = *(_BYTE *)(v3 + 1014);
    v19 = (unsigned int)**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
    if ( (v19 & 8) != 0 )
    {
      *v12 = 3;
      goto LABEL_20;
    }
    goto LABEL_164;
  }
  if ( (_DWORD)v19 != 5 )
  {
    if ( !(_DWORD)v19 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          30,
          18,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 8) != 0 && (v50 & 0xC8) != 8 )
        goto LABEL_36;
      v19 = *(unsigned __int8 *)(v3 + 1101);
      *(_DWORD *)(v3 + 980) = 0;
      *(_WORD *)(v3 + 978) = 0;
      v26 = v50;
      if ( (v19 & 1) != 0 || (v50 & 1) == 0 )
      {
        v6 = 0;
        if ( (v19 & 1) == 0 || (v50 & 1) != 0 )
        {
LABEL_79:
          if ( (v19 & 2) != 0 )
          {
            if ( (v26 & 2) != 0 )
              goto LABEL_83;
            LOWORD(v6) = v6 | 8;
          }
          else
          {
            if ( (v26 & 2) == 0 )
            {
LABEL_83:
              if ( (v19 & 4) != 0 )
              {
                if ( (v26 & 4) != 0 )
                {
LABEL_87:
                  *(_BYTE *)(v3 + 1101) = v26 & 7 | v19 & 0x30;
                  v27 = v50 & 0xF0;
                  *v12 = 1;
                  *(_BYTE *)(v3 + 1014) = v27;
                  goto LABEL_20;
                }
                LOWORD(v6) = v6 | 0x20;
              }
              else
              {
                if ( (v26 & 4) == 0 )
                  goto LABEL_87;
                LOWORD(v6) = v6 | 0x10;
              }
              *(_WORD *)(v3 + 980) = v6;
              v26 = v50;
              goto LABEL_87;
            }
            LOWORD(v6) = v6 | 4;
          }
          *(_WORD *)(v3 + 980) = v6;
          v26 = v50;
          goto LABEL_83;
        }
        *(_WORD *)(v3 + 980) = 2;
        v6 = 2;
      }
      else
      {
        *(_WORD *)(v3 + 980) = 1;
        v6 = 1;
      }
      v26 = v50;
      goto LABEL_79;
    }
    v6 = (unsigned int)(v19 - 1);
    if ( (_DWORD)v19 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          30,
          19,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      v24 = *(_BYTE *)(v3 + 1014);
      if ( (v24 & 0x40) != 0 )
      {
        v43 = *(_BYTE *)(v3 + 1015);
        if ( (v43 & 0x40) != 0 && ((v24 ^ v43) & 0x10) != 0 )
        {
          v24 ^= 0x10u;
          *(_BYTE *)(v3 + 1014) = v24;
        }
        v19 = 4294967040LL;
        if ( (v24 & 0x10) == 0 )
          v19 = 255;
        *(_DWORD *)(v3 + 988) = v19;
      }
      else
      {
        v6 = v50;
        *(_DWORD *)(v3 + 988) = v50;
        if ( (v24 & 0x10) != 0 )
        {
          v6 = (unsigned int)v6 | 0xFFFFFF00;
          *(_DWORD *)(v3 + 988) = v6;
        }
      }
      *v12 = 2;
      goto LABEL_20;
    }
    v6 = (unsigned int)(v19 - 3);
    if ( (_DWORD)v19 != 3 )
    {
      if ( (_DWORD)v19 == 4 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            1,
            30,
            22,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dD(
              WPP_GLOBAL_Control->DeviceExtension,
              v6,
              30,
              23,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              250,
              v50);
        }
        if ( v50 == 0xFA )
        {
          *v12 = 0;
          *(_BYTE *)(v3 + 931) = 0;
          goto LABEL_20;
        }
        if ( v50 == 0xFE )
        {
          LOBYTE(v6) = -12;
          goto LABEL_21;
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            (unsigned int)&WPP_RECORDER_INITIALIZED,
            31,
            51,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            v19);
LABEL_109:
        v31 = (struct _KDPC *)(v3 + 232);
        v32 = 0;
        v33 = -1073414094;
LABEL_110:
        KeInsertQueueDpc(v31, v32, (PVOID)v33);
      }
      goto LABEL_20;
    }
    v6 = (__int64)&WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        30,
        21,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) == 0 )
    {
      v42 = (char)v50;
      if ( v50 )
      {
        *(_WORD *)(v3 + 980) |= 0x400u;
        *(_WORD *)(v3 + 982) = -120 * v42;
      }
      goto LABEL_164;
    }
    v38 = v50;
    LOBYTE(v39) = v50 & 0xF;
    if ( (v50 & 0xF) != 0 )
    {
      if ( (v50 & 8) != 0 )
        v39 = (char)(v50 | 0xF0);
      else
        v39 = (unsigned __int8)v39;
      *(_WORD *)(v3 + 982) = -120 * v39;
      *(_WORD *)(v3 + 980) |= 0x400u;
      v38 = v50;
    }
    v40 = *(_BYTE *)(v3 + 1101);
    if ( (v40 & 0x10) != 0 )
    {
      if ( (v38 & 0x10) != 0 )
        goto LABEL_157;
      *(_WORD *)(v3 + 980) |= 0x80u;
    }
    else
    {
      if ( (v38 & 0x10) == 0 )
        goto LABEL_157;
      *(_WORD *)(v3 + 980) |= 0x40u;
    }
    v38 = v50;
LABEL_157:
    if ( (v40 & 0x20) != 0 )
    {
      if ( (v38 & 0x20) == 0 )
      {
        v41 = 512;
        goto LABEL_162;
      }
    }
    else if ( (v38 & 0x20) != 0 )
    {
      v41 = 256;
LABEL_162:
      *(_WORD *)(v3 + 980) |= v41;
      v38 = v50;
    }
    *(_BYTE *)(v3 + 1101) = v38 & 0x30 | v40 & 7;
LABEL_164:
    I8xQueueCurrentMouseInput(ServiceContext, v6, v7, v8);
    *v12 = 0;
    goto LABEL_20;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      30,
      24,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      5,
      *v9);
LABEL_41:
  v22 = 0x140000000uLL;
  while ( 2 )
  {
    v6 = *v9;
    v21 = 0;
    v20 = 1;
    switch ( (_DWORD)v6 )
    {
      case 4:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            30,
            36,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 != 0xFA )
        {
LABEL_75:
          if ( v50 == 0xFE )
          {
            LOBYTE(v6) = -24;
            goto LABEL_21;
          }
          goto LABEL_104;
        }
        v52 = *(unsigned __int8 *)(v3 + 1105);
        *v9 = 5;
LABEL_20:
        LOBYTE(v6) = 0;
        goto LABEL_21;
      case 0xA:
LABEL_88:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            31,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          v19 = (unsigned int)*v9;
          v47 = 11;
          if ( (_DWORD)v19 != 10 )
            v47 = v19 + 1;
          *v9 = v47;
          v6 = 230;
          v48 = 233;
          if ( (_DWORD)v19 != 10 )
            v48 = 230;
          v52 = v48;
          goto LABEL_20;
        }
        if ( v50 != 0xFE )
        {
LABEL_92:
          v28 = -1073414110;
          goto LABEL_93;
        }
        LOBYTE(v6) = -26;
LABEL_21:
        if ( *v12 != 5 )
          goto LABEL_22;
        if ( v20 )
        {
          if ( v50 != 0xFA )
          {
            if ( v50 != 0xFE )
            {
LABEL_57:
              *(_WORD *)(v3 + 560) = 0;
LABEL_22:
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v6,
                  29,
                  52,
                  (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
              return 1;
            }
            v19 = *(unsigned __int16 *)(v3 + 560);
            *(_WORD *)(v3 + 560) = v19 + 1;
            if ( (__int16)v19 >= 4 )
            {
              *(_WORD *)(v3 + 560) = 0;
              goto LABEL_36;
            }
            LOBYTE(v52) = v6;
          }
          LOBYTE(v6) = -44;
          LOBYTE(v19) = 1;
          I8xPutByteAsynchronous(v19, v6);
          v30 = (unsigned __int8)v52;
        }
        else
        {
          if ( !v21 )
            goto LABEL_56;
          LOBYTE(v6) = -44;
          LOBYTE(v19) = 1;
          I8xPutByteAsynchronous(v19, v6);
          v30 = v21;
        }
        I8xPutByteAsynchronous(0, v30);
LABEL_56:
        if ( v50 == 0xFE )
          goto LABEL_22;
        goto LABEL_57;
      case 0xD:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            13,
            29,
            34,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            0,
            v50);
        *v9 = 14;
        v20 = 0;
        v19 = v50;
        if ( (unsigned __int8)(v50 - 2) > 1u )
          v29 = 2;
        else
          v29 = v50;
        *(_WORD *)(v3 + 586) = v29;
        goto LABEL_20;
      case 0x10:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            16,
            30,
            38,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          v19 = *(unsigned __int8 *)(v3 + 1100);
          v52 = *(unsigned __int8 *)(v19 + *(_QWORD *)(v3 + 1088));
          *v9 = 17;
          goto LABEL_20;
        }
        if ( v50 != 0xFE )
          goto LABEL_340;
        LOBYTE(v6) = -13;
        goto LABEL_21;
    }
    if ( (int)v6 > 1002 )
    {
      switch ( (int)v6 )
      {
        case 1003:
        case 1211:
          v20 = 0;
          *v9 = 27;
          v21 = -14;
          goto LABEL_20;
        case 1004:
          v20 = 0;
          *v9 = 34;
          v21 = -14;
          goto LABEL_20;
        case 1101:
          return 1;
        case 1200:
        case 1201:
        case 1202:
        case 1203:
        case 1204:
        case 1205:
        case 1206:
        case 1207:
        case 1208:
        case 1209:
        case 1210:
          v20 = 0;
          *v9 = v6 + 1;
          goto LABEL_20;
        default:
          goto LABEL_336;
      }
    }
    if ( (_DWORD)v6 == 1002 )
    {
      *v9 = 18;
      qword_140013158 = v3 + 1048;
      *(_OWORD *)(v3 + 1048) = 0;
      v20 = 0;
      goto LABEL_20;
    }
    v44 = v50;
    switch ( (int)v6 )
    {
      case 0:
        if ( v50 == 0xFA )
        {
          v20 = 0;
          goto LABEL_20;
        }
        if ( v50 == 0xFE )
        {
          v19 = *(unsigned __int16 *)(v3 + 560);
          v20 = 0;
          *(_WORD *)(v3 + 560) = v19 + 1;
          if ( (__int16)v19 < 10 && !*(_DWORD *)(v3 + 928) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v6,
                30,
                26,
                (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
            KeStallExecutionProcessor(*(_DWORD *)(v3 + 1096));
            v21 = -1;
          }
          goto LABEL_20;
        }
        if ( v50 != 0xAA )
          goto LABEL_20;
        if ( *(_BYTE *)(v3 + 1012) < 3u )
        {
          *v9 = 1;
          goto LABEL_20;
        }
        goto LABEL_36;
      case 1:
        *v9 = 2;
        if ( v50 == 3 )
        {
          v20 = 0;
          v21 = -14;
        }
        else
        {
          *v9 = 0;
        }
        goto LABEL_20;
      case 2:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            27,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          *v9 = 3;
          v20 = 0;
          goto LABEL_20;
        }
        if ( v50 != 0xFE )
          goto LABEL_36;
        LOBYTE(v6) = -14;
        goto LABEL_21;
      case 3:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            28,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            v50);
        v20 = 0;
        v19 = 4;
        v21 = -24;
        if ( !*(_BYTE *)(v3 + 1107) )
          v19 = 6;
        *v9 = v19;
        goto LABEL_20;
      case 5:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            37,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
          v22 = 0x140000000uLL;
        }
        if ( v50 == 0xFA )
        {
          v45 = *(_BYTE *)(v3 + 1106);
          if ( v45 == 2 )
          {
            *v9 = 25;
          }
          else
          {
            if ( v45 != 1 )
            {
              LOBYTE(v52) = -14;
              v19 = 27;
              LOBYTE(v6) = 0;
LABEL_213:
              *v9 = v19;
              goto LABEL_21;
            }
            *v9 = 15;
          }
          continue;
        }
        if ( v50 == 0xFE )
        {
          LOBYTE(v6) = -24;
          v19 = 4;
          goto LABEL_213;
        }
LABEL_104:
        KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050017LL);
LABEL_36:
        if ( *(_BYTE *)(v3 + 1106) == 1 )
          *(_BYTE *)(v3 + 1106) = 2;
LABEL_38:
        *v9 = 1100;
        KeInsertQueueDpc((PRKDPC)(v3 + 736), 0, 0);
        return v14;
      case 6:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            29,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          *v9 = 7;
        }
        else
        {
          if ( v50 == 0xFE )
          {
            LOBYTE(v6) = -24;
            goto LABEL_263;
          }
          KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050017LL);
          v20 = 0;
          *v9 = 27;
          v21 = -14;
        }
        LOBYTE(v6) = 0;
LABEL_263:
        LOBYTE(v52) = 0;
        goto LABEL_21;
      case 7:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            30,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          LOBYTE(v52) = -26;
          *v9 = 8;
        }
        else if ( v50 != 0xFE )
        {
          KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050016LL);
          v20 = 0;
          *v9 = 27;
          v21 = -14;
        }
        LOBYTE(v6) = 0;
        goto LABEL_21;
      case 8:
      case 9:
        goto LABEL_88;
      case 11:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            32,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          *v9 = 12;
          v20 = 0;
          goto LABEL_20;
        }
        if ( v50 != 0xFE )
          goto LABEL_92;
        LOBYTE(v6) = -23;
        goto LABEL_21;
      case 12:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            29,
            33,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            0,
            v50);
        v20 = 0;
        *v9 = 13;
        goto LABEL_20;
      case 14:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            29,
            35,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            0,
            v50);
        v20 = 0;
        *v9 = 4;
        v21 = -24;
        goto LABEL_20;
      case 15:
        LOBYTE(v52) = -13;
        *(_QWORD *)(v3 + 1088) = qword_1400109C0;
        *v9 = 16;
        *(_BYTE *)(v3 + 1100) = 0;
        *(_WORD *)(v3 + 1102) = 1002;
        goto LABEL_20;
      case 17:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            39,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              *(unsigned __int8 *)(*(unsigned __int8 *)(v3 + 1100) + *(_QWORD *)(v3 + 1088)),
              30,
              40,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              *(_BYTE *)(*(unsigned __int8 *)(v3 + 1100) + *(_QWORD *)(v3 + 1088)));
          v22 = 0x140000000uLL;
        }
        if ( v50 != 0xFA )
        {
          if ( v50 == 0xFE )
          {
            v19 = *(unsigned __int8 *)(v3 + 1100);
            v6 = *(unsigned __int8 *)(v19 + *(_QWORD *)(v3 + 1088));
            goto LABEL_21;
          }
LABEL_340:
          v28 = -1073414122;
LABEL_93:
          KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)v28);
          v20 = 0;
          *v9 = 27;
          v21 = -14;
          goto LABEL_20;
        }
        v19 = (unsigned __int8)++*(_BYTE *)(v3 + 1100);
        if ( *(_BYTE *)(v19 + *(_QWORD *)(v3 + 1088)) )
        {
          LOBYTE(v52) = -13;
          *v9 = 16;
          goto LABEL_20;
        }
        *v9 = *(unsigned __int16 *)(v3 + 1102);
        continue;
      case 18:
      case 20:
      case 21:
      case 22:
      case 23:
      case 24:
        goto LABEL_202;
      case 19:
        if ( *(_WORD *)(v3 + 1048) == 80 && v50 == 0x99 )
        {
          *v9 = 1200;
          v20 = 0;
          goto LABEL_20;
        }
LABEL_202:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            29,
            41,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            v6 - 17,
            v50);
          v44 = v50;
        }
        if ( v44 >= 0x36u )
          *(_WORD *)qword_140013158 = 63;
        else
          *(_WORD *)qword_140013158 = *((unsigned __int8 *)qword_140010988 + v44);
        qword_140013158 += 2;
        v20 = 0;
        if ( *v9 != 24 )
        {
          v19 = (unsigned int)(*v9 + 1);
          goto LABEL_219;
        }
        if ( !(unsigned __int8)I8xVerifyMousePnPID(v3, v3 + 1048) )
        {
          v21 = -14;
          v19 = 27;
LABEL_219:
          *v9 = v19;
          goto LABEL_20;
        }
        *v9 = 25;
        goto LABEL_41;
      case 25:
        v20 = 0;
        *v9 = 16;
        *(_BYTE *)(v3 + 1100) = 0;
        *(_QWORD *)(v3 + 1088) = &qword_140010980;
        v21 = -13;
        *(_WORD *)(v3 + 1102) = 1004;
        goto LABEL_20;
      case 26:
        v20 = 0;
        *v9 = 16;
        *(_BYTE *)(v3 + 1100) = 0;
        *(_QWORD *)(v3 + 1088) = &dword_14001097C;
        v21 = -13;
        *(_WORD *)(v3 + 1102) = 1003;
        goto LABEL_20;
      case 27:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            42,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 != 0xFA )
          goto LABEL_226;
        *v9 = 28;
        v20 = 0;
        goto LABEL_20;
      case 28:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            29,
            43,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            v50);
        **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFEFF7;
        v19 = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels | 2u;
        **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = v19;
        v6 = v50;
        if ( v50 )
        {
          v6 = (unsigned int)v50 - 3;
          if ( v50 == 3 )
          {
            v19 = (unsigned int)v19 | 8;
            **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = v19;
            *(_DWORD *)(v3 + 584) = 196640;
          }
          else
          {
            if ( v50 != 4 )
            {
              KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFF80050012LL);
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (unsigned int)&WPP_RECORDER_INITIALIZED,
                  30,
                  44,
                  (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
              **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFDF5;
              *(_DWORD *)(v3 + 584) = 0;
              goto LABEL_36;
            }
            v19 = (unsigned int)v19 | 0x1008;
            **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = v19;
            *(_DWORD *)(v3 + 584) = 327712;
          }
        }
        else
        {
          v46 = *(unsigned __int8 *)(v3 + 1107);
          *(_WORD *)(v3 + 584) = 2;
          if ( (_BYTE)v46 )
            *(_WORD *)(v3 + 586) = v46;
        }
        v20 = 0;
        *v9 = 29;
        v21 = -13;
        goto LABEL_20;
      case 29:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            45,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          v52 = *(unsigned __int8 *)(v3 + 588);
          *v9 = 30;
          goto LABEL_20;
        }
        if ( v50 != 0xFE )
          goto LABEL_306;
        LOBYTE(v6) = -13;
        goto LABEL_21;
      case 30:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            46,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          LOBYTE(v52) = -24;
          v19 = 32;
          LOBYTE(v6) = 0;
        }
        else
        {
          if ( v50 != 0xFE )
          {
LABEL_306:
            KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050016LL);
            goto LABEL_36;
          }
          LOBYTE(v6) = -13;
          v19 = 29;
        }
        *v9 = v19;
        goto LABEL_21;
      case 31:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            49,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          *(_WORD *)(v3 + 978) |= 4u;
          *v12 = 0;
          *(_WORD *)(v3 + 560) = 0;
          *(_WORD *)(v3 + 1012) = -1;
          I8xQueueCurrentMouseInput(ServiceContext, v6, &WPP_RECORDER_INITIALIZED, v22);
          v32 = *(void **)(v3 + 600);
          v31 = (struct _KDPC *)(ServiceContext + 200);
          v33 = 3;
          goto LABEL_110;
        }
        if ( v50 == 0xFE )
        {
          LOBYTE(v6) = -12;
          goto LABEL_21;
        }
        KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050029LL);
        goto LABEL_36;
      case 32:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            47,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 != 0xFA )
          goto LABEL_75;
        v52 = *(unsigned __int8 *)(v3 + 1105);
        *v9 = 33;
        goto LABEL_20;
      case 33:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            48,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          LOBYTE(v52) = -12;
          v19 = 31;
          LOBYTE(v6) = 0;
        }
        else
        {
          if ( v50 != 0xFE )
            goto LABEL_104;
          LOBYTE(v6) = -24;
          v19 = 32;
        }
        *v9 = v19;
        goto LABEL_21;
      case 34:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            30,
            25,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            250,
            v50);
        if ( v50 == 0xFA )
        {
          v20 = 0;
          *v9 = 35;
          goto LABEL_20;
        }
LABEL_226:
        if ( v50 == 0xFE )
        {
          LOBYTE(v6) = -14;
          goto LABEL_21;
        }
        KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC0050028LL);
        goto LABEL_36;
      case 35:
        *v9 = 26;
        continue;
      default:
LABEL_336:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            31,
            50,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            v6);
        goto LABEL_109;
    }
  }
}

```

## disassembly

```asm
0x140002610  push    rbp
0x140002612  push    rbx
0x140002613  push    rsi
0x140002614  push    rdi
0x140002615  push    r15
0x140002617  mov     rbp, rsp
0x14000261a  sub     rsp, 60h
0x14000261e  mov     rdi, rdx
0x140002621  mov     [rbp+arg_8], 0
0x140002625  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000262c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002633  lea     r15, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000263a  jnz     loc_1400027FA
0x140002640  mov     rbx, [rdi+40h]
0x140002644  mov     [rsp+60h+arg_0], r12
0x14000264c  mov     [rsp+60h+var_8], r13
0x140002651  mov     [rsp+60h+var_10], r14
0x140002656  cmp     dword ptr [rbx+50h], 1
0x14000265a  jnz     loc_140002DED
0x140002660  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140002667  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000266e  mov     rcx, [rcx+0D8h]
0x140002675  call    _guard_dispatch_icall
0x14000267a  movzx   edx, al
0x14000267d  movzx   r14d, al
0x140002681  and     dl, 21h
0x140002684  cmp     dl, 21h ; '!'
0x140002687  jnz     loc_140002D8A
0x14000268d  lea     rdx, [rbp+arg_8]
0x140002691  mov     cl, 2
0x140002693  call    I8xGetByteAsynchronous
0x140002698  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000269f  jnz     loc_140002B2D
0x1400026a5  mov     r15, 0FFFFF78000000320h
0x1400026af  lea     rsi, [rbx+3ECh]
0x1400026b6  mov     r15, [r15]
0x1400026b9  cmp     dword ptr [rsi], 44Ch
0x1400026bf  jz      loc_1400027F3; jumptable 0000000140002CFE case 1101
0x1400026c5  movzx   ecx, [rbp+arg_8]
0x1400026c9  lea     r12, [rbx+3E8h]
0x1400026d0  cmp     dword ptr [r12], 5
0x1400026d5  jz      loc_140002D73
0x1400026db  mov     rax, [rbx+428h]
0x1400026e2  mov     r13b, 1
0x1400026e5  test    rax, rax
0x1400026e8  jz      loc_140002820
0x1400026ee  mov     [rsp+60h+var_28], rsi
0x1400026f3  lea     rcx, [rbp+arg_10]
0x1400026f7  mov     [rsp+60h+var_30], r12
0x1400026fc  lea     r8, [rbx+200h]
0x140002703  mov     [rsp+60h+var_38], rcx
0x140002708  lea     rdx, [rbx+3D0h]
0x14000270f  lea     rcx, [rbp+arg_8]
0x140002713  mov     [rbp+arg_10], 0
0x140002717  mov     [rsp+60h+var_40], rcx
0x14000271c  movzx   r9d, r14b
0x140002720  mov     rcx, [rbx+430h]
0x140002727  call    _guard_dispatch_icall
0x14000272c  cmp     [rbp+arg_10], 0
0x140002730  movzx   r13d, al
0x140002734  jnz     loc_140002DF4
0x14000273a  jmp     loc_14000415B
0x140002740  lea     r8, WPP_RECORDER_INITIALIZED
0x140002747  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14000274e  jz      short loc_14000277F
0x140002750  mov     rcx, cs:WPP_GLOBAL_Control
0x140002757  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000275e  mov     r9d, 14h
0x140002764  mov     [rsp+60h+var_40], rax
0x140002769  mov     r8d, 1Eh
0x14000276f  mov     rcx, [rcx+40h]
0x140002773  call    WPP_RECORDER_SF_
0x140002778  lea     r8, WPP_RECORDER_INITIALIZED
0x14000277f  movzx   ecx, byte ptr [rbx+3F6h]
0x140002786  test    cl, cl
0x140002788  js      loc_1400040AC
0x14000278e  movzx   eax, [rbp+arg_8]
0x140002792  mov     [rbx+3E0h], eax
0x140002798  test    cl, 20h
0x14000279b  jz      short loc_1400027A8
0x14000279d  or      eax, 0FFFFFF00h
0x1400027a2  mov     [rbx+3E0h], eax
0x1400027a8  neg     eax
0x1400027aa  mov     [rbx+3E0h], eax
0x1400027b0  movzx   eax, byte ptr [rbx+3F6h]
0x1400027b7  mov     [rbx+3F7h], al
0x1400027bd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400027c4  mov     ecx, [rax]
0x1400027c6  test    cl, 8
0x1400027c9  jz      loc_1400031A6
0x1400027cf  mov     dword ptr [r12], 3
0x1400027d7  xor     edi, edi
0x1400027d9  xor     dl, dl
0x1400027db  cmp     dword ptr [r12], 5
0x1400027e0  jz      loc_1400029D6
0x1400027e6  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400027ed  jnz     loc_140004122
0x1400027f3  mov     al, 1; jumptable 0000000140002CFE case 1101
0x1400027f5  jmp     loc_14000415B
0x1400027fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002801  mov     r9d, 0Ah
0x140002807  mov     r8d, 1Dh
0x14000280d  mov     [rsp+60h+var_40], r15
0x140002812  mov     rcx, [rcx+40h]
0x140002816  call    WPP_RECORDER_SF_
0x14000281b  jmp     loc_140002640
0x140002820  cmp     byte ptr [rbx+450h], 0AAh
0x140002827  jz      loc_140002DFD
0x14000282d  cmp     dword ptr [r12], 0
0x140002832  jz      loc_140002A4C
0x140002838  mov     [rbx+450h], cl
0x14000283e  mov     ecx, [r12]
0x140002842  test    ecx, 0FFFFFFFAh
0x140002848  jnz     loc_140002973
0x14000284e  cmp     ecx, 1
0x140002851  jz      loc_140002973
0x140002857  mov     [rbx+3F8h], r15
0x14000285e  xor     r14b, r14b
0x140002861  xor     r15d, r15d
0x140002864  mov     byte ptr [rbp+arg_18], 0
0x140002868  cmp     ecx, 2
0x14000286b  jz      loc_140002740
0x140002871  cmp     ecx, 5
0x140002874  jz      short loc_1400028E8
0x140002876  mov     edx, ecx
0x140002878  test    ecx, ecx
0x14000287a  jnz     loc_140002A01
0x140002880  lea     rdx, WPP_RECORDER_INITIALIZED
0x140002887  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000288e  jnz     loc_140002C7E
0x140002894  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000289b  mov     ecx, [rax]
0x14000289d  test    cl, 8
0x1400028a0  jz      loc_140002B5B
0x1400028a6  movzx   eax, [rbp+arg_8]
0x1400028aa  and     al, 0C8h
0x1400028ac  cmp     al, 8
0x1400028ae  jz      loc_140002B5B
0x1400028b4  cmp     byte ptr [rbx+452h], 1
0x1400028bb  jz      loc_14000414F
0x1400028c1  lea     rcx, [rbx+2E0h]; Dpc
0x1400028c8  mov     dword ptr [rsi], 44Ch
0x1400028ce  xor     r8d, r8d; SystemArgument2
0x1400028d1  xor     edx, edx; SystemArgument1
0x1400028d3  call    cs:__imp_KeInsertQueueDpc
0x1400028da  nop     dword ptr [rax+rax+00h]
0x1400028df  movzx   eax, r13b
0x1400028e3  jmp     loc_14000415B
0x1400028e8  lea     r8, WPP_RECORDER_INITIALIZED
0x1400028ef  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400028f6  jnz     loc_1400032B8
0x1400028fc  mov     r11d, 3Fh ; '?'
0x140002902  lea     r9, cs:140000000h
0x140002909  mov     r10d, 3EAh
0x14000290f  movsxd  rdx, dword ptr [rsi]
0x140002912  xor     r15b, r15b
0x140002915  mov     r14b, 1
0x140002918  cmp     edx, 4
0x14000291b  jz      loc_140002AC8
0x140002921  cmp     edx, 0Ah
0x140002924  jz      loc_140002BF3; jumptable 000000014000331B cases 8,9
0x14000292a  cmp     edx, 0Dh
0x14000292d  jz      loc_140002C48
0x140002933  cmp     edx, 10h
0x140002936  jnz     loc_140002CCE
0x14000293c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140002943  jnz     loc_140003F7B
0x140002949  cmp     [rbp+arg_8], 0FAh
0x14000294d  jnz     loc_140003FBF
0x140002953  mov     rax, [rbx+440h]
0x14000295a  movzx   ecx, byte ptr [rbx+44Ch]
0x140002961  movzx   eax, byte ptr [rcx+rax]
0x140002965  mov     [rbp+arg_18], eax
0x140002968  mov     dword ptr [rsi], 11h
0x14000296e  jmp     loc_1400027D7
0x140002973  mov     rax, r15
0x140002976  sub     rax, [rbx+3F8h]
0x14000297d  cmp     eax, [rbx+400h]
0x140002983  jnb     short loc_140002991
0x140002985  shr     rax, 20h
0x140002989  test    eax, eax
0x14000298b  jz      loc_140002857
0x140002991  lea     rdx, WPP_RECORDER_INITIALIZED
0x140002998  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000299f  jz      loc_1400028B4
0x1400029a5  mov     dword ptr [rsp+60h+var_38], ecx
0x1400029a9  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x1400029b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029b7  mov     r9d, 11h
0x1400029bd  mov     r8d, 1Eh
0x1400029c3  mov     [rsp+60h+var_40], rax
0x1400029c8  mov     rcx, [rcx+40h]
0x1400029cc  call    WPP_RECORDER_SF_d
0x1400029d1  jmp     loc_1400028B4
0x1400029d6  test    r14b, r14b
0x1400029d9  jnz     loc_140002CAB
0x1400029df  test    r15b, r15b
0x1400029e2  jnz     loc_140004110
0x1400029e8  cmp     [rbp+arg_8], 0FEh
0x1400029ec  jz      short loc_1400029F5
0x1400029ee  mov     [rbx+230h], di
0x1400029f5  lea     r8, WPP_RECORDER_INITIALIZED
0x1400029fc  jmp     loc_1400027E6
0x140002a01  sub     edx, 1
0x140002a04  jnz     loc_140002D25
0x140002a0a  lea     r8, WPP_RECORDER_INITIALIZED
0x140002a11  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140002a18  jnz     loc_1400031DF
0x140002a1e  movzx   eax, byte ptr [rbx+3F6h]
0x140002a25  test    al, 40h
0x140002a27  jnz     loc_140003213
0x140002a2d  movzx   edx, [rbp+arg_8]
0x140002a31  mov     [rbx+3DCh], edx
0x140002a37  test    al, 10h
0x140002a39  jnz     loc_140003248
0x140002a3f  mov     dword ptr [r12], 2
0x140002a47  jmp     loc_1400027D7
0x140002a4c  cmp     dword ptr [rbx+210h], 0
0x140002a53  jz      loc_140002838
0x140002a59  cmp     qword ptr [rdi+20h], 0
0x140002a5e  jz      loc_140002838
0x140002a64  cmp     cl, 0FEh
0x140002a67  jnz     loc_140002EF3
0x140002a6d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140002a74  cmp     dword ptr [rax+0CCh], 0
0x140002a7b  jz      loc_140002DED
0x140002a81  mov     dword ptr [rax+0CCh], 0FFFFFFFFh
0x140002a8b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140002a92  movsx   edx, word ptr [rbx+230h]
0x140002a99  movzx   ecx, word ptr [rax+46h]
0x140002a9d  mov     eax, edx
0x140002a9f  cmp     edx, ecx
0x140002aa1  jge     loc_140002EC8
0x140002aa7  dec     dword ptr [rbx+208h]
0x140002aad  inc     dx
0x140002ab0  mov     rcx, rdi
0x140002ab3  mov     [rbx+230h], dx
0x140002aba  call    I8xInitiateIo
0x140002abf  movzx   ecx, [rbp+arg_8]
0x140002ac3  jmp     loc_140002838
0x140002ac8  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140002acf  jz      short loc_140002B10
0x140002ad1  movzx   eax, [rbp+arg_8]
0x140002ad5  mov     r9d, 24h ; '$'
0x140002adb  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ae2  mov     r8d, 1Eh
0x140002ae8  mov     dword ptr [rsp+60h+var_30], eax
0x140002aec  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x140002af3  mov     dword ptr [rsp+60h+var_38], 0FAh
0x140002afb  mov     [rsp+60h+var_40], rax
0x140002b00  mov     rcx, [rcx+40h]
0x140002b04  call    WPP_RECORDER_SF_dD
0x140002b09  lea     r8, WPP_RECORDER_INITIALIZED
0x140002b10  cmp     [rbp+arg_8], 0FAh
0x140002b14  jz      loc_140004097
0x140002b1a  cmp     [rbp+arg_8], 0FEh
0x140002b1e  jnz     loc_140002D04
0x140002b24  mov     dl, 0E8h
0x140002b26  xor     edi, edi
0x140002b28  jmp     loc_1400027DB
0x140002b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b34  mov     r9d, 0Ch
0x140002b3a  movzx   eax, [rbp+arg_8]
0x140002b3e  mov     r8d, 1Eh
0x140002b44  mov     dword ptr [rsp+60h+var_38], eax
0x140002b48  mov     [rsp+60h+var_40], r15
0x140002b4d  mov     rcx, [rcx+40h]
0x140002b51  call    WPP_RECORDER_SF_D
0x140002b56  jmp     loc_1400026A5
0x140002b5b  movzx   ecx, byte ptr [rbx+44Dh]
0x140002b62  mov     r9d, 1
0x140002b68  movzx   eax, cl
0x140002b6b  mov     [rbx+3D4h], r15d
0x140002b72  mov     [rbx+3D2h], r15w
0x140002b7a  movzx   r8d, [rbp+arg_8]
0x140002b7f  and     al, r9b
0x140002b82  jz      loc_140003259
0x140002b88  mov     edx, r15d
0x140002b8b  test    al, al
0x140002b8d  jnz     loc_140003270
0x140002b93  test    cl, 2
0x140002b96  jz      loc_140003292
0x140002b9c  test    r8b, 2
0x140002ba0  jnz     short loc_140002BB2
0x140002ba2  or      dx, 8
0x140002ba6  mov     [rbx+3D4h], dx
0x140002bad  movzx   r8d, [rbp+arg_8]
0x140002bb2  test    cl, 4
0x140002bb5  jz      loc_1400032A5
0x140002bbb  test    r8b, 4
0x140002bbf  jnz     short loc_140002BD1
0x140002bc1  or      dx, 20h
0x140002bc5  mov     [rbx+3D4h], dx
0x140002bcc  movzx   r8d, [rbp+arg_8]
0x140002bd1  and     cl, 30h
0x140002bd4  and     r8b, 7
0x140002bd8  or      cl, r8b
0x140002bdb  mov     [rbx+44Dh], cl
0x140002be1  movzx   eax, [rbp+arg_8]
0x140002be5  and     al, 0F0h
  ... truncated ...
```
