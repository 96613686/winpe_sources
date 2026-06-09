# PrjfPostCreate

- ea: `0x140022320`
- end: `0x140023461`
- name: `PrjfPostCreate`
- size: `4417`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _UNKNOWN **)`
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140002b50`
- `0x140002f3c`
- `0x1400037e0`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d5e8`
- `0x14000d754`
- `0x14000dab0`
- `0x14000e058`
- `0x14000e188`
- `0x14000e384`
- `0x14000e57c`
- `0x14000e7cc`
- `0x14000e9f4`
- `0x14000ec4c`
- `0x14002208c`
- `0x1400220d0`
- `0x140022320`
- `0x140023d68`
- `0x140024184`
- `0x14003be88`
- `0x14003d620`
- `0x14003df88`
- `0x140042cf0`
- `0x140042eac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023436`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023436`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233cc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233e2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233cc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400226b6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400230c5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400232d1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400226b6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400230c5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400232d1`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140023396`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400233b5`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140023396`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400233b5`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140022b66`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140022b66`
- `FLTMGR!FltReissueSynchronousIo` at `0x140022585`
- `FLTMGR!FltReissueSynchronousIo` at `0x140022585`
- `FLTMGR!FltAcknowledgeEcp` at `0x140023280`
- `FLTMGR!FltAcknowledgeEcp` at `0x140023280`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140023213`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140023213`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400231e0`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400231e0`
- `FLTMGR!FltClose` at `0x1400230b5`
- `FLTMGR!FltClose` at `0x1400230b5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023377`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023377`
- `FLTMGR!FltReleaseContext` at `0x140023294`
- `FLTMGR!FltReleaseContext` at `0x1400232a8`
- `FLTMGR!FltReleaseContext` at `0x1400233f7`
- `FLTMGR!FltReleaseContext` at `0x14002340f`
- `FLTMGR!FltReleaseContext` at `0x140023294`
- `FLTMGR!FltReleaseContext` at `0x1400232a8`
- `FLTMGR!FltReleaseContext` at `0x1400233f7`
- `FLTMGR!FltReleaseContext` at `0x14002340f`

## string_xrefs

