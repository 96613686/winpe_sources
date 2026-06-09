# ClasspPowerUpCompletion

- ea: `0x140011ba0`
- end: `0x1400129fa`
- name: `ClasspPowerUpCompletion`
- size: `3674`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x1400073d4`
- `0x140008360`
- `0x14000f3e0`
- `0x140011ba0`
- `0x140012e18`
- `0x1400134a0`
- `0x140018424`
- `0x14001fc38`
- `0x14002001c`
- `0x140027870`
- `0x140027a24`
- `0x1400291d0`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140011d6f`
- `ntoskrnl!IofCallDriver` at `0x1400120e7`
- `ntoskrnl!IofCallDriver` at `0x140011d6f`
- `ntoskrnl!IofCallDriver` at `0x1400120e7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001243f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140040068`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400401ab`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001243f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140040068`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400401ab`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140012341`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140012341`
- `ntoskrnl!PoCallDriver` at `0x1400121cb`
- `ntoskrnl!PoCallDriver` at `0x140040146`
- `ntoskrnl!PoCallDriver` at `0x1400121cb`
- `ntoskrnl!PoCallDriver` at `0x140040146`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140011e15`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140040010`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140011e15`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140040010`
- `ntoskrnl!PoSetPowerState` at `0x14001230b`
- `ntoskrnl!PoSetPowerState` at `0x14001230b`

## pseudocode

```c
__int64 __fastcall ClasspPowerUpCompletion(__int64 a1, IRP *a2, _DWORD *a3)
{
  unsigned int v3; // r12d
  __int64 v6; // r9
  __int64 v7; // rsi
  IRP *v8; // r14
  __int64 v9; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v11; // rdi
  int v12; // r8d
  __int64 v13; // r13
  ULONG v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rax
  NTSTATUS v17; // r8d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int Status; // eax
  struct _DEVICE_OBJECT *v21; // rcx
  ULONG v22; // ecx
  unsigned int v23; // r8d
  __int64 v24; // r9
  __int64 v25; // rax
  __int16 v27; // ax
  PFUNCTIONAL_DEVICE_EXTENSION *v28; // r8
  __int64 v29; // rcx
  unsigned int v30; // edx
  unsigned int v31; // r10d
  _SENSE_DATA *SenseData; // r11
  __int64 v33; // rcx
  unsigned __int64 v34; // r9
  __int64 v35; // r14
  int v36; // ecx
  UCHAR v37; // r9
  unsigned int v38; // r11d
  unsigned int v39; // r8d
  __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  __int64 v42; // r10
  int v43; // ecx
  char v44; // cl
  unsigned int v45; // r11d
  unsigned int v46; // r8d
  __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  __int64 v49; // r10
  __int64 v50; // r9
  int v51; // ecx
  unsigned __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  _IO_STACK_LOCATION *v56; // rax
  _IO_STACK_LOCATION *v57; // rax
  IRP *v58; // r9
  _DWORD *v59; // rax
  __int64 v60; // rax
  char v61; // al
  int v62; // eax
  __int64 v63; // r9
  int v64; // ecx
  __int64 v65; // rax
  __int64 v66; // rax
  unsigned int v67; // r10d
  unsigned int i; // r8d
  __int64 v69; // rcx
  unsigned __int64 v70; // rdx
  int v71; // r11d
  int v72; // ecx
  int v73; // ecx
  int v74; // r11d
  int v75; // ecx
  int v76; // r14d
  ULONG v77; // eax
  _IO_STACK_LOCATION *v78; // rax
  ULONG SecondsRemaining; // [rsp+48h] [rbp-19h] BYREF
  int v80; // [rsp+4Ch] [rbp-15h] BYREF
  _IO_STACK_LOCATION *v81; // [rsp+50h] [rbp-11h]
  __int64 v82; // [rsp+58h] [rbp-9h] BYREF
  __int64 v83; // [rsp+60h] [rbp-1h]
  __int128 v84; // [rsp+68h] [rbp+7h] BYREF

  v3 = -1073741802;
  v80 = -1073741802;
  v84 = 0;
  if ( a3 )
  {
    v6 = *((_QWORD *)a3 + 4);
    v7 = *(_QWORD *)(v6 + 64);
    v8 = (IRP *)*((_QWORD *)a3 + 5);
    v9 = *(_QWORD *)(v7 + 1144);
    CurrentStackLocation = v8->Tail.Overlay.CurrentStackLocation;
    v81 = CurrentStackLocation;
    v83 = *(_QWORD *)(*(_QWORD *)(v9 + 3904) + 184LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids);
    }
    v11 = (__int64)(a3 + 12);
    if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 && *((_WORD *)a3 + 24) != 88 )
      v11 = *(_QWORD *)(v7 + 1144) + 944LL;
    if ( a2 == v8 && a2->PendingReturned )
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( ++*a3 != 2 )
    {
      if ( *a3 == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
        }
        v56 = v8->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v56[-1].MajorFunction = *(_OWORD *)&v56->MajorFunction;
        *(_OWORD *)&v56[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v56->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v56[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v56->Parameters.SetQuota + 6);
        v56[-1].FileObject = v56->FileObject;
        v56[-1].Control = 0;
        if ( (a3[1] & 2) != 0 && a2->IoStatus.Status < 0 )
        {
          if ( ClassPnPETWEnabled )
          {
            IoGetActivityIdIrp(v8, &v84);
            ClasspWriteSrbErrorResultEvent((unsigned int)&v84, *(_QWORD *)(v7 + 8), a2->IoStatus.Status, v11, 0);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                12,
                WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                a2,
                a2->IoStatus.Status);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                13,
                WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                a2,
                *(unsigned __int8 *)(v11 + 3));
            }
          }
          v78 = v8->Tail.Overlay.CurrentStackLocation;
          v78[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspDeviceLockFailurePowerIrpCompletion;
          v78[-1].Context = a3;
          v78[-1].Control = -32;
          PoCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), v8);
          return v3;
        }
        *((_BYTE *)a3 + 9) = (a3[1] & 2) != 0;
        a2->IoStatus.Status = -1073741637;
        *a3 = 1;
        v57 = v8->Tail.Overlay.CurrentStackLocation;
        v57[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClasspPowerUpCompletion;
        v57[-1].Context = a3;
        v57[-1].Control = -32;
        v17 = PoCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), v8);
        v80 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v19 = 14;
          v58 = v8;
