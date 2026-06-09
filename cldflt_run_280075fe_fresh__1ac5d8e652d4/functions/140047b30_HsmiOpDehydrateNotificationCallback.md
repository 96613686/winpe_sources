# HsmiOpDehydrateNotificationCallback

- ea: `0x140047b30`
- end: `0x140048828`
- name: `HsmiOpDehydrateNotificationCallback`
- size: `3320`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `33`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x140003c50`
- `0x140006da0`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000d09c`
- `0x140015248`
- `0x140015e40`
- `0x1400160dc`
- `0x14001e140`
- `0x14003547c`
- `0x1400356f0`
- `0x1400365e8`
- `0x140043234`
- `0x140047b30`
- `0x1400547b0`
- `0x140056520`
- `0x140058cbc`
- `0x140058cd8`
- `0x140059618`
- `0x14005c8c0`
- `0x14005cd20`
- `0x1400651c4`
- `0x14006781c`
- `0x140067838`
- `0x140067b50`
- `0x140067d04`
- `0x14006f080`
- `0x14006f16c`
- `0x14007446c`
- `0x140075cd0`
- `0x140075d4c`
- `0x14007658c`
- `0x14007ecd4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004877a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400487d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004877a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400487d4`
- `ntoskrnl!ExAllocatePool2` at `0x140048569`
- `ntoskrnl!ExAllocatePool2` at `0x140048569`
- `FLTMGR!FltQueryInformationFile` at `0x140048074`
- `FLTMGR!FltQueryInformationFile` at `0x140048074`
- `FLTMGR!FltFsControlFile` at `0x1400484ab`
- `FLTMGR!FltFsControlFile` at `0x1400484ab`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400487f4`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400487f4`
- `FLTMGR!FltGetRequestorProcess` at `0x140047d20`
- `FLTMGR!FltGetRequestorProcess` at `0x140047d20`
- `FLTMGR!FltReleasePushLockEx` at `0x14004875d`
- `FLTMGR!FltReleasePushLockEx` at `0x14004875d`
- `FLTMGR!FltReleaseContext` at `0x1400487c0`
- `FLTMGR!FltReleaseContext` at `0x1400487c0`

## pseudocode

