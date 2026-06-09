# FTPostOnlyOpCallback

- ea: `0x1400010b0`
- end: `0x140001ada`
- name: `FTPostOnlyOpCallback`
- size: `2602`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400010b0`
- `0x140002d68`
- `0x1400031f0`
- `0x140003510`
- `0x140003550`
- `0x14000bce4`
- `0x14000c8ec`
- `0x14000cf0c`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x1400018d4`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400018d4`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140001310`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140001310`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400016f6`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400016f6`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000169f`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000169f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400019ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400019ac`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400013b8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140001511`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400013b8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140001511`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140001455`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000152e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140001455`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000152e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000195d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000198c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000195d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000198c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e5e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000190c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000190c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400014f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400014f9`
- `FLTMGR!FltGetRequestorProcessId` at `0x1400012e6`
- `FLTMGR!FltGetRequestorProcessId` at `0x1400012e6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001a55`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003e0f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001a55`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003e0f`
- `FLTMGR!FltGetFileNameInformation` at `0x140001370`
- `FLTMGR!FltGetFileNameInformation` at `0x140001370`
- `FLTMGR!FltIsDirectory` at `0x1400014a2`
- `FLTMGR!FltIsDirectory` at `0x1400014a2`
- `FLTMGR!FltReleaseContext` at `0x140001a85`
- `FLTMGR!FltReleaseContext` at `0x140003e43`
- `FLTMGR!FltReleaseContext` at `0x140001a85`
- `FLTMGR!FltReleaseContext` at `0x140003e43`
- `FLTMGR!FltGetRequestorProcess` at `0x1400012fc`
- `FLTMGR!FltGetRequestorProcess` at `0x14000168b`
- `FLTMGR!FltGetRequestorProcess` at `0x1400016e2`
- `FLTMGR!FltGetRequestorProcess` at `0x1400012fc`
- `FLTMGR!FltGetRequestorProcess` at `0x14000168b`
- `FLTMGR!FltGetRequestorProcess` at `0x1400016e2`
- `FLTMGR!FltGetVolumeContext` at `0x140001341`
- `FLTMGR!FltGetVolumeContext` at `0x140001341`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000196c`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000196c`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001947`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001947`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400018eb`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400018eb`

## pseudocode