LABEL_229:
          WPP_SF_qD(v18->AttachedDevice, v19, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v58, v17);
        }
      }
      else
      {
        if ( *a3 == 3 )
        {
          v12 = *(unsigned __int8 *)(v11 + 3);
          LOWORD(v13) = 0;
          if ( (v12 & 0x3F) != 1 )
          {
            v82 = 0;
            SecondsRemaining = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqD(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                a2,
                v11,
                v12);
            }
            a3[5] = 0;
            LOBYTE(v6) = 15;
            v61 = InterpretSenseInfoWithoutHistory(
                    *(_QWORD *)(v7 + 8),
                    a2,
                    v11,
                    v6,
                    22,
                    *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) - a3[4],
                    &v80,
                    &v82);
            a3[5] = (v82 + 9999999) / 10000000;
            if ( v61 == 1 )
            {
              v75 = a3[4];
              a3[4] = v75 - 1;
              if ( v75 )
              {
                v76 = 240;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
                }
                --*a3;
                if ( PoQueryWatchdogTime(*(PDEVICE_OBJECT *)(v7 + 512), &SecondsRemaining) )
                {
                  v77 = SecondsRemaining;
                  if ( SecondsRemaining >= 5 )
                  {
                    v77 = SecondsRemaining - 5;
                    SecondsRemaining -= 5;
                  }
                  if ( v77 >= 0x3C )
                  {
                    if ( v77 < 0xF0 )
                      v76 = 60;
                  }
                  else
                  {
                    v76 = 30;
                  }
                }
                if ( *(_BYTE *)(v11 + 2) == 40 )
                  *(_DWORD *)(v11 + 40) = v76;
                else
                  *(_DWORD *)(v11 + 20) = v76;
                RetryPowerRequest(*(_QWORD *)(v7 + 8), a2, a3);
                return v3;
              }
            }
            if ( v80 < 0 && ClassPnPETWEnabled )
            {
              IoGetActivityIdIrp(v8, &v84);
              ClasspWriteSrbErrorResultEvent(
                (unsigned int)&v84,
                *(_QWORD *)(v7 + 8),
                a2->IoStatus.Status,
                v11,
                *(_BYTE *)(*(_QWORD *)(v7 + 1144) + 3896LL) - *((_BYTE *)a3 + 16));
            }
            *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) = 4;
            a3[4] = 4;
          }
          goto LABEL_9;
        }
        v14 = *a3 - 4;
        if ( *a3 == 4 )
          goto LABEL_89;
      }
      return v3;
    }
    Status = a2->IoStatus.Status;
    v13 = 0;
    if ( Status < 0 )
    {
      a3[3] = Status;
LABEL_9:
      v14 = (unsigned int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
      }
      if ( *((_BYTE *)a3 + 9) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
        }
        if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
        {
          v80 = InitializeStorageRequestBlock(v11);
          if ( v80 < 0 )
          {
            v11 = (__int64)(a3 + 12);
            memset((char *)a3 + 51, 0, 0x55u);
            *((_BYTE *)a3 + 50) = 25;
            LOWORD(v13) = 88;
          }
          else
          {
            *(_DWORD *)(v11 + 20) = 25;
          }
          *((_WORD *)a3 + 24) = v13;
        }
        else
        {
          memset((void *)(v11 + 3), 0, 0x55u);
          *(_WORD *)v11 = 88;
          *(_BYTE *)(v11 + 2) = 25;
        }
        if ( *(_BYTE *)(v11 + 2) == 40 )
        {
          *(_DWORD *)(v11 + 24) = 0x80000;
          *(_QWORD *)(v11 + 80) = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
        }
        else
        {
          *(_DWORD *)(v11 + 12) = 0x80000;
          *(_QWORD *)(v11 + 48) = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
        }
        v15 = v83;
        *(_QWORD *)(v83 - 64) = v11;
        *(_BYTE *)(v15 - 72) = 15;
        *a3 = 3;
        v16 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
        *(_QWORD *)(v16 - 16) = ClasspPowerUpCompletion;
        *(_QWORD *)(v16 - 8) = a3;
        *(_BYTE *)(v16 - 69) = -32;
        v17 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
        v80 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          return v3;
        }
        v19 = 21;
