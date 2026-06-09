# ClasspPowerDownCompletion

- ea: `0x140010400`
- end: `0x140011b8b`
- name: `ClasspPowerDownCompletion`
- size: `6027`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x1400073d4`
- `0x140008360`
- `0x14000f3e0`
- `0x140010400`
- `0x140012e18`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x140027a24`
- `0x1400291d0`
- `0x14002944c`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400109c9`
- `ntoskrnl!IofCallDriver` at `0x140010b7a`
- `ntoskrnl!IofCallDriver` at `0x140011070`
- `ntoskrnl!IofCallDriver` at `0x1400111ab`
- `ntoskrnl!IofCallDriver` at `0x1400109c9`
- `ntoskrnl!IofCallDriver` at `0x140010b7a`
- `ntoskrnl!IofCallDriver` at `0x140011070`
- `ntoskrnl!IofCallDriver` at `0x1400111ab`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001171c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400118b4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140011a4a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003fc8a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003fe58`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001171c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400118b4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140011a4a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003fc8a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003fe58`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001057f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001057f`
- `ntoskrnl!PoCallDriver` at `0x140010c47`
- `ntoskrnl!PoCallDriver` at `0x14003fd33`
- `ntoskrnl!PoCallDriver` at `0x140010c47`
- `ntoskrnl!PoCallDriver` at `0x14003fd33`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140010666`
- `ntoskrnl!PoQueryWatchdogTime` at `0x140010666`
- `ntoskrnl!PoSetPowerState` at `0x14003fd0d`
- `ntoskrnl!PoSetPowerState` at `0x14003fd0d`

## pseudocode

```c
__int64 __fastcall ClasspPowerDownCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // r9
  IRP *v5; // r15
  __int64 v7; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v9; // r10
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r14
  BOOLEAN v15; // al
  __int64 v16; // r8
  __int64 v17; // rax
  ULONG v19; // r15d
  __int64 v20; // rax
  __int16 v21; // ax
  PFUNCTIONAL_DEVICE_EXTENSION *v22; // r8
  __int64 v23; // rcx
  unsigned int v24; // edx
  unsigned int v25; // r11d
  _SENSE_DATA *SenseData; // r12
  __int64 v27; // rcx
  unsigned __int64 v28; // r9
  __int64 v29; // r10
  int v30; // ecx
  UCHAR v31; // dl
  unsigned int v32; // r11d
  unsigned int i; // r8d
  __int64 v34; // rcx
  unsigned __int64 v35; // r9
  __int64 v36; // r10
  int v37; // ecx
  _OWORD *v38; // r14
  PFUNCTIONAL_DEVICE_EXTENSION *v39; // r8
  __int64 v40; // rcx
  unsigned int v41; // r10d
  unsigned int v42; // r11d
  _SENSE_DATA *v43; // r15
  __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  __int64 v46; // r9
  int v47; // ecx
  UCHAR v48; // r15
  unsigned int v49; // r10d
  unsigned int k; // r8d
  __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  int v53; // r11d
  __int64 v54; // rax
  __int64 v55; // rax
  NTSTATUS v56; // eax
  PDEVICE_OBJECT v57; // rcx
  int v59; // eax
  unsigned int v60; // r10d
  unsigned int m; // edx
  __int64 v62; // rcx
  unsigned __int64 v63; // r8
  int v64; // r11d
  int Status; // r8d
  __int64 v66; // rbx
  int v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rax
  NTSTATUS v70; // r8d
  __int64 v71; // rdx
  __int64 v72; // r8
  _IO_STACK_LOCATION *v73; // rax
  _IO_STACK_LOCATION *v74; // rax
  NTSTATUS v75; // eax
  unsigned int v76; // r10d
  unsigned int j; // r8d
  __int64 v78; // rcx
  unsigned __int64 v79; // rdx
  int v80; // r11d
  char v81; // al
  unsigned int v82; // r10d
  unsigned int v83; // r9d
  __int64 v84; // rcx
  unsigned __int64 v85; // rdx
  __int64 v86; // r11
  __int64 v87; // r8
  int v88; // ecx
  unsigned __int64 v89; // rcx
  unsigned int v90; // r11d
  unsigned int v91; // r9d
  __int64 v92; // rcx
  unsigned __int64 v93; // rdx
  __int64 v94; // r10
  __int64 v95; // r8
  int v96; // ecx
  unsigned __int64 v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rax
  NTSTATUS v100; // r8d
  __int64 v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rax
  int v104; // ecx
  int v105; // ecx
  char v106; // al
  unsigned __int64 v107; // r11
  __int64 v108; // rcx
  unsigned __int64 v109; // r8
  __int64 v110; // r10
  __int64 v111; // r9
  int v112; // ecx
  unsigned __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rcx
  unsigned __int64 v116; // r8
  __int64 v117; // r10
  __int64 v118; // r9
  int v119; // ecx
  unsigned __int64 v120; // rcx
  int v121; // ecx
  int v122; // ecx
  int v123; // ecx
  int v124; // ecx
  int v125; // r11d
  int v126; // r11d
  int v127; // r11d
  int v128; // ecx
  unsigned __int8 v129; // r8
  char v130; // r9
  char v131; // r10
  _BYTE *v132; // rcx
  _BYTE *v133; // rax
  char v134; // al
  char v135; // cl
  char *v136; // r10
  unsigned int v137; // eax
  unsigned __int64 v138; // r8
  __int16 v139; // ax
  _IO_STACK_LOCATION *v140; // rax
  _IO_STACK_LOCATION *v141; // rax
  char v142; // al
  int v143; // ecx
  int v144; // ecx
  NTSTATUS v145; // [rsp+20h] [rbp-39h]
  __int64 v146; // [rsp+28h] [rbp-31h]
  int v147; // [rsp+44h] [rbp-15h] BYREF
  ULONG SecondsRemaining; // [rsp+48h] [rbp-11h] BYREF
  _IO_STACK_LOCATION *v149; // [rsp+50h] [rbp-9h]
  __int64 v150; // [rsp+58h] [rbp-1h] BYREF
  __int64 v151; // [rsp+60h] [rbp+7h]
  __int128 v152; // [rsp+68h] [rbp+Fh] BYREF

  v3 = *(_QWORD *)(a3 + 32);
  v5 = *(IRP **)(a3 + 40);
  v7 = *(_QWORD *)(v3 + 64);
  CurrentStackLocation = v5->Tail.Overlay.CurrentStackLocation;
  v149 = CurrentStackLocation;
  v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
  v151 = v9;
  v147 = -1073741802;
  v152 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    HIDWORD(v146) = HIDWORD(a3);
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids);
    CurrentStackLocation = v149;
    v9 = v151;
  }
  v10 = a3 + 48;
  if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 && *(_WORD *)(a3 + 48) != 88 )
    v10 = *(_QWORD *)(v7 + 1144) + 944LL;
  if ( a2 == v5 && a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  switch ( ++*(_DWORD *)a3 )
  {
    case 2:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
        CurrentStackLocation = v149;
      }
      if ( a2->IoStatus.Status < 0 && ClassPnPETWEnabled )
      {
        IoGetActivityIdIrp(v5, &v152);
        ClasspWriteSrbErrorResultEvent((unsigned int)&v152, *(_QWORD *)(v7 + 8), a2->IoStatus.Status, v10, 0);
        CurrentStackLocation = v149;
      }
      v12 = *(_QWORD *)(v7 + 1144);
      if ( (*(_BYTE *)(v12 + 1320) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
            *(_QWORD *)(a3 + 32));
          CurrentStackLocation = v149;
        }
        ++*(_DWORD *)a3;
        *(_BYTE *)(v10 + 3) = 1;
LABEL_30:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
          CurrentStackLocation = v149;
        }
        v13 = *(unsigned __int8 *)(v10 + 3);
        v14 = 0;
        if ( (*(_BYTE *)(v10 + 3) & 0x3F) != 1 )
        {
          v150 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            LODWORD(v146) = v13;
            WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 35, v13, a2, v10, v146);
          }
          *(_DWORD *)(a3 + 20) = 0;
          LOBYTE(v3) = 15;
          v142 = InterpretSenseInfoWithoutHistory(
                   *(_QWORD *)(v7 + 8),
                   a2,
                   v10,
                   v3,
                   22,
                   *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) - *(_DWORD *)(a3 + 16),
                   &v147,
                   &v150);
          *(_DWORD *)(a3 + 20) = (v150 + 9999999) / 10000000 + v150 + 9999999;
          if ( v142 == 1 )
          {
            v143 = *(_DWORD *)(a3 + 16);
            *(_DWORD *)(a3 + 16) = v143 - 1;
            if ( v143 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
              }
              --*(_DWORD *)a3;
              RetryPowerRequest(*(_QWORD *)(v7 + 8), a2, a3);
              return 3221225494LL;
            }
          }
          if ( v147 < 0 && ClassPnPETWEnabled )
          {
            IoGetActivityIdIrp(v5, &v152);
            ClasspWriteSrbErrorResultEvent(
              (unsigned int)&v152,
              *(_QWORD *)(v7 + 8),
              a2->IoStatus.Status,
              v10,
              *(_BYTE *)(*(_QWORD *)(v7 + 1144) + 3896LL) - *(_BYTE *)(a3 + 16));
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
          }
          CurrentStackLocation = v149;
          *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) = 4;
          *(_DWORD *)(a3 + 16) = 4;
        }
        if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 4
          && CurrentStackLocation->Parameters.Create.EaLength == 3
          && *(_DWORD *)(v7 + 176) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              38,
              WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
              *(_QWORD *)(a3 + 32));
            CurrentStackLocation = v149;
          }
          ++*(_DWORD *)a3;
          *(_BYTE *)(v10 + 3) = 1;
          v147 = 0;
