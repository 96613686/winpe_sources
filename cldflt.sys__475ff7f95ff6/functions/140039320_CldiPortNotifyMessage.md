# CldiPortNotifyMessage

- ea: `0x140039320`
- end: `0x14003a055`
- name: `CldiPortNotifyMessage`
- size: `3381`
- prototype: `__int64 __fastcall(_QWORD *PortCookie, UCHAR *InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x14000dbd0`
- `0x14000e310`
- `0x14000e3d4`
- `0x14000e468`
- `0x14000e764`
- `0x1400368d0`
- `0x140037030`
- `0x140038b8c`
- `0x140039320`
- `0x14003a938`
- `0x14003bb10`
- `0x140056090`
- `0x14007cb14`
- `0x14007e674`
- `0x14007f484`
- `0x1400824e8`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039640`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039640`
- `ntoskrnl!RtlComputeCrc32` at `0x140039690`
- `ntoskrnl!RtlComputeCrc32` at `0x140039690`
- `ntoskrnl!PsGetProcessId` at `0x1400393e5`
- `ntoskrnl!PsGetProcessId` at `0x1400393e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a014`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a014`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a032`
- `ntoskrnl!ExAllocatePool2` at `0x1400394c6`
- `ntoskrnl!ExAllocatePool2` at `0x140039585`
- `ntoskrnl!ExAllocatePool2` at `0x1400394c6`
- `ntoskrnl!ExAllocatePool2` at `0x140039585`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003937b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393d6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039413`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003937b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393d6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039413`

## pseudocode