LABEL_228:
        v58 = *(IRP **)(*(_QWORD *)(v7 + 1144) + 3904LL);
        goto LABEL_229;
      }
      CurrentStackLocation = v81;
LABEL_89:
      LOBYTE(v14) = 0;
      SecondsRemaining = v14;
      if ( *((_BYTE *)a3 + 9) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v8);
          LOBYTE(v14) = SecondsRemaining;
        }
        v62 = a2->IoStatus.Status;
        if ( v62 >= 0 || v62 == -1073741738 || v62 == -1073741632 || !ClassPnPETWEnabled )
          goto LABEL_134;
        IoGetActivityIdIrp(v8, &v84);
        ClasspWriteSrbErrorResultEvent((unsigned int)&v84, *(_QWORD *)(v7 + 8), a2->IoStatus.Status, v11, 0);
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_91;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
LABEL_134:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v8);
            LOBYTE(v14) = SecondsRemaining;
          }
LABEL_91:
          v80 = a3[3];
          v8->IoStatus.Status = v80;
          if ( v80 >= 0 )
            *(_DWORD *)(v7 + 536) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          v59 = *(_DWORD **)(v7 + 824);
          if ( v59 && *v59 )
            LOBYTE(v14) = 1;
          if ( *(_QWORD *)(*(_QWORD *)(v7 + 32) + 400LL)
            || *(_QWORD *)(v7 + 648) && (v66 = *(_QWORD *)(v7 + 1152)) != 0 && !*(_BYTE *)(v66 + 37) )
          {
            if ( !(_BYTE)v14 )
            {
LABEL_141:
              ClasspEnableTimer(v7);
LABEL_99:
              PoSetPowerState(
                *((PDEVICE_OBJECT *)a3 + 4),
                CurrentStackLocation->Parameters.Power.Type,
                CurrentStackLocation->Parameters.Power.State);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v8);
              }
              ClassReleaseRemoveLock(*((PDEVICE_OBJECT *)a3 + 4), v8);
              *((_BYTE *)a3 + 8) = 0;
              PoStartNextPowerIrp(v8);
              v60 = *(_QWORD *)(v7 + 1144);
              if ( v60 && a2 == *(IRP **)(v60 + 3904) )
                ClassCompleteRequest(*(PDEVICE_OBJECT *)(v7 + 8), v8, 0);
              else
                return (unsigned int)v80;
              return v3;
            }
          }
          else if ( !(_BYTE)v14 )
          {
            goto LABEL_99;
          }
          v63 = *(_QWORD *)(v7 + 824);
          if ( (MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v63 + 48)) / 10000000LL >= *(unsigned int *)(v63 + 8) )
            *(_DWORD *)(v63 + 4) = 1;
          goto LABEL_141;
        }
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v8);
      }
      LOBYTE(v14) = SecondsRemaining;
      goto LABEL_134;
    }
    v21 = *(struct _DEVICE_OBJECT **)(v7 + 512);
    SecondsRemaining = 0;
    if ( PoQueryWatchdogTime(v21, &SecondsRemaining) )
    {
      v22 = SecondsRemaining;
      v23 = 240;
      LODWORD(v81) = 240;
      if ( SecondsRemaining < 0x258 )
      {
        if ( SecondsRemaining < 0xF0 )
        {
          v23 = 60;
          LODWORD(v81) = 60;
        }
      }
      else
      {
        v22 = 600;
        SecondsRemaining = 600;
      }
      v24 = *(_QWORD *)(v7 + 1144);
      if ( v22 < v23 + 5 )
      {
        *(_DWORD *)(v24 + 3896) = 0;
        LODWORD(v81) = 30;
      }
      else
      {
        *(_DWORD *)(v24 + 3896) = (v22 - 5) / v23;
        v25 = *(_QWORD *)(v7 + 1144);
        if ( (*(_DWORD *)(v25 + 3896))-- == 1 )
          LODWORD(v81) = SecondsRemaining - 5;
      }
    }
    else
    {
      v65 = *(_QWORD *)(v7 + 1144);
      LODWORD(v81) = 240;
      *(_DWORD *)(v65 + 3896) = 1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
    }
    a3[4] = *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL);
    if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
    {
      v80 = InitializeStorageRequestBlock(v11);
      if ( v80 < 0 )
      {
        v11 = (__int64)(a3 + 12);
        memset((char *)a3 + 51, 0, 0x55u);
        v27 = 88;
        *((_BYTE *)a3 + 50) = 0;
      }
      else
      {
        *(_DWORD *)(v11 + 20) = 0;
        v27 = 0;
      }
      *((_WORD *)a3 + 24) = v27;
    }
    else
    {
      memset((void *)(v11 + 3), 0, 0x55u);
      *(_WORD *)v11 = 88;
      *(_BYTE *)(v11 + 2) = 0;
    }
    v28 = (PFUNCTIONAL_DEVICE_EXTENSION *)(v7 + 24);
    v29 = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
    if ( *(_BYTE *)(v11 + 2) != 40 )
    {
      *(_QWORD *)(v11 + 48) = v29;
      *(_QWORD *)(v11 + 32) = (*v28)->SenseData;
      goto LABEL_46;
    }
    *(_QWORD *)(v11 + 80) = v29;
    if ( !*(_DWORD *)(v11 + 20) )
    {
      v30 = 0;
      v31 = *(_DWORD *)(v11 + 56);
      SenseData = (*v28)->SenseData;
      if ( v31 )
      {
        do
        {
          v33 = *(unsigned int *)(v11 + 4LL * v30 + 120);
          if ( (unsigned int)v33 >= 0x80 )
          {
            v34 = *(unsigned int *)(v11 + 16);
            if ( (unsigned int)v33 < (unsigned int)v34 )
            {
              v35 = (unsigned int)v33;
              v36 = *(_DWORD *)(v33 + v11);
              if ( v36 == 64 )
              {
                if ( v35 + 40 <= v34 )
                  goto LABEL_45;
              }
              else
              {
                v72 = v36 - 65;
                if ( v72 )
                {
                  if ( v72 == 1 && v35 + 40 <= v34 )
                  {
                    *(_QWORD *)(v35 + v11 + 24) = SenseData;
                    break;
                  }
                }
                else if ( v35 + 56 <= v34 )
                {
LABEL_45:
                  *(_QWORD *)(v35 + v11 + 16) = SenseData;
                  break;
                }
              }
            }
          }
          ++v30;
        }
        while ( v30 < v31 );
      }
    }
