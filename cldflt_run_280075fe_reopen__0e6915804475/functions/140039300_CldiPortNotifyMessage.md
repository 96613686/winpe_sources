# CldiPortNotifyMessage

- ea: `0x140039300`
- end: `0x14003a035`
- name: `CldiPortNotifyMessage`
- size: `3381`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
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
- `0x1400368b0`
- `0x140037010`
- `0x140038b6c`
- `0x140039300`
- `0x14003a918`
- `0x14003baf0`
- `0x140055f70`
- `0x14007c9d4`
- `0x14007e4dc`
- `0x14007f2ec`
- `0x140082348`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039620`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039620`
- `ntoskrnl!RtlComputeCrc32` at `0x140039670`
- `ntoskrnl!RtlComputeCrc32` at `0x140039670`
- `ntoskrnl!PsGetProcessId` at `0x1400393c5`
- `ntoskrnl!PsGetProcessId` at `0x1400393c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039ff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039ff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a012`
- `ntoskrnl!ExAllocatePool2` at `0x1400394a6`
- `ntoskrnl!ExAllocatePool2` at `0x140039565`
- `ntoskrnl!ExAllocatePool2` at `0x1400394a6`
- `ntoskrnl!ExAllocatePool2` at `0x140039565`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003935b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393b6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393f3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003935b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393b6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400393f3`

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
      v50 = CldiPortProcessServiceCommands((__int64)PortCookie, v82, (__int64)v25, v7);
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
0x140039300  mov     rax, rsp
0x140039303  mov     [rax+20h], r9
0x140039307  mov     [rax+18h], r8d
0x14003930b  mov     [rax+10h], rdx
0x14003930f  mov     [rax+8], rcx
0x140039313  push    rbx
0x140039314  push    rsi
0x140039315  push    rdi
0x140039316  push    r12
0x140039318  push    r13
0x14003931a  push    r14
0x14003931c  push    r15
0x14003931e  sub     rsp, 0B0h
0x140039325  mov     r13, r9
0x140039328  mov     r15d, r8d
0x14003932b  mov     r12, rcx
0x14003932e  xor     ebx, ebx
0x140039330  mov     [rsp+0E8h+P], rbx
0x140039338  mov     word ptr [rsp+0E8h+var_68], bx
0x140039340  mov     [rax-48h], rbx
0x140039344  mov     [rax-50h], rbx
0x140039348  mov     esi, ebx
0x14003934a  mov     [rsp+0E8h+var_58], rbx
0x140039352  mov     edi, ebx
0x140039354  mov     [rsp+0E8h+var_64], ebx
0x14003935b  call    cs:__imp_IoGetCurrentProcess
0x140039362  nop     dword ptr [rax+rax+00h]
0x140039367  cmp     [r12+48h], rax
0x14003936c  jz      loc_140039467
0x140039372  mov     r13d, 0C000CF18h
0x140039378  mov     [rsp+0E8h+var_68], r13d
0x140039380  mov     ecx, r13d
0x140039383  call    HsmDbgBreakOnStatus
0x140039388  lea     rax, WPP_GLOBAL_Control
0x14003938f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039396  cmp     rcx, rax
0x140039399  jz      loc_140039FA0
0x14003939f  test    dword ptr [rcx+2Ch], 100h
0x1400393a6  jz      loc_140039FA0
0x1400393ac  cmp     byte ptr [rcx+29h], 2
0x1400393b0  jb      loc_140039FA0
0x1400393b6  call    cs:__imp_IoGetCurrentProcess
0x1400393bd  nop     dword ptr [rax+rax+00h]
0x1400393c2  mov     rcx, rax; Process
0x1400393c5  call    cs:__imp_PsGetProcessId
0x1400393cc  nop     dword ptr [rax+rax+00h]
0x1400393d1  mov     rbx, rax
0x1400393d4  mov     rdi, [r12+58h]
0x1400393d9  mov     rsi, [r12+50h]
0x1400393de  mov     r14d, [r12+60h]
0x1400393e3  mov     r15, [r12+48h]
0x1400393e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400393ef  mov     r12, [rax+18h]
0x1400393f3  call    cs:__imp_IoGetCurrentProcess
0x1400393fa  nop     dword ptr [rax+rax+00h]
0x1400393ff  mov     [rsp+0E8h+var_80], ebx
0x140039403  mov     [rsp+0E8h+var_88], rax
0x140039408  mov     [rsp+0E8h+var_90], rdi
0x14003940d  mov     [rsp+0E8h+var_98], rsi
0x140039412  mov     dword ptr [rsp+0E8h+var_A0], r14d
0x140039417  mov     [rsp+0E8h+var_A8], r15
0x14003941c  mov     eax, [rsp+0E8h+OutputBufferLength]
0x140039423  mov     [rsp+0E8h+var_B0], eax
0x140039427  mov     r14, [rsp+0E8h+arg_18]
0x14003942f  mov     [rsp+0E8h+Size], r14
0x140039434  mov     eax, [rsp+0E8h+arg_10]
0x14003943b  mov     dword ptr [rsp+0E8h+var_C0], eax
0x14003943f  mov     rax, [rsp+0E8h+Src]
0x140039447  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14003944c  mov     r9, qword ptr [rsp+0E8h+arg_0]
0x140039454  mov     rcx, r12
0x140039457  call    WPP_SF_qPDPDqDZZqDd
0x14003945c  xor     ebx, ebx
0x14003945e  mov     esi, ebx
0x140039460  mov     edi, ebx
0x140039462  jmp     loc_140039FA8
0x140039467  mov     rax, ds:0FFFFF78000000014h
0x140039471  mov     [r12+20h], rax
0x140039476  test    r13, r13
0x140039479  jz      loc_14003954F
0x14003947f  mov     r14d, [rsp+0E8h+OutputBufferLength]
0x140039487  test    r14d, r14d
0x14003948a  jz      loc_140039557
0x140039490  mov     [rsp+0E8h+var_64], r14d
0x140039498  mov     edx, r14d
0x14003949b  mov     ecx, 100h
0x1400394a0  mov     r8d, 424F6C43h
0x1400394a6  call    cs:__imp_ExAllocatePool2
0x1400394ad  nop     dword ptr [rax+rax+00h]
0x1400394b2  mov     rsi, rax
0x1400394b5  mov     [rsp+0E8h+var_58], rax
0x1400394bd  test    rax, rax
0x1400394c0  jnz     loc_140039557
0x1400394c6  mov     edi, 0C000009Ah
0x1400394cb  mov     r13d, edi
0x1400394ce  mov     [rsp+0E8h+var_68], edi
0x1400394d5  mov     ecx, edi
0x1400394d7  call    HsmDbgBreakOnStatus
0x1400394dc  lea     rax, WPP_GLOBAL_Control
0x1400394e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400394ea  cmp     rcx, rax
0x1400394ed  jz      loc_140039F99
0x1400394f3  test    dword ptr [rcx+2Ch], 100h
0x1400394fa  jz      loc_140039F99
0x140039500  cmp     byte ptr [rcx+29h], 2
0x140039504  jb      loc_140039F99
0x14003950a  mov     edx, 85h
0x14003950f  mov     dword ptr [rsp+0E8h+var_A8], edi
0x140039513  mov     [rsp+0E8h+var_B0], r14d
0x140039518  mov     r14, [rsp+0E8h+arg_18]
0x140039520  mov     [rsp+0E8h+Size], r14
0x140039525  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x14003952a  mov     rax, [rsp+0E8h+Src]
0x140039532  mov     qword ptr [rsp+0E8h+var_C8], rax
0x140039537  mov     r9, r12
0x14003953a  mov     rcx, [rcx+18h]
0x14003953e  call    WPP_SF_qPDPDd
0x140039543  mov     edi, [rsp+0E8h+var_64]
0x14003954a  jmp     loc_140039FA8
0x14003954f  mov     r14d, [rsp+0E8h+OutputBufferLength]
0x140039557  mov     r8d, 736D6C43h
0x14003955d  mov     rdx, r15
0x140039560  mov     ecx, 102h
0x140039565  call    cs:__imp_ExAllocatePool2
0x14003956c  nop     dword ptr [rax+rax+00h]
0x140039571  mov     rdi, rax
0x140039574  mov     [rsp+0E8h+P], rax
0x14003957c  test    rax, rax
0x14003957f  jnz     loc_14003960F
0x140039585  mov     edi, 0C000009Ah
0x14003958a  mov     r13d, edi
0x14003958d  mov     [rsp+0E8h+var_68], edi
0x140039594  mov     ecx, edi
0x140039596  call    HsmDbgBreakOnStatus
0x14003959b  lea     rax, WPP_GLOBAL_Control
0x1400395a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395a9  cmp     rcx, rax
0x1400395ac  jz      loc_140039F91
0x1400395b2  test    dword ptr [rcx+2Ch], 100h
0x1400395b9  jz      loc_140039F91
0x1400395bf  cmp     byte ptr [rcx+29h], 2
0x1400395c3  jb      loc_140039F84
0x1400395c9  mov     edx, 86h
0x1400395ce  mov     dword ptr [rsp+0E8h+var_A8], edi
0x1400395d2  mov     [rsp+0E8h+var_B0], r14d
0x1400395d7  mov     r14, [rsp+0E8h+arg_18]
0x1400395df  mov     [rsp+0E8h+Size], r14
0x1400395e4  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x1400395e9  mov     rax, [rsp+0E8h+Src]
0x1400395f1  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1400395f6  mov     r9, r12
0x1400395f9  mov     rcx, [rcx+18h]
0x1400395fd  call    WPP_SF_qPDPDd
0x140039602  mov     rsi, [rsp+0E8h+var_58]
0x14003960a  jmp     loc_140039543
0x14003960f  mov     rax, [rsp+0E8h+Src]
0x140039617  test    r15d, r15d
0x14003961a  jz      short loc_14003962D
0x14003961c  test    al, 3
0x14003961e  jz      short loc_14003962D
0x140039620  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140039627  nop     dword ptr [rax+rax+00h]
0x14003962c  int     3; Trap to Debugger
0x14003962d  mov     r8, r15; Size
0x140039630  mov     rdx, rax; Src
0x140039633  mov     rcx, rdi; void *
0x140039636  call    RtlCopyFromUser
0x14003963b  mov     [rsp+0E8h+var_64+4], r15d
0x140039643  movzx   r12d, bl
0x140039647  mov     r13b, bl
0x14003964a  cmp     r15d, 18h
0x14003964e  jb      loc_140039783
0x140039654  cmp     dword ptr [rdi], 706D6C43h
0x14003965a  jnz     loc_140039783
0x140039660  test    byte ptr [rdi+0Ch], 2
0x140039664  jz      short loc_140039685
0x140039666  lea     r8d, [r15-8]; Length
0x14003966a  lea     rdx, [rdi+8]; Buffer
0x14003966e  xor     ecx, ecx; InitialCrc
0x140039670  call    cs:__imp_RtlComputeCrc32
0x140039677  nop     dword ptr [rax+rax+00h]
0x14003967c  cmp     [rdi+4], eax
0x14003967f  jnz     loc_140039783
0x140039685  mov     edx, [rdi+8]
0x140039688  cmp     r15d, edx
0x14003968b  jb      loc_140039783
0x140039691  movzx   r9d, word ptr [rdi+0Eh]
0x140039696  test    r9w, r9w
0x14003969a  jz      loc_140039783
0x1400396a0  lea     r11, ds:10h[r9*8]
0x1400396a8  cmp     r11, rdx
0x1400396ab  jnb     loc_140039783
0x1400396b1  mov     r10d, ebx
0x1400396b4  mov     esi, 17h
0x1400396b9  lea     r14d, [rsi-16h]
0x1400396bd  cmp     r9w, si
0x1400396c1  mov     eax, r9d
0x1400396c4  jb      short loc_1400396C8
0x1400396c6  mov     eax, esi
0x1400396c8  cmp     r10d, eax
0x1400396cb  jnb     short loc_140039714
0x1400396cd  mov     r8d, r10d
0x1400396d0  cmp     word ptr [rdi+r8*8+10h], 12h
0x1400396d7  jnb     loc_140039789
0x1400396dd  mov     ecx, [rdi+r8*8+14h]
0x1400396e2  test    ecx, ecx
0x1400396e4  jz      short loc_1400396EF
0x1400396e6  cmp     rcx, r11
0x1400396e9  jb      loc_140039789
0x1400396ef  cmp     ecx, edx
0x1400396f1  ja      loc_140039789
0x1400396f7  movzx   eax, word ptr [rdi+r8*8+12h]
0x1400396fd  cmp     eax, edx
0x1400396ff  ja      loc_140039789
0x140039705  add     eax, ecx
0x140039707  cmp     eax, ecx
0x140039709  jb      short loc_140039789
0x14003970b  cmp     eax, edx
0x14003970d  ja      short loc_140039789
0x14003970f  add     r10d, r14d
0x140039712  jmp     short loc_1400396BD
0x140039714  cmp     edx, 18h
0x140039717  jb      short loc_140039789
0x140039719  cmp     bx, r9w
0x14003971d  jnb     short loc_14003976F
0x14003971f  movzx   r9d, word ptr [rdi+10h]
0x140039724  cmp     r9w, 12h
0x140039729  jnb     short loc_14003976F
0x14003972b  mov     ecx, [rdi+14h]
0x14003972e  test    ecx, ecx
0x140039730  jz      short loc_140039737
0x140039732  cmp     rcx, r11
0x140039735  jb      short loc_14003976F
0x140039737  cmp     ecx, edx
0x140039739  ja      short loc_14003976F
0x14003973b  movzx   eax, word ptr [rdi+12h]
0x14003973f  cmp     eax, edx
0x140039741  ja      short loc_14003976F
0x140039743  lea     r8d, [rax+rcx]
0x140039747  cmp     r8d, ecx
0x14003974a  jb      short loc_14003976F
0x14003974c  cmp     r8d, edx
0x14003974f  ja      short loc_14003976F
0x140039751  mov     edx, 7
0x140039756  cmp     r9w, dx
0x14003975a  jnz     short loc_14003976F
0x14003975c  cmp     ax, r14w
0x140039760  jnz     short loc_14003976F
0x140039762  mov     r13b, [rcx+rdi]
0x140039766  mov     eax, ebx
0x140039768  mov     esi, 0C0000225h
0x14003976d  jmp     short loc_140039776
0x14003976f  mov     esi, 0C0000225h
0x140039774  mov     eax, esi
0x140039776  test    eax, eax
0x140039778  js      short loc_14003978E
0x14003977a  cmp     r13b, r14b
0x14003977d  cmovbe  r12d, r14d
0x140039781  jmp     short loc_14003978E
0x140039783  mov     r14d, 1
0x140039789  mov     esi, 0C0000225h
0x14003978e  test    r12b, r12b
0x140039791  jnz     short loc_140039810
0x140039793  mov     r13d, 0C000000Dh
0x140039799  mov     [rsp+0E8h+var_68], r13d
0x1400397a1  mov     ecx, r13d
0x1400397a4  call    HsmDbgBreakOnStatus
0x1400397a9  lea     rax, WPP_GLOBAL_Control
0x1400397b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400397b7  cmp     rcx, rax
0x1400397ba  jz      loc_140039F91
0x1400397c0  test    dword ptr [rcx+2Ch], 100h
0x1400397c7  jz      loc_140039F91
0x1400397cd  mov     r14, [rsp+0E8h+arg_18]
0x1400397d5  cmp     byte ptr [rcx+29h], 2
0x1400397d9  jb      loc_140039602
0x1400397df  mov     edx, 88h
0x1400397e4  mov     dword ptr [rsp+0E8h+var_A8], r13d
0x1400397e9  mov     eax, [rsp+0E8h+OutputBufferLength]
0x1400397f0  mov     [rsp+0E8h+var_B0], eax
0x1400397f4  mov     [rsp+0E8h+Size], r14
0x1400397f9  mov     dword ptr [rsp+0E8h+var_C0], r15d
0x1400397fe  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x140039803  mov     r9, qword ptr [rsp+0E8h+arg_0]
0x14003980b  jmp     loc_1400395F9
0x140039810  cmp     r15d, 18h
0x140039814  jb      short loc_140039886
0x140039816  movzx   eax, word ptr [rdi+0Eh]
0x14003981a  cmp     r14w, ax
0x14003981e  jnb     short loc_140039886
0x140039820  mov     r8d, [rdi+8]
0x140039824  cmp     r8d, 20h ; ' '
0x140039828  jb      short loc_140039886
0x14003982a  movzx   r9d, word ptr [rdi+18h]
0x14003982f  cmp     r9w, 12h
0x140039834  jnb     short loc_140039886
0x140039836  mov     edx, [rdi+1Ch]
0x140039839  test    edx, edx
0x14003983b  jz      short loc_14003984A
0x14003983d  lea     rcx, ds:10h[rax*8]
  ... truncated ...
```