```c
__int64 __fastcall FTPostOnlyOpCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  int v6; // r12d
  char v7; // r13
  __int64 result; // rax
  void *v9; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS v12; // ebx
  struct _UNICODE_STRING *p_Destination; // rax
  PWSTR v14; // rcx
  unsigned __int16 v15; // ax
  WCHAR v16; // ax
  int v17; // eax
  PFLT_IO_PARAMETER_BLOCK v18; // rcx
  NTSTATUS v19; // ecx
  unsigned __int8 v20; // dl
  void *v21; // r11
  int v22; // esi
  int v23; // r14d
  PFLT_IO_PARAMETER_BLOCK v24; // rax
  ULONG_PTR Information; // rax
  void *v26; // rax
  int ProcessSessionId; // eax
  PEPROCESS v28; // rax
  __int64 ProcessWin32WindowStation; // rax
  PEPROCESS v30; // rax
  _DWORD *v31; // r10
  int v32; // edx
  PVOID v33; // r14
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rbx
  _QWORD *PoolWithTag; // rax
  void *v36; // rsi
  unsigned __int8 IsDirectory[4]; // [rsp+30h] [rbp-3C8h] BYREF
  int v38; // [rsp+34h] [rbp-3C4h]
  int v39; // [rsp+38h] [rbp-3C0h] BYREF
  char v40; // [rsp+3Ch] [rbp-3BCh]
  void *v41; // [rsp+40h] [rbp-3B8h] BYREF
  int v42; // [rsp+48h] [rbp-3B0h] BYREF
  int v43; // [rsp+4Ch] [rbp-3ACh] BYREF
  int v44; // [rsp+50h] [rbp-3A8h] BYREF
  PVOID v45; // [rsp+58h] [rbp-3A0h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-398h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-390h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-380h] BYREF
  NTSTATUS v49; // [rsp+88h] [rbp-370h]
  unsigned int MajorFunction; // [rsp+90h] [rbp-368h]
  int v51; // [rsp+94h] [rbp-364h]
  void *v52; // [rsp+98h] [rbp-360h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-358h]
  void *v54; // [rsp+A8h] [rbp-350h] BYREF
  PVOID P[2]; // [rsp+B0h] [rbp-348h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-338h] BYREF
  struct _UNICODE_STRING *v57; // [rsp+C8h] [rbp-330h]
  __int16 v58; // [rsp+D0h] [rbp-328h]
  bool v59; // [rsp+D2h] [rbp-326h]
  int v60; // [rsp+D3h] [rbp-325h]
  char v61; // [rsp+D7h] [rbp-321h]
  __int64 v62; // [rsp+D8h] [rbp-320h]
  PFLT_CONTEXT Context[2]; // [rsp+E0h] [rbp-318h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-308h]
  LONGLONG TimeQuadPart; // [rsp+F8h] [rbp-300h]
  char v66; // [rsp+100h] [rbp-2F8h]
  int v67; // [rsp+101h] [rbp-2F7h]
  __int16 v68; // [rsp+105h] [rbp-2F3h]
  char v69; // [rsp+107h] [rbp-2F1h]
  void *v70; // [rsp+108h] [rbp-2F0h]
  int v71; // [rsp+110h] [rbp-2E8h]
  int v72; // [rsp+114h] [rbp-2E4h]
  void *v73; // [rsp+118h] [rbp-2E0h]
  __int64 v74; // [rsp+120h] [rbp-2D8h]
  void *v75; // [rsp+128h] [rbp-2D0h]
  __int64 v76; // [rsp+130h] [rbp-2C8h]
  __int64 v77; // [rsp+138h] [rbp-2C0h]
  PVOID v78; // [rsp+140h] [rbp-2B8h]
  __int64 v79; // [rsp+148h] [rbp-2B0h] BYREF
  void *v80; // [rsp+150h] [rbp-2A8h] BYREF
  __int64 v81; // [rsp+158h] [rbp-2A0h]
  void *v82; // [rsp+160h] [rbp-298h]
  PWSTR v83; // [rsp+170h] [rbp-288h]
  struct _UNICODE_STRING DestinationString; // [rsp+178h] [rbp-280h] BYREF
  int v85; // [rsp+188h] [rbp-270h]
  __int64 v86; // [rsp+190h] [rbp-268h]
  __int64 v87; // [rsp+198h] [rbp-260h]
  int WnodeEventItem; // [rsp+1A0h] [rbp-258h] BYREF
  __int128 v89; // [rsp+1A4h] [rbp-254h]
  _BYTE v90[44]; // [rsp+1B4h] [rbp-244h] BYREF
  __int16 v91; // [rsp+1E0h] [rbp-218h] BYREF
  __int128 v92; // [rsp+1E2h] [rbp-216h]
  _BYTE v93[30]; // [rsp+1F2h] [rbp-206h] BYREF
  char v94; // [rsp+210h] [rbp-1E8h] BYREF
  char v95; // [rsp+228h] [rbp-1D0h] BYREF
  _BYTE v96[384]; // [rsp+240h] [rbp-1B8h] BYREF

  v86 = a2;
  v6 = 0;
  v44 = 0;
  v39 = 0;
  FileNameInformation = 0;
  WnodeEventItem = 0;
  v89 = 0;
  memset(v90, 0, sizeof(v90));
  v7 = 2;
  v52 = 0;
  v38 = -1;
  v53 = 0;
  v54 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v45 = 0;
  v91 = 48;
  v92 = 0;
  memset(v93, 0, sizeof(v93));
  *(_QWORD *)&Destination.Length = 3145728;
  Destination.Buffer = (PWSTR)&v91;
  v56 = 0;
  v57 = 0;
  v58 = 2;
  v59 = 0;
  result = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  *(_OWORD *)Context = 0;
  v64 = 0;
  TimeQuadPart = 0;
  v66 = 2;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = -1;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  if ( (a4 & 1) == 0 )
  {
    v9 = 0;
    v41 = 0;
    Iopb = CallbackData->Iopb;
    MajorFunction = Iopb->MajorFunction;
    P[0] = v96;
    LODWORD(v56) = CallbackData->IoStatus.Status;
    WORD2(v56) = *(_WORD *)&Iopb->MajorFunction;
    Context[1] = *(PFLT_CONTEXT *)(a2 + 32);
    HIBYTE(v58) = (Iopb->IrpFlags & 2) != 0;
    v59 = (CallbackData->Flags & 2) != 0;
    v62 = MEMORY[0xFFFFF78000000014];
    LODWORD(v64) = FltGetRequestorProcessId(CallbackData);
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    if ( RequestorProcess )
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    else
      TimeQuadPart = 0;
    if ( FltGetVolumeContext((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, *(PFLT_VOLUME *)(a2 + 16), Context) >= 0 )
    {
      if ( *(_QWORD *)(a2 + 32) )
      {
        v12 = FltGetFileNameInformation(CallbackData, dword_140007244 | 1, &FileNameInformation);
        if ( v12 < 0 )
        {
          *(_QWORD *)&Source.Length = 1179648;
          Source.Buffer = (PWSTR)&v94;
          if ( RtlAppendUnicodeToString(&Destination, L":00000000-") >= 0 )
          {
            v49 = v12;
            v83 = 0;
            if ( !Source.Buffer || Source.Length || Source.MaximumLength < 0x12u )
            {
              v17 = -1073741811;
            }
            else
            {
              v14 = Source.Buffer + 8;
              v83 = Source.Buffer + 8;
              Source.Buffer[8] = 0;
              do
              {
                v15 = v12 & 0xF;
                if ( v15 <= 9u )
                  v16 = v15 + 48;
                else
                  v16 = v15 + 55;
                v83 = --v14;
                *v14 = v16;
                v12 = (unsigned int)v12 >> 4;
                v49 = v12;
              }
              while ( v12 );
              Source.Length = 18;
              v17 = 0;
            }
            if ( v17 >= 0 )
              RtlAppendUnicodeStringToString(&Destination, &Source);
          }
          p_Destination = &Destination;
        }
        else
        {
          p_Destination = &FileNameInformation->Name;
        }
        v57 = p_Destination;
        v18 = CallbackData->Iopb;
        if ( (v18->IrpFlags & 2) == 0 )
        {
          if ( *(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) )
          {
            IsDirectory[0] = 0;
            if ( CallbackData->IoStatus.Status >= 0 )
            {
              v19 = FltIsDirectory(v18->TargetFileObject, *(PFLT_INSTANCE *)(a2 + 24), IsDirectory);
              v20 = 4;
              if ( v19 >= 0 )
                v20 = IsDirectory[0];
              LOBYTE(v58) = v20;
            }
          }
          else
          {
            LOBYTE(v58) = 3;
          }
        }
      }
      else
      {
        *(_QWORD *)&DestinationString.Length = 0;
        DestinationString.Buffer = (PWSTR)&v95;
        RtlInitUnicodeString(&DestinationString, L"0x00000000");
        if ( RtlAppendUnicodeToString(&Destination, L":00000001-") >= 0 )
          RtlAppendUnicodeStringToString(&Destination, &DestinationString);
        v57 = &Destination;
      }
      LOWORD(WnodeEventItem) = 64;
      *(_DWORD *)&v90[24] = 1179648;
      LOWORD(v89) = CallbackData->Iopb->MajorFunction;
      *(_OWORD *)&v90[4] = FT_MessageGuid;
      LODWORD(v21) = 0;
      while ( 1 )
      {
        v51 = v6;
        if ( v6 >= 8 )
        {
LABEL_99:
          v9 = v41;
          goto LABEL_100;
        }
        v66 = 2;
        v22 = *((_DWORD *)LogSessions + 10 * v6 + 3);
        v23 = *((_DWORD *)LogSessions + 10 * v6 + 5);
        *(_QWORD *)((char *)&v89 + 4) = *((_QWORD *)LogSessions + 5 * v6);
        if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 0x40) != 0 )
        {
          v24 = CallbackData->Iopb;
          if ( v24->MajorFunction == (_BYTE)v21 )
          {
            if ( v7 == 2 )
            {
              if ( CallbackData->IoStatus.Status >= (int)v21 )
              {
                if ( (v24->OperationFlags & 4) != 0 )
                {
                  v7 = 1;
                }
                else
                {
                  Information = CallbackData->IoStatus.Information;
                  if ( Information == 2 || (v7 = 1, Information == 5) )
                    v7 = (char)v21;
                }
              }
              v40 = v7;
            }
            v66 = v7;
          }
        }
        if ( (CallbackData->Iopb->IrpFlags & 2) == 0 && (*((_DWORD *)LogSessions + 10 * v6 + 7) & 4) != 0 )
        {
          v26 = v52;
          if ( !v52 )
          {
            GetLastAccessTime(CallbackData, v86, &v52);
            v26 = v52;
          }
          v70 = v26;
        }
        if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 2) != 0 )
        {
          ProcessSessionId = v38;
          if ( v38 == -1 )
          {
            v38 = -1;
            v28 = FltGetRequestorProcess(CallbackData);
            if ( v28 )
            {
              ProcessSessionId = PsGetProcessSessionId(v28);
              v38 = ProcessSessionId;
            }
            else
            {
              ProcessSessionId = v38;
            }
            v85 = ProcessSessionId;
          }
          v71 = ProcessSessionId;
        }
        if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 0x80u) != 0 )
        {
          ProcessWin32WindowStation = v53;
          if ( !v53 )
          {
            v30 = FltGetRequestorProcess(CallbackData);
            if ( v30 )
            {
              ProcessWin32WindowStation = PsGetProcessWin32WindowStation(v30);
              v53 = ProcessWin32WindowStation;
              v87 = ProcessWin32WindowStation;
            }
            else
            {
              ProcessWin32WindowStation = v53;
            }
          }
          v76 = ProcessWin32WindowStation;
        }
        if ( (CallbackData->Iopb->IrpFlags & 2) == 0
          && (GlobalLateBoundFunctions && !(unsigned __int8)GlobalLateBoundFunctions()
           || (CallbackData->Iopb->IrpFlags & 2) == 0)
          && (*((_DWORD *)LogSessions + 10 * v6 + 7) & 1) != 0 )
        {
          if ( !v54 )
            GetUserSidAndAcessToken(CallbackData, &v42, &v41, &v54);
          LODWORD(v74) = v42;
          v75 = v41;
          v73 = v54;
        }
        if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 8) != 0 )
        {
          if ( !v45 )
            CreateParameterBlob(CallbackData, &v43, &v45);
          v78 = v45;
          LODWORD(v77) = v43;
        }
        LODWORD(v79) = 0;
        v80 = 0;
        SetCallResult(CallbackData, *((unsigned int *)LogSessions + 10 * v6 + 7), &v79, &v80);
        if ( v22 )
        {
          if ( v22 == v31[3] )
          {
            if ( _bittest(&v23, MajorFunction) )
            {
              v32 = v31[8];
              if ( ((v32 & 0x4000000) != 0 || (v32 & *((_DWORD *)Context[0] + 120)) != 0)
                && ((CallbackData->Iopb->IrpFlags & 2) == 0 || (v31[7] & 0x100) == 0) )
              {
                break;
              }
            }
          }
        }
LABEL_97:
        v71 = -1;
        v70 = v21;
        v73 = v21;
        v75 = v21;
        v78 = v21;
        LODWORD(v77) = (_DWORD)v21;
        v80 = v21;
        LODWORD(v79) = (_DWORD)v21;
        v82 = v21;
        LODWORD(v81) = (_DWORD)v21;
        v66 = 2;
        v76 = (__int64)v21;
        ++v6;
      }
      if ( !(unsigned __int8)FormatFileTraceEvent((int)v31, (int)&v56, (int)&v39, (int)&v44, (size_t)P) )
        goto LABEL_99;
      v33 = P[0];
      *(PVOID *)&v90[28] = P[0];
      *(_DWORD *)&v90[36] = v44;
      if ( IoWMIWriteEvent(&WnodeEventItem) == -1073741816 )
      {
        GenericWorkItem = FltAllocateGenericWorkItem();
        if ( GenericWorkItem )
        {
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x72744C46u);
          v36 = PoolWithTag;
          if ( PoolWithTag )
          {
            *PoolWithTag = *(_QWORD *)((char *)&v89 + 4);
            if ( FltQueueGenericWorkItem(
                   GenericWorkItem,
                   WmiRegistrationContext.SecurityDescriptor,
                   DisableSession,
                   DelayedWorkQueue,
                   PoolWithTag) >= 0 )
              goto LABEL_90;
            ExFreePoolWithTag(v36, 0x72744C46u);
          }
          FltFreeGenericWorkItem(GenericWorkItem);
        }
      }
LABEL_90:
      if ( v39 == 1 )
      {
        ExFreeToNPagedLookasideList(&Lookaside, v33);
      }
      else
      {
        if ( v39 != 2 )
        {
          v21 = 0;
          goto LABEL_96;
        }
        ExFreePoolWithTag(v33, 0x72744C46u);
      }
      v21 = 0;
      v39 = 0;
LABEL_96:
      P[0] = v96;
      goto LABEL_97;
    }
LABEL_100:
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( v9 )
      ExFreePoolWithTag(v9, 0x72744C46u);
    if ( Context[0] )
      FltReleaseContext(Context[0]);
    if ( v45 )
      ExFreePoolWithTag(v45, 0x72744C46u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400010b0  mov     r11, rsp
0x1400010b3  mov     [r11+18h], rbx
0x1400010b7  mov     [r11+20h], rsi
0x1400010bb  push    rdi
0x1400010bc  push    r12
0x1400010be  push    r13
0x1400010c0  push    r14
0x1400010c2  push    r15
0x1400010c4  sub     rsp, 3D0h
0x1400010cb  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x1400010d2  xor     rax, rsp
0x1400010d5  mov     [rsp+3F8h+var_38], rax
0x1400010dd  mov     r14, rdx
0x1400010e0  mov     [rsp+3F8h+var_268], rdx
0x1400010e8  mov     rdi, rcx
0x1400010eb  xor     r12d, r12d
0x1400010ee  mov     [rsp+3F8h+var_3A8], r12d
0x1400010f3  mov     [rsp+3F8h+var_3C0], r12d
0x1400010f8  mov     [rsp+3F8h+FileNameInformation], r12
0x1400010fd  mov     [r11-258h], r12d
0x140001104  xorps   xmm0, xmm0
0x140001107  xor     eax, eax
0x140001109  movups  [rsp+3F8h+var_254], xmm0
0x140001111  movups  [rsp+3F8h+var_244], xmm0
0x140001119  movups  [rsp+3F8h+var_234], xmm0
0x140001121  movups  [rsp+3F8h+var_234+0Ch], xmm0
0x140001129  mov     r13b, 2
0x14000112c  mov     [r11-360h], r12
0x140001133  or      ecx, 0FFFFFFFFh
0x140001136  mov     [rsp+3F8h+var_3C4], ecx
0x14000113a  mov     [r11-358h], r12
0x140001141  mov     [r11-350h], r12
0x140001148  mov     [rsp+3F8h+var_3B8], r12
0x14000114d  mov     [rsp+3F8h+var_3B0], r12d
0x140001152  mov     [rsp+3F8h+var_3AC], r12d
0x140001157  mov     [rsp+3F8h+var_3A0], r12
0x14000115c  lea     r15d, [r12+30h]
0x140001161  mov     [r11-218h], r15w
0x140001169  movups  [rsp+3F8h+var_216], xmm0
0x140001171  movups  xmmword ptr [rsp+3F8h+var_206], xmm0
0x140001179  movups  xmmword ptr [rsp+3F8h+var_206+0Eh], xmm0
0x140001181  mov     qword ptr [rsp+3F8h+Destination.Length], 300000h
0x14000118a  lea     rax, [r11-218h]
0x140001191  mov     [r11-378h], rax
0x140001198  mov     [r11-338h], r12
0x14000119f  mov     [r11-330h], r12
0x1400011a6  mov     [rsp+3F8h+var_328], 2
0x1400011b0  mov     [r11-326h], r12b
0x1400011b7  xor     eax, eax
0x1400011b9  mov     [rsp+3F8h+var_325], eax
0x1400011c0  mov     [rsp+3F8h+var_321], al
0x1400011c7  mov     [r11-320h], r12
0x1400011ce  movdqa  xmmword ptr [rsp+3F8h+Context], xmm0
0x1400011d7  mov     [r11-308h], r12
0x1400011de  mov     [r11-300h], r12
0x1400011e5  mov     [r11-2F8h], r13b
0x1400011ec  mov     [rsp+3F8h+var_2F7], eax
0x1400011f3  mov     [rsp+3F8h+var_2F3], ax
0x1400011fb  mov     [rsp+3F8h+var_2F1], al
0x140001202  mov     [r11-2F0h], r12
0x140001209  mov     [rsp+3F8h+var_2E8], ecx
0x140001210  mov     [rsp+3F8h+var_2E4], eax
0x140001217  mov     [r11-2E0h], r12
0x14000121e  mov     [r11-2D8h], r12
0x140001225  mov     [r11-2D0h], r12
0x14000122c  mov     [r11-2C8h], r12
0x140001233  mov     [r11-2C0h], r12
0x14000123a  mov     [r11-2B8h], r12
0x140001241  mov     [r11-2B0h], r12
0x140001248  mov     [r11-2A8h], r12
0x14000124f  mov     [r11-2A0h], r12
0x140001256  mov     [r11-298h], r12
0x14000125d  test    r9b, 1
0x140001261  jnz     loc_140001AAC
0x140001267  mov     esi, r12d
0x14000126a  mov     [rsp+3F8h+var_3B8], r12
0x14000126f  mov     rcx, [rdi+10h]
0x140001273  movzx   eax, byte ptr [rcx+4]
0x140001277  mov     [rsp+3F8h+var_368], eax
0x14000127e  lea     rdx, [r11-1B8h]
0x140001285  mov     [r11-348h], rdx
0x14000128c  mov     eax, [rdi+18h]
0x14000128f  mov     [rsp+3F8h+var_338], eax
0x140001296  mov     al, [rcx+4]
0x140001299  mov     [rsp+3F8h+var_334], al
0x1400012a0  mov     al, [rcx+5]
0x1400012a3  mov     [rsp+3F8h+var_333], al
0x1400012aa  mov     rax, [r14+20h]
0x1400012ae  mov     [r11-310h], rax
0x1400012b5  mov     eax, [rcx]
0x1400012b7  shr     eax, 1
0x1400012b9  and     al, 1
0x1400012bb  mov     byte ptr [rsp+3F8h+var_328+1], al
0x1400012c2  mov     eax, [rdi]
0x1400012c4  shr     eax, 1
0x1400012c6  and     al, 1
0x1400012c8  mov     [rsp+3F8h+var_326], al
0x1400012cf  mov     rax, 0FFFFF78000000014h
0x1400012d9  mov     rax, [rax]
0x1400012dc  mov     [r11-320h], rax
0x1400012e3  mov     rcx, rdi; CallbackData
0x1400012e6  call    cs:__imp_FltGetRequestorProcessId
0x1400012ed  nop     dword ptr [rax+rax+00h]
0x1400012f2  mov     dword ptr [rsp+3F8h+var_308], eax
0x1400012f9  mov     rcx, rdi; CallbackData
0x1400012fc  call    cs:__imp_FltGetRequestorProcess
0x140001303  nop     dword ptr [rax+rax+00h]
0x140001308  test    rax, rax
0x14000130b  jz      short loc_140001326
0x14000130d  mov     rcx, rax; Process
0x140001310  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140001317  nop     dword ptr [rax+rax+00h]
0x14000131c  mov     [rsp+3F8h+var_300], rax
0x140001324  jmp     short loc_14000132E
0x140001326  mov     [rsp+3F8h+var_300], r12
0x14000132e  lea     r8, [rsp+3F8h+Context]; Context
0x140001336  mov     rdx, [r14+10h]; Volume
0x14000133a  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x140001341  call    cs:__imp_FltGetVolumeContext
0x140001348  nop     dword ptr [rax+rax+00h]
0x14000134d  test    eax, eax
0x14000134f  js      loc_140001A3E
0x140001355  cmp     [r14+20h], r12
0x140001359  jz      loc_1400014D2
0x14000135f  mov     edx, cs:dword_140007244
0x140001365  or      edx, 1; NameOptions
0x140001368  lea     r8, [rsp+3F8h+FileNameInformation]; FileNameInformation
0x14000136d  mov     rcx, rdi; CallbackData
0x140001370  call    cs:__imp_FltGetFileNameInformation
0x140001377  nop     dword ptr [rax+rax+00h]
0x14000137c  mov     ebx, eax
0x14000137e  test    eax, eax
0x140001380  js      short loc_140001390
0x140001382  mov     rax, [rsp+3F8h+FileNameInformation]
0x140001387  add     rax, 8
0x14000138b  jmp     loc_140001466
0x140001390  mov     qword ptr [rsp+3F8h+Source.Length], r12
0x140001395  lea     rax, [rsp+3F8h+var_1E8]
0x14000139d  mov     [rsp+3F8h+Source.Buffer], rax
0x1400013a2  mov     esi, 12h
0x1400013a7  mov     [rsp+3F8h+Source.MaximumLength], si
0x1400013ac  lea     rdx, Source; ":00000000-"
0x1400013b3  lea     rcx, [rsp+3F8h+Destination]; Destination
0x1400013b8  call    cs:__imp_RtlAppendUnicodeToString
0x1400013bf  nop     dword ptr [rax+rax+00h]
0x1400013c4  test    eax, eax
0x1400013c6  js      loc_140001461
0x1400013cc  mov     [rsp+3F8h+var_370], ebx
0x1400013d3  mov     [rsp+3F8h+var_288], r12
0x1400013db  mov     rcx, [rsp+3F8h+Source.Buffer]
0x1400013e0  test    rcx, rcx
0x1400013e3  jz      short loc_140001442
0x1400013e5  cmp     [rsp+3F8h+Source.Length], r12w
0x1400013eb  jnz     short loc_140001442
0x1400013ed  cmp     [rsp+3F8h+Source.MaximumLength], si
0x1400013f2  jb      short loc_140001442
0x1400013f4  add     rcx, 10h
0x1400013f8  mov     [rsp+3F8h+var_288], rcx
0x140001400  mov     [rcx], r12w
0x140001404  movzx   eax, bx
0x140001407  and     ax, 0Fh
0x14000140b  cmp     ax, 9
0x14000140f  jbe     short loc_140001417
0x140001411  add     ax, 37h ; '7'
0x140001415  jmp     short loc_14000141B
0x140001417  add     ax, r15w
0x14000141b  sub     rcx, 2
0x14000141f  mov     [rsp+3F8h+var_288], rcx
0x140001427  mov     [rcx], ax
0x14000142a  shr     ebx, 4
0x14000142d  mov     [rsp+3F8h+var_370], ebx
0x140001434  test    ebx, ebx
0x140001436  jnz     short loc_140001404
0x140001438  mov     [rsp+3F8h+Source.Length], si
0x14000143d  mov     eax, r12d
0x140001440  jmp     short loc_140001447
0x140001442  mov     eax, 0C000000Dh
0x140001447  test    eax, eax
0x140001449  js      short loc_140001461
0x14000144b  lea     rdx, [rsp+3F8h+Source]; Source
0x140001450  lea     rcx, [rsp+3F8h+Destination]; Destination
0x140001455  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000145c  nop     dword ptr [rax+rax+00h]
0x140001461  lea     rax, [rsp+3F8h+Destination]
0x140001466  mov     [rsp+3F8h+var_330], rax
0x14000146e  mov     rcx, [rdi+10h]
0x140001472  mov     eax, [rcx]
0x140001474  test    al, 2
0x140001476  jnz     loc_140001547
0x14000147c  mov     rax, [r14+20h]
0x140001480  cmp     [rax+18h], r12
0x140001484  jz      short loc_1400014C8
0x140001486  mov     [rsp+3F8h+IsDirectory], r12b
0x14000148b  cmp     [rdi+18h], r12d
0x14000148f  jl      loc_140001547
0x140001495  lea     r8, [rsp+3F8h+IsDirectory]; IsDirectory
0x14000149a  mov     rdx, [r14+18h]; Instance
0x14000149e  mov     rcx, [rcx+8]; FileObject
0x1400014a2  call    cs:__imp_FltIsDirectory
0x1400014a9  nop     dword ptr [rax+rax+00h]
0x1400014ae  mov     ecx, eax
0x1400014b0  mov     edx, 4
0x1400014b5  movzx   eax, [rsp+3F8h+IsDirectory]
0x1400014ba  test    ecx, ecx
0x1400014bc  cmovns  edx, eax
0x1400014bf  mov     byte ptr [rsp+3F8h+var_328], dl
0x1400014c6  jmp     short loc_140001547
0x1400014c8  mov     byte ptr [rsp+3F8h+var_328], 3
0x1400014d0  jmp     short loc_140001547
0x1400014d2  mov     qword ptr [rsp+3F8h+DestinationString.Length], r12
0x1400014da  lea     rax, [rsp+3F8h+var_1D0]
0x1400014e2  mov     [rsp+3F8h+DestinationString.Buffer], rax
0x1400014ea  lea     rdx, SourceString; "0x00000000"
0x1400014f1  lea     rcx, [rsp+3F8h+DestinationString]; DestinationString
0x1400014f9  call    cs:__imp_RtlInitUnicodeString
0x140001500  nop     dword ptr [rax+rax+00h]
0x140001505  lea     rdx, a00000001; ":00000001-"
0x14000150c  lea     rcx, [rsp+3F8h+Destination]; Destination
0x140001511  call    cs:__imp_RtlAppendUnicodeToString
0x140001518  nop     dword ptr [rax+rax+00h]
0x14000151d  test    eax, eax
0x14000151f  js      short loc_14000153A
0x140001521  lea     rdx, [rsp+3F8h+DestinationString]; Source
0x140001529  lea     rcx, [rsp+3F8h+Destination]; Destination
0x14000152e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140001535  nop     dword ptr [rax+rax+00h]
0x14000153a  lea     rax, [rsp+3F8h+Destination]
0x14000153f  mov     [rsp+3F8h+var_330], rax
0x140001547  mov     r8d, 40h ; '@'
0x14000154d  mov     word ptr [rsp+3F8h+WnodeEventItem], r8w
0x140001556  mov     dword ptr [rsp+3F8h+var_234+8], 120000h
0x140001561  mov     rax, [rdi+10h]
0x140001565  mov     cl, [rax+4]
0x140001568  mov     byte ptr [rsp+3F8h+var_254], cl
0x14000156f  mov     byte ptr [rsp+3F8h+var_254+1], r12b
0x140001577  movups  xmm0, cs:FT_MessageGuid
0x14000157e  movdqu  [rsp+3F8h+var_244+4], xmm0
0x140001587  mov     r15d, 72744C46h
0x14000158d  xor     r11d, r11d
0x140001590  mov     [rsp+3F8h+var_364], r12d
0x140001598  cmp     r12d, 8
0x14000159c  jge     loc_140001A46
0x1400015a2  mov     [rsp+3F8h+var_2F8], 2
0x1400015aa  movsxd  rax, r12d
0x1400015ad  lea     rbx, [rax+rax*4]
0x1400015b1  mov     rax, cs:LogSessions
0x1400015b8  mov     esi, [rax+rbx*8+0Ch]
0x1400015bc  mov     rdx, cs:LogSessions
0x1400015c3  mov     r14d, [rdx+rbx*8+14h]
0x1400015c8  mov     rax, [rdx+rbx*8]
0x1400015cc  mov     qword ptr [rsp+3F8h+var_254+4], rax
0x1400015d4  mov     eax, [rdx+rbx*8+1Ch]
0x1400015d8  test    r8b, al
0x1400015db  jz      short loc_140001621
0x1400015dd  mov     rax, [rdi+10h]
0x1400015e1  cmp     [rax+4], r11b
0x1400015e5  jnz     short loc_140001621
0x1400015e7  cmp     r13b, 2
0x1400015eb  jnz     short loc_140001619
0x1400015ed  cmp     [rdi+18h], r11d
0x1400015f1  jl      short loc_140001614
0x1400015f3  test    byte ptr [rax+6], 4
0x1400015f7  jz      short loc_1400015FE
0x1400015f9  mov     r13b, 1
0x1400015fc  jmp     short loc_140001614
0x1400015fe  mov     rax, [rdi+20h]
0x140001602  cmp     rax, 2
0x140001606  jz      short loc_140001611
0x140001608  cmp     rax, 5
0x14000160c  mov     r13b, 1
0x14000160f  jnz     short loc_140001614
0x140001611  mov     r13b, r11b
0x140001614  mov     [rsp+3F8h+var_3BC], r13b
0x140001619  mov     [rsp+3F8h+var_2F8], r13b
0x140001621  mov     rax, [rdi+10h]
0x140001625  mov     ecx, [rax]
0x140001627  test    cl, 2
0x14000162a  jnz     short loc_140001669
0x14000162c  mov     eax, [rdx+rbx*8+1Ch]
0x140001630  test    al, 4
0x140001632  jz      short loc_140001669
0x140001634  mov     rax, [rsp+3F8h+var_360]
0x14000163c  test    rax, rax
0x14000163f  jnz     short loc_140001661
0x140001641  lea     r8, [rsp+3F8h+var_360]
0x140001649  mov     rdx, [rsp+3F8h+var_268]
0x140001651  mov     rcx, rdi
0x140001654  call    GetLastAccessTime
0x140001659  mov     rax, [rsp+3F8h+var_360]
0x140001661  mov     [rsp+3F8h+var_2F0], rax
0x140001669  mov     rax, cs:LogSessions
0x140001670  mov     ecx, [rax+rbx*8+1Ch]
0x140001674  test    cl, 2
0x140001677  jz      short loc_1400016C3
0x140001679  mov     eax, [rsp+3F8h+var_3C4]
0x14000167d  or      ecx, 0FFFFFFFFh
0x140001680  cmp     eax, ecx
0x140001682  jnz     short loc_1400016BC
0x140001684  mov     [rsp+3F8h+var_3C4], ecx
0x140001688  mov     rcx, rdi; CallbackData
  ... truncated ...
```