LABEL_109:
          v72 = *(unsigned __int8 *)(v10 + 3);
          if ( (*(_BYTE *)(v10 + 3) & 0x3F) != 1 )
          {
            v150 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              LODWORD(v146) = v72;
              WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 41, v72, a2, v10, v146);
            }
            *(_DWORD *)(a3 + 20) = 0;
            LOBYTE(v3) = 15;
            v81 = InterpretSenseInfoWithoutHistory(
                    *(_QWORD *)(v7 + 8),
                    a2,
                    v10,
                    v3,
                    22,
                    *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) - *(_DWORD *)(a3 + 16),
                    &v147,
                    &v150);
            *(_DWORD *)(a3 + 20) = (v150 + 9999999) / 10000000 + v150 + 9999999;
            if ( v81 == 1 )
            {
              v144 = *(_DWORD *)(a3 + 16);
              *(_DWORD *)(a3 + 16) = v144 - 1;
              if ( v144 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
                }
                --*(_DWORD *)a3;
                if ( *(_BYTE *)(v10 + 2) == 40 )
                  *(_DWORD *)(v10 + 40) = 10;
                else
                  *(_DWORD *)(v10 + 20) = 10;
                RetryPowerRequest(*(_QWORD *)(v7 + 8), a2, a3);
                return 3221225494LL;
              }
            }
            if ( v147 < 0 && ClassPnPETWEnabled )
            {
              IoGetActivityIdIrp(v5, &v152);
              ClasspWriteSrbErrorResultEvent(
                (unsigned int)&v152,
                *(_QWORD *)(v7 + 8),
                a2->IoStatus.Status,
                v10,
                *(_BYTE *)(*(_QWORD *)(v7 + 1144) + 3896LL) - *(_BYTE *)(a3 + 16));
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
            }
            CurrentStackLocation = v149;
            *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) = 4;
            *(_DWORD *)(a3 + 16) = 4;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
            CurrentStackLocation = v149;
          }
          if ( v147 >= 0 )
            goto LABEL_112;
          v106 = *(_BYTE *)(v10 + 2);
          if ( v106 != 40 )
          {
            v107 = *(_QWORD *)(v10 + 32);
            goto LABEL_233;
          }
          v107 = 0;
          if ( !*(_DWORD *)(v10 + 20) )
          {
            SecondsRemaining = *(_DWORD *)(v10 + 56);
            if ( !SecondsRemaining )
              goto LABEL_264;
            while ( 1 )
            {
              v108 = *(unsigned int *)(v10 + 4 * v107 + 120);
              if ( (unsigned int)v108 < 0x80 )
                goto LABEL_221;
              v109 = *(unsigned int *)(v10 + 16);
              if ( (unsigned int)v108 >= (unsigned int)v109 )
                goto LABEL_221;
              v110 = v108 + v10;
              v111 = (unsigned int)v108;
              v112 = *(_DWORD *)(v108 + v10);
              if ( v112 == 64 )
              {
                v113 = v111 + 40;
              }
              else
              {
                v121 = v112 - 65;
                if ( v121 )
                {
                  if ( v121 == 1 && v111 + 40 <= v109 )
                  {
                    v107 = *(_QWORD *)(v110 + 24);
                    v106 = 40;
                    break;
                  }
                  goto LABEL_221;
                }
                v113 = v111 + 56;
              }
              if ( v113 <= v109 )
              {
                v107 = *(_QWORD *)(v110 + 16);
LABEL_264:
                v106 = 40;
                break;
              }
LABEL_221:
              v107 = (unsigned int)(v107 + 1);
              if ( (unsigned int)v107 >= SecondsRemaining )
              {
                v106 = 40;
                v107 = 0;
                break;
              }
            }
          }