```c
__int64 __fastcall CldiPortNotifyMessage(
        _QWORD *PortCookie,
        UCHAR *InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  size_t v7; // r15
  _QWORD *Pool2; // rsi
  ULONG v10; // edi
  unsigned int RangeInfo; // r13d
  struct _KPROCESS *CurrentProcess; // rax
  char ProcessId; // bl
  __int64 v14; // rdi
  __int64 v15; // rsi
  int v16; // r14d
  __int64 v17; // r15
  struct _DEVICE_OBJECT *AttachedDevice; // r12
  char v19; // al
  PVOID v20; // r14
  int v21; // edx
  int v22; // r8d
  ULONG v23; // r14d
  __int64 v24; // r8
  UCHAR *v25; // rdi
  __int64 v26; // r8
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // r9
  char v30; // r12
  UCHAR v31; // r13
  unsigned __int64 v32; // rdx
  __int64 v33; // r9
  unsigned __int64 v34; // r11
  unsigned int i; // r10d
  unsigned int v36; // eax
  unsigned __int64 v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned __int16 v40; // r9
  unsigned __int64 v41; // rcx
  unsigned int v42; // eax
  int v43; // eax
  __int64 v44; // rax
  unsigned int v45; // r8d
  unsigned __int16 v46; // r9
  unsigned __int64 v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // eax
  __int64 v51; // rcx
  int v52; // r14d
  __int64 v53; // rax
  unsigned int v54; // r8d
  unsigned __int16 v55; // r9
  unsigned __int64 v56; // rdx
  unsigned int v57; // eax
  int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // rax
  unsigned int v62; // r8d
  unsigned __int16 v63; // r9
  unsigned __int64 v64; // rdx
  unsigned int v65; // eax
  __int64 v66; // rax
  unsigned int v67; // r8d
  unsigned __int16 v68; // r9
  unsigned __int64 v69; // rdx
  unsigned int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  UCHAR *v74; // [rsp+20h] [rbp-C8h]
  int v75; // [rsp+28h] [rbp-C0h]
  size_t Size; // [rsp+30h] [rbp-B8h]
  size_t Sizea; // [rsp+30h] [rbp-B8h]
  ULONG v78; // [rsp+38h] [rbp-B0h]
  int v79; // [rsp+40h] [rbp-A8h]
  int v80; // [rsp+40h] [rbp-A8h]
  char v81; // [rsp+48h] [rbp-A0h]
  unsigned __int16 v82; // [rsp+80h] [rbp-68h]
  ULONG v83; // [rsp+84h] [rbp-64h]
  _QWORD *v84; // [rsp+90h] [rbp-58h]
  int v85[2]; // [rsp+98h] [rbp-50h]
  int v86[2]; // [rsp+A0h] [rbp-48h]
  UCHAR *P; // [rsp+A8h] [rbp-40h]
  char v90; // [rsp+100h] [rbp+18h]

  v90 = InputBufferLength;
  v7 = InputBufferLength;
  P = 0;
  v82 = 0;
  *(_QWORD *)v86 = 0;
  *(_QWORD *)v85 = 0;
  Pool2 = 0;
  v84 = 0;
  v10 = 0;
  v83 = 0;
  if ( (PEPROCESS)PortCookie[9] == IoGetCurrentProcess() )
  {
    PortCookie[4] = MEMORY[0xFFFFF78000000014];
    if ( OutputBuffer )
    {
      v23 = OutputBufferLength;
      if ( OutputBufferLength )
      {
        v83 = OutputBufferLength;
        Pool2 = (_QWORD *)ExAllocatePool2(256, OutputBufferLength, 1112501315);
        v84 = Pool2;
        if ( !Pool2 )
        {
          RangeInfo = -1073741670;
          HsmDbgBreakOnStatus(3221225626LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v20 = OutputBuffer;
            WPP_SF_qPDPDd(
              WPP_GLOBAL_Control->AttachedDevice,
              133,
              v24,
              PortCookie,
              InputBuffer,
              v7,
              OutputBuffer,
              OutputBufferLength,
              -1073741670);
LABEL_13:
            v10 = v83;
            goto LABEL_180;
          }
LABEL_178:
          v10 = v83;
LABEL_179:
          v20 = OutputBuffer;
          goto LABEL_180;
        }
      }
    }
    else
    {
      v23 = OutputBufferLength;
    }
    v25 = (UCHAR *)ExAllocatePool2(258, v7, 1936550979);
    P = v25;
    if ( !v25 )
    {
      RangeInfo = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v20 = OutputBuffer;
          goto LABEL_21;
        }
        v28 = 134;
        v79 = -1073741670;
        v78 = v23;
        v20 = OutputBuffer;
        Sizea = (size_t)OutputBuffer;
        v75 = v7;
        v74 = InputBuffer;
        v29 = PortCookie;
        goto LABEL_20;
      }
LABEL_177:
      Pool2 = v84;
      goto LABEL_178;
    }
    if ( (_DWORD)v7 && ((unsigned __int8)InputBuffer & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v25, InputBuffer, v7);
    v30 = 0;
    v31 = 0;
    if ( (unsigned int)v7 >= 0x18
      && *(_DWORD *)v25 == 1886219331
      && ((v25[12] & 2) == 0 || *((_DWORD *)v25 + 1) == RtlComputeCrc32(0, v25 + 8, v7 - 8)) )
    {
      v32 = *((unsigned int *)v25 + 2);
      if ( (unsigned int)v7 >= (unsigned int)v32 )
      {
        v33 = *((unsigned __int16 *)v25 + 7);
        if ( (_WORD)v33 )
        {
          v34 = 8 * v33 + 16;
          if ( v34 < v32 )
          {
            for ( i = 0; ; ++i )
            {
              v36 = *((unsigned __int16 *)v25 + 7);
              if ( (unsigned __int16)v33 >= 0x17u )
                v36 = 23;
              if ( i >= v36 )
                break;
              if ( *(_WORD *)&v25[8 * i + 16] >= 0x12u )
                goto LABEL_59;
              v37 = *(unsigned int *)&v25[8 * i + 20];
              if ( (_DWORD)v37 )
              {
                if ( v37 < v34 )
                  goto LABEL_59;
              }
              if ( (unsigned int)v37 > (unsigned int)v32 )
                goto LABEL_59;
              v38 = *(unsigned __int16 *)&v25[8 * i + 18];
              if ( v38 > (unsigned int)v32 )
                goto LABEL_59;
              v39 = v37 + v38;
              if ( v39 < (unsigned int)v37 || v39 > (unsigned int)v32 )
                goto LABEL_59;
            }
            if ( (unsigned int)v32 >= 0x18 )
            {
              if ( (v40 = *((_WORD *)v25 + 8), v40 < 0x12u)
                && ((v41 = *((unsigned int *)v25 + 5), !(_DWORD)v41) || v41 >= v34)
                && (unsigned int)v41 <= (unsigned int)v32
                && (v42 = *((unsigned __int16 *)v25 + 9), v42 <= (unsigned int)v32)
                && v42 + (unsigned int)v41 >= (unsigned int)v41
                && v42 + (unsigned int)v41 <= (unsigned int)v32
                && v40 == 7
                && (_WORD)v42 == 1 )
              {
                v31 = v25[v41];
                v43 = 0;
              }
              else
              {
                v43 = -1073741275;
              }
              if ( v43 >= 0 && v31 <= 1u )
                v30 = 1;
            }
          }
        }
      }
    }
LABEL_59:
    if ( !v30 )
    {
      RangeInfo = -1073741811;
      HsmDbgBreakOnStatus(3221225485LL);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_177;
      }
      v20 = OutputBuffer;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_21;
      v28 = 136;
      v79 = -1073741811;
      v78 = OutputBufferLength;
      Sizea = (size_t)OutputBuffer;
      v75 = v7;
      v74 = v25;
LABEL_64:
      v29 = PortCookie;
LABEL_20:
      WPP_SF_qPDPDd(v27->AttachedDevice, v28, v26, v29, v74, v75, Sizea, v78, v79);
LABEL_21:
      Pool2 = v84;
      goto LABEL_13;
    }
    if ( (unsigned int)v7 >= 0x18
      && (v44 = *((unsigned __int16 *)v25 + 7), (unsigned __int16)v44 > 1u)
      && (v45 = *((_DWORD *)v25 + 2), v45 >= 0x20)
      && (v46 = *((_WORD *)v25 + 12), v46 < 0x12u)
      && ((v47 = *((unsigned int *)v25 + 7), !(_DWORD)v47) || v47 >= 8 * v44 + 16)
      && (unsigned int)v47 <= v45
      && (v48 = *((unsigned __int16 *)v25 + 13), v48 <= v45)
      && v48 + (unsigned int)v47 >= (unsigned int)v47
      && v48 + (unsigned int)v47 <= v45
      && v46 == 8
      && v48 == 2 )
    {
      v82 = *(_WORD *)&v25[v47];
      RangeInfo = 0;
    }
    else
    {
      RangeInfo = -1073741275;
    }
    HsmDbgBreakOnStatus(RangeInfo);
    if ( (RangeInfo & 0x80000000) != 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_177;
      }
      v20 = OutputBuffer;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_21;
      v28 = 137;
      goto LABEL_84;
    }
    if ( (unsigned __int16)(v82 + 0x3FFF) <= 4u )
    {
      if ( v82 == 0xC001 )
      {
        RangeInfo = HsmpCheckLegacyFilterAbsence();
        HsmDbgBreakOnStatus(RangeInfo);
        if ( (RangeInfo & 0x80000000) != 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_452df49304b034ad87c0baec305776b3_Traceguids, RangeInfo);
        }
      }
      else
      {
        if ( v82 == 0xC005 )
        {
          Pool2 = v84;
          RangeInfo = CldiPortAddCrossVmProgressEvent(v25, (unsigned int)v7, v84, v83);
LABEL_96:
          HsmDbgBreakOnStatus(RangeInfo);
          v49 = RangeInfo;
LABEL_97:
          HsmDbgBreakOnStatus(v49);
          goto LABEL_178;
        }
        RangeInfo = -1073741822;
      }
      Pool2 = v84;
      goto LABEL_96;
    }
    if ( (unsigned __int16)(v82 - 16385) <= 1u )
    {
      Pool2 = v84;
      RangeInfo = CldiPortProcessFilterControl((_DWORD)PortCookie, v82, (_DWORD)v25, v7, (__int64)v84, v83);
      v49 = RangeInfo;
      goto LABEL_97;
    }
    PortCookie[6] = MEMORY[0xFFFFF78000000014];
    if ( (unsigned __int16)(v82 - 1) <= 6u )
    {
      v50 = CldiPortProcessServiceCommands(PortCookie, v82, v25, (unsigned int)v7);
      goto LABEL_102;
    }
    if ( (unsigned int)v7 < 0x18 )
      goto LABEL_135;
    v52 = 0;
    v53 = *((unsigned __int16 *)v25 + 7);
    if ( (unsigned __int16)v53 <= 8u
      || (v54 = *((_DWORD *)v25 + 2), v54 < 0x58)
      || (v55 = *((_WORD *)v25 + 40), v55 >= 0x12u)
      || (v56 = *((unsigned int *)v25 + 21), (_DWORD)v56) && v56 < 8 * v53 + 16
      || (unsigned int)v56 > v54
      || (v57 = *((unsigned __int16 *)v25 + 41), v57 > v54)
      || v57 + (unsigned int)v56 < (unsigned int)v56
      || v57 + (unsigned int)v56 > v54
      || v55 != 17 )
    {
      v58 = -1073741275;
    }
    else
    {
      v52 = *((unsigned __int16 *)v25 + 41);
      v58 = 0;
    }
    if ( v58 >= 0 && v52 != 130 )
    {
      RangeInfo = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v80 = v52;
        v20 = OutputBuffer;
        WPP_SF_qPDPDDDd(
          WPP_GLOBAL_Control->AttachedDevice,
          v59,
          v60,
          PortCookie,
          InputBuffer,
          v7,
          OutputBuffer,
          OutputBufferLength,
          v80);
        goto LABEL_21;
      }
      goto LABEL_177;
    }
    if ( (v61 = *((unsigned __int16 *)v25 + 7), (unsigned __int16)v61 > 4u)
      && (v62 = *((_DWORD *)v25 + 2), v62 >= 0x38)
      && (v63 = *((_WORD *)v25 + 24), v63 < 0x12u)
      && ((v64 = *((unsigned int *)v25 + 13), !(_DWORD)v64) || v64 >= 8 * v61 + 16)
      && (unsigned int)v64 <= v62
      && (v65 = *((unsigned __int16 *)v25 + 25), v65 <= v62)
      && v65 + (unsigned int)v64 >= (unsigned int)v64
      && v65 + (unsigned int)v64 <= v62
      && v63 == 6
      && (_WORD)v65 == 8 )
    {
      *(_QWORD *)v86 = *(_QWORD *)&v25[v64];
      RangeInfo = 0;
    }
    else
    {
LABEL_135:
      RangeInfo = -1073741275;
    }
    HsmDbgBreakOnStatus(RangeInfo);
    if ( (RangeInfo & 0x80000000) == 0 )
    {
      if ( (unsigned int)v7 >= 0x18
        && (v66 = *((unsigned __int16 *)v25 + 7), (unsigned __int16)v66 > 7u)
        && (v67 = *((_DWORD *)v25 + 2), v67 >= 0x50)
        && (v68 = *((_WORD *)v25 + 36), v68 < 0x12u)
        && ((v69 = *((unsigned int *)v25 + 19), !(_DWORD)v69) || v69 >= 8 * v66 + 16)
        && (unsigned int)v69 <= v67
        && (v70 = *((unsigned __int16 *)v25 + 37), v70 <= v67)
        && v70 + (unsigned int)v69 >= (unsigned int)v69
        && v70 + (unsigned int)v69 <= v67
        && v68 == 6
        && (_WORD)v70 == 8 )
      {
        *(_QWORD *)v85 = *(_QWORD *)&v25[v69];
        RangeInfo = 0;
      }
      else
      {
        RangeInfo = -1073741275;
      }
      HsmDbgBreakOnStatus(RangeInfo);
      if ( (RangeInfo & 0x80000000) == 0 )
      {
        if ( v82 != 513 )
        {
          RangeInfo = CldiPortAccessCheck(PortCookie, *(_QWORD *)v86, *(_QWORD *)v85);
          HsmDbgBreakOnStatus(RangeInfo);
          if ( (RangeInfo & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qiild(
                WPP_GLOBAL_Control->AttachedDevice,
                v71,
                v72,
                PortCookie,
                *(_QWORD *)v86,
                *(_QWORD *)v85,
                v82,
                RangeInfo);
            }
            goto LABEL_177;
          }
        }
        if ( v82 == 0xD001 )
        {
          if ( v84 && v83 == 8 )
            *v84 = 0;
          LODWORD(Size) = v83;
          RangeInfo = CldiPortProcessGetRangeInfo((int)PortCookie, v86[0], v85[0], (int)v25, v7, v84, Size);
          HsmDbgBreakOnStatus(RangeInfo);
          v51 = RangeInfo;
          goto LABEL_103;
        }
        CldiPortSetSyncStatus((_DWORD)PortCookie, v86[0], v85[0], (_DWORD)v25, v7);
        if ( (unsigned __int16)(v82 - 257) > 5u )
        {
          if ( v82 != 513 )
          {
            v51 = 3221278475LL;
            RangeInfo = -1073688821;
            goto LABEL_103;
          }
          v50 = CldiPortProcessAckNotification((_DWORD)PortCookie, v86[0], v85[0], (_DWORD)v25, v7);
        }
        else
        {
          v50 = CldiPortProcessTransfer((_DWORD)PortCookie, v86[0], v85[0], v82, (__int64)v25, v7, (__int64)v84, v83);
        }
LABEL_102:
        RangeInfo = v50;
        v51 = v50;
LABEL_103:
        HsmDbgBreakOnStatus(v51);
        goto LABEL_177;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_177;
      }
      v20 = OutputBuffer;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_21;
      v28 = 140;
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_177;
      }
      v20 = OutputBuffer;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_21;
      v28 = 139;
    }
LABEL_84:
    v79 = RangeInfo;
    v78 = OutputBufferLength;
    Sizea = (size_t)v20;
    v75 = v7;
    v74 = InputBuffer;
    goto LABEL_64;
  }
  RangeInfo = -1073688808;
  HsmDbgBreakOnStatus(3221278488LL);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_179;
  }
  CurrentProcess = IoGetCurrentProcess();
  ProcessId = (unsigned __int8)PsGetProcessId(CurrentProcess);
  v14 = PortCookie[11];
  v15 = PortCookie[10];
  v16 = *((_DWORD *)PortCookie + 24);
  v17 = PortCookie[9];
  AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
  v19 = (unsigned __int8)IoGetCurrentProcess();
  v81 = v16;
  v20 = OutputBuffer;
  WPP_SF_qPDPDqDZZqDd(
    (_DWORD)AttachedDevice,
    v21,
    v22,
    (_DWORD)PortCookie,
    (char)InputBuffer,
    v90,
    (char)OutputBuffer,
    OutputBufferLength,
    v17,
    v81,
    v15,
    v14,
    v19,
    ProcessId);
  Pool2 = 0;
  v10 = 0;
LABEL_180:
  if ( v20 && Pool2 )
    RtlCopyToUser(v20, Pool2, v10);
  else
    v10 = 0;
  *ReturnOutputBufferLength = v10;
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x424F6C43u);
  if ( P )
    ExFreePoolWithTag(P, 0x736D6C43u);
  return RangeInfo;
}

```