LABEL_46:
    v37 = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(*v28);
    if ( *(_BYTE *)(v11 + 2) == 40 )
    {
      if ( *(_DWORD *)(v11 + 20) )
        goto LABEL_55;
      v38 = *(_DWORD *)(v11 + 56);
      v39 = 0;
      if ( !v38 )
        goto LABEL_55;
      while ( 1 )
      {
        v40 = *(unsigned int *)(v11 + 4LL * v39 + 120);
        if ( (unsigned int)v40 >= 0x80 )
        {
          v41 = *(unsigned int *)(v11 + 16);
          if ( (unsigned int)v40 < (unsigned int)v41 )
          {
            v42 = (unsigned int)v40;
            v43 = *(_DWORD *)(v40 + v11);
            if ( v43 == 64 )
            {
              if ( v42 + 40 <= v41 )
                goto LABEL_53;
            }
            else
            {
              v73 = v43 - 65;
              if ( v73 )
              {
                if ( v73 == 1 && v42 + 40 <= v41 )
                {
LABEL_53:
                  *(_BYTE *)(v42 + v11 + 9) = v37;
                  goto LABEL_55;
                }
              }
              else if ( v42 + 56 <= v41 )
              {
                goto LABEL_53;
              }
            }
          }
        }
        if ( ++v39 >= v38 )
          goto LABEL_55;
      }
    }
    *(_BYTE *)(v11 + 11) = v37;