- `0x1400223cc`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022bf5`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022c57`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022d34`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022d74`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022e17`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140022fc4`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023011`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400232c1`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400232ec`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _UNKNOWN **a3)
{
  int v3; // r12d
  void *v4; // r13
  __int64 v5; // rsi
  int v7; // edi
  char v8; // r14
  char *v9; // r15
  int v10; // eax
  ULONG_PTR *p_Information; // r15
  char v12; // r12
  int v13; // eax
  __int64 v14; // rcx
  NTSTATUS Status; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // r10
  char v17; // di
  int v18; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v19; // r8
  struct _FLT_INSTANCE *v20; // rdx
  int UnparsedNameLength; // eax
  char v22; // r12
  PFLT_IO_PARAMETER_BLOCK v23; // rcx
  char v24; // r14
  char v25; // r10
  char FsInformationClass_high; // al
  int v27; // eax
  int UnionContextByFileName; // eax
  PECP_LIST v29; // r14
  struct _FLT_INSTANCE **v30; // r14
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int SetContextFileObject; // eax
  int v35; // r11d
  PFLT_IO_PARAMETER_BLOCK v36; // r9
  char v37; // r12
  bool v38; // zf
  int v39; // eax
  int v40; // edx
  struct _FLT_INSTANCE *v41; // rcx
  int v42; // edx
  int v43; // r8d
  int v44; // eax
  int v45; // edx
  _UNKNOWN **v46; // r8
  struct _FILE_OBJECT *v47; // rsi
  struct _FLT_INSTANCE *v48; // r14
  char ContextFileObject; // al
  HANDLE v50; // r14
  PFLT_CONTEXT v51; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v52; // rcx
  __int64 v53; // r8
  __int64 v54; // rdx
  int EcpContextSize; // [rsp+20h] [rbp-89h]
  int EcpContextSizea; // [rsp+20h] [rbp-89h]
  int v58; // [rsp+28h] [rbp-81h]
  int v59; // [rsp+28h] [rbp-81h]
  int v60; // [rsp+30h] [rbp-79h]
  int v61; // [rsp+30h] [rbp-79h]
  int v62; // [rsp+38h] [rbp-71h]
  int v63; // [rsp+38h] [rbp-71h]
  int v64; // [rsp+40h] [rbp-69h]
  int v65; // [rsp+40h] [rbp-69h]
  int v66; // [rsp+48h] [rbp-61h]
  int v67; // [rsp+50h] [rbp-59h]
  char v68; // [rsp+78h] [rbp-31h]
  PECP_LIST EcpList; // [rsp+80h] [rbp-29h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-21h] BYREF
  PFLT_CONTEXT Context; // [rsp+90h] [rbp-19h] BYREF
  unsigned int v72; // [rsp+98h] [rbp-11h]
  PVOID Object; // [rsp+A0h] [rbp-9h] BYREF
  PFLT_CONTEXT v74; // [rsp+A8h] [rbp-1h] BYREF
  PFLT_CONTEXT v75; // [rsp+B0h] [rbp+7h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp+Fh] BYREF
  ULONG v77; // [rsp+110h] [rbp+67h] BYREF
  PVOID EcpContext; // [rsp+120h] [rbp+77h] BYREF

  v3 = *((_DWORD *)a3 + 5);
  v4 = a3;
  v5 = a2;
  LOBYTE(v7) = 0;
  v72 = 0;
  v8 = 0;
  LOBYTE(v77) = 0;
  v9 = 0;
  Object = 0;
  EcpList = 0;
  *(_OWORD *)P = 0;
  LODWORD(FileHandle) = 0;
  v74 = 0;
  v75 = 0;
  if ( CallbackData->IoStatus.Status < 0 )
  {
    v10 = PrjfProcessFileDirectoryStatus();
    LOBYTE(v7) = v10;
    if ( v10 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          30,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          55,
          v10);
      }
      goto LABEL_156;
    }
    if ( CallbackData->IoStatus.Status < 0 )
      goto LABEL_156;
  }
  p_Information = &CallbackData->IoStatus.Information;
  v12 = v3 & 1;
  if ( v12 )
  {
    LODWORD(Context) = 0;
    while ( 1 )
    {
      v13 = PrjfCheckAndCancelTransactedOpen((__int64)CallbackData, (_QWORD *)v5);
      LOBYTE(v7) = v13;
      if ( v13 < 0 )
        goto LABEL_133;
      Status = CallbackData->IoStatus.Status;
      if ( Status != 260 )
      {
        if ( !Status )
          goto LABEL_81;
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2);
        if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(a2) = BYTE8(xmmword_14001A3D0) & 0x20;
          WPP_RECORDER_AND_TRACE_SF_sDqDld(
            773,
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3,
            v58,
            39,
            v62,
            v64,
            172,
            *(_QWORD *)(v5 + 32),
            (char)CallbackData->Iopb->Parameters.QueryEa.EaList,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            v7);
        }
        goto LABEL_32;
      }
      Iopb = CallbackData->Iopb;
      if ( (Iopb->Parameters.Create.Options & 0x2000) != 0 )
      {
        CallbackData->IoStatus.Status = -1073741766;
        v72 = 4;
        *p_Information = 0;
        if ( (xmmword_14001A3E0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = xmmword_14001A3E0 & 0x20;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZDl(
            1029,
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            4,
            v58,
            31,
            v62,
            v64,
            106,
            58,
            *(_QWORD *)(v5 + 32) + 88LL,
            (char)Iopb->Parameters.QueryEa.EaList,
            HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass));
        }
        goto LABEL_32;
      }
      if ( v8 )
      {
        if ( (*((_DWORD *)v4 + 5) & 4) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2);
        CallbackData->IoStatus.Status = -1073741766;
        *p_Information = 0;
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDqDld(
            517,
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            v58,
            32,
            v62,
            v64,
            143,
            *(_QWORD *)(v5 + 32),
            (char)CallbackData->Iopb->Parameters.QueryEa.EaList,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            58);
        }
        goto LABEL_32;
      }
      v17 = (char)Context;
      if ( (_WORD)Context == CallbackData->TagData->UnparsedNameLength && !(_DWORD)FileHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2);
        LOBYTE(a2) = BYTE8(xmmword_14001A3D0) & 0x20;
        if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDZdDl(
            *((_DWORD *)v4 + 12) + 8,
            a2,
            v18,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            EcpContextSize,
            v58,
            v60,
            v62,
            v64,
            v66,
            *((_QWORD *)v4 + 6) + 8LL,
            v17,
            CallbackData->Iopb->Parameters.Create.Options,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass));
        }
      }
      if ( !CallbackData->TagData->UnparsedNameLength )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, a2);
      v19 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)v4 + 6);
      v20 = *(struct _FLT_INSTANCE **)(v5 + 24);
      UnparsedNameLength = CallbackData->TagData->UnparsedNameLength;
      LOBYTE(EcpContext) = 0;
      LODWORD(Context) = UnparsedNameLength;
      v7 = PrjfProcessPrjReparsePointBounce(
             CallbackData,
             v20,
             v19,
             (__int64)&FileHandle,
             (__int64)&v77,
             (__int64)&Object,
             (__int64)&EcpContext);
      if ( v7 < 0 )
      {
        CallbackData->IoStatus.Status = v7;
        *p_Information = 0;
        if ( v7 == -1073741772 || v7 == -1073741766 )
          goto LABEL_32;
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZDl(
            517,
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            v58,
            34,
            v62,
            v64,
            222,
            v7,
            *((_QWORD *)v4 + 6) + 8LL,
            CallbackData->Iopb->Parameters.Create.Options,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass));
        }
        goto LABEL_66;
      }
      v22 = v77;
      *((_DWORD *)v4 + 5) = -2147483644;
      *((_WORD *)v4 + 21) = 0;
      if ( v22 )
        *((_DWORD *)v4 + 5) = 0x80000000;
      FltReissueSynchronousIo(*(PFLT_INSTANCE *)(v5 + 24), CallbackData);
      v24 = *((_BYTE *)v4 + 20) & 1;
      if ( !(_BYTE)EcpContext )
        goto LABEL_38;
      if ( v22 )
        break;
      if ( !v24 || CallbackData->IoStatus.Status != 260 )
        goto LABEL_38;
      v25 = (char)Context;
      if ( (_WORD)Context == CallbackData->TagData->UnparsedNameLength && !(_DWORD)FileHandle )
      {
        *p_Information = 0;
        LOBYTE(v7) = -27;
        CallbackData->IoStatus.Status = -1073741595;
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZqdDl(
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            EcpContextSize,
            v58,
            v60,
            v62,
            v64,
            v66,
            v67,
            *((_QWORD *)v4 + 6) + 8LL,
            *(_QWORD *)(v5 + 32),
            v25,
            (char)CallbackData->Iopb->Parameters.QueryEa.EaList,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass));
        }
        goto LABEL_32;
      }
LABEL_39:
      p_Information = &CallbackData->IoStatus.Information;
      if ( CallbackData->IoStatus.Information == 2 )
      {
        if ( !v22 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, a2);
        if ( v24 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, a2);
        v27 = PrjfSetPlaceHolderFlagsSynchronized(CallbackData, *(PFLT_INSTANCE *)(v5 + 24), (PFILE_OBJECT)Object);
        LOBYTE(v7) = v27;
        if ( v27 < 0
          && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
        {
          LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDDld(
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            a2,
            (_DWORD)a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            EcpContextSize,
            v58,
            v60,
            v62,
            v64,
            v66,
            (char)CallbackData->Iopb->Parameters.QueryEa.EaList,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            v27);
        }
        v12 = v24;
        goto LABEL_81;
      }
      if ( Object )
      {
        ObfDereferenceObject(Object);
        Object = 0;
      }
      v12 = v24;
      if ( !v24 )
        goto LABEL_80;
      v8 = v77;
    }
    v23 = CallbackData->Iopb;
    FsInformationClass_high = HIBYTE(v23->Parameters.SetVolumeInformation.FsInformationClass);
    if ( (FsInformationClass_high == 1 || FsInformationClass_high == 4) && CallbackData->IoStatus.Status == -1073741772 )
    {
      a3 = &WPP_RECORDER_INITIALIZED;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZqDl(
          v23->Parameters.Create.Options & 0xFFFFFF,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          EcpContextSize,
          v58,
          36,
          v62,
          v64,
          75,
          52,
          *((_QWORD *)v4 + 6) + 8LL,
          *(_QWORD *)(v5 + 32),
          (char)v23->Parameters.QueryEa.EaList,
          FsInformationClass_high);
      }
      *p_Information = 0;
      LOBYTE(v7) = -27;
      CallbackData->IoStatus.Status = -1073741595;
      goto LABEL_32;
    }
    if ( FsInformationClass_high == 2 && CallbackData->IoStatus.Status >= 0 )
    {
      *p_Information = 0;
      LOBYTE(v7) = -27;
      CallbackData->IoStatus.Status = -1073741595;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZqDl(
          v23->Parameters.Create.Options & 0xFFFFFF,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          EcpContextSize,
          v58,
          37,
          v62,
          v64,
          102,
          229,
          *(_QWORD *)(v5 + 32) + 88LL,
          *(_QWORD *)(v5 + 32),
          (char)v23->Parameters.QueryEa.EaList,
          HIBYTE(v23->Parameters.SetVolumeInformation.FsInformationClass));
      }
      PrjfCancelFileOpen(
        (__int64)CallbackData,
        *(struct _FLT_INSTANCE **)(v5 + 24),
        *(struct _FILE_OBJECT **)(v5 + 32),
        -1073741595);
      goto LABEL_32;
    }
LABEL_38:
    if ( CallbackData->IoStatus.Status < 0 )
      goto LABEL_32;
    goto LABEL_39;
  }
LABEL_80:
  v12 = 0;
LABEL_81:
  if ( CallbackData->IoStatus.Status != 260 || *p_Information != 2684354594 )
  {
LABEL_86:
    v29 = EcpList;
    goto LABEL_87;
  }
  UnionContextByFileName = PrjfGetUnionContextByFileNameEx(
                             CallbackData,
                             1,
                             *(struct _FLT_INSTANCE **)(v5 + 24),
                             0,
                             (char **)&EcpList,
                             (__int64)P,
                             0);
  LOBYTE(v7) = UnionContextByFileName;
  if ( UnionContextByFileName < 0 )
  {
    if ( UnionContextByFileName != -1073741191 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          517,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          40,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          231,
          *(_QWORD *)(v5 + 32),
          UnionContextByFileName);
        goto LABEL_96;
      }
LABEL_32:
      v9 = (char *)EcpList;
      goto LABEL_154;
    }
    CallbackData->IoStatus.Status = -1073741766;
    CallbackData->TagData = 0;
    FltSetCallbackDataDirty(CallbackData);
    LOBYTE(v7) = 0;
    goto LABEL_86;
  }
  v29 = EcpList;
  if ( EcpList )
  {
    v32 = PrjfCheckAndCancelTransactedOpen((__int64)CallbackData, (_QWORD *)v5);
    LOBYTE(v7) = v32;
    if ( v32 < 0 )
      goto LABEL_133;
  }
  v33 = PrjfProcessTombstoneBounce(CallbackData, *(PFLT_INSTANCE *)(v5 + 24), (__int64)v29);
  v7 = v33;
  if ( v33 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        41,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        4,
        v33);
    }
    CallbackData->IoStatus.Status = v7;
    *p_Information = 0;
    goto LABEL_104;
  }
LABEL_87:
  if ( CallbackData->IoStatus.Status )
  {
LABEL_133:
    v9 = (char *)EcpList;
    goto LABEL_154;
  }
  v38 = v29 == 0;
  v30 = (struct _FLT_INSTANCE **)(v5 + 24);
  if ( v38 )
  {
    v31 = PrjfGetUnionContextByFileNameEx(CallbackData, 0, *v30, 0, (char **)&EcpList, (__int64)P, 0);
    LOBYTE(v7) = v31;
    if ( v31 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          517,
          a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          42,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          39,
          *(_QWORD *)(v5 + 32),
          v31);
LABEL_96:
        v9 = (char *)EcpList;
        goto LABEL_154;
      }
      goto LABEL_32;
    }
    if ( !EcpList )
    {
      if ( v12 )
      {
        SetContextFileObject = PrjfGetSetContextFileObject(
                                 *v30,
                                 *(PFILE_OBJECT *)(v5 + 32),
                                 0x80000000,
                                 1,
                                 0,
                                 0,
                                 0,
                                 &v75,
                                 &v74);
        LOBYTE(v7) = SetContextFileObject;
        if ( SetContextFileObject < 0 )
        {
          if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              517,
              a2,
              (_DWORD)a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              5,
              43,
              (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
              72,
              SetContextFileObject);
LABEL_104:
            v9 = (char *)EcpList;
            goto LABEL_154;
          }
LABEL_66:
          v9 = (char *)EcpList;
          goto LABEL_154;
        }
        v35 = *((_DWORD *)v75 + 16);
        if ( v35 != 3 )
        {
          v36 = CallbackData->Iopb;
          v37 = 0;
          LODWORD(a3) = *(_DWORD *)(v36->Parameters.WMI.ProviderId + 16);
          FileHandle = 0;
          EcpContext = 0;
          if ( *(_DWORD *)v74 <= 1u )
          {
            if ( !*p_Information || *p_Information == 3 )
              v37 = 1;
            v38 = ((unsigned __int8)a3 & 6) == 0;
          }
          else
          {
            v38 = ((unsigned __int8)a3 & 0x16) == 0;
          }
          if ( !v38 )
          {
            LOBYTE(v7) = 1;
            if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v68 = (char)a3;
              LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              LOBYTE(a2) = BYTE8(xmmword_14001A3D0) & 0x20;
              WPP_RECORDER_AND_TRACE_SF_sDdZDlLL(
                HIBYTE(v36->Parameters.SetVolumeInformation.FsInformationClass),
                a2,
                (_DWORD)a3,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                EcpContextSizea,
                v59,
                v61,
                v63,
                v65,
                v66,
                v67,
                *(_QWORD *)(v5 + 32) + 88LL,
                (char)v36->Parameters.QueryEa.EaList,
                HIBYTE(v36->Parameters.SetVolumeInformation.FsInformationClass),
                v35,
                v68);
            }
            PrjfCancelFileOpen((__int64)CallbackData, *v30, *(struct _FILE_OBJECT **)(v5 + 32), -1073689087);
            if ( v37 )
            {
              v39 = PrjfOpenAsReparsePoint(*((_QWORD *)v4 + 6) + 8LL, 0, *v30, 65920);
              if ( v39 < 0
                && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
              {
                LOBYTE(v40) = xmmword_14001A3D0 & 0x20;
                LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  517,
                  v40,
                  (_DWORD)a3,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  2,
                  5,
                  45,
                  (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
                  181,
                  v39);
              }
            }
            LODWORD(a2) = (_DWORD)EcpContext;
            if ( EcpContext )
            {
              v41 = *v30;
              v77 = 0;
              if ( (int)PrjfSetDeleteDisposition(v41, (PFILE_OBJECT)EcpContext, 0, (__int64)&v77) < 0
                && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
              {
                LOBYTE(v42) = xmmword_14001A3D0 & 0x20;
                LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDdd(517, v42, v43, *((_QWORD *)WPP_GLOBAL_Control + 8));
              }
              FltClose(FileHandle);
              ObfDereferenceObject(EcpContext);
            }
            goto LABEL_66;
          }
        }
      }
      goto LABEL_133;
    }
  }
  v44 = PrjfCheckAndCancelTransactedOpen((__int64)CallbackData, (_QWORD *)v5);
  v9 = (char *)EcpList;
  LOBYTE(v7) = v44;
  if ( v44 >= 0 )
  {
    v7 = PrjfProcessOpenWithinVirtualizationRoots(
           CallbackData,
           *v30,
           *(PFILE_OBJECT *)(v5 + 32),
           (__int64)EcpList,
           (__int64)P);
    if ( v7 < 0 )
    {
      v46 = &WPP_RECORDER_INITIALIZED;
      if ( (xmmword_14001A3D0 & 0x20) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_140:
          PrjfCancelFileOpen((__int64)CallbackData, *v30, *(struct _FILE_OBJECT **)(v5 + 32), v7);
          goto LABEL_154;
        }
        v30 = (struct _FLT_INSTANCE **)(v5 + 24);
      }
      LOBYTE(v45) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v46) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZDl(
        517,
        v45,
        (_DWORD)v46,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        v58,
        47,
        v62,
        v64,
        251,
        v7,
        *(_QWORD *)(v5 + 32) + 88LL,
        CallbackData->Iopb->Parameters.Create.Options,
        HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass));
      goto LABEL_140;
    }
    v47 = *(struct _FILE_OBJECT **)(v5 + 32);
    v48 = *v30;
    EcpList = 0;
    EcpContext = 0;
    Context = 0;
    FileHandle = 0;
    v77 = 0;
    if ( FltGetEcpListFromCallbackData(Globals, CallbackData, &EcpList) >= 0
      && FltFindExtraCreateParameter(Globals, EcpList, &GUID_ECP_CREATE_REDIRECTION, &EcpContext, &v77) >= 0 )
    {
      if ( *(_WORD *)EcpContext < 4u )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(4, a2);
      ContextFileObject = PrjfGetContextFileObject(v48, v47, (__int64 *)&Context, &FileHandle);
      v50 = FileHandle;
      v51 = Context;
      if ( ContextFileObject )
      {
        if ( !Context )
        {
LABEL_152:
          if ( v50 )
            FltReleaseContext(v50);
          goto LABEL_154;
        }
        if ( *((_DWORD *)Context + 16) != 3 && !*(_DWORD *)FileHandle )
        {
          *((_WORD *)EcpContext + 1) |= 0x10u;
          FltAcknowledgeEcp(Globals, EcpContext);
        }
      }
      if ( v51 )
        FltReleaseContext(v51);
      goto LABEL_152;
    }
  }
LABEL_154:
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_156:
  v52 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)v4 + 6);
  if ( v52 )
  {
    if ( CallbackData->IoStatus.Status == -1073741191
      && ((BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(a2) = BYTE8(xmmword_14001A3D0) & 0x20;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        773,
        a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        5,
        48,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        25,
        v7,
        (__int64)&v52->Name);
      v52 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)v4 + 6);
    }
    FltReleaseFileNameInformation(v52);
  }
  if ( *(void **)v4 != v4 )
    FltRemoveOpenReparseEntry(Globals, CallbackData, v4);
  v53 = *((_QWORD *)v4 + 7);
  if ( v53 )
  {
    FltRemoveOpenReparseEntry(Globals, CallbackData, v53);
    ExFreeToPagedLookasideList(&stru_14001A6C0, *((PVOID *)v4 + 7));
  }
  ExFreeToPagedLookasideList(&stru_14001A740, v4);
  if ( v74 )
    FltReleaseContext(v74);
  if ( v75 )
    FltReleaseContext(v75);
  if ( v9 )
    PrjfReleaseUnionContext(v9, v54);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  return v72;
}

```