```c
void __fastcall HsmiOpDehydrateNotificationCallback(__int64 a1, int a2)
{
  struct _FLT_CALLBACK_DATA *v2; // r13
  __int64 InformationFile; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  PMDL *MdlChain; // r15
  __int64 v7; // rdi
  struct _FILE_OBJECT *TargetFileObject; // rsi
  __int64 v9; // r14
  __int64 v10; // r12
  int Timer_high; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  PEPROCESS RequestorProcess; // rax
  __int64 v19; // rdx
  __int64 StreamSize; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // eax
  int v30; // r9d
  int v31; // r11d
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rsi
  __int64 v38; // rax
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  char v41; // al
  __int64 v42; // r10
  __int16 v43; // dx
  __int64 v44; // r8
  unsigned int v45; // edx
  __int64 v46; // rcx
  int v47; // edx
  __int64 v48; // rcx
  int v49; // r8d
  unsigned __int64 v50; // rsi
  __int64 v51; // r8
  unsigned int v52; // eax
  __int64 LastHydrationTime; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  int LastDehydrationReason; // eax
  int v57; // r8d
  int v58; // r9d
  __int64 v59; // r10
  int v60; // r11d
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // r8
  _QWORD *Pool2; // rax
  __int64 v67; // r8
  __int64 v68; // rdx
  int v69; // r8d
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // r8
  __int64 v73; // rdx
  PVOID v74; // rdi
  void *v75; // rcx
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-79h]
  char v77; // [rsp+58h] [rbp-71h]
  char v78; // [rsp+59h] [rbp-70h]
  bool v79; // [rsp+5Ch] [rbp-6Dh]
  __int64 v80; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v81; // [rsp+68h] [rbp-61h]
  __int64 v82; // [rsp+70h] [rbp-59h]
  __int64 v83; // [rsp+78h] [rbp-51h]
  __int64 v84; // [rsp+80h] [rbp-49h] BYREF
  __int64 v85; // [rsp+88h] [rbp-41h]
  PVOID P; // [rsp+90h] [rbp-39h]
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-31h]
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp-29h]
  PVOID v89; // [rsp+A8h] [rbp-21h]
  __int128 InputBuffer; // [rsp+B0h] [rbp-19h] BYREF
  _OWORD FileInformation[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v92; // [rsp+E0h] [rbp+17h]

  v2 = *(struct _FLT_CALLBACK_DATA **)(a1 + 8);
  v89 = (PVOID)a1;
  LODWORD(InformationFile) = a2;
  v78 = 0;
  Iopb = v2->Iopb;
  v85 = *(_QWORD *)(a1 + 16);
  MdlChain = Iopb->Parameters.MdlRead.MdlChain;
  v7 = *(_QWORD *)(v85 + 16);
  TargetFileObject = Iopb->TargetFileObject;
  Instance = Iopb->TargetInstance;
  LODWORD(v84) = *(_DWORD *)(a1 + 24);
  LODWORD(v81) = *(_DWORD *)(a1 + 28);
  Context = *(PFLT_CONTEXT *)(v7 + 16);
  FileObject = TargetFileObject;
  v9 = *((_QWORD *)Context + 2);
  v10 = *((_QWORD *)Context + 4);
  v83 = (__int64)MdlChain[2];
  v82 = (__int64)MdlChain[3];
  v92 = 0;
  InputBuffer = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v2->IoStatus.Information = 0;
  if ( a2 < 0 )
  {
    HsmDbgBreakOnStatus((unsigned int)a2);
    goto LABEL_140;
  }
  InformationFile = (unsigned int)HsmpPrepareForMgmtOperation(v9, TargetFileObject, 1, 1);
  HsmDbgBreakOnStatus(InformationFile);
  if ( (int)InformationFile < 0 )
  {
    v12 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qqiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          49,
          WPP_GLOBAL_Control,
          v2,
          v9,
          v10,
          v7,
          MdlChain[2],
          MdlChain[3],
          InformationFile);
    }
    goto LABEL_140;
  }
  v79 = 0;
  P = 0;
  HsmpWaitForUserRequestRundownRelease(v7);
  LOBYTE(v14) = 1;
  HsmpAcquireReparseUpdateLock(v7, v14);
  if ( (unsigned __int8)HsmpIsPlaceholder(v7) )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v85 + 16) + 76LL) > ((*(_DWORD *)(v85 + 40) >> 5) & 1) )
    {
      LODWORD(InformationFile) = -1073688812;
      HsmDbgBreakOnStatus(3221278484LL);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 50;
      goto LABEL_135;
    }
    if ( !*(_QWORD *)(v7 + 48) || !*(_DWORD *)(v7 + 56) || (*(_DWORD *)(v7 + 28) & 0x8000) != 0 )
    {
      LODWORD(InformationFile) = -1073688800;
      HsmDbgBreakOnStatus(3221278496LL);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 51;
LABEL_135:
      WPP_SF_qqiqiid(v16->AttachedDevice, v17, v15, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
      goto LABEL_136;
    }
    RequestorProcess = FltGetRequestorProcess(v2);
    if ( !(unsigned __int8)HsmOsIsSyncProviderProcess(RequestorProcess) && (v81 & 0x2000000) == 0 )
    {
      HsmpAcquireBitmapLock(v7, 0);
      if ( (*(_DWORD *)(v7 + 28) & 0x40) == 0 )
      {
        v80 = 0;
        StreamSize = HsmpGetStreamSize(v7);
        InformationFile = (unsigned int)HsmiQueryFileRangesTotalNoLock(v21, 16964, StreamSize, &v80);
        HsmDbgBreakOnStatus(InformationFile);
        if ( (int)InformationFile < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_130;
          }
          v24 = 65;
LABEL_25:
          WPP_SF_qqiqiid(v23->AttachedDevice, v24, v22, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
LABEL_130:
          HsmpReleaseBitmapLock(v7);
          goto LABEL_136;
        }
        if ( !v80 )
          goto LABEL_130;
      }
      InformationFile = (unsigned int)HsmpToggleFileAttributesNotify(v9, (_DWORD)TargetFileObject, 0, 0x100000, 0x80000);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile >= 0 )
      {
        InformationFile = (unsigned int)HsmpQueueDehydrationRequest(v7, v2);
        HsmDbgBreakOnStatus(InformationFile);
        if ( (int)InformationFile >= 0 )
        {
          v78 = 1;
          v25 = HsmpComputeDehydrationReason(*((unsigned int *)MdlChain + 2));
          HsmpSetLastDehydrationReasonNoLock(v7, v25);
          HsmpGetLastDehydrationReason(v7, v26, v27);
          v29 = HsmpGetStreamSize(v28);
          TlmWriteDehydrationQueued(v31, v10, v29, v30, v2);
          goto LABEL_130;
        }
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_130;
        }
        v24 = 67;
      }
      else
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_130;
        }
        v24 = 66;
      }
      goto LABEL_25;
    }
    LOBYTE(v19) = 1;
    v79 = (v81 & 0x2000000) == 0;
    HsmpAcquireBitmapLock(v7, v19);
    if ( (*(_DWORD *)(v7 + 28) & 0x2000) == 0 )
    {
      LODWORD(InformationFile) = -1073688824;
      HsmDbgBreakOnStatus(3221278472LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          52,
          v72,
          v2,
          v9,
          v10,
          v7,
          MdlChain[2],
          MdlChain[3],
          -1073688824);
      }
      goto LABEL_130;
    }
    v77 = 0;
    if ( !TargetFileObject->WriteAccess )
    {
      TargetFileObject->WriteAccess = 1;
      v77 = 1;
    }
    if ( (*(_DWORD *)(v7 + 28) & 0x40) == 0 )
    {
      v80 = 0;
      v32 = HsmpGetStreamSize(v7);
      InformationFile = (unsigned int)HsmiQueryFileRangesTotalNoLock(v33, 16964, v32, &v80);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v36 = 53;
        goto LABEL_121;
      }
      if ( !v80 )
        goto LABEL_123;
    }
    if ( MdlChain[3] == (PMDL)-1LL )
    {
      v37 = HsmpGetStreamSize(v7);
      v38 = v83;
    }
    else
    {
      v38 = v83;
      v37 = v83 + v82;
    }
    v80 = v37;
    if ( v38 < 0 || v38 > v37 )
    {
      LODWORD(InformationFile) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_122;
      }
      v36 = 54;
    }
    else
    {
      InformationFile = (unsigned int)HsmpNotifyDataChange(v7);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          goto LABEL_122;
        }
        v40 = 55;
        goto LABEL_58;
      }
      InformationFile = (unsigned int)FltQueryInformationFile(
                                        *(PFLT_INSTANCE *)(v9 + 32),
                                        FileObject,
                                        FileInformation,
                                        0x28u,
                                        FileBasicInformation,
                                        0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v41 = HsmpGetStreamSize(v7);
          WPP_SF_qLiid(
            *(_QWORD *)(v42 + 24),
            56,
            (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            v7,
            *(_DWORD *)(v7 + 28),
            v41,
            v10,
            InformationFile);
        }
        goto LABEL_122;
      }
      v43 = v92;
      if ( (v92 & 0x800) != 0 )
      {
        InformationFile = (unsigned int)HsmpSetCompressionNoLock(
                                          v9,
                                          (struct _FILE_OBJECT *)((unsigned __int64)FileObject
                                                                & -(__int64)((FileObject->Flags & 2) != 0)),
                                          0,
                                          v10);
        HsmDbgBreakOnStatus(InformationFile);
        if ( (int)InformationFile < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              57,
              WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
              v9,
              v10,
              v7,
              InformationFile);
          }
          goto LABEL_122;
        }
        v43 = v92;
      }
      v44 = v83;
      v45 = *(_DWORD *)(v7 + 28) & 0xFFFEFFFF | (32 * (v43 & 0x800));
      *(_DWORD *)(v7 + 28) = v45;
      v46 = (v45 & 2) == 0 ? 0x1000 : 0;
      v82 = -v46 & (v46 + v44 - 1);
      if ( v37 < HsmpGetStreamSize(v7) )
        v50 = v80 & -(__int64)(v47 == 0) & 0xFFFFFFFFFFFFF000uLL;
      else
        v50 = HsmpGetStreamSize(v48);
      v81 = v50;
      InformationFile = (unsigned int)HsmiMarkFileRangeNoLock(v7, 16964, v49, v50, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(WPP_GLOBAL_Control->AttachedDevice, 58, v82, v2, v9, v10, v7, v82, v81, InformationFile);
        }
        goto LABEL_122;
      }
      InformationFile = (unsigned int)HsmiMarkFileRangeNoLock(v7, 16982, v82, v50, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(WPP_GLOBAL_Control->AttachedDevice, 59, v51, v2, v9, v10, v7, v82, v81, InformationFile);
        }
        goto LABEL_122;
      }
      *(_QWORD *)(*(_QWORD *)(v7 + 160) + 8LL) = MEMORY[0xFFFFF78000000014];
      v52 = HsmpComputeDehydrationReason(*((unsigned int *)MdlChain + 2));
      HsmpSetLastDehydrationReasonNoLock(v7, v52);
      HsmpGetStreamSize(v7);
      LastHydrationTime = HsmpGetLastHydrationTime();
      LastDehydrationReason = HsmpGetLastDehydrationReason(v55, v54, LastHydrationTime);
      TlmWriteDehydrationEvent(v60, LastDehydrationReason, v57, v58, v10, v59);
      InformationFile = (unsigned int)HsmpRpCommitNoLock(v9, v7, (_DWORD)FileObject, 0, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v40 = 60;
        goto LABEL_58;
      }
      LOBYTE(v61) = 1;
      InformationFile = (unsigned int)HsmpToggleFileSparseAttribute(v9, FileObject, v61);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v40 = 61;
LABEL_58:
        WPP_SF_qqiqd(
          v39->AttachedDevice,
          v40,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v2,
          v9,
          v10,
          v7,
          InformationFile);
        goto LABEL_122;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          62,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v2,
          v9,
          v10,
          v7,
          InformationFile);
      }
      *(_QWORD *)&InputBuffer = -(__int64)*(unsigned int *)(v9 + 88) & (*(unsigned int *)(v9 + 88) + v83 - 1);
      v62 = HsmpGetStreamSize(v7);
      if ( v80 < v62 )
        v64 = v80 & -(__int64)*(unsigned int *)(v9 + 88);
      else
        v64 = 0x7FFFFFFFFFFFFFFFLL;
      *((_QWORD *)&InputBuffer + 1) = v64;
      if ( v63 >= v64 )
        goto LABEL_112;
      InformationFile = (unsigned int)FltFsControlFile(Instance, FileObject, 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(
            WPP_GLOBAL_Control->AttachedDevice,
            63,
            v65,
            v2,
            v9,
            v10,
            v7,
            InputBuffer,
            *((_QWORD *)&InputBuffer + 1),
            InformationFile);
        }
        goto LABEL_122;
      }
      InformationFile = (unsigned int)HsmpPrepareForMgmtOperation(v9, FileObject, 0, 1);
      HsmDbgBreakOnStatus(InformationFile);
      if ( (int)InformationFile >= 0 )
      {
LABEL_112:
        v2->IoStatus.Information = 1;
        Pool2 = (_QWORD *)ExAllocatePool2(258, 28, 1666085704);
        P = Pool2;
        v68 = (__int64)Pool2;
        if ( Pool2 )
        {
          *Pool2 = 1666085704;
          *((_DWORD *)Pool2 + 2) = 24;
          *((_DWORD *)Pool2 + 3) = 0x10000;
          Pool2[2] = 0;
          v69 = HsmpGetLastDehydrationReason(v7, Pool2, v67);
          if ( *(_WORD *)(v68 + 14) )
          {
            v70 = *(unsigned int *)(v68 + 8);
            if ( ((v70 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x1C )
            {
              v71 = ((_DWORD)v70 + 3) & 0xFFFFFFFC;
              *(_DWORD *)(v68 + 8) = v71;
              *(_DWORD *)(v68 + 16) = 262154;
              *(_DWORD *)(v68 + 20) = v71;
              *(_DWORD *)(v71 + v68) = v69;
              *(_DWORD *)(v68 + 8) += 4;
            }
          }
        }
        HsmpCldNotifyPostOperation(3u, v2, 0, 1, v68);
        goto LABEL_122;
      }
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_122:
        TargetFileObject = FileObject;
LABEL_123:
        if ( v77 )
          TargetFileObject->WriteAccess = 0;
        goto LABEL_130;
      }
      v36 = 64;
    }
LABEL_121:
    WPP_SF_qqiqiid(v35->AttachedDevice, v36, v34, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
    goto LABEL_122;
  }
LABEL_136:
  HsmpReInitializeUserRequestRundownProtection(v7);
  FltReleasePushLockEx(*(_QWORD *)(v7 + 16) + 24LL, 0);
  if ( P )
    ExFreePoolWithTag(P, 0x634E7348u);
  if ( v79 )
  {
    LOBYTE(v73) = 1;
    HsmpCompletePendedDehydrationRequests(v7, v73, (unsigned int)InformationFile);
  }
LABEL_140:
  HsmiOpCompleteOperation(Timer_high, v9, v12, v13, Context, (__int64)&v84);
  v74 = v89;
  v75 = (void *)*((_QWORD *)v89 + 2);
  if ( v75 )
    FltReleaseContext(v75);
  ExFreePoolWithTag(v74, 0x63447348u);
  if ( !v78 )
  {
    v2->IoStatus.Status = InformationFile;
    FltCompletePendedPreOperation(v2, FLT_PREOP_COMPLETE, 0);
  }
}

```