## disassembly

```asm
0x140039320  mov     rax, rsp
0x140039323  mov     [rax+20h], r9
0x140039327  mov     [rax+18h], r8d
0x14003932b  mov     [rax+10h], rdx
0x14003932f  mov     [rax+8], rcx
0x140039333  push    rbx
0x140039334  push    rsi
0x140039335  push    rdi
0x140039336  push    r12
0x140039338  push    r13
0x14003933a  push    r14
0x14003933c  push    r15
0x14003933e  sub     rsp, 0B0h
0x140039345  mov     r13, r9
0x140039348  mov     r15d, r8d
0x14003934b  mov     r12, rcx
0x14003934e  xor     ebx, ebx
0x140039350  mov     [rsp+0E8h+P], rbx
0x140039358  mov     word ptr [rsp+0E8h+var_68], bx
0x140039360  mov     [rax-48h], rbx
0x140039364  mov     [rax-50h], rbx
0x140039368  mov     esi, ebx
0x14003936a  mov     [rsp+0E8h+var_58], rbx
0x140039372  mov     edi, ebx
0x140039374  mov     [rsp+0E8h+var_64], ebx
0x14003937b  call    cs:__imp_IoGetCurrentProcess
0x140039382  nop     dword ptr [rax+rax+00h]
0x140039387  cmp     [r12+48h], rax
0x14003938c  jz      loc_140039487
0x140039392  mov     r13d, 0C000CF18h
0x140039398  mov     [rsp+0E8h+var_68], r13d
0x1400393a0  mov     ecx, r13d
0x1400393a3  call    HsmDbgBreakOnStatus
0x1400393a8  lea     rax, WPP_GLOBAL_Control
0x1400393af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400393b6  cmp     rcx, rax
0x1400393b9  jz      loc_140039FC0
0x1400393bf  test    dword ptr [rcx+2Ch], 100h
0x1400393c6  jz      loc_140039FC0
0x1400393cc  cmp     byte ptr [rcx+29h], 2
0x1400393d0  jb      loc_140039FC0
0x1400393d6  call    cs:__imp_IoGetCurrentProcess
0x1400393dd  nop     dword ptr [rax+rax+00h]
0x1400393e2  mov     rcx, rax; Process
0x1400393e5  call    cs:__imp_PsGetProcessId
0x1400393ec  nop     dword ptr [rax+rax+00h]
0x1400393f1  mov     rbx, rax
0x1400393f4  mov     rdi, [r12+58h]
0x1400393f9  mov     rsi, [r12+50h]
0x1400393fe  mov     r14d, [r12+60h]
0x140039403  mov     r15, [r12+48h]
0x140039408  mov     rax, cs:WPP_GLOBAL_Control
0x14003940f  mov     r12, [rax+18h]
0x140039413  call    cs:__imp_IoGetCurrentProcess
0x14003941a  nop     dword ptr [rax+rax+00h]
0x14003941f  mov     [rsp+0E8h+var_80], ebx
0x140039423  mov     [rsp+0E8h+var_88], rax
0x140039428  mov     [rsp+0E8h+var_90], rdi
0x14003942d  mov     [rsp+0E8h+var_98], rsi
0x140039432  mov     dword ptr [rsp+0E8h+var_A0], r14d
0x140039437  mov     [rsp+0E8h+var_A8], r15
0x14003943c  mov     eax, [rsp+0E8h+OutputBufferLength]
0x140039443  mov     [rsp+0E8h+var_B0], eax
0x140039447  mov     r14, [rsp+0E8h+arg_18]
0x14003944f  mov     [rsp+0E8h+Size], r14
0x140039454  mov     eax, [rsp+0E8h+arg_10]
0x14003945b  mov     dword ptr [rsp+0E8h+var_C0], eax
0x14003945f  mov     rax, [rsp+0E8h+Src]
0x140039467  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14003946c  mov     r9, qword ptr [rsp+0E8h+arg_0]
0x140039474  mov     rcx, r12
0x140039477  call    WPP_SF_qPDPDqDZZqDd
0x14003947c  xor     ebx, ebx
0x14003947e  mov     esi, ebx
0x140039480  mov     edi, ebx
0x140039482  jmp     loc_140039FC8
0x140039487  mov     rax, ds:0FFFFF78000000014h
0x140039491  mov     [r12+20h], rax
0x140039496  test    r13, r13
0x140039499  jz      loc_14003956F
0x14003949f  mov     r14d, [rsp+0E8h+OutputBufferLength]
0x1400394a7  test    r14d, r14d
0x1400394aa  jz      loc_140039577
0x1400394b0  mov     [rsp+0E8h+var_64], r14d
0x1400394b8  mov     edx, r14d
0x1400394bb  mov     ecx, 100h
0x1400394c0  mov     r8d, 424F6C43h
0x1400394c6  call    cs:__imp_ExAllocatePool2
0x1400394cd  nop     dword ptr [rax+rax+00h]
0x1400394d2  mov     rsi, rax
0x1400394d5  mov     [rsp+0E8h+var_58], rax
0x1400394dd  test    rax, rax
0x1400394e0  jnz     loc_140039577
0x1400394e6  mov     edi, 0C000009Ah
0x1400394eb  mov     r13d, edi
0x1400394ee  mov     [rsp+0E8h+var_68], edi
0x1400394f5  mov     ecx, edi
0x1400394f7  call    HsmDbgBreakOnStatus
0x1400394fc  lea     rax, WPP_GLOBAL_Control
0x140039503  mov     rcx, cs:WPP_GLOBAL_Control
0x14003950a  cmp     rcx, rax
0x14003950d  jz      loc_140039FB9
0x140039513  test    dword ptr [rcx+2Ch], 100h
0x14003951a  jz      loc_140039FB9
0x140039520  cmp     byte ptr [rcx+29h], 2
0x140039524  jb      loc_140039FB9
0x14003952a  mov     edx, 85h
0x14003952f  mov     dword ptr [rsp+0E8h+var_A8], edi
0x140039533  mov     [rsp+0E8h+var_B0], r14d
0x140039538  mov     r14, [rsp+0E8h+arg_18]
0x140039540  mov     [rsp+0E8h+Size], r14
0x140039545  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x14003954a  mov     rax, [rsp+0E8h+Src]
0x140039552  mov     qword ptr [rsp+0E8h+var_C8], rax
0x140039557  mov     r9, r12
0x14003955a  mov     rcx, [rcx+18h]
0x14003955e  call    WPP_SF_qPDPDd
0x140039563  mov     edi, [rsp+0E8h+var_64]
0x14003956a  jmp     loc_140039FC8
0x14003956f  mov     r14d, [rsp+0E8h+OutputBufferLength]
0x140039577  mov     r8d, 736D6C43h
0x14003957d  mov     rdx, r15
0x140039580  mov     ecx, 102h
0x140039585  call    cs:__imp_ExAllocatePool2
0x14003958c  nop     dword ptr [rax+rax+00h]
0x140039591  mov     rdi, rax
0x140039594  mov     [rsp+0E8h+P], rax
0x14003959c  test    rax, rax
0x14003959f  jnz     loc_14003962F
0x1400395a5  mov     edi, 0C000009Ah
0x1400395aa  mov     r13d, edi
0x1400395ad  mov     [rsp+0E8h+var_68], edi
0x1400395b4  mov     ecx, edi
0x1400395b6  call    HsmDbgBreakOnStatus
0x1400395bb  lea     rax, WPP_GLOBAL_Control
0x1400395c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395c9  cmp     rcx, rax
0x1400395cc  jz      loc_140039FB1
0x1400395d2  test    dword ptr [rcx+2Ch], 100h
0x1400395d9  jz      loc_140039FB1
0x1400395df  cmp     byte ptr [rcx+29h], 2
0x1400395e3  jb      loc_140039FA4
0x1400395e9  mov     edx, 86h
0x1400395ee  mov     dword ptr [rsp+0E8h+var_A8], edi
0x1400395f2  mov     [rsp+0E8h+var_B0], r14d
0x1400395f7  mov     r14, [rsp+0E8h+arg_18]
0x1400395ff  mov     [rsp+0E8h+Size], r14
0x140039604  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x140039609  mov     rax, [rsp+0E8h+Src]
0x140039611  mov     qword ptr [rsp+0E8h+var_C8], rax
0x140039616  mov     r9, r12
0x140039619  mov     rcx, [rcx+18h]
0x14003961d  call    WPP_SF_qPDPDd
0x140039622  mov     rsi, [rsp+0E8h+var_58]
0x14003962a  jmp     loc_140039563
0x14003962f  mov     rax, [rsp+0E8h+Src]
0x140039637  test    r15d, r15d
0x14003963a  jz      short loc_14003964D
0x14003963c  test    al, 3
0x14003963e  jz      short loc_14003964D
0x140039640  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140039647  nop     dword ptr [rax+rax+00h]
0x14003964c  int     3; Trap to Debugger
0x14003964d  mov     r8, r15; Size
0x140039650  mov     rdx, rax; Src
0x140039653  mov     rcx, rdi; void *
0x140039656  call    RtlCopyFromUser
0x14003965b  mov     [rsp+0E8h+var_64+4], r15d
0x140039663  movzx   r12d, bl
0x140039667  mov     r13b, bl
0x14003966a  cmp     r15d, 18h
0x14003966e  jb      loc_1400397A3
0x140039674  cmp     dword ptr [rdi], 706D6C43h
0x14003967a  jnz     loc_1400397A3
0x140039680  test    byte ptr [rdi+0Ch], 2
0x140039684  jz      short loc_1400396A5
0x140039686  lea     r8d, [r15-8]; Length
0x14003968a  lea     rdx, [rdi+8]; Buffer
0x14003968e  xor     ecx, ecx; InitialCrc
0x140039690  call    cs:__imp_RtlComputeCrc32
0x140039697  nop     dword ptr [rax+rax+00h]
0x14003969c  cmp     [rdi+4], eax
0x14003969f  jnz     loc_1400397A3
0x1400396a5  mov     edx, [rdi+8]
0x1400396a8  cmp     r15d, edx
0x1400396ab  jb      loc_1400397A3
0x1400396b1  movzx   r9d, word ptr [rdi+0Eh]
0x1400396b6  test    r9w, r9w
0x1400396ba  jz      loc_1400397A3
0x1400396c0  lea     r11, ds:10h[r9*8]
0x1400396c8  cmp     r11, rdx
0x1400396cb  jnb     loc_1400397A3
0x1400396d1  mov     r10d, ebx
0x1400396d4  mov     esi, 17h
0x1400396d9  lea     r14d, [rsi-16h]
0x1400396dd  cmp     r9w, si
0x1400396e1  mov     eax, r9d
0x1400396e4  jb      short loc_1400396E8
0x1400396e6  mov     eax, esi
0x1400396e8  cmp     r10d, eax
0x1400396eb  jnb     short loc_140039734
0x1400396ed  mov     r8d, r10d
0x1400396f0  cmp     word ptr [rdi+r8*8+10h], 12h
0x1400396f7  jnb     loc_1400397A9
0x1400396fd  mov     ecx, [rdi+r8*8+14h]
0x140039702  test    ecx, ecx
0x140039704  jz      short loc_14003970F
0x140039706  cmp     rcx, r11
0x140039709  jb      loc_1400397A9
0x14003970f  cmp     ecx, edx
0x140039711  ja      loc_1400397A9
0x140039717  movzx   eax, word ptr [rdi+r8*8+12h]
0x14003971d  cmp     eax, edx
0x14003971f  ja      loc_1400397A9
0x140039725  add     eax, ecx
0x140039727  cmp     eax, ecx
0x140039729  jb      short loc_1400397A9
0x14003972b  cmp     eax, edx
0x14003972d  ja      short loc_1400397A9
0x14003972f  add     r10d, r14d
0x140039732  jmp     short loc_1400396DD
0x140039734  cmp     edx, 18h
0x140039737  jb      short loc_1400397A9
0x140039739  cmp     bx, r9w
0x14003973d  jnb     short loc_14003978F
0x14003973f  movzx   r9d, word ptr [rdi+10h]
0x140039744  cmp     r9w, 12h
0x140039749  jnb     short loc_14003978F
0x14003974b  mov     ecx, [rdi+14h]
0x14003974e  test    ecx, ecx
0x140039750  jz      short loc_140039757
0x140039752  cmp     rcx, r11
0x140039755  jb      short loc_14003978F
0x140039757  cmp     ecx, edx
0x140039759  ja      short loc_14003978F
0x14003975b  movzx   eax, word ptr [rdi+12h]
0x14003975f  cmp     eax, edx
0x140039761  ja      short loc_14003978F
0x140039763  lea     r8d, [rax+rcx]
0x140039767  cmp     r8d, ecx
0x14003976a  jb      short loc_14003978F
0x14003976c  cmp     r8d, edx
0x14003976f  ja      short loc_14003978F
0x140039771  mov     edx, 7
0x140039776  cmp     r9w, dx
0x14003977a  jnz     short loc_14003978F
0x14003977c  cmp     ax, r14w
0x140039780  jnz     short loc_14003978F
0x140039782  mov     r13b, [rcx+rdi]
0x140039786  mov     eax, ebx
0x140039788  mov     esi, 0C0000225h
0x14003978d  jmp     short loc_140039796
0x14003978f  mov     esi, 0C0000225h
0x140039794  mov     eax, esi
0x140039796  test    eax, eax
0x140039798  js      short loc_1400397AE
0x14003979a  cmp     r13b, r14b
0x14003979d  cmovbe  r12d, r14d
0x1400397a1  jmp     short loc_1400397AE
0x1400397a3  mov     r14d, 1
0x1400397a9  mov     esi, 0C0000225h
0x1400397ae  test    r12b, r12b
0x1400397b1  jnz     short loc_140039830
0x1400397b3  mov     r13d, 0C000000Dh
0x1400397b9  mov     [rsp+0E8h+var_68], r13d
0x1400397c1  mov     ecx, r13d
0x1400397c4  call    HsmDbgBreakOnStatus
0x1400397c9  lea     rax, WPP_GLOBAL_Control
0x1400397d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400397d7  cmp     rcx, rax
0x1400397da  jz      loc_140039FB1
0x1400397e0  test    dword ptr [rcx+2Ch], 100h
0x1400397e7  jz      loc_140039FB1
0x1400397ed  mov     r14, [rsp+0E8h+arg_18]
0x1400397f5  cmp     byte ptr [rcx+29h], 2
0x1400397f9  jb      loc_140039622
0x1400397ff  mov     edx, 88h
0x140039804  mov     dword ptr [rsp+0E8h+var_A8], r13d
0x140039809  mov     eax, [rsp+0E8h+OutputBufferLength]
0x140039810  mov     [rsp+0E8h+var_B0], eax
0x140039814  mov     [rsp+0E8h+Size], r14
0x140039819  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x14003981e  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x140039823  mov     r9, qword ptr [rsp+0E8h+arg_0]
0x14003982b  jmp     loc_140039619
0x140039830  cmp     r15d, 18h
0x140039834  jb      short loc_1400398A6
0x140039836  movzx   eax, word ptr [rdi+0Eh]
0x14003983a  cmp     r14w, ax
0x14003983e  jnb     short loc_1400398A6
0x140039840  mov     r8d, [rdi+8]
0x140039844  cmp     r8d, 20h ; ' '
0x140039848  jb      short loc_1400398A6
0x14003984a  movzx   r9d, word ptr [rdi+18h]
0x14003984f  cmp     r9w, 12h
0x140039854  jnb     short loc_1400398A6
0x140039856  mov     edx, [rdi+1Ch]
0x140039859  test    edx, edx
0x14003985b  jz      short loc_14003986A
0x14003985d  lea     rcx, ds:10h[rax*8]
  ... truncated ...
```