## disassembly

```asm
0x140022320  mov     [rsp-8+arg_8], rbx
0x140022325  push    rbp
0x140022326  push    rsi
0x140022327  push    rdi
0x140022328  push    r12
0x14002232a  push    r13
0x14002232c  push    r14
0x14002232e  push    r15
0x140022330  lea     rbp, [rsp-27h]
0x140022335  sub     rsp, 0D0h
0x14002233c  mov     r12d, [r8+14h]
0x140022340  xor     r9d, r9d
0x140022343  xorps   xmm0, xmm0
0x140022346  mov     r13, r8
0x140022349  mov     rsi, rdx
0x14002234c  mov     rbx, rcx
0x14002234f  mov     edi, r9d
0x140022352  mov     [rbp+57h+var_68], r9d
0x140022356  mov     r14b, r9b
0x140022359  mov     byte ptr [rbp+57h+arg_0], r9b
0x14002235d  mov     r15d, r9d
0x140022360  mov     [rbp+57h+Object], r9
0x140022364  mov     [rbp+57h+EcpList], r9
0x140022368  movups  xmmword ptr [rbp+57h+P], xmm0
0x14002236c  mov     dword ptr [rbp+57h+FileHandle], r9d
0x140022370  mov     [rbp+57h+var_58], r9
0x140022374  mov     [rbp+57h+var_50], r9
0x140022378  cmp     [rcx+18h], r9d
0x14002237c  jge     loc_140022416
0x140022382  call    PrjfProcessFileDirectoryStatus
0x140022387  xor     r9d, r9d
0x14002238a  mov     edi, eax
0x14002238c  test    eax, eax
0x14002238e  jns     short loc_14002240C
0x140022390  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140022396  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002239d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400223a4  lea     r12d, [r15+20h]
0x1400223a8  setnz   r8b
0x1400223ac  and     dl, r12b
0x1400223af  jnz     short loc_1400223BA
0x1400223b1  test    r8b, r8b
0x1400223b4  jz      loc_1400232EC
0x1400223ba  mov     r9, cs:WPP_GLOBAL_Control
0x1400223c1  lea     r10, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400223c8  mov     dword ptr [rsp+100h+var_B0], eax
0x1400223cc  lea     r14, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400223d3  mov     dword ptr [rsp+100h+var_B8], 537h
0x1400223db  mov     ecx, 205h
0x1400223e0  mov     [rsp+100h+var_C0], r14
0x1400223e5  mov     r9, [r9+40h]
0x1400223e9  mov     [rsp+100h+var_C8], r10
0x1400223ee  mov     word ptr [rsp+100h+var_D0], 1Eh
0x1400223f5  mov     dword ptr [rsp+100h+var_D8], 5
0x1400223fd  mov     byte ptr [rsp+100h+EcpContextSize], 2
0x140022402  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140022407  jmp     loc_1400232F3
0x14002240c  cmp     [rbx+18h], r9d
0x140022410  jl      loc_1400232DF
0x140022416  lea     r15, [rbx+20h]
0x14002241a  and     r12b, 1
0x14002241e  jz      loc_140022B02
0x140022424  mov     dword ptr [rbp+57h+Context], r9d
0x140022428  mov     rdx, rsi
0x14002242b  mov     rcx, rbx
0x14002242e  call    PrjfCheckAndCancelTransactedOpen
0x140022433  xor     r9d, r9d
0x140022436  mov     edi, eax
0x140022438  test    eax, eax
0x14002243a  js      loc_1400230D6
0x140022440  mov     eax, [rbx+18h]
0x140022443  cmp     eax, 104h
0x140022448  jnz     loc_140022A7D
0x14002244e  mov     r10, [rbx+10h]
0x140022452  test    dword ptr [r10+20h], 2000h
0x14002245a  jnz     loc_1400229E2
0x140022460  test    r14b, r14b
0x140022463  jnz     loc_140022940
0x140022469  mov     rax, [rbx+28h]
0x14002246d  mov     edi, dword ptr [rbp+57h+Context]
0x140022470  cmp     di, [rax+6]
0x140022474  jnz     short loc_1400224F3
0x140022476  cmp     dword ptr [rbp+57h+FileHandle], r9d
0x14002247a  jnz     short loc_1400224F3
0x14002247c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140022481  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140022487  lea     rax, WPP_RECORDER_INITIALIZED
0x14002248e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022495  mov     r12d, 20h ; ' '
0x14002249b  setnz   r8b
0x14002249f  xor     r9d, r9d
0x1400224a2  and     dl, r12b
0x1400224a5  jnz     short loc_1400224AC
0x1400224a7  test    r8b, r8b
0x1400224aa  jz      short loc_1400224F9
0x1400224ac  mov     rax, [rbx+10h]
0x1400224b0  mov     rcx, [r13+30h]
0x1400224b4  add     rcx, 8
0x1400224b8  movzx   r9d, byte ptr [rax+23h]
0x1400224bd  mov     r10d, [rax+20h]
0x1400224c1  mov     [rsp+100h+var_98], r9d
0x1400224c6  and     r10d, 0FFFFFFh
0x1400224cd  mov     r9, cs:WPP_GLOBAL_Control
0x1400224d4  mov     dword ptr [rsp+100h+var_A0], r10d
0x1400224d9  movzx   eax, di
0x1400224dc  mov     dword ptr [rsp+100h+var_A8], eax
0x1400224e0  mov     r9, [r9+40h]
0x1400224e4  mov     [rsp+100h+var_B0], rcx
0x1400224e9  call    WPP_RECORDER_AND_TRACE_SF_sDZdDl
0x1400224ee  xor     r9d, r9d
0x1400224f1  jmp     short loc_1400224F9
0x1400224f3  mov     r12d, 20h ; ' '
0x1400224f9  mov     rax, [rbx+28h]
0x1400224fd  cmp     [rax+6], r9w
0x140022502  ja      short loc_14002250C
0x140022504  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140022509  xor     r9d, r9d
0x14002250c  mov     rax, [rbx+28h]
0x140022510  lea     rcx, [rbp+57h+EcpContext]
0x140022514  mov     r8, [r13+30h]
0x140022518  mov     rdx, [rsi+18h]
0x14002251c  mov     [rsp+100h+var_C8], rcx
0x140022521  lea     rcx, [rbp+57h+Object]
0x140022525  movzx   eax, word ptr [rax+6]
0x140022529  mov     [rsp+100h+var_D0], rcx
0x14002252e  lea     rcx, [rbp+57h+arg_0]
0x140022532  mov     [rsp+100h+var_D8], rcx
0x140022537  lea     rcx, [rbp+57h+FileHandle]
0x14002253b  mov     [rsp+100h+EcpContextSize], rcx
0x140022540  mov     rcx, rbx
0x140022543  mov     byte ptr [rbp+57h+EcpContext], r9b
0x140022547  movzx   r9d, ax
0x14002254b  mov     dword ptr [rbp+57h+Context], eax
0x14002254e  call    PrjfProcessPrjReparsePointBounce
0x140022553  xor     r9d, r9d
0x140022556  mov     edi, eax
0x140022558  test    eax, eax
0x14002255a  js      loc_140022894
0x140022560  mov     r12b, byte ptr [rbp+57h+arg_0]
0x140022564  mov     dword ptr [r13+14h], 80000004h
0x14002256c  mov     [r13+2Ah], r9w
0x140022571  test    r12b, r12b
0x140022574  jz      short loc_14002257E
0x140022576  mov     dword ptr [r13+14h], 80000000h
0x14002257e  mov     rcx, [rsi+18h]; InitiatingInstance
0x140022582  mov     rdx, rbx; CallbackData
0x140022585  call    cs:__imp_FltReissueSynchronousIo
0x14002258c  nop     dword ptr [rax+rax+00h]
0x140022591  mov     r14b, [r13+14h]
0x140022595  xor     r9d, r9d
0x140022598  and     r14b, 1
0x14002259c  cmp     byte ptr [rbp+57h+EcpContext], r9b
0x1400225a0  jz      loc_140022695
0x1400225a6  test    r12b, r12b
0x1400225a9  jnz     loc_14002266B
0x1400225af  test    r14b, r14b
0x1400225b2  jz      loc_140022695
0x1400225b8  cmp     dword ptr [rbx+18h], 104h
0x1400225bf  jnz     loc_140022695
0x1400225c5  mov     rax, [rbx+28h]
0x1400225c9  mov     r10d, dword ptr [rbp+57h+Context]
0x1400225cd  cmp     r10w, [rax+6]
0x1400225d2  jnz     loc_14002269F
0x1400225d8  cmp     dword ptr [rbp+57h+FileHandle], r9d
0x1400225dc  jnz     loc_14002269F
0x1400225e2  mov     r14d, 0C00000E5h
0x1400225e8  mov     [r15], r9
0x1400225eb  mov     edi, r14d
0x1400225ee  mov     [rbx+18h], r14d
0x1400225f2  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400225f8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400225ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022606  lea     r12d, [r9+20h]
0x14002260a  setnz   r8b
0x14002260e  and     dl, r12b
0x140022611  jnz     short loc_140022618
0x140022613  test    r8b, r8b
0x140022616  jz      short loc_140022662
0x140022618  mov     rax, [rbx+10h]
0x14002261c  mov     r9d, [rax+20h]
0x140022620  movzx   ecx, byte ptr [rax+23h]
0x140022624  and     r9d, 0FFFFFFh
0x14002262b  mov     dword ptr [rsp+100h+var_88], ecx
0x14002262f  mov     [rsp+100h+var_90], r9d
0x140022634  mov     r9, cs:WPP_GLOBAL_Control
0x14002263b  movzx   eax, r10w
0x14002263f  mov     r10, [r13+30h]
0x140022643  mov     [rsp+100h+var_98], eax
0x140022647  add     r10, 8
0x14002264b  mov     rax, [rsi+20h]
0x14002264f  mov     r9, [r9+40h]
0x140022653  mov     [rsp+100h+var_A0], rax
0x140022658  mov     [rsp+100h+var_A8], r10
0x14002265d  call    WPP_RECORDER_AND_TRACE_SF_sDdZqdDl
0x140022662  mov     r15, [rbp+57h+EcpList]
0x140022666  jmp     loc_1400232BA
0x14002266b  mov     rcx, [rbx+10h]
0x14002266f  movzx   eax, byte ptr [rcx+23h]
0x140022673  cmp     al, 1
0x140022675  jz      short loc_14002267B
0x140022677  cmp     al, 4
0x140022679  jnz     short loc_14002268B
0x14002267b  mov     r11d, 0C0000034h
0x140022681  cmp     [rbx+18h], r11d
0x140022685  jz      loc_140022779
0x14002268b  cmp     al, 2
0x14002268d  jnz     short loc_140022695
0x14002268f  cmp     [rbx+18h], r9d
0x140022693  jge     short loc_1400226DE
0x140022695  cmp     [rbx+18h], r9d
0x140022699  jl      loc_140022935
0x14002269f  lea     r15, [rbx+20h]
0x1400226a3  cmp     qword ptr [r15], 2
0x1400226a7  jz      loc_140022804
0x1400226ad  mov     rcx, [rbp+57h+Object]; Object
0x1400226b1  test    rcx, rcx
0x1400226b4  jz      short loc_1400226C9
0x1400226b6  call    cs:__imp_ObfDereferenceObject
0x1400226bd  nop     dword ptr [rax+rax+00h]
0x1400226c2  xor     r9d, r9d
0x1400226c5  mov     [rbp+57h+Object], r9
0x1400226c9  mov     r12b, r14b
0x1400226cc  test    r14b, r14b
0x1400226cf  jz      loc_140022B02
0x1400226d5  mov     r14b, byte ptr [rbp+57h+arg_0]
0x1400226d9  jmp     loc_140022428
0x1400226de  mov     r14d, 0C00000E5h
0x1400226e4  mov     [r15], r9
0x1400226e7  mov     edi, r14d
0x1400226ea  mov     [rbx+18h], r14d
0x1400226ee  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400226f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400226fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022702  mov     r12d, 20h ; ' '
0x140022708  setnz   r8b
0x14002270c  and     dl, r12b
0x14002270f  jnz     short loc_140022716
0x140022711  test    r8b, r8b
0x140022714  jz      short loc_140022761
0x140022716  movzx   eax, byte ptr [rcx+23h]
0x14002271a  mov     r11, [rsi+20h]
0x14002271e  mov     ecx, [rcx+20h]
0x140022721  mov     r9, cs:WPP_GLOBAL_Control
0x140022728  and     ecx, 0FFFFFFh
0x14002272e  mov     [rsp+100h+var_90], eax
0x140022732  mov     [rsp+100h+var_98], ecx
0x140022736  lea     r10, [r11+58h]
0x14002273a  mov     [rsp+100h+var_A0], r11
0x14002273f  mov     r9, [r9+40h]
0x140022743  mov     [rsp+100h+var_A8], r10
0x140022748  mov     dword ptr [rsp+100h+var_B0], r14d
0x14002274d  mov     dword ptr [rsp+100h+var_B8], 666h
0x140022755  mov     word ptr [rsp+100h+var_D0], 25h ; '%'
0x14002275c  call    WPP_RECORDER_AND_TRACE_SF_sDdZqDl
0x140022761  mov     r8, [rsi+20h]
0x140022765  mov     r9d, r14d
0x140022768  mov     rdx, [rsi+18h]
0x14002276c  mov     rcx, rbx
0x14002276f  call    PrjfCancelFileOpen
0x140022774  jmp     loc_140022662
0x140022779  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002277f  lea     r8, WPP_RECORDER_INITIALIZED
0x140022786  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14002278d  mov     r12d, 20h ; ' '
0x140022793  setnz   r8b
0x140022797  and     dl, r12b
0x14002279a  jnz     short loc_1400227A1
0x14002279c  test    r8b, r8b
0x14002279f  jz      short loc_1400227EF
0x1400227a1  mov     ecx, [rcx+20h]
0x1400227a4  mov     r9, [r13+30h]
0x1400227a8  and     ecx, 0FFFFFFh
0x1400227ae  mov     [rsp+100h+var_90], eax
0x1400227b2  add     r9, 8
0x1400227b6  mov     rax, [rsi+20h]
0x1400227ba  mov     [rsp+100h+var_98], ecx
0x1400227be  mov     [rsp+100h+var_A0], rax
0x1400227c3  mov     [rsp+100h+var_A8], r9
0x1400227c8  mov     r9, cs:WPP_GLOBAL_Control
0x1400227cf  mov     dword ptr [rsp+100h+var_B0], r11d
0x1400227d4  mov     dword ptr [rsp+100h+var_B8], 64Bh
0x1400227dc  mov     word ptr [rsp+100h+var_D0], 24h ; '$'
0x1400227e3  mov     r9, [r9+40h]
0x1400227e7  call    WPP_RECORDER_AND_TRACE_SF_sDdZqDl
0x1400227ec  xor     r9d, r9d
0x1400227ef  mov     r14d, 0C00000E5h
0x1400227f5  mov     [r15], r9
0x1400227f8  mov     edi, r14d
0x1400227fb  mov     [rbx+18h], r14d
0x1400227ff  jmp     loc_140022662
0x140022804  test    r12b, r12b
0x140022807  jnz     short loc_14002280E
0x140022809  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002280e  test    r14b, r14b
0x140022811  jz      short loc_140022818
0x140022813  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140022818  mov     r8, [rbp+57h+Object]; FileObject
0x14002281c  mov     r9d, 2
0x140022822  mov     rdx, [rsi+18h]; Instance
0x140022826  mov     rcx, rbx; CallbackData
  ... truncated ...
```