LABEL_233:
          if ( *(char *)(v10 + 3) >= 0 || !v107 )
            goto LABEL_112;
          if ( v106 == 40 )
          {
            if ( !*(_DWORD *)(v10 + 20) )
            {
              LODWORD(v150) = *(_DWORD *)(v10 + 56);
              if ( (_DWORD)v150 )
              {
                v114 = 0;
                SecondsRemaining = 0;
                while ( 1 )
                {
                  v115 = *(unsigned int *)(v10 + 4 * v114 + 120);
                  if ( (unsigned int)v115 < 0x80 )
                    goto LABEL_286;
                  v116 = *(unsigned int *)(v10 + 16);
                  if ( (unsigned int)v115 >= (unsigned int)v116 )
                    goto LABEL_286;
                  v117 = v115 + v10;
                  v118 = (unsigned int)v115;
                  v119 = *(_DWORD *)(v115 + v10);
                  if ( v119 == 64 )
                    break;
                  v128 = v119 - 65;
                  if ( !v128 )
                  {
                    v120 = v118 + 56;
LABEL_285:
                    if ( v120 <= v116 )
                      goto LABEL_283;
                    goto LABEL_286;
                  }
                  if ( v128 == 1 && v118 + 40 <= v116 )
                  {
LABEL_283:
                    v129 = *(_BYTE *)(v117 + 9);
                    goto LABEL_289;
                  }
LABEL_286:
                  v114 = SecondsRemaining + 1;
                  SecondsRemaining = v114;
                  if ( (unsigned int)v114 >= (unsigned int)v150 )
                    goto LABEL_112;
                }
                v120 = v118 + 40;
                goto LABEL_285;
              }
LABEL_112:
              v73 = v5->Tail.Overlay.CurrentStackLocation;
              *(_OWORD *)&v73[-1].MajorFunction = *(_OWORD *)&v73->MajorFunction;
              *(_OWORD *)&v73[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v73->Parameters.NotifyDirectoryEx.CompletionFilter;
              *(_OWORD *)(&v73[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v73->Parameters.SetQuota + 6);
              v73[-1].FileObject = v73->FileObject;
              v73[-1].Control = 0;
              v74 = v5->Tail.Overlay.CurrentStackLocation;
              v74[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClasspPowerDownCompletion;
              v74[-1].Context = (void *)a3;
              v74[-1].Control = -32;
              v75 = PoCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), v5);
              v147 = v75;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  45,
                  WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                  v5,
                  v75);
              }
              return 3221225494LL;
            }
            v129 = 0;
          }
          else
          {
            v129 = *(_BYTE *)(v10 + 11);
          }
LABEL_289:
          if ( !v129 )
            goto LABEL_112;
          v130 = 0;
          v131 = 0;
          v132 = (_BYTE *)(v107 + v129);
          v133 = (_BYTE *)(v107 + 8);
          if ( (unsigned __int8)((*(_BYTE *)v107 & 0x7F) - 114) > 1u )
          {
            if ( v133 <= v132 )
            {
              v136 = (char *)(v107 + 13);
              v137 = v129;
              v130 = *(_BYTE *)(v107 + 2) & 0xF;
              if ( (unsigned int)*(unsigned __int8 *)(v107 + 7) + 8 <= v129 )
                v137 = *(unsigned __int8 *)(v107 + 7) + 8;
              v138 = v107 + v137;
              if ( (unsigned __int64)v136 > v138 )
                v135 = 0;
              else
                v135 = *(_BYTE *)(v107 + 12);
              if ( v107 + 14 > v138 )
                v131 = 0;
              else
                v131 = *v136;
              v134 = 1;
LABEL_337:
              if ( v134 && v130 == 2 && v135 == 4 && v131 == 4 )
              {
                *(_DWORD *)(a3 + 12) = -2147483631;
                v147 = -2147483631;
LABEL_187:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
                  CurrentStackLocation = v149;
                }
                if ( !*(_BYTE *)(a3 + 9) )
                  goto LABEL_265;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
                }
                if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
                {
                  v147 = InitializeStorageRequestBlock(v10);
                  if ( v147 < 0 )
                  {
                    v10 = a3 + 48;
                    memset((void *)(a3 + 51), 0, 0x55u);
                    *(_BYTE *)(a3 + 50) = 25;
                    LOWORD(v14) = 88;
                  }
                  else
                  {
                    *(_DWORD *)(v10 + 20) = 25;
                  }
                  *(_WORD *)(a3 + 48) = v14;
                }
                else
                {
                  memset((void *)(v10 + 3), 0, 0x55u);
                  *(_WORD *)v10 = 88;
                  *(_BYTE *)(v10 + 2) = 25;
                }
                v101 = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
                if ( *(_BYTE *)(v10 + 2) == 40 )
                {
                  *(_QWORD *)(v10 + 80) = v101;
                  *(_DWORD *)(v10 + 24) = 526336;
                }
                else
                {
                  *(_QWORD *)(v10 + 48) = v101;
                  *(_DWORD *)(v10 + 12) = 526336;
                }
                v102 = v151;
                *(_QWORD *)(v151 - 64) = v10;
                *(_BYTE *)(v102 - 72) = 15;
                v103 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
                *(_QWORD *)(v103 - 16) = ClasspPowerDownCompletion;
                *(_QWORD *)(v103 - 8) = a3;
                *(_BYTE *)(v103 - 69) = -32;
                v56 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
                v147 = v56;
                v57 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                {
                  return 3221225494LL;
                }
                v71 = 48;
                goto LABEL_404;
              }
              goto LABEL_112;
            }
          }
          else if ( v133 <= v132 )
          {
            v134 = 1;
            v135 = *(_BYTE *)(v107 + 2);
            v130 = *(_BYTE *)(v107 + 1) & 0xF;
            v131 = *(_BYTE *)(v107 + 3);
            goto LABEL_337;
          }
          v134 = 0;
          v135 = 0;
          goto LABEL_337;
        }
        SecondsRemaining = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
        }
        v15 = PoQueryWatchdogTime(*(PDEVICE_OBJECT *)(v7 + 512), &SecondsRemaining);
        v16 = *(_QWORD *)(v7 + 1144);
        if ( v15 )
        {
          if ( SecondsRemaining < 0x28 )
          {
            *(_DWORD *)(v16 + 3896) = 0;
            if ( SecondsRemaining <= 4 )
              v19 = 2;
            else
              v19 = SecondsRemaining - 2;
          }
          else
          {
            *(_DWORD *)(v16 + 3896) = (SecondsRemaining - 30) / 0xA;
            v17 = *(_QWORD *)(v7 + 1144);
            if ( (*(_DWORD *)(v17 + 3896))-- == 1 )
              v19 = SecondsRemaining - 30;
            else
              v19 = 10;
            v20 = *(_QWORD *)(v7 + 1144);
            if ( *(_DWORD *)(v20 + 3896) > 4u )
              *(_DWORD *)(v20 + 3896) = 4;
          }
        }
        else
        {
          *(_DWORD *)(v16 + 3896) = 4;
          v19 = 10;
        }
        *(_DWORD *)(a3 + 16) = *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL);
        if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
        {
          v147 = InitializeStorageRequestBlock(v10);
          if ( v147 < 0 )
          {
            v10 = a3 + 48;
            memset((void *)(a3 + 51), 0, 0x55u);
            v21 = 88;
            *(_BYTE *)(a3 + 50) = 0;
          }
          else
          {
            *(_DWORD *)(v10 + 20) = 0;
            v21 = 0;
          }
          *(_WORD *)(a3 + 48) = v21;
        }
        else
        {
          memset((void *)(v10 + 3), 0, 0x55u);
          *(_WORD *)v10 = 88;
          *(_BYTE *)(v10 + 2) = 0;
        }
        v22 = (PFUNCTIONAL_DEVICE_EXTENSION *)(v7 + 24);
        v23 = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
        if ( *(_BYTE *)(v10 + 2) != 40 )
        {
          *(_QWORD *)(v10 + 48) = v23;
          *(_QWORD *)(v10 + 32) = (*v22)->SenseData;
          goto LABEL_54;
        }
        *(_QWORD *)(v10 + 80) = v23;
        if ( !*(_DWORD *)(v10 + 20) )
        {
          v24 = 0;
          v25 = *(_DWORD *)(v10 + 56);
          SenseData = (*v22)->SenseData;
          if ( v25 )
          {
            do
            {
              v27 = *(unsigned int *)(v10 + 4LL * v24 + 120);
              if ( (unsigned int)v27 >= 0x80 )
              {
                v28 = *(unsigned int *)(v10 + 16);
                if ( (unsigned int)v27 < (unsigned int)v28 )
                {
                  v29 = (unsigned int)v27;
                  v30 = *(_DWORD *)(v27 + v10);
                  if ( v30 == 64 )
                  {
                    if ( v29 + 40 <= v28 )
                      goto LABEL_53;
                  }
                  else
                  {
                    v122 = v30 - 65;
                    if ( v122 )
                    {
                      if ( v122 == 1 && v29 + 40 <= v28 )
                      {
                        *(_QWORD *)(v29 + v10 + 24) = SenseData;
                        break;
                      }
                    }
                    else if ( v29 + 56 <= v28 )
                    {
LABEL_53:
                      *(_QWORD *)(v29 + v10 + 16) = SenseData;
                      break;
                    }
                  }
                }
              }
              ++v24;
            }
            while ( v24 < v25 );
          }
        }