## disassembly

```asm
0x140047b30  mov     [rsp-8+arg_10], rbx
0x140047b35  push    rbp
0x140047b36  push    rsi
0x140047b37  push    rdi
0x140047b38  push    r12
0x140047b3a  push    r13
0x140047b3c  push    r14
0x140047b3e  push    r15
0x140047b40  lea     rbp, [rsp-27h]
0x140047b45  sub     rsp, 0F0h
0x140047b4c  mov     rax, cs:__security_cookie
0x140047b53  xor     rax, rsp
0x140047b56  mov     [rbp+57h+var_38], rax
0x140047b5a  mov     r13, [rcx+8]
0x140047b5e  mov     r8, rcx
0x140047b61  xorps   xmm0, xmm0
0x140047b64  mov     [rbp+57h+var_78], rcx
0x140047b68  mov     ebx, edx
0x140047b6a  mov     [rbp+57h+var_C7], 0
0x140047b6e  mov     rcx, [r13+10h]
0x140047b72  mov     rdx, [r8+10h]
0x140047b76  mov     [rbp+57h+var_98], rdx
0x140047b7a  mov     rax, [rcx+10h]
0x140047b7e  mov     r15, [rcx+30h]
0x140047b82  mov     rdi, [rdx+10h]
0x140047b86  mov     rsi, [rcx+8]
0x140047b8a  mov     [rbp+57h+Instance], rax
0x140047b8e  mov     eax, [r8+18h]
0x140047b92  mov     dword ptr [rbp+57h+var_A0], eax
0x140047b95  mov     eax, [r8+1Ch]
0x140047b99  mov     dword ptr [rbp+57h+var_B8], eax
0x140047b9c  mov     rax, [rdi+10h]
0x140047ba0  mov     [rbp+57h+Context], rax
0x140047ba4  mov     [rbp+57h+FileObject], rsi
0x140047ba8  mov     r14, [rax+10h]
0x140047bac  mov     r12, [rax+20h]
0x140047bb0  mov     rax, [r15+10h]
0x140047bb4  mov     [rbp+57h+var_A8], rax
0x140047bb8  mov     rax, [r15+18h]
0x140047bbc  mov     [rbp+57h+var_B0], rax
0x140047bc0  xor     eax, eax
0x140047bc2  mov     [rbp+57h+var_40], rax
0x140047bc6  movups  [rbp+57h+InputBuffer], xmm0
0x140047bca  movups  [rbp+57h+FileInformation], xmm0
0x140047bce  movups  [rbp+57h+var_50], xmm0
0x140047bd2  mov     [r13+20h], rax
0x140047bd6  test    ebx, ebx
0x140047bd8  jns     short loc_140047BE6
0x140047bda  mov     ecx, ebx
0x140047bdc  call    HsmDbgBreakOnStatus
0x140047be1  jmp     loc_140048799
0x140047be6  mov     eax, 1
0x140047beb  mov     rdx, rsi
0x140047bee  mov     r9b, al
0x140047bf1  mov     r8d, eax
0x140047bf4  mov     rcx, r14
0x140047bf7  call    HsmpPrepareForMgmtOperation
0x140047bfc  mov     ecx, eax
0x140047bfe  mov     ebx, eax
0x140047c00  call    HsmDbgBreakOnStatus
0x140047c05  test    ebx, ebx
0x140047c07  jns     short loc_140047C73
0x140047c09  mov     r8, cs:WPP_GLOBAL_Control
0x140047c10  lea     rsi, WPP_GLOBAL_Control
0x140047c17  cmp     r8, rsi
0x140047c1a  jz      loc_140048799
0x140047c20  mov     ecx, [r8+2Ch]
0x140047c24  test    cl, 1
0x140047c27  jz      loc_140048799
0x140047c2d  cmp     byte ptr [r8+29h], 2
0x140047c32  jb      loc_140048799
0x140047c38  mov     rax, [r15+18h]
0x140047c3c  mov     edx, 31h ; '1'
0x140047c41  mov     rcx, [r8+18h]
0x140047c45  mov     r9, r13
0x140047c48  mov     [rsp+120h+var_D8], ebx
0x140047c4c  mov     [rsp+120h+var_E0], rax
0x140047c51  mov     rax, [r15+10h]
0x140047c55  mov     [rsp+120h+var_E8], rax
0x140047c5a  mov     qword ptr [rsp+120h+OutputBufferLength], rdi
0x140047c5f  mov     [rsp+120h+LengthReturned], r12
0x140047c64  mov     qword ptr [rsp+120h+FileInformationClass], r14
0x140047c69  call    WPP_SF_qqiqiid
0x140047c6e  jmp     loc_140048799
0x140047c73  mov     rcx, rdi
0x140047c76  mov     byte ptr [rbp+57h+var_C4], 0
0x140047c7a  mov     [rbp+57h+P], 0
0x140047c82  call    HsmpWaitForUserRequestRundownRelease
0x140047c87  mov     dl, 1
0x140047c89  mov     rcx, rdi
0x140047c8c  call    HsmpAcquireReparseUpdateLock
0x140047c91  mov     rcx, rdi
0x140047c94  call    HsmpIsPlaceholder
0x140047c99  test    al, al
0x140047c9b  jz      loc_14004874B
0x140047ca1  mov     rax, [rbp+57h+var_98]
0x140047ca5  mov     edx, [rax+28h]
0x140047ca8  mov     rax, [rax+10h]
0x140047cac  shr     edx, 5
0x140047caf  and     edx, 1
0x140047cb2  mov     ecx, [rax+4Ch]
0x140047cb5  cmp     ecx, edx
0x140047cb7  jle     short loc_140047CFB
0x140047cb9  mov     ebx, 0C000CF14h
0x140047cbe  mov     ecx, ebx
0x140047cc0  call    HsmDbgBreakOnStatus
0x140047cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ccc  lea     rsi, WPP_GLOBAL_Control
0x140047cd3  cmp     rcx, rsi
0x140047cd6  jz      loc_14004874B
0x140047cdc  mov     eax, [rcx+2Ch]
0x140047cdf  test    al, 1
0x140047ce1  jz      loc_14004874B
0x140047ce7  cmp     byte ptr [rcx+29h], 2
0x140047ceb  jb      loc_14004874B
0x140047cf1  mov     edx, 32h ; '2'
0x140047cf6  jmp     loc_14004871A
0x140047cfb  xor     ebx, ebx
0x140047cfd  cmp     [rdi+30h], rbx
0x140047d01  jz      loc_1400486E9
0x140047d07  cmp     [rdi+38h], ebx
0x140047d0a  jz      loc_1400486E9
0x140047d10  test    dword ptr [rdi+1Ch], 8000h
0x140047d17  jnz     loc_1400486E9
0x140047d1d  mov     rcx, r13; CallbackData
0x140047d20  call    cs:__imp_FltGetRequestorProcess
0x140047d27  nop     dword ptr [rax+rax+00h]
0x140047d2c  mov     rcx, rax
0x140047d2f  call    HsmOsIsSyncProviderProcess
0x140047d34  test    al, al
0x140047d36  mov     eax, dword ptr [rbp+57h+var_B8]
0x140047d39  jnz     loc_140047EFC
0x140047d3f  bt      eax, 19h
0x140047d43  jb      loc_140047EFC
0x140047d49  xor     edx, edx
0x140047d4b  mov     rcx, rdi
0x140047d4e  call    HsmpAcquireBitmapLock
0x140047d53  mov     eax, [rdi+1Ch]
0x140047d56  test    al, 40h
0x140047d58  jnz     loc_140047DFA
0x140047d5e  mov     rcx, rdi
0x140047d61  mov     [rbp+57h+var_C0], rbx
0x140047d65  call    HsmpGetStreamSize
0x140047d6a  mov     r8, rax
0x140047d6d  lea     r9, [rbp+57h+var_C0]
0x140047d71  mov     edx, 4244h
0x140047d76  call    HsmiQueryFileRangesTotalNoLock
0x140047d7b  mov     ecx, eax
0x140047d7d  mov     ebx, eax
0x140047d7f  call    HsmDbgBreakOnStatus
0x140047d84  test    ebx, ebx
0x140047d86  jns     short loc_140047DEF
0x140047d88  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d8f  lea     rsi, WPP_GLOBAL_Control
0x140047d96  cmp     rcx, rsi
0x140047d99  jz      loc_1400486DF
0x140047d9f  mov     eax, [rcx+2Ch]
0x140047da2  test    al, 1
0x140047da4  jz      loc_1400486DF
0x140047daa  cmp     byte ptr [rcx+29h], 2
0x140047dae  jb      loc_1400486DF
0x140047db4  mov     edx, 41h ; 'A'
0x140047db9  mov     rax, [r15+18h]
0x140047dbd  mov     r9, r13
0x140047dc0  mov     rcx, [rcx+18h]
0x140047dc4  mov     [rsp+120h+var_D8], ebx
0x140047dc8  mov     [rsp+120h+var_E0], rax
0x140047dcd  mov     rax, [r15+10h]
0x140047dd1  mov     [rsp+120h+var_E8], rax
0x140047dd6  mov     qword ptr [rsp+120h+OutputBufferLength], rdi
0x140047ddb  mov     [rsp+120h+LengthReturned], r12
0x140047de0  mov     qword ptr [rsp+120h+FileInformationClass], r14
0x140047de5  call    WPP_SF_qqiqiid
0x140047dea  jmp     loc_1400486DF
0x140047def  cmp     [rbp+57h+var_C0], 0
0x140047df4  jz      loc_1400486DF
0x140047dfa  mov     r9d, 100000h
0x140047e00  mov     [rsp+120h+FileInformationClass], 80000h
0x140047e08  xor     r8d, r8d
0x140047e0b  mov     rdx, rsi
0x140047e0e  mov     rcx, r14
0x140047e11  call    HsmpToggleFileAttributesNotify
0x140047e16  mov     ecx, eax
0x140047e18  mov     ebx, eax
0x140047e1a  call    HsmDbgBreakOnStatus
0x140047e1f  test    ebx, ebx
0x140047e21  jns     short loc_140047E59
0x140047e23  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e2a  lea     rsi, WPP_GLOBAL_Control
0x140047e31  cmp     rcx, rsi
0x140047e34  jz      loc_1400486DF
0x140047e3a  mov     eax, [rcx+2Ch]
0x140047e3d  test    al, 1
0x140047e3f  jz      loc_1400486DF
0x140047e45  cmp     byte ptr [rcx+29h], 2
0x140047e49  jb      loc_1400486DF
0x140047e4f  mov     edx, 42h ; 'B'
0x140047e54  jmp     loc_140047DB9
0x140047e59  mov     rdx, r13
0x140047e5c  mov     rcx, rdi
0x140047e5f  call    HsmpQueueDehydrationRequest
0x140047e64  mov     ecx, eax
0x140047e66  mov     ebx, eax
0x140047e68  call    HsmDbgBreakOnStatus
0x140047e6d  test    ebx, ebx
0x140047e6f  jns     short loc_140047EA7
0x140047e71  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e78  lea     rsi, WPP_GLOBAL_Control
0x140047e7f  cmp     rcx, rsi
0x140047e82  jz      loc_1400486DF
0x140047e88  mov     eax, [rcx+2Ch]
0x140047e8b  test    al, 1
0x140047e8d  jz      loc_1400486DF
0x140047e93  cmp     byte ptr [rcx+29h], 2
0x140047e97  jb      loc_1400486DF
0x140047e9d  mov     edx, 43h ; 'C'
0x140047ea2  jmp     loc_140047DB9
0x140047ea7  mov     ecx, [r15+8]
0x140047eab  mov     [rbp+57h+var_C7], 1
0x140047eaf  call    HsmpComputeDehydrationReason
0x140047eb4  mov     edx, eax
0x140047eb6  mov     rcx, rdi
0x140047eb9  call    HsmpSetLastDehydrationReasonNoLock
0x140047ebe  mov     rcx, [rbp+57h+var_98]
0x140047ec2  lea     r11, qword_1400294D0
0x140047ec9  mov     rcx, [rcx+60h]
0x140047ecd  test    rcx, rcx
0x140047ed0  cmovnz  r11, rcx
0x140047ed4  mov     rcx, rdi
0x140047ed7  call    HsmpGetLastDehydrationReason
0x140047edc  mov     r9d, eax
0x140047edf  call    HsmpGetStreamSize
0x140047ee4  mov     r8, rax; int
0x140047ee7  mov     qword ptr [rsp+120h+FileInformationClass], r13; CallbackData
0x140047eec  mov     rdx, r12; int
0x140047eef  mov     rcx, r11; int
0x140047ef2  call    TlmWriteDehydrationQueued
0x140047ef7  jmp     loc_1400486DF
0x140047efc  shr     eax, 19h
0x140047eff  mov     ecx, 1
0x140047f04  not     al
0x140047f06  mov     dl, cl
0x140047f08  and     al, cl
0x140047f0a  mov     rcx, rdi
0x140047f0d  mov     [rbp+57h+var_C4], eax
0x140047f10  call    HsmpAcquireBitmapLock
0x140047f15  test    dword ptr [rdi+1Ch], 2000h
0x140047f1c  jz      loc_140048677
0x140047f22  mov     [rbp+57h+var_C8], bl
0x140047f25  cmp     [rsi+4Bh], bl
0x140047f28  jnz     short loc_140047F35
0x140047f2a  mov     eax, 1
0x140047f2f  mov     [rsi+4Bh], al
0x140047f32  mov     [rbp+57h+var_C8], al
0x140047f35  mov     eax, [rdi+1Ch]
0x140047f38  test    al, 40h
0x140047f3a  jnz     short loc_140047FA7
0x140047f3c  mov     rcx, rdi
0x140047f3f  mov     [rbp+57h+var_C0], rbx
0x140047f43  call    HsmpGetStreamSize
0x140047f48  mov     r8, rax
0x140047f4b  lea     r9, [rbp+57h+var_C0]
0x140047f4f  mov     edx, 4244h
0x140047f54  call    HsmiQueryFileRangesTotalNoLock
0x140047f59  mov     ecx, eax
0x140047f5b  mov     ebx, eax
0x140047f5d  call    HsmDbgBreakOnStatus
0x140047f62  test    ebx, ebx
0x140047f64  jns     short loc_140047F9C
0x140047f66  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f6d  lea     rsi, WPP_GLOBAL_Control
0x140047f74  cmp     rcx, rsi
0x140047f77  jz      loc_14004865F
0x140047f7d  mov     eax, [rcx+2Ch]
0x140047f80  test    al, 1
0x140047f82  jz      loc_14004865F
0x140047f88  cmp     byte ptr [rcx+29h], 2
0x140047f8c  jb      loc_14004865F
0x140047f92  mov     edx, 35h ; '5'
0x140047f97  jmp     loc_14004862E
0x140047f9c  cmp     [rbp+57h+var_C0], 0
0x140047fa1  jz      loc_140048663
0x140047fa7  cmp     qword ptr [r15+18h], 0FFFFFFFFFFFFFFFFh
0x140047fac  jnz     short loc_140047FBF
0x140047fae  mov     rcx, rdi
0x140047fb1  call    HsmpGetStreamSize
0x140047fb6  mov     rsi, rax
0x140047fb9  mov     rax, [rbp+57h+var_A8]
0x140047fbd  jmp     short loc_140047FCA
0x140047fbf  mov     rax, [rbp+57h+var_A8]
0x140047fc3  mov     rsi, [rbp+57h+var_B0]
0x140047fc7  add     rsi, rax
0x140047fca  mov     [rbp+57h+var_C0], rsi
0x140047fce  test    rax, rax
0x140047fd1  js      loc_1400485FD
0x140047fd7  cmp     rax, rsi
0x140047fda  jg      loc_1400485FD
0x140047fe0  mov     rcx, rdi
0x140047fe3  call    HsmpNotifyDataChange
0x140047fe8  mov     ecx, eax
  ... truncated ...
```
