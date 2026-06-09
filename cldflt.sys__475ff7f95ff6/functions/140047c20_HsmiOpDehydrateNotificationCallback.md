# HsmiOpDehydrateNotificationCallback

- ea: `0x140047c20`
- end: `0x140048918`
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
- `0x1400152c8`
- `0x140015ec0`
- `0x14001615c`
- `0x14001e1c0`
- `0x14003547c`
- `0x1400356f0`
- `0x1400365e8`
- `0x140043324`
- `0x140047c20`
- `0x1400548d0`
- `0x140056640`
- `0x140058ddc`
- `0x140058df8`
- `0x140059738`
- `0x14005c9e0`
- `0x14005ce40`
- `0x1400652e4`
- `0x14006793c`
- `0x140067958`
- `0x140067c70`
- `0x140067e24`
- `0x14006f1a0`
- `0x14006f28c`
- `0x14007458c`
- `0x140075df0`
- `0x140075e6c`
- `0x1400766ac`
- `0x14007ee6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004886a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400488c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004886a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400488c4`
- `ntoskrnl!ExAllocatePool2` at `0x140048659`
- `ntoskrnl!ExAllocatePool2` at `0x140048659`
- `FLTMGR!FltQueryInformationFile` at `0x140048164`
- `FLTMGR!FltQueryInformationFile` at `0x140048164`
- `FLTMGR!FltFsControlFile` at `0x14004859b`
- `FLTMGR!FltFsControlFile` at `0x14004859b`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400488e4`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400488e4`
- `FLTMGR!FltGetRequestorProcess` at `0x140047e10`
- `FLTMGR!FltGetRequestorProcess` at `0x140047e10`
- `FLTMGR!FltReleasePushLockEx` at `0x14004884d`
- `FLTMGR!FltReleasePushLockEx` at `0x14004884d`
- `FLTMGR!FltReleaseContext` at `0x1400488b0`
- `FLTMGR!FltReleaseContext` at `0x1400488b0`

## pseudocode