LABEL_54:
        v31 = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(*v22);
        if ( *(_BYTE *)(v10 + 2) == 40 )
        {
          if ( !*(_DWORD *)(v10 + 20) )
          {
            v32 = *(_DWORD *)(v10 + 56);
            for ( i = 0; i < v32; ++i )
            {
              v34 = *(unsigned int *)(v10 + 4LL * i + 120);
              if ( (unsigned int)v34 >= 0x80 )
              {
                v35 = *(unsigned int *)(v10 + 16);
                if ( (unsigned int)v34 < (unsigned int)v35 )
                {
                  v36 = (unsigned int)v34;
                  v37 = *(_DWORD *)(v34 + v10);
                  if ( v37 == 64 )
                  {
                    if ( v36 + 40 <= v35 )
                      goto LABEL_61;
                  }
                  else
                  {
                    v124 = v37 - 65;
                    if ( v124 )
                    {
                      if ( v124 == 1 && v36 + 40 <= v35 )
                      {
LABEL_61:
                        *(_BYTE *)(v36 + v10 + 9) = v31;
                        break;
                      }
                    }
                    else if ( v36 + 56 <= v35 )
                    {
                      goto LABEL_61;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          *(_BYTE *)(v10 + 11) = v31;
        }
        if ( *(_BYTE *)(v10 + 2) == 40 )
        {
          *(_DWORD *)(v10 + 40) = v19;
          *(_DWORD *)(v10 + 24) = 526632;
          if ( !*(_DWORD *)(v10 + 20) )
          {
            v76 = *(_DWORD *)(v10 + 56);
            for ( j = 0; j < v76; ++j )
            {
              v78 = *(unsigned int *)(v10 + 4LL * j + 120);
              if ( (unsigned int)v78 >= 0x80 )
              {
                v79 = *(unsigned int *)(v10 + 16);
                if ( (unsigned int)v78 < (unsigned int)v79 )
                {
                  v80 = *(_DWORD *)(v78 + v10);
                  if ( v80 == 64 )
                  {
                    if ( v78 + 40 <= v79 )
                      goto LABEL_127;
                  }
                  else
                  {
                    v127 = v80 - 65;
                    if ( v127 )
                    {
                      if ( v127 == 1 && v78 + 40 <= v79 )
                        break;
                    }
                    else if ( v78 + 56 <= v79 )
                    {
LABEL_127:
                      *(_BYTE *)(v78 + v10 + 10) = 6;
                      break;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          *(_DWORD *)(v10 + 20) = v19;
          *(_DWORD *)(v10 + 12) = 526632;
          *(_BYTE *)(v10 + 10) = 6;
        }
        if ( *(_BYTE *)(v10 + 2) != 40 )
        {
          v14 = v10 + 72;
          goto LABEL_84;
        }
        if ( *(_DWORD *)(v10 + 20) || (v82 = *(_DWORD *)(v10 + 56)) == 0 )
        {
LABEL_84:
          *(_OWORD *)v14 = 0;
          *(_BYTE *)(v14 + 4) &= ~1u;
          *(_BYTE *)(v14 + 1) |= 1u;
          *(_BYTE *)v14 = 27;
          v54 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
          *(_QWORD *)(v54 - 16) = ClasspPowerDownCompletion;
          *(_QWORD *)(v54 - 8) = a3;
          *(_BYTE *)(v54 - 69) = -32;
          v55 = v151;
          *(_QWORD *)(v151 - 64) = v10;
          *(_BYTE *)(v55 - 72) = 15;
          v56 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
          v147 = v56;
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            return 3221225494LL;
          }
          v71 = 40;
LABEL_404:
          v145 = v56;
          goto LABEL_405;
        }
        v83 = 0;
        while ( 1 )
        {
          v84 = *(unsigned int *)(v10 + 4LL * v83 + 120);
          if ( (unsigned int)v84 < 0x80 )
            goto LABEL_161;
          v85 = *(unsigned int *)(v10 + 16);
          if ( (unsigned int)v84 >= (unsigned int)v85 )
            goto LABEL_161;
          v86 = v84 + v10;
          v87 = (unsigned int)v84;
          v88 = *(_DWORD *)(v84 + v10);
          if ( v88 == 64 )
            break;
          v104 = v88 - 65;
          if ( !v104 )
          {
            v89 = v87 + 56;
LABEL_160:
            if ( v89 <= v85 )
            {
              if ( *(_BYTE *)(v86 + 10) )
                v14 = v86 + 24;
              goto LABEL_84;
            }
            goto LABEL_161;
          }
          if ( v104 == 1 && v87 + 40 <= v85 )
          {
            if ( *(_DWORD *)(v86 + 12) )
              v14 = v86 + 32;
            goto LABEL_84;
          }
LABEL_161:
          if ( ++v83 >= v82 )
            goto LABEL_84;
        }
        v89 = v87 + 40;
        goto LABEL_160;
      }
      *(_DWORD *)(v12 + 3896) = 4;
      v38 = 0;
      *(_DWORD *)(a3 + 16) = 4;
      if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
      {
        v147 = InitializeStorageRequestBlock(v10);
        if ( v147 < 0 )
        {
          v10 = a3 + 48;
          memset((void *)(a3 + 51), 0, 0x55u);
          v139 = 88;
          *(_BYTE *)(a3 + 50) = 0;
        }
        else
        {
          *(_DWORD *)(v10 + 20) = 0;
          v139 = 0;
        }
        *(_WORD *)(a3 + 48) = v139;
      }
      else
      {
        memset((void *)(v10 + 3), 0, 0x55u);
        *(_WORD *)v10 = 88;
        *(_BYTE *)(v10 + 2) = 0;
      }
      v39 = (PFUNCTIONAL_DEVICE_EXTENSION *)(v7 + 24);
      v40 = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
      if ( *(_BYTE *)(v10 + 2) != 40 )
      {
        *(_QWORD *)(v10 + 48) = v40;
        *(_QWORD *)(v10 + 32) = (*v39)->SenseData;
        goto LABEL_75;
      }
      *(_QWORD *)(v10 + 80) = v40;
      if ( !*(_DWORD *)(v10 + 20) )
      {
        v41 = 0;
        v42 = *(_DWORD *)(v10 + 56);
        v43 = (*v39)->SenseData;
        if ( v42 )
        {
          do
          {
            v44 = *(unsigned int *)(v10 + 4LL * v41 + 120);
            if ( (unsigned int)v44 >= 0x80 )
            {
              v45 = *(unsigned int *)(v10 + 16);
              if ( (unsigned int)v44 < (unsigned int)v45 )
              {
                v46 = (unsigned int)v44;
                v47 = *(_DWORD *)(v44 + v10);
                if ( v47 == 64 )
                {
                  if ( v46 + 40 <= v45 )
                    goto LABEL_74;
                }
                else
                {
                  v123 = v47 - 65;
                  if ( v123 )
                  {
                    if ( v123 == 1 && v46 + 40 <= v45 )
                    {
                      *(_QWORD *)(v46 + v10 + 24) = v43;
                      break;
                    }
                  }
                  else if ( v46 + 56 <= v45 )
                  {
LABEL_74:
                    *(_QWORD *)(v46 + v10 + 16) = v43;
                    break;
                  }
                }
              }
            }
            ++v41;
          }
          while ( v41 < v42 );
        }
      }
LABEL_75:
      v48 = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(*v39);
      if ( *(_BYTE *)(v10 + 2) == 40 )
      {
        if ( !*(_DWORD *)(v10 + 20) )
        {
          v49 = *(_DWORD *)(v10 + 56);
          for ( k = 0; k < v49; ++k )
          {
            v51 = *(unsigned int *)(v10 + 4LL * k + 120);
            if ( (unsigned int)v51 >= 0x80 )
            {
              v52 = *(unsigned int *)(v10 + 16);
              if ( (unsigned int)v51 < (unsigned int)v52 )
              {
                v53 = *(_DWORD *)(v51 + v10);
                if ( v53 == 64 )
                {
                  if ( v51 + 40 <= v52 )
                    goto LABEL_82;
                }
                else
                {
                  v125 = v53 - 65;
                  if ( v125 )
                  {
                    if ( v125 == 1 && v51 + 40 <= v52 )
                    {
LABEL_82:
                      *(_BYTE *)(v51 + v10 + 9) = v48;
                      break;
                    }
                  }
                  else if ( v51 + 56 <= v52 )
                  {
                    goto LABEL_82;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        *(_BYTE *)(v10 + 11) = v48;
      }
      v59 = *(_DWORD *)(v7 + 584);
      if ( *(_BYTE *)(v10 + 2) == 40 )
      {
        *(_DWORD *)(v10 + 40) = v59;
        *(_DWORD *)(v10 + 24) = 526632;
        if ( !*(_DWORD *)(v10 + 20) )
        {
          v60 = *(_DWORD *)(v10 + 56);
          for ( m = 0; m < v60; ++m )
          {
            v62 = *(unsigned int *)(v10 + 4LL * m + 120);
            if ( (unsigned int)v62 >= 0x80 )
            {
              v63 = *(unsigned int *)(v10 + 16);
              if ( (unsigned int)v62 < (unsigned int)v63 )
              {
                v64 = *(_DWORD *)(v62 + v10);
                if ( v64 == 64 )
                {
                  if ( v62 + 40 <= v63 )
                    goto LABEL_94;
                }
                else
                {
                  v126 = v64 - 65;
                  if ( v126 )
                  {
                    if ( v126 == 1 && v62 + 40 <= v63 )
                      break;
                  }
                  else if ( v62 + 56 <= v63 )
                  {
LABEL_94:
                    *(_BYTE *)(v62 + v10 + 10) = 10;
                    break;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        *(_DWORD *)(v10 + 20) = v59;
        *(_DWORD *)(v10 + 12) = 526632;
        *(_BYTE *)(v10 + 10) = 10;
      }
      if ( *(_BYTE *)(v10 + 2) != 40 )
      {
        v38 = (_OWORD *)(v10 + 72);
        goto LABEL_180;
      }
      if ( *(_DWORD *)(v10 + 20) || (v90 = *(_DWORD *)(v10 + 56)) == 0 )
      {
LABEL_180:
        *v38 = 0;
        *(_BYTE *)v38 = 53;
        v98 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
        *(_QWORD *)(v98 - 16) = ClasspPowerDownCompletion;
        *(_QWORD *)(v98 - 8) = a3;
        *(_BYTE *)(v98 - 69) = -32;
        v99 = v151;
        *(_QWORD *)(v151 - 64) = v10;
        *(_BYTE *)(v99 - 72) = 15;
        v100 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
        v147 = v100;
        v57 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          return 3221225494LL;
        }
        v71 = 32;
        v145 = v100;
        goto LABEL_405;
      }
      v91 = 0;
      while ( 1 )
      {
        v92 = *(unsigned int *)(v10 + 4LL * v91 + 120);
        if ( (unsigned int)v92 < 0x80 )
          goto LABEL_177;
        v93 = *(unsigned int *)(v10 + 16);
        if ( (unsigned int)v92 >= (unsigned int)v93 )
          goto LABEL_177;
        v94 = v92 + v10;
        v95 = (unsigned int)v92;
        v96 = *(_DWORD *)(v92 + v10);
        if ( v96 == 64 )
          break;
        v105 = v96 - 65;
        if ( !v105 )
        {
          v97 = v95 + 56;
LABEL_176:
          if ( v97 <= v93 )
          {
            if ( *(_BYTE *)(v94 + 10) )
              v38 = (_OWORD *)(v94 + 24);
            goto LABEL_180;
          }
          goto LABEL_177;
        }
        if ( v105 == 1 && v95 + 40 <= v93 )
        {
          if ( *(_DWORD *)(v94 + 12) )
            v38 = (_OWORD *)(v94 + 32);
          goto LABEL_180;
        }
LABEL_177:
        if ( ++v91 >= v90 )
          goto LABEL_180;
      }
      v97 = v95 + 40;
      goto LABEL_176;
    case 1:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, a2);
        CurrentStackLocation = v149;
        v9 = v151;
      }
      if ( (*(_DWORD *)(a3 + 4) & 2) != 0 )
      {
        Status = a2->IoStatus.Status;
        if ( Status < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                28,
                WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                a2,
                Status);
              CurrentStackLocation = v149;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
                a2,
                *(unsigned __int8 *)(v10 + 3));
              CurrentStackLocation = v149;
            }
          }
          if ( ClassPnPETWEnabled )
          {
            IoGetActivityIdIrp(v5, &v152);
            ClasspWriteSrbErrorResultEvent((unsigned int)&v152, *(_QWORD *)(v7 + 8), a2->IoStatus.Status, v10, 0);
            CurrentStackLocation = v149;
          }
          *(_DWORD *)(v7 + 536) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          v140 = v5->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v140[-1].MajorFunction = *(_OWORD *)&v140->MajorFunction;
          *(_OWORD *)&v140[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v140->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v140[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v140->Parameters.SetQuota + 6);
          v140[-1].FileObject = v140->FileObject;
          v140[-1].Control = 0;
          v141 = v5->Tail.Overlay.CurrentStackLocation;
          v141[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspStartNextPowerIrpCompletion;
          v141[-1].Context = (void *)a3;
          v141[-1].Control = -32;
          PoSetPowerState(
            *(PDEVICE_OBJECT *)(a3 + 32),
            CurrentStackLocation->Parameters.Power.Type,
            CurrentStackLocation->Parameters.Power.State);
          *(_BYTE *)(v7 + 832) = 0;
          ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(v7 + 8), v5);
          PoCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), v5);
          return 3221225494LL;
        }
      }
      *(_BYTE *)(a3 + 9) = (*(_DWORD *)(a3 + 4) & 2) != 0;
      *(_DWORD *)(*(_QWORD *)(v7 + 1144) + 3896LL) = 0;
      *(_DWORD *)(a3 + 16) = 0;
      if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1
        && (v66 = *(_QWORD *)(v7 + 1144) + 944LL,
            v67 = InitializeStorageRequestBlock(v66),
            v9 = v151,
            v147 = v67,
            v67 >= 0) )
      {
        *(_DWORD *)(v66 + 20) = 26;
      }
      else
      {
        *(_BYTE *)(a3 + 50) = 26;
        v66 = a3 + 48;
        *(_WORD *)(a3 + 48) = 88;
      }
      v68 = *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL);
      if ( *(_BYTE *)(v66 + 2) == 40 )
      {
        *(_QWORD *)(v66 + 80) = v68;
        *(_DWORD *)(v66 + 40) = *(_DWORD *)(v7 + 584);
        *(_DWORD *)(v66 + 24) = 526632;
      }
      else
      {
        *(_QWORD *)(v66 + 48) = v68;
        *(_DWORD *)(v66 + 20) = *(_DWORD *)(v7 + 584);
        *(_DWORD *)(v66 + 12) = 526632;
      }
      v69 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL) + 184LL);
      *(_QWORD *)(v69 - 16) = ClasspPowerDownCompletion;
      *(_QWORD *)(v69 - 8) = a3;
      *(_BYTE *)(v69 - 69) = -32;
      *(_QWORD *)(v9 - 64) = v66;
      *(_BYTE *)(v9 - 72) = 15;
      v70 = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 16), *(PIRP *)(*(_QWORD *)(v7 + 1144) + 3904LL));
      v147 = v70;
      v57 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        return 3221225494LL;
      }
      v71 = 30;
      v145 = v70;
LABEL_405:
      WPP_SF_qD(
        v57->AttachedDevice,
        v71,
        WPP_62cb9f8746703568f010ef341ff474b6_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v7 + 1144) + 3904LL),
        v145);
      return 3221225494LL;
    case 3:
      goto LABEL_30;
    case 4:
      LOWORD(v14) = 0;
      goto LABEL_109;
    case 5:
      LOWORD(v14) = 0;
      goto LABEL_187;
  }
  if ( *(_DWORD *)a3 != 6 )
    return 3221225494LL;
  if ( *(_BYTE *)(a3 + 9) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
      CurrentStackLocation = v149;
    }
    if ( a2->IoStatus.Status >= 0 )
    {
      *(_BYTE *)(a3 + 9) = 0;
      goto LABEL_16;
    }
    if ( !ClassPnPETWEnabled )
      goto LABEL_16;
    IoGetActivityIdIrp(v5, &v152);
    ClasspWriteSrbErrorResultEvent((unsigned int)&v152, *(_QWORD *)(v7 + 8), a2->IoStatus.Status, v10, 0);
LABEL_402:
    CurrentStackLocation = v149;
    goto LABEL_16;
  }
LABEL_265:
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
    goto LABEL_402;
  }
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
    CurrentStackLocation = v149;
  }
LABEL_18:
  v147 = *(_DWORD *)(a3 + 12);
  v5->IoStatus.Status = v147;
  v5->IoStatus.Information = 0;
  if ( v147 >= 0 )
    *(_DWORD *)(v7 + 536) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_62cb9f8746703568f010ef341ff474b6_Traceguids, v5);
  }
  ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(a3 + 32), v5);
  *(_BYTE *)(a3 + 8) = 0;
  PoStartNextPowerIrp(v5);
  v11 = *(_QWORD *)(v7 + 1144);
  *(_BYTE *)(v7 + 832) = 0;
  if ( a2 == *(IRP **)(v11 + 3904) )
  {
    ClassCompleteRequest(*(PDEVICE_OBJECT *)(v7 + 8), v5, 0);
    return 3221225494LL;
  }
  return (unsigned int)v147;
}