LABEL_55:
    v44 = *(_BYTE *)(v11 + 2);
    if ( v44 == 40 )
    {
      *(_DWORD *)(v11 + 40) = (_DWORD)v81;
      *(_DWORD *)(v11 + 24) = 296;
    }
    else
    {
      *(_DWORD *)(v11 + 20) = (_DWORD)v81;
      *(_DWORD *)(v11 + 12) = 296;
    }
    if ( (a3[1] & 2) != 0 )
    {
      if ( v44 != 40 )
      {
        *(_DWORD *)(v11 + 12) |= 0x80000u;
LABEL_61:
        *(_BYTE *)(v11 + 10) = 6;
        goto LABEL_62;
      }
      *(_DWORD *)(v11 + 24) |= 0x80000u;
    }
    else if ( v44 != 40 )
    {
      goto LABEL_61;
    }
    if ( !*(_DWORD *)(v11 + 20) )
    {
      v67 = *(_DWORD *)(v11 + 56);
      for ( i = 0; i < v67; ++i )
      {
        v69 = *(unsigned int *)(v11 + 4LL * i + 120);
        if ( (unsigned int)v69 >= 0x80 )
        {
          v70 = *(unsigned int *)(v11 + 16);
          if ( (unsigned int)v69 < (unsigned int)v70 )
          {
            v71 = *(_DWORD *)(v69 + v11);
            if ( v71 == 64 )
            {
              if ( v69 + 40 <= v70 )
                goto LABEL_165;
            }
            else
            {
              v74 = v71 - 65;
              if ( v74 )
              {
                if ( v74 == 1 && v69 + 40 <= v70 )
                  break;
              }
              else if ( v69 + 56 <= v70 )
              {
LABEL_165:
                *(_BYTE *)(v69 + v11 + 10) = 6;
                break;
              }
            }
          }
        }
      }
    }
LABEL_62:
    if ( *(_BYTE *)(v11 + 2) != 40 )
    {
      v13 = v11 + 72;
      goto LABEL_74;
    }
    if ( *(_DWORD *)(v11 + 20) || (v45 = *(_DWORD *)(v11 + 56)) == 0 )
    {
LABEL_74:
      *(_OWORD *)v13 = 0;
      *(_BYTE *)(v13 + 4) |= 1u;
      *(_BYTE *)v13 = 27;
      *a3 = 2;
      v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
      *(_QWORD *)(v53 - 16) = ClasspPowerUpCompletion;
      *(_QWORD *)(v53 - 8) = a3;
      *(_BYTE *)(v53 - 69) = -32;
      v54 = v83;
      *(_QWORD *)(v83 - 64) = v11;
      *(_BYTE *)(v54 - 72) = 15;
      v17 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
      v80 = v17;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        return v3;
      }
      v19 = 16;
      goto LABEL_228;
    }
    v46 = 0;
    while ( 1 )
    {
      v47 = *(unsigned int *)(v11 + 4LL * v46 + 120);
      if ( (unsigned int)v47 < 0x80 )
        goto LABEL_71;
      v48 = *(unsigned int *)(v11 + 16);
      if ( (unsigned int)v47 >= (unsigned int)v48 )
        goto LABEL_71;
      v49 = v47 + v11;
      v50 = (unsigned int)v47;
      v51 = *(_DWORD *)(v47 + v11);
      if ( v51 == 64 )
        break;
      v64 = v51 - 65;
      if ( !v64 )
      {
        v52 = v50 + 56;
LABEL_70:
        if ( v52 <= v48 )
        {
          if ( *(_BYTE *)(v49 + 10) )
            v13 = v49 + 24;
          goto LABEL_74;
        }
        goto LABEL_71;
      }
      if ( v64 == 1 && v50 + 40 <= v48 )
      {
        if ( *(_DWORD *)(v49 + 12) )
          v13 = v49 + 32;
        goto LABEL_74;
      }
LABEL_71:
      if ( ++v46 >= v45 )
        goto LABEL_74;
    }
    v52 = v50 + 40;
    goto LABEL_70;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140011ba0  mov     r11, rsp