```c
void __fastcall HsmiOpDehydrateNotificationCallback(__int64 a1, int a2)
{
  struct _FLT_CALLBACK_DATA *v2; // r13
  NTSTATUS InformationFile; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  PMDL *MdlChain; // r15
  __int64 v7; // rdi
  PFILE_OBJECT TargetFileObject; // rsi
  __int64 v9; // r14
  __int64 v10; // r12
  __int64 Timer_high; // rcx
  PDEVICE_OBJECT v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PEPROCESS RequestorProcess; // rax
  __int64 v20; // rdx
  __int64 StreamSize; // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  int v30; // eax
  int v31; // r9d
  int v32; // r11d
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r8
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rsi
  __int64 v39; // rax
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  char v42; // al
  __int64 v43; // r10
  __int16 v44; // dx
  __int64 v45; // r8
  unsigned int v46; // edx
  __int64 v47; // rcx
  int v48; // edx
  __int64 v49; // rcx
  int v50; // r8d
  unsigned __int64 v51; // rsi
  __int64 v52; // r8
  unsigned int v53; // eax
  __int64 LastHydrationTime; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  int LastDehydrationReason; // eax
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // r10
  int v61; // r11d
  __int64 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // r8
  _QWORD *Pool2; // rax
  __int64 v68; // r8
  _QWORD *v69; // rdx
  int v70; // r8d
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // r8
  __int64 v74; // rdx
  PVOID v75; // rdi
  void *v76; // rcx
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-79h]
  char v78; // [rsp+58h] [rbp-71h]
  char v79; // [rsp+59h] [rbp-70h]
  bool v80; // [rsp+5Ch] [rbp-6Dh]
  __int64 v81; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v82; // [rsp+68h] [rbp-61h]
  __int64 v83; // [rsp+70h] [rbp-59h]
  __int64 v84; // [rsp+78h] [rbp-51h]
  __int64 v85; // [rsp+80h] [rbp-49h] BYREF
  __int64 v86; // [rsp+88h] [rbp-41h]
  PVOID P; // [rsp+90h] [rbp-39h]
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-31h]
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp-29h]
  PVOID v90; // [rsp+A8h] [rbp-21h]
  __int128 InputBuffer; // [rsp+B0h] [rbp-19h] BYREF
  _OWORD FileInformation[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v93; // [rsp+E0h] [rbp+17h]

  v2 = *(struct _FLT_CALLBACK_DATA **)(a1 + 8);
  v90 = (PVOID)a1;
  InformationFile = a2;
  v79 = 0;
  Iopb = v2->Iopb;
  v86 = *(_QWORD *)(a1 + 16);
  MdlChain = Iopb->Parameters.MdlRead.MdlChain;
  v7 = *(_QWORD *)(v86 + 16);
  TargetFileObject = Iopb->TargetFileObject;
  Instance = Iopb->TargetInstance;
  LODWORD(v85) = *(_DWORD *)(a1 + 24);
  LODWORD(v82) = *(_DWORD *)(a1 + 28);
  Context = *(PFLT_CONTEXT *)(v7 + 16);
  FileObject = TargetFileObject;
  v9 = *((_QWORD *)Context + 2);
  v10 = *((_QWORD *)Context + 4);
  v84 = (__int64)MdlChain[2];
  v83 = (__int64)MdlChain[3];
  v93 = 0;
  InputBuffer = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v2->IoStatus.Information = 0;
  if ( a2 < 0 )
  {
    HsmDbgBreakOnStatus(a2);
    goto LABEL_140;
  }
  InformationFile = HsmpPrepareForMgmtOperation(v9, TargetFileObject, 1);
  HsmDbgBreakOnStatus(InformationFile);
  if ( InformationFile < 0 )
  {
    v12 = WPP_GLOBAL_Control;
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
  v80 = 0;
  P = 0;
  HsmpWaitForUserRequestRundownRelease(v7);
  LOBYTE(v14) = 1;
  HsmpAcquireReparseUpdateLock(v7, v14);
  if ( (unsigned __int8)HsmpIsPlaceholder(v7, v15) )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v86 + 16) + 76LL) > ((*(_DWORD *)(v86 + 40) >> 5) & 1) )
    {
      InformationFile = -1073688812;
      HsmDbgBreakOnStatus(-1073688812);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_136;
      }
      v18 = 50;
      goto LABEL_135;
    }
    if ( !*(_QWORD *)(v7 + 48) || !*(_DWORD *)(v7 + 56) || (*(_DWORD *)(v7 + 28) & 0x8000) != 0 )
    {
      InformationFile = -1073688800;
      HsmDbgBreakOnStatus(-1073688800);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_136;
      }
      v18 = 51;
LABEL_135:
      WPP_SF_qqiqiid(v17->AttachedDevice, v18, v16, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
      goto LABEL_136;
    }
    RequestorProcess = FltGetRequestorProcess(v2);
    if ( !(unsigned __int8)HsmOsIsSyncProviderProcess(RequestorProcess) && (v82 & 0x2000000) == 0 )
    {
      HsmpAcquireBitmapLock(v7, 0);
      if ( (*(_DWORD *)(v7 + 28) & 0x40) == 0 )
      {
        v81 = 0;
        StreamSize = HsmpGetStreamSize(v7);
        InformationFile = HsmiQueryFileRangesTotalNoLock(v22, 16964, StreamSize, &v81);
        HsmDbgBreakOnStatus(InformationFile);
        if ( InformationFile < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_130;
          }
          v25 = 65;
LABEL_25:
          WPP_SF_qqiqiid(v24->AttachedDevice, v25, v23, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
LABEL_130:
          HsmpReleaseBitmapLock(v7);
          goto LABEL_136;
        }
        if ( !v81 )
          goto LABEL_130;
      }
      InformationFile = HsmpToggleFileAttributesNotify(v9, (_DWORD)TargetFileObject, 0, 0x100000, 0x80000);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile >= 0 )
      {
        InformationFile = HsmpQueueDehydrationRequest(v7, v2);
        HsmDbgBreakOnStatus(InformationFile);
        if ( InformationFile >= 0 )
        {
          v79 = 1;
          v26 = HsmpComputeDehydrationReason(*((unsigned int *)MdlChain + 2));
          HsmpSetLastDehydrationReasonNoLock(v7, v26);
          HsmpGetLastDehydrationReason(v7, v27, v28);
          v30 = HsmpGetStreamSize(v29);
          TlmWriteDehydrationQueued(v32, v10, v30, v31, v2);
          goto LABEL_130;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_130;
        }
        v25 = 67;
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_130;
        }
        v25 = 66;
      }
      goto LABEL_25;
    }
    LOBYTE(v20) = 1;
    v80 = (v82 & 0x2000000) == 0;
    HsmpAcquireBitmapLock(v7, v20);
    if ( (*(_DWORD *)(v7 + 28) & 0x2000) == 0 )
    {
      InformationFile = -1073688824;
      HsmDbgBreakOnStatus(-1073688824);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          52,
          v73,
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
    v78 = 0;
    if ( !TargetFileObject->WriteAccess )
    {
      TargetFileObject->WriteAccess = 1;
      v78 = 1;
    }
    if ( (*(_DWORD *)(v7 + 28) & 0x40) == 0 )
    {
      v81 = 0;
      v33 = HsmpGetStreamSize(v7);
      InformationFile = HsmiQueryFileRangesTotalNoLock(v34, 16964, v33, &v81);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v37 = 53;
        goto LABEL_121;
      }
      if ( !v81 )
        goto LABEL_123;
    }
    if ( MdlChain[3] == (PMDL)-1LL )
    {
      v38 = HsmpGetStreamSize(v7);
      v39 = v84;
    }
    else
    {
      v39 = v84;
      v38 = v84 + v83;
    }
    v81 = v38;
    if ( v39 < 0 || v39 > v38 )
    {
      InformationFile = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_122;
      }
      v37 = 54;
    }
    else
    {
      InformationFile = HsmpNotifyDataChange(v7);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          goto LABEL_122;
        }
        v41 = 55;
        goto LABEL_58;
      }
      InformationFile = FltQueryInformationFile(
                          *(PFLT_INSTANCE *)(v9 + 32),
                          FileObject,
                          FileInformation,
                          0x28u,
                          FileBasicInformation,
                          0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v42 = HsmpGetStreamSize(v7);
          WPP_SF_qLiid(
            *(_QWORD *)(v43 + 24),
            56,
            (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            v7,
            *(_DWORD *)(v7 + 28),
            v42,
            v10,
            InformationFile);
        }
        goto LABEL_122;
      }
      v44 = v93;
      if ( (v93 & 0x800) != 0 )
      {
        InformationFile = HsmpSetCompressionNoLock(
                            v9,
                            (unsigned __int64)FileObject & -(__int64)((FileObject->Flags & 2) != 0),
                            0,
                            v10);
        HsmDbgBreakOnStatus(InformationFile);
        if ( InformationFile < 0 )
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
        v44 = v93;
      }
      v45 = v84;
      v46 = *(_DWORD *)(v7 + 28) & 0xFFFEFFFF | (32 * (v44 & 0x800));
      *(_DWORD *)(v7 + 28) = v46;
      v47 = (v46 & 2) == 0 ? 0x1000 : 0;
      v83 = -v47 & (v47 + v45 - 1);
      if ( v38 < HsmpGetStreamSize(v7) )
        v51 = v81 & -(__int64)(v48 == 0) & 0xFFFFFFFFFFFFF000uLL;
      else
        v51 = HsmpGetStreamSize(v49);
      v82 = v51;
      InformationFile = HsmiMarkFileRangeNoLock(v7, 16964, v50, v51, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(WPP_GLOBAL_Control->AttachedDevice, 58, v83, v2, v9, v10, v7, v83, v82, InformationFile);
        }
        goto LABEL_122;
      }
      InformationFile = HsmiMarkFileRangeNoLock(v7, 16982, v83, v51, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(WPP_GLOBAL_Control->AttachedDevice, 59, v52, v2, v9, v10, v7, v83, v82, InformationFile);
        }
        goto LABEL_122;
      }
      *(_QWORD *)(*(_QWORD *)(v7 + 160) + 8LL) = MEMORY[0xFFFFF78000000014];
      v53 = HsmpComputeDehydrationReason(*((unsigned int *)MdlChain + 2));
      HsmpSetLastDehydrationReasonNoLock(v7, v53);
      HsmpGetStreamSize(v7);
      LastHydrationTime = HsmpGetLastHydrationTime();
      LastDehydrationReason = HsmpGetLastDehydrationReason(v56, v55, LastHydrationTime);
      TlmWriteDehydrationEvent(v61, LastDehydrationReason, v58, v59, v10, v60);
      InformationFile = HsmpRpCommitNoLock(v9, v7, (_DWORD)FileObject, 0, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v41 = 60;
        goto LABEL_58;
      }
      LOBYTE(v62) = 1;
      InformationFile = HsmpToggleFileSparseAttribute(v9, FileObject, v62);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_122;
        }
        v41 = 61;
LABEL_58:
        WPP_SF_qqiqd(
          v40->AttachedDevice,
          v41,
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
      *(_QWORD *)&InputBuffer = -(__int64)*(unsigned int *)(v9 + 88) & (*(unsigned int *)(v9 + 88) + v84 - 1);
      v63 = HsmpGetStreamSize(v7);
      if ( v81 < v63 )
        v65 = v81 & -(__int64)*(unsigned int *)(v9 + 88);
      else
        v65 = 0x7FFFFFFFFFFFFFFFLL;
      *((_QWORD *)&InputBuffer + 1) = v65;
      if ( v64 >= v65 )
        goto LABEL_112;
      InformationFile = FltFsControlFile(Instance, FileObject, 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqiqiid(
            WPP_GLOBAL_Control->AttachedDevice,
            63,
            v66,
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
      InformationFile = HsmpPrepareForMgmtOperation(v9, FileObject, 0);
      HsmDbgBreakOnStatus(InformationFile);
      if ( InformationFile >= 0 )
      {
LABEL_112:
        v2->IoStatus.Information = 1;
        Pool2 = (_QWORD *)ExAllocatePool2(258, 28, 1666085704);
        P = Pool2;
        v69 = Pool2;
        if ( Pool2 )
        {
          *Pool2 = 1666085704;
          *((_DWORD *)Pool2 + 2) = 24;
          *((_DWORD *)Pool2 + 3) = 0x10000;
          Pool2[2] = 0;
          v70 = HsmpGetLastDehydrationReason(v7, Pool2, v68);
          if ( *((_WORD *)v69 + 7) )
          {
            v71 = *((unsigned int *)v69 + 2);
            if ( ((v71 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x1C )
            {
              v72 = ((_DWORD)v71 + 3) & 0xFFFFFFFC;
              *((_DWORD *)v69 + 2) = v72;
              *((_DWORD *)v69 + 4) = 262154;
              *((_DWORD *)v69 + 5) = v72;
              *(_DWORD *)((char *)v69 + v72) = v70;
              *((_DWORD *)v69 + 2) += 4;
            }
          }
        }
        HsmpCldNotifyPostOperation(3, v2, 0, 1, v69);
        goto LABEL_122;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_122:
        TargetFileObject = FileObject;
LABEL_123:
        if ( v78 )
          TargetFileObject->WriteAccess = 0;
        goto LABEL_130;
      }
      v37 = 64;
    }
LABEL_121:
    WPP_SF_qqiqiid(v36->AttachedDevice, v37, v35, v2, v9, v10, v7, MdlChain[2], MdlChain[3], InformationFile);
    goto LABEL_122;
  }
LABEL_136:
  HsmpReInitializeUserRequestRundownProtection(v7);
  FltReleasePushLockEx(*(_QWORD *)(v7 + 16) + 24LL, 0);
  if ( P )
    ExFreePoolWithTag(P, 0x634E7348u);
  if ( v80 )
  {
    LOBYTE(v74) = 1;
    HsmpCompletePendedDehydrationRequests(v7, v74, (unsigned int)InformationFile);
  }
LABEL_140:
  HsmiOpCompleteOperation(Timer_high, (struct _KEVENT *)v9, (__int64)v12, v13, (struct _KEVENT *)Context, &v85);
  v75 = v90;
  v76 = (void *)*((_QWORD *)v90 + 2);
  if ( v76 )
    FltReleaseContext(v76);
  ExFreePoolWithTag(v75, 0x63447348u);
  if ( !v79 )
  {
    v2->IoStatus.Status = InformationFile;
    FltCompletePendedPreOperation(v2, FLT_PREOP_COMPLETE, 0);
  }
}

```