```

## disassembly

```asm
0x140010400  push    rbp
0x140010402  push    rsi
0x140010403  push    rdi
0x140010404  push    r12
0x140010406  push    r13
0x140010408  push    r15
0x14001040a  lea     rbp, [rsp-2Fh]
0x14001040f  sub     rsp, 88h
0x140010416  mov     rax, cs:__security_cookie
0x14001041d  xor     rax, rsp
0x140010420  mov     [rbp+57h+var_38], rax
0x140010424  mov     r9, [r8+20h]
0x140010428  mov     r13, rdx
0x14001042b  mov     r15, [r8+28h]
0x14001042f  xorps   xmm0, xmm0
0x140010432  mov     rdi, r8
0x140010435  mov     rsi, [r9+40h]
0x140010439  mov     rdx, [r15+0B8h]
0x140010440  mov     [rbp+57h+var_60], rdx
0x140010444  mov     rax, [rsi+478h]
0x14001044b  mov     rcx, [rax+0F40h]
0x140010452  mov     r10, [rcx+0B8h]
0x140010459  mov     [rbp+57h+var_50], r10
0x14001045d  mov     [rbp+57h+var_6C], 0C0000016h
0x140010464  movups  [rbp+57h+var_48], xmm0
0x140010468  mov     rcx, cs:WPP_GLOBAL_Control
0x14001046f  lea     r11, WPP_GLOBAL_Control
0x140010476  cmp     rcx, r11
0x140010479  jz      short loc_140010486
0x14001047b  mov     eax, [rcx+2Ch]
0x14001047e  test    al, 4
0x140010480  jnz     loc_14001167A
0x140010486  mov     rax, [rsi+210h]
0x14001048d  mov     [rsp+0B0h+arg_0], rbx
0x140010495  lea     rbx, [rdi+30h]
0x140010499  cmp     byte ptr [rax+1Eh], 1
0x14001049d  jz      loc_14001081E
0x1400104a3  cmp     r13, r15
0x1400104a6  jz      loc_1400116B7
0x1400104ac  inc     dword ptr [rdi]
0x1400104ae  mov     ecx, [rdi]
0x1400104b0  mov     [rsp+0B0h+var_30], r14
0x1400104b8  cmp     ecx, 2
0x1400104bb  jz      loc_1400105BA
0x1400104c1  sub     ecx, 1
0x1400104c4  jz      loc_140010A7A
0x1400104ca  sub     ecx, 2
0x1400104cd  jz      loc_140010606
0x1400104d3  sub     ecx, 1
0x1400104d6  jz      loc_140010BC7
0x1400104dc  sub     ecx, 1
0x1400104df  jz      loc_1400110EA
0x1400104e5  cmp     ecx, 1
0x1400104e8  jnz     loc_1400109EF
0x1400104ee  xor     r14d, r14d
0x1400104f1  cmp     [rdi+9], r14b
0x1400104f5  jz      loc_1400114BC
0x1400104fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140010502  cmp     rcx, r11
0x140010505  jz      short loc_140010512
0x140010507  mov     eax, [rcx+2Ch]
0x14001050a  test    al, 4
0x14001050c  jnz     loc_140011A04
0x140010512  cmp     dword ptr [r13+30h], 0
0x140010517  jl      loc_140011A36
0x14001051d  mov     byte ptr [rdi+9], 0
0x140010521  mov     rcx, cs:WPP_GLOBAL_Control
0x140010528  cmp     rcx, r11
0x14001052b  jz      short loc_140010538
0x14001052d  mov     eax, [rcx+2Ch]
0x140010530  test    al, 4
0x140010532  jnz     loc_140011A75
0x140010538  mov     eax, [rdi+0Ch]
0x14001053b  mov     [rbp+57h+var_6C], eax
0x14001053e  mov     [r15+30h], eax
0x140010542  mov     [r15+38h], r14
0x140010546  cmp     [rbp+57h+var_6C], 0
0x14001054a  jl      short loc_140010555
0x14001054c  mov     eax, [rdx+18h]
0x14001054f  mov     [rsi+218h], eax
0x140010555  mov     rcx, cs:WPP_GLOBAL_Control
0x14001055c  cmp     rcx, r11
0x14001055f  jz      short loc_14001056C
0x140010561  mov     eax, [rcx+2Ch]
0x140010564  test    al, 4
0x140010566  jnz     loc_140011AA7
0x14001056c  mov     rcx, [rdi+20h]; DeviceObject
0x140010570  mov     rdx, r15; Tag
0x140010573  call    ClassReleaseRemoveLock
0x140010578  mov     rcx, r15; Irp
0x14001057b  mov     byte ptr [rdi+8], 0
0x14001057f  call    cs:__imp_PoStartNextPowerIrp
0x140010586  nop     dword ptr [rax+rax+00h]
0x14001058b  mov     rax, [rsi+478h]
0x140010592  mov     byte ptr [rsi+340h], 0
0x140010599  cmp     r13, [rax+0F40h]
0x1400105a0  jnz     loc_140011ACE
0x1400105a6  mov     rcx, [rsi+8]; DeviceObject
0x1400105aa  xor     r8d, r8d; PriorityBoost
0x1400105ad  mov     rdx, r15; Irp
0x1400105b0  call    ClassCompleteRequest
0x1400105b5  jmp     loc_1400109EF
0x1400105ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105c1  cmp     rcx, r11
0x1400105c4  jnz     loc_140010C94
0x1400105ca  cmp     dword ptr [r13+30h], 0
0x1400105cf  jl      loc_140011708
0x1400105d5  mov     rcx, [rsi+478h]
0x1400105dc  test    byte ptr [rcx+528h], 4
0x1400105e3  jz      loc_14001083A
0x1400105e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105f0  cmp     rcx, r11
0x1400105f3  jz      short loc_140010600
0x1400105f5  mov     eax, [rcx+2Ch]
0x1400105f8  test    al, 4
0x1400105fa  jnz     loc_140011789
0x140010600  inc     dword ptr [rdi]
0x140010602  mov     byte ptr [rbx+3], 1
0x140010606  mov     rcx, cs:WPP_GLOBAL_Control
0x14001060d  cmp     rcx, r11
0x140010610  jz      short loc_14001061D
0x140010612  mov     eax, [rcx+2Ch]
0x140010615  test    al, 4
0x140010617  jnz     loc_1400117BC
0x14001061d  movzx   r8d, byte ptr [rbx+3]
0x140010622  xor     r14d, r14d
0x140010625  mov     eax, r8d
0x140010628  and     eax, 0FFFFFF3Fh
0x14001062d  cmp     eax, 1
0x140010630  jnz     loc_1400117EE
0x140010636  cmp     dword ptr [rdx+18h], 4
0x14001063a  jz      loc_140010D4A
0x140010640  mov     [rbp+57h+SecondsRemaining], r14d
0x140010644  mov     rcx, cs:WPP_GLOBAL_Control
0x14001064b  cmp     rcx, r11
0x14001064e  jz      short loc_14001065B
0x140010650  mov     eax, [rcx+2Ch]
0x140010653  test    al, 4
0x140010655  jnz     loc_140011AD6
0x14001065b  mov     rcx, [rsi+200h]; Pdo
0x140010662  lea     rdx, [rbp+57h+SecondsRemaining]; SecondsRemaining
0x140010666  call    cs:__imp_PoQueryWatchdogTime
0x14001066d  nop     dword ptr [rax+rax+00h]
0x140010672  mov     r8, [rsi+478h]
0x140010679  test    al, al
0x14001067b  jz      loc_1400110BD
0x140010681  mov     ecx, [rbp+57h+SecondsRemaining]
0x140010684  cmp     ecx, 28h ; '('
0x140010687  jb      loc_140011AFD
0x14001068d  add     ecx, 0FFFFFFE2h
0x140010690  mov     eax, 0CCCCCCCDh
0x140010695  mul     ecx
0x140010697  shr     edx, 3
0x14001069a  mov     [r8+0F38h], edx
0x1400106a1  mov     rax, [rsi+478h]
0x1400106a8  add     dword ptr [rax+0F38h], 0FFFFFFFFh
0x1400106af  jz      loc_14001126E
0x1400106b5  mov     r15d, 0Ah
0x1400106bb  mov     rax, [rsi+478h]
0x1400106c2  cmp     dword ptr [rax+0F38h], 4
0x1400106c9  jbe     short loc_1400106D5
0x1400106cb  mov     dword ptr [rax+0F38h], 4
0x1400106d5  mov     rax, [rsi+478h]
0x1400106dc  mov     ecx, [rax+0F38h]
0x1400106e2  mov     [rdi+10h], ecx
0x1400106e5  mov     rax, [rsi+210h]
0x1400106ec  cmp     byte ptr [rax+1Eh], 1
0x1400106f0  jnz     loc_140010D9D
0x1400106f6  mov     r9d, 1
0x1400106fc  movzx   edx, r14w
0x140010700  mov     r8d, 0B8h
0x140010706  mov     dword ptr [rsp+0B0h+var_90], 40h ; '@'
0x14001070e  mov     rcx, rbx
0x140010711  call    InitializeStorageRequestBlock
0x140010716  mov     [rbp+57h+var_6C], eax
0x140010719  test    eax, eax
0x14001071b  js      loc_140011B1B
0x140010721  mov     [rbx+14h], r14d
0x140010725  movzx   eax, r14w
0x140010729  mov     [rdi+30h], ax
0x14001072d  cmp     byte ptr [rbx+2], 28h ; '('
0x140010731  lea     r8, [rsi+18h]
0x140010735  mov     rax, [rsi+478h]
0x14001073c  mov     rcx, [rax+0F40h]
0x140010743  jnz     loc_140010F9E
0x140010749  mov     [rbx+50h], rcx
0x14001074d  cmp     [rbx+14h], r14d
0x140010751  jnz     short loc_1400107A9
0x140010753  mov     rax, [r8]
0x140010756  mov     edx, r14d
0x140010759  mov     r11d, [rbx+38h]
0x14001075d  mov     r12, [rax+240h]
0x140010764  test    r11d, r11d
0x140010767  jz      short loc_1400107A9
0x140010769  mov     eax, edx
0x14001076b  mov     ecx, [rbx+rax*4+78h]
0x14001076f  cmp     ecx, 80h
0x140010775  jb      loc_140010D8D
0x14001077b  mov     r9d, [rbx+10h]
0x14001077f  cmp     ecx, r9d
0x140010782  jnb     loc_140010D8D
0x140010788  mov     r10d, ecx
0x14001078b  mov     ecx, [rcx+rbx]
0x14001078e  cmp     ecx, 40h ; '@'
0x140010791  jnz     loc_140011413
0x140010797  lea     rcx, [r10+28h]
0x14001079b  cmp     rcx, r9
0x14001079e  ja      loc_140010D8D
0x1400107a4  mov     [r10+rbx+10h], r12
0x1400107a9  mov     rcx, [r8]; FdoExtension
0x1400107ac  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x1400107b1  cmp     byte ptr [rbx+2], 28h ; '('
0x1400107b5  movzx   edx, al
0x1400107b8  jnz     loc_140010CD1
0x1400107be  cmp     [rbx+14h], r14d
0x1400107c2  jnz     loc_140010CD4
0x1400107c8  mov     r11d, [rbx+38h]
0x1400107cc  mov     r8d, r14d
0x1400107cf  test    r11d, r11d
0x1400107d2  jz      loc_140010CD4
0x1400107d8  mov     eax, r8d
0x1400107db  mov     ecx, [rbx+rax*4+78h]
0x1400107df  cmp     ecx, 80h
0x1400107e5  jb      loc_140010DC9
0x1400107eb  mov     r9d, [rbx+10h]
0x1400107ef  cmp     ecx, r9d
0x1400107f2  jnb     loc_140010DC9
0x1400107f8  mov     r10d, ecx
0x1400107fb  mov     ecx, [rcx+rbx]
0x1400107fe  cmp     ecx, 40h ; '@'
0x140010801  jnz     loc_140011465
0x140010807  lea     rcx, [r10+28h]
0x14001080b  cmp     rcx, r9
0x14001080e  ja      loc_140010DC9
0x140010814  mov     [r10+rbx+9], dl
0x140010819  jmp     loc_140010CD4
0x14001081e  mov     rcx, [rsi+478h]
0x140010825  add     rcx, 3B0h
0x14001082c  cmp     word ptr [rdi+30h], 58h ; 'X'
0x140010831  cmovnz  rbx, rcx
0x140010835  jmp     loc_1400104A3
0x14001083a  mov     dword ptr [rcx+0F38h], 4
0x140010844  xor     r14d, r14d
0x140010847  mov     dword ptr [rdi+10h], 4
0x14001084e  mov     rax, [rsi+210h]
0x140010855  cmp     byte ptr [rax+1Eh], 1
0x140010859  jz      loc_140011751
0x14001085f  lea     rcx, [rbx+3]; void *
0x140010863  xor     edx, edx; Val
0x140010865  mov     r8d, 55h ; 'U'; Size
0x14001086b  call    memset
0x140010870  mov     word ptr [rbx], 58h ; 'X'
0x140010875  mov     [rbx+2], r14b
0x140010879  cmp     byte ptr [rbx+2], 28h ; '('
0x14001087d  lea     r8, [rsi+18h]
0x140010881  mov     rax, [rsi+478h]
0x140010888  mov     rcx, [rax+0F40h]
0x14001088f  jnz     loc_1400110D3
0x140010895  mov     [rbx+50h], rcx
0x140010899  cmp     [rbx+14h], r14d
0x14001089d  jnz     short loc_1400108F4
0x14001089f  mov     rax, [r8]
0x1400108a2  mov     r10d, r14d
0x1400108a5  mov     r11d, [rbx+38h]
0x1400108a9  mov     r15, [rax+240h]
0x1400108b0  test    r11d, r11d
0x1400108b3  jz      short loc_1400108F4
0x1400108b5  mov     eax, r10d
0x1400108b8  mov     ecx, [rbx+rax*4+78h]
0x1400108bc  cmp     ecx, 80h
0x1400108c2  jb      loc_140010EF8
0x1400108c8  mov     edx, [rbx+10h]
0x1400108cb  cmp     ecx, edx
0x1400108cd  jnb     loc_140010EF8
0x1400108d3  mov     r9d, ecx
0x1400108d6  mov     ecx, [rcx+rbx]
0x1400108d9  cmp     ecx, 40h ; '@'
0x1400108dc  jnz     loc_14001143C
0x1400108e2  lea     rcx, [r9+28h]
0x1400108e6  cmp     rcx, rdx
0x1400108e9  ja      loc_140010EF8
0x1400108ef  mov     [r9+rbx+10h], r15
0x1400108f4  mov     rcx, [r8]; FdoExtension
0x1400108f7  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x1400108fc  cmp     byte ptr [rbx+2], 28h ; '('
0x140010900  movzx   r15d, al
0x140010904  jnz     loc_1400109FA
0x14001090a  cmp     [rbx+14h], r14d
0x14001090e  jnz     loc_1400109FE
0x140010914  mov     r10d, [rbx+38h]
0x140010918  mov     r8d, r14d
0x14001091b  test    r10d, r10d
0x14001091e  jz      loc_1400109FE
0x140010924  mov     eax, r8d
0x140010927  mov     ecx, [rbx+rax*4+78h]
0x14001092b  cmp     ecx, 80h
0x140010931  jb      loc_140010F8D
0x140010937  mov     edx, [rbx+10h]
0x14001093a  cmp     ecx, edx
0x14001093c  jnb     loc_140010F8D
  ... truncated ...
```