0x140011ba3  push    rbp
0x140011ba4  push    rbx
0x140011ba5  push    r12
0x140011ba7  push    r15
0x140011ba9  lea     rbp, [r11-5Fh]
0x140011bad  sub     rsp, 98h
0x140011bb4  mov     rax, cs:__security_cookie
0x140011bbb  xor     rax, rsp
0x140011bbe  mov     [rbp+57h+var_40], rax
0x140011bc2  mov     r12d, 0C0000016h
0x140011bc8  xorps   xmm0, xmm0
0x140011bcb  mov     [rbp+57h+var_6C], r12d
0x140011bcf  mov     rbx, r8
0x140011bd2  mov     r15, rdx
0x140011bd5  movups  [rbp+57h+var_50], xmm0
0x140011bd9  test    r8, r8
0x140011bdc  jz      loc_1400128B6
0x140011be2  mov     r9, [r8+20h]
0x140011be6  mov     [r11+8], rsi
0x140011bea  mov     [r11-30h], r13
0x140011bee  mov     [r11-38h], r14
0x140011bf2  mov     rsi, [r9+40h]
0x140011bf6  mov     r14, [r8+28h]
0x140011bfa  mov     rax, [rsi+478h]
0x140011c01  mov     r13, [r14+0B8h]
0x140011c08  mov     [rbp+57h+var_68], r13
0x140011c0c  mov     rcx, [rax+0F40h]
0x140011c13  mov     rax, [rcx+0B8h]
0x140011c1a  mov     [rbp+57h+var_58], rax
0x140011c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c25  lea     r10, WPP_GLOBAL_Control
0x140011c2c  cmp     rcx, r10
0x140011c2f  jnz     loc_140011DB7
0x140011c35  mov     rax, [rsi+210h]
0x140011c3c  mov     [rsp+90h], rdi
0x140011c44  lea     rdi, [rbx+30h]
0x140011c48  cmp     byte ptr [rax+1Eh], 1
0x140011c4c  jz      loc_140012216
0x140011c52  cmp     r15, r14
0x140011c55  jz      loc_1400124CE
0x140011c5b  inc     dword ptr [rbx]
0x140011c5d  mov     ecx, [rbx]
0x140011c5f  cmp     ecx, 2
0x140011c62  jz      loc_140011DF7
0x140011c68  sub     ecx, 1
0x140011c6b  jz      loc_14001214E
0x140011c71  sub     ecx, 2
0x140011c74  jnz     loc_140012269
0x140011c7a  movzx   r8d, byte ptr [rdi+3]
0x140011c7f  xor     r13d, r13d
0x140011c82  mov     eax, r8d
0x140011c85  and     eax, 0FFFFFF3Fh
0x140011c8a  cmp     eax, 1
0x140011c8d  jnz     loc_1400124E9
0x140011c93  mov     r11, 0D6BF94D5E57A42BDh
0x140011c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ca4  cmp     rcx, r10
0x140011ca7  jz      short loc_140011CB4
0x140011ca9  mov     eax, [rcx+2Ch]
0x140011cac  test    al, 4
0x140011cae  jnz     loc_140012928
0x140011cb4  cmp     byte ptr [rbx+9], 0
0x140011cb8  jz      loc_140012470
0x140011cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cc5  cmp     rcx, r10
0x140011cc8  jz      short loc_140011CD5
0x140011cca  mov     eax, [rcx+2Ch]
0x140011ccd  test    al, 4
0x140011ccf  jnz     loc_140012960
0x140011cd5  mov     rax, [rsi+210h]
0x140011cdc  cmp     byte ptr [rax+1Eh], 1
0x140011ce0  jz      loc_140012479
0x140011ce6  lea     rcx, [rdi+3]; void *
0x140011cea  xor     edx, edx; Val
0x140011cec  mov     r8d, 55h ; 'U'; Size
0x140011cf2  call    memset
0x140011cf7  mov     word ptr [rdi], 58h ; 'X'
0x140011cfc  mov     byte ptr [rdi+2], 19h
0x140011d00  cmp     byte ptr [rdi+2], 28h ; '('
0x140011d04  jnz     loc_14001271C
0x140011d0a  mov     dword ptr [rdi+18h], 80000h
0x140011d11  mov     rax, [rsi+478h]
0x140011d18  mov     rcx, [rax+0F40h]
0x140011d1f  mov     [rdi+50h], rcx
0x140011d23  mov     rax, [rbp+57h+var_58]
0x140011d27  mov     [rax-40h], rdi
0x140011d2b  mov     byte ptr [rax-48h], 0Fh
0x140011d2f  mov     dword ptr [rbx], 3
0x140011d35  mov     rax, [rsi+478h]
0x140011d3c  mov     rcx, [rax+0F40h]
0x140011d43  mov     rax, [rcx+0B8h]
0x140011d4a  lea     rcx, ClasspPowerUpCompletion
0x140011d51  mov     [rax-10h], rcx
0x140011d55  mov     [rax-8], rbx
0x140011d59  mov     byte ptr [rax-45h], 0E0h
0x140011d5d  mov     rdx, [rsi+478h]
0x140011d64  mov     rcx, [rsi+10h]; DeviceObject
0x140011d68  mov     rdx, [rdx+0F40h]; Irp
0x140011d6f  call    cs:__imp_IofCallDriver
0x140011d76  nop     dword ptr [rax+rax+00h]
0x140011d7b  mov     r8d, eax
0x140011d7e  mov     [rbp+57h+var_6C], eax
0x140011d81  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d88  lea     rax, WPP_GLOBAL_Control
0x140011d8f  cmp     rcx, rax
0x140011d92  jz      loc_140012110
0x140011d98  mov     eax, [rcx+2Ch]
0x140011d9b  test    al, 4
0x140011d9d  jz      loc_140012110
0x140011da3  cmp     byte ptr [rcx+29h], 4
0x140011da7  jb      loc_140012110
0x140011dad  mov     edx, 15h
0x140011db2  jmp     loc_140040158
0x140011db7  mov     eax, [rcx+2Ch]
0x140011dba  test    al, 4
0x140011dbc  jz      loc_140011C35
0x140011dc2  cmp     byte ptr [rcx+29h], 4
0x140011dc6  jb      loc_140011C35
0x140011dcc  mov     rcx, [rcx+18h]
0x140011dd0  lea     r8, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids
0x140011dd7  mov     edx, 0Ah
0x140011ddc  mov     [rsp+0B0h+var_88], rbx
0x140011de1  mov     [rsp+0B0h+var_90], r15
0x140011de6  call    WPP_SF_qqq
0x140011deb  lea     r10, WPP_GLOBAL_Control
0x140011df2  jmp     loc_140011C35
0x140011df7  mov     eax, [r15+30h]
0x140011dfb  xor     r13d, r13d
0x140011dfe  test    eax, eax
0x140011e00  js      loc_1400127EF
0x140011e06  mov     rcx, [rsi+200h]; Pdo
0x140011e0d  lea     rdx, [rbp+57h+SecondsRemaining]; SecondsRemaining
0x140011e11  mov     [rbp+57h+SecondsRemaining], r13d
0x140011e15  call    cs:__imp_PoQueryWatchdogTime
0x140011e1c  nop     dword ptr [rax+rax+00h]
0x140011e21  mov     edx, 1
0x140011e26  test    al, al
0x140011e28  jz      loc_1400126E4
0x140011e2e  mov     ecx, [rbp+57h+SecondsRemaining]
0x140011e31  mov     r8d, 0F0h
0x140011e37  mov     dword ptr [rbp+57h+var_68], r8d
0x140011e3b  cmp     ecx, 258h
0x140011e41  jb      loc_140012232
0x140011e47  mov     ecx, 258h
0x140011e4c  mov     [rbp+57h+SecondsRemaining], ecx
0x140011e4f  mov     r9, [rsi+478h]
0x140011e56  lea     eax, [r8+5]
0x140011e5a  cmp     ecx, eax
0x140011e5c  jb      loc_14001273A
0x140011e62  xor     edx, edx
0x140011e64  lea     eax, [rcx-5]
0x140011e67  div     r8d
0x140011e6a  mov     edx, 1
0x140011e6f  mov     [r9+0F38h], eax
0x140011e76  mov     rax, [rsi+478h]
0x140011e7d  add     dword ptr [rax+0F38h], 0FFFFFFFFh
0x140011e84  jnz     short loc_140011E8F
0x140011e86  mov     eax, [rbp+57h+SecondsRemaining]
0x140011e89  add     eax, 0FFFFFFFBh
0x140011e8c  mov     dword ptr [rbp+57h+var_68], eax
0x140011e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e96  lea     rax, WPP_GLOBAL_Control
0x140011e9d  cmp     rcx, rax
0x140011ea0  jz      short loc_140011EAD
0x140011ea2  mov     eax, [rcx+2Ch]
0x140011ea5  test    al, 4
0x140011ea7  jnz     loc_1400128FC
0x140011ead  mov     rax, [rsi+478h]
0x140011eb4  mov     ecx, [rax+0F38h]
0x140011eba  mov     [rbx+10h], ecx
0x140011ebd  mov     rax, [rsi+210h]
0x140011ec4  cmp     byte ptr [rax+1Eh], 1
0x140011ec8  jnz     loc_14001224A
0x140011ece  mov     r9d, edx
0x140011ed1  mov     dword ptr [rsp+0B0h+var_90], 40h ; '@'
0x140011ed9  movzx   edx, r13w
0x140011edd  mov     r8d, 0B8h
0x140011ee3  mov     rcx, rdi
0x140011ee6  call    InitializeStorageRequestBlock
0x140011eeb  mov     [rbp+57h+var_6C], eax
0x140011eee  lea     r14, [rbx+30h]
0x140011ef2  test    eax, eax
0x140011ef4  js      loc_14001274D
0x140011efa  mov     [rdi+14h], r13d
0x140011efe  movzx   eax, r13w
0x140011f02  mov     [r14], ax
0x140011f06  cmp     byte ptr [rdi+2], 28h ; '('
0x140011f0a  lea     r8, [rsi+18h]
0x140011f0e  mov     rax, [rsi+478h]
0x140011f15  mov     rcx, [rax+0F40h]
0x140011f1c  jnz     loc_1400123F9
0x140011f22  mov     [rdi+50h], rcx
0x140011f26  cmp     [rdi+14h], r13d
0x140011f2a  jnz     short loc_140011F82
0x140011f2c  mov     rax, [r8]
0x140011f2f  mov     edx, r13d
0x140011f32  mov     r10d, [rdi+38h]
0x140011f36  mov     r11, [rax+240h]
0x140011f3d  test    r10d, r10d
0x140011f40  jz      short loc_140011F82
0x140011f42  mov     eax, edx
0x140011f44  mov     ecx, [rdi+rax*4+78h]
0x140011f48  cmp     ecx, 80h
0x140011f4e  jb      loc_140012373
0x140011f54  mov     r9d, [rdi+10h]
0x140011f58  cmp     ecx, r9d
0x140011f5b  jnb     loc_140012373
0x140011f61  mov     r14d, ecx
0x140011f64  mov     ecx, [rcx+rdi]
0x140011f67  cmp     ecx, 40h ; '@'
0x140011f6a  jnz     loc_140012821
0x140011f70  lea     rcx, [r14+28h]
0x140011f74  cmp     rcx, r9
0x140011f77  ja      loc_140012373
0x140011f7d  mov     [r14+rdi+10h], r11
0x140011f82  mov     rcx, [r8]; FdoExtension
0x140011f85  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x140011f8a  cmp     byte ptr [rdi+2], 28h ; '('
0x140011f8e  movzx   r9d, al
0x140011f92  jnz     short loc_140011FE7
0x140011f94  cmp     [rdi+14h], r13d
0x140011f98  jnz     short loc_140011FEB
0x140011f9a  mov     r11d, [rdi+38h]
0x140011f9e  mov     r8d, r13d
0x140011fa1  test    r11d, r11d
0x140011fa4  jz      short loc_140011FEB
0x140011fa6  mov     eax, r8d
0x140011fa9  mov     ecx, [rdi+rax*4+78h]
0x140011fad  cmp     ecx, 80h
0x140011fb3  jb      loc_140012390
0x140011fb9  mov     edx, [rdi+10h]
0x140011fbc  cmp     ecx, edx
0x140011fbe  jnb     loc_140012390
0x140011fc4  mov     r10d, ecx
0x140011fc7  mov     ecx, [rcx+rdi]
0x140011fca  cmp     ecx, 40h ; '@'
0x140011fcd  jnz     loc_14001284A
0x140011fd3  lea     rcx, [r10+28h]
0x140011fd7  cmp     rcx, rdx
0x140011fda  ja      loc_140012390
0x140011fe0  mov     [r10+rdi+9], r9b
0x140011fe5  jmp     short loc_140011FEB
0x140011fe7  mov     [rdi+0Bh], r9b
0x140011feb  movzx   ecx, byte ptr [rdi+2]
0x140011fef  mov     r14d, dword ptr [rbp+57h+var_68]
0x140011ff3  cmp     cl, 28h ; '('
0x140011ff6  jnz     loc_140012410
0x140011ffc  mov     [rdi+28h], r14d
0x140012000  mov     dword ptr [rdi+18h], 128h
0x140012007  mov     eax, [rbx+4]
0x14001200a  test    al, 2
0x14001200c  jz      short loc_140012020
0x14001200e  cmp     cl, 28h ; '('
0x140012011  jz      loc_140012793
0x140012017  or      dword ptr [rdi+0Ch], 80000h
0x14001201e  jmp     short loc_140012029
0x140012020  cmp     cl, 28h ; '('
0x140012023  jz      loc_14001279A
0x140012029  mov     byte ptr [rdi+0Ah], 6
0x14001202d  cmp     byte ptr [rdi+2], 28h ; '('
0x140012031  jnz     short loc_140012085
0x140012033  cmp     [rdi+14h], r13d
0x140012037  jnz     short loc_140012089
0x140012039  mov     r11d, [rdi+38h]
0x14001203d  test    r11d, r11d
0x140012040  jz      short loc_140012089
0x140012042  mov     r8d, r13d
0x140012045  mov     eax, r8d
0x140012048  mov     ecx, [rdi+rax*4+78h]
0x14001204c  cmp     ecx, 80h
0x140012052  jb      short loc_14001207B
0x140012054  mov     edx, [rdi+10h]
0x140012057  cmp     ecx, edx
0x140012059  jnb     short loc_14001207B
0x14001205b  lea     r10, [rcx+rdi]
0x14001205f  mov     r9d, ecx
0x140012062  mov     ecx, [r10]
0x140012065  cmp     ecx, 40h ; '@'
0x140012068  jnz     loc_1400126B2
0x14001206e  lea     rcx, [r9+28h]
0x140012072  cmp     rcx, rdx
0x140012075  jbe     loc_1400127F7
0x14001207b  inc     r8d
0x14001207e  cmp     r8d, r11d
0x140012081  jb      short loc_140012045
0x140012083  jmp     short loc_140012089
0x140012085  lea     r13, [rdi+48h]
0x140012089  xorps   xmm0, xmm0
0x14001208c  movups  xmmword ptr [r13+0], xmm0
0x140012091  or      byte ptr [r13+4], 1
0x140012096  mov     byte ptr [r13+0], 1Bh
0x14001209b  mov     dword ptr [rbx], 2
0x1400120a1  mov     rax, [rsi+478h]
0x1400120a8  mov     rcx, [rax+0F40h]
0x1400120af  mov     rax, [rcx+0B8h]
0x1400120b6  lea     rcx, ClasspPowerUpCompletion
0x1400120bd  mov     [rax-10h], rcx
0x1400120c1  mov     [rax-8], rbx
0x1400120c5  mov     byte ptr [rax-45h], 0E0h
  ... truncated ...
```