## disassembly

```asm
0x140047c20  mov     [rsp-8+arg_10], rbx
0x140047c25  push    rbp
0x140047c26  push    rsi
0x140047c27  push    rdi
0x140047c28  push    r12
0x140047c2a  push    r13
0x140047c2c  push    r14
0x140047c2e  push    r15
0x140047c30  lea     rbp, [rsp-27h]
0x140047c35  sub     rsp, 0F0h
0x140047c3c  mov     rax, cs:__security_cookie
0x140047c43  xor     rax, rsp
0x140047c46  mov     [rbp+57h+var_38], rax
0x140047c4a  mov     r13, [rcx+8]
0x140047c4e  mov     r8, rcx
0x140047c51  xorps   xmm0, xmm0
0x140047c54  mov     [rbp+57h+var_78], rcx
0x140047c58  mov     ebx, edx
0x140047c5a  mov     [rbp+57h+var_C7], 0
0x140047c5e  mov     rcx, [r13+10h]
0x140047c62  mov     rdx, [r8+10h]
0x140047c66  mov     [rbp+57h+var_98], rdx
0x140047c6a  mov     rax, [rcx+10h]
0x140047c6e  mov     r15, [rcx+30h]
0x140047c72  mov     rdi, [rdx+10h]
0x140047c76  mov     rsi, [rcx+8]
0x140047c7a  mov     [rbp+57h+Instance], rax
0x140047c7e  mov     eax, [r8+18h]
0x140047c82  mov     dword ptr [rbp+57h+var_A0], eax
0x140047c85  mov     eax, [r8+1Ch]
0x140047c89  mov     dword ptr [rbp+57h+var_B8], eax
0x140047c8c  mov     rax, [rdi+10h]
0x140047c90  mov     [rbp+57h+Context], rax
0x140047c94  mov     [rbp+57h+FileObject], rsi
0x140047c98  mov     r14, [rax+10h]
0x140047c9c  mov     r12, [rax+20h]
0x140047ca0  mov     rax, [r15+10h]
0x140047ca4  mov     [rbp+57h+var_A8], rax
0x140047ca8  mov     rax, [r15+18h]
0x140047cac  mov     [rbp+57h+var_B0], rax
0x140047cb0  xor     eax, eax
0x140047cb2  mov     [rbp+57h+var_40], rax
0x140047cb6  movups  [rbp+57h+InputBuffer], xmm0
0x140047cba  movups  [rbp+57h+FileInformation], xmm0
0x140047cbe  movups  [rbp+57h+var_50], xmm0
0x140047cc2  mov     [r13+20h], rax
0x140047cc6  test    ebx, ebx
0x140047cc8  jns     short loc_140047CD6
0x140047cca  mov     ecx, ebx
0x140047ccc  call    HsmDbgBreakOnStatus
0x140047cd1  jmp     loc_140048889
0x140047cd6  mov     eax, 1
0x140047cdb  mov     rdx, rsi
0x140047cde  mov     r9b, al
0x140047ce1  mov     r8d, eax
0x140047ce4  mov     rcx, r14
0x140047ce7  call    HsmpPrepareForMgmtOperation
0x140047cec  mov     ecx, eax
0x140047cee  mov     ebx, eax
0x140047cf0  call    HsmDbgBreakOnStatus
0x140047cf5  test    ebx, ebx
0x140047cf7  jns     short loc_140047D63
0x140047cf9  mov     r8, cs:WPP_GLOBAL_Control
0x140047d00  lea     rsi, WPP_GLOBAL_Control
0x140047d07  cmp     r8, rsi
0x140047d0a  jz      loc_140048889
0x140047d10  mov     ecx, [r8+2Ch]
0x140047d14  test    cl, 1
0x140047d17  jz      loc_140048889
0x140047d1d  cmp     byte ptr [r8+29h], 2
0x140047d22  jb      loc_140048889
0x140047d28  mov     rax, [r15+18h]
0x140047d2c  mov     edx, 31h ; '1'
0x140047d31  mov     rcx, [r8+18h]
0x140047d35  mov     r9, r13
0x140047d38  mov     [rsp+120h+var_D8], ebx
0x140047d3c  mov     [rsp+120h+var_E0], rax
0x140047d41  mov     rax, [r15+10h]
0x140047d45  mov     [rsp+120h+var_E8], rax
0x140047d4a  mov     qword ptr [rsp+120h+OutputBufferLength], rdi
0x140047d4f  mov     [rsp+120h+LengthReturned], r12
0x140047d54  mov     qword ptr [rsp+120h+FileInformationClass], r14
0x140047d59  call    WPP_SF_qqiqiid
0x140047d5e  jmp     loc_140048889
0x140047d63  mov     rcx, rdi
0x140047d66  mov     byte ptr [rbp+57h+var_C4], 0
0x140047d6a  mov     [rbp+57h+P], 0
0x140047d72  call    HsmpWaitForUserRequestRundownRelease
0x140047d77  mov     dl, 1
0x140047d79  mov     rcx, rdi
0x140047d7c  call    HsmpAcquireReparseUpdateLock
0x140047d81  mov     rcx, rdi
0x140047d84  call    HsmpIsPlaceholder
0x140047d89  test    al, al
0x140047d8b  jz      loc_14004883B
0x140047d91  mov     rax, [rbp+57h+var_98]
0x140047d95  mov     edx, [rax+28h]
0x140047d98  mov     rax, [rax+10h]
0x140047d9c  shr     edx, 5
0x140047d9f  and     edx, 1
0x140047da2  mov     ecx, [rax+4Ch]
0x140047da5  cmp     ecx, edx
0x140047da7  jle     short loc_140047DEB
0x140047da9  mov     ebx, 0C000CF14h
0x140047dae  mov     ecx, ebx
0x140047db0  call    HsmDbgBreakOnStatus
0x140047db5  mov     rcx, cs:WPP_GLOBAL_Control
0x140047dbc  lea     rsi, WPP_GLOBAL_Control
0x140047dc3  cmp     rcx, rsi
0x140047dc6  jz      loc_14004883B
0x140047dcc  mov     eax, [rcx+2Ch]
0x140047dcf  test    al, 1
0x140047dd1  jz      loc_14004883B
0x140047dd7  cmp     byte ptr [rcx+29h], 2
0x140047ddb  jb      loc_14004883B
0x140047de1  mov     edx, 32h ; '2'
0x140047de6  jmp     loc_14004880A
0x140047deb  xor     ebx, ebx
0x140047ded  cmp     [rdi+30h], rbx
0x140047df1  jz      loc_1400487D9
0x140047df7  cmp     [rdi+38h], ebx
0x140047dfa  jz      loc_1400487D9
0x140047e00  test    dword ptr [rdi+1Ch], 8000h
0x140047e07  jnz     loc_1400487D9
0x140047e0d  mov     rcx, r13; CallbackData
0x140047e10  call    cs:__imp_FltGetRequestorProcess
0x140047e17  nop     dword ptr [rax+rax+00h]
0x140047e1c  mov     rcx, rax
0x140047e1f  call    HsmOsIsSyncProviderProcess
0x140047e24  test    al, al
0x140047e26  mov     eax, dword ptr [rbp+57h+var_B8]
0x140047e29  jnz     loc_140047FEC
0x140047e2f  bt      eax, 19h
0x140047e33  jb      loc_140047FEC
0x140047e39  xor     edx, edx
0x140047e3b  mov     rcx, rdi
0x140047e3e  call    HsmpAcquireBitmapLock
0x140047e43  mov     eax, [rdi+1Ch]
0x140047e46  test    al, 40h
0x140047e48  jnz     loc_140047EEA
0x140047e4e  mov     rcx, rdi
0x140047e51  mov     [rbp+57h+var_C0], rbx
0x140047e55  call    HsmpGetStreamSize
0x140047e5a  mov     r8, rax
0x140047e5d  lea     r9, [rbp+57h+var_C0]
0x140047e61  mov     edx, 4244h
0x140047e66  call    HsmiQueryFileRangesTotalNoLock
0x140047e6b  mov     ecx, eax
0x140047e6d  mov     ebx, eax
0x140047e6f  call    HsmDbgBreakOnStatus
0x140047e74  test    ebx, ebx
0x140047e76  jns     short loc_140047EDF
0x140047e78  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e7f  lea     rsi, WPP_GLOBAL_Control
0x140047e86  cmp     rcx, rsi
0x140047e89  jz      loc_1400487CF
0x140047e8f  mov     eax, [rcx+2Ch]
0x140047e92  test    al, 1
0x140047e94  jz      loc_1400487CF
0x140047e9a  cmp     byte ptr [rcx+29h], 2
0x140047e9e  jb      loc_1400487CF
0x140047ea4  mov     edx, 41h ; 'A'
0x140047ea9  mov     rax, [r15+18h]
0x140047ead  mov     r9, r13
0x140047eb0  mov     rcx, [rcx+18h]
0x140047eb4  mov     [rsp+120h+var_D8], ebx
0x140047eb8  mov     [rsp+120h+var_E0], rax
0x140047ebd  mov     rax, [r15+10h]
0x140047ec1  mov     [rsp+120h+var_E8], rax
0x140047ec6  mov     qword ptr [rsp+120h+OutputBufferLength], rdi
0x140047ecb  mov     [rsp+120h+LengthReturned], r12
0x140047ed0  mov     qword ptr [rsp+120h+FileInformationClass], r14
0x140047ed5  call    WPP_SF_qqiqiid
0x140047eda  jmp     loc_1400487CF
0x140047edf  cmp     [rbp+57h+var_C0], 0
0x140047ee4  jz      loc_1400487CF
0x140047eea  mov     r9d, 100000h
0x140047ef0  mov     [rsp+120h+FileInformationClass], 80000h
0x140047ef8  xor     r8d, r8d
0x140047efb  mov     rdx, rsi
0x140047efe  mov     rcx, r14
0x140047f01  call    HsmpToggleFileAttributesNotify
0x140047f06  mov     ecx, eax
0x140047f08  mov     ebx, eax
0x140047f0a  call    HsmDbgBreakOnStatus
0x140047f0f  test    ebx, ebx
0x140047f11  jns     short loc_140047F49
0x140047f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f1a  lea     rsi, WPP_GLOBAL_Control
0x140047f21  cmp     rcx, rsi
0x140047f24  jz      loc_1400487CF
0x140047f2a  mov     eax, [rcx+2Ch]
0x140047f2d  test    al, 1
0x140047f2f  jz      loc_1400487CF
0x140047f35  cmp     byte ptr [rcx+29h], 2
0x140047f39  jb      loc_1400487CF
0x140047f3f  mov     edx, 42h ; 'B'
0x140047f44  jmp     loc_140047EA9
0x140047f49  mov     rdx, r13
0x140047f4c  mov     rcx, rdi
0x140047f4f  call    HsmpQueueDehydrationRequest
0x140047f54  mov     ecx, eax
0x140047f56  mov     ebx, eax
0x140047f58  call    HsmDbgBreakOnStatus
0x140047f5d  test    ebx, ebx
0x140047f5f  jns     short loc_140047F97
0x140047f61  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f68  lea     rsi, WPP_GLOBAL_Control
0x140047f6f  cmp     rcx, rsi
0x140047f72  jz      loc_1400487CF
0x140047f78  mov     eax, [rcx+2Ch]
0x140047f7b  test    al, 1
0x140047f7d  jz      loc_1400487CF
0x140047f83  cmp     byte ptr [rcx+29h], 2
0x140047f87  jb      loc_1400487CF
0x140047f8d  mov     edx, 43h ; 'C'
0x140047f92  jmp     loc_140047EA9
0x140047f97  mov     ecx, [r15+8]
0x140047f9b  mov     [rbp+57h+var_C7], 1
0x140047f9f  call    HsmpComputeDehydrationReason
0x140047fa4  mov     edx, eax
0x140047fa6  mov     rcx, rdi
0x140047fa9  call    HsmpSetLastDehydrationReasonNoLock
0x140047fae  mov     rcx, [rbp+57h+var_98]
0x140047fb2  lea     r11, qword_1400294D0
0x140047fb9  mov     rcx, [rcx+60h]
0x140047fbd  test    rcx, rcx
0x140047fc0  cmovnz  r11, rcx
0x140047fc4  mov     rcx, rdi
0x140047fc7  call    HsmpGetLastDehydrationReason
0x140047fcc  mov     r9d, eax
0x140047fcf  call    HsmpGetStreamSize
0x140047fd4  mov     r8, rax; int
0x140047fd7  mov     qword ptr [rsp+120h+FileInformationClass], r13; CallbackData
0x140047fdc  mov     rdx, r12; int
0x140047fdf  mov     rcx, r11; int
0x140047fe2  call    TlmWriteDehydrationQueued
0x140047fe7  jmp     loc_1400487CF
0x140047fec  shr     eax, 19h
0x140047fef  mov     ecx, 1
0x140047ff4  not     al
0x140047ff6  mov     dl, cl
0x140047ff8  and     al, cl
0x140047ffa  mov     rcx, rdi
0x140047ffd  mov     [rbp+57h+var_C4], eax
0x140048000  call    HsmpAcquireBitmapLock
0x140048005  test    dword ptr [rdi+1Ch], 2000h
0x14004800c  jz      loc_140048767
0x140048012  mov     [rbp+57h+var_C8], bl
0x140048015  cmp     [rsi+4Bh], bl
0x140048018  jnz     short loc_140048025
0x14004801a  mov     eax, 1
0x14004801f  mov     [rsi+4Bh], al
0x140048022  mov     [rbp+57h+var_C8], al
0x140048025  mov     eax, [rdi+1Ch]
0x140048028  test    al, 40h
0x14004802a  jnz     short loc_140048097
0x14004802c  mov     rcx, rdi
0x14004802f  mov     [rbp+57h+var_C0], rbx
0x140048033  call    HsmpGetStreamSize
0x140048038  mov     r8, rax
0x14004803b  lea     r9, [rbp+57h+var_C0]
0x14004803f  mov     edx, 4244h
0x140048044  call    HsmiQueryFileRangesTotalNoLock
0x140048049  mov     ecx, eax
0x14004804b  mov     ebx, eax
0x14004804d  call    HsmDbgBreakOnStatus
0x140048052  test    ebx, ebx
0x140048054  jns     short loc_14004808C
0x140048056  mov     rcx, cs:WPP_GLOBAL_Control
0x14004805d  lea     rsi, WPP_GLOBAL_Control
0x140048064  cmp     rcx, rsi
0x140048067  jz      loc_14004874F
0x14004806d  mov     eax, [rcx+2Ch]
0x140048070  test    al, 1
0x140048072  jz      loc_14004874F
0x140048078  cmp     byte ptr [rcx+29h], 2
0x14004807c  jb      loc_14004874F
0x140048082  mov     edx, 35h ; '5'
0x140048087  jmp     loc_14004871E
0x14004808c  cmp     [rbp+57h+var_C0], 0
0x140048091  jz      loc_140048753
0x140048097  cmp     qword ptr [r15+18h], 0FFFFFFFFFFFFFFFFh
0x14004809c  jnz     short loc_1400480AF
0x14004809e  mov     rcx, rdi
0x1400480a1  call    HsmpGetStreamSize
0x1400480a6  mov     rsi, rax
0x1400480a9  mov     rax, [rbp+57h+var_A8]
0x1400480ad  jmp     short loc_1400480BA
0x1400480af  mov     rax, [rbp+57h+var_A8]
0x1400480b3  mov     rsi, [rbp+57h+var_B0]
0x1400480b7  add     rsi, rax
0x1400480ba  mov     [rbp+57h+var_C0], rsi
0x1400480be  test    rax, rax
0x1400480c1  js      loc_1400486ED
0x1400480c7  cmp     rax, rsi
0x1400480ca  jg      loc_1400486ED
0x1400480d0  mov     rcx, rdi
0x1400480d3  call    HsmpNotifyDataChange
0x1400480d8  mov     ecx, eax
  ... truncated ...
```
