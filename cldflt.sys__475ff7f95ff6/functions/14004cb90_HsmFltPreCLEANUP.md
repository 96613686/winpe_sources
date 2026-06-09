# HsmFltPreCLEANUP

- ea: `0x14004cb90`
- end: `0x14004d6f5`
- name: `HsmFltPreCLEANUP`
- size: `2917`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x140001910`
- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x14000abb8`
- `0x14000cde0`
- `0x14000d388`
- `0x14001b290`
- `0x14001e2a0`
- `0x14001e300`
- `0x140036178`
- `0x14004c6b0`
- `0x14004cb90`
- `0x14004d6fc`
- `0x14004d7bc`
- `0x14004d818`
- `0x1400521f0`
- `0x1400548ec`
- `0x140054b24`
- `0x140058ddc`
- `0x140059090`
- `0x14006f28c`
- `0x14007456c`
- `0x14007646c`

## import_xrefs

- `ntoskrnl!FsRtlFastUnlockAll` at `0x14004cf08`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14004cf08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd7b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cd57`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cd57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cd45`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cd45`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004d49a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004d49a`
- `ntoskrnl!KeInitializeEvent` at `0x14004d042`
- `ntoskrnl!KeInitializeEvent` at `0x14004d042`
- `ntoskrnl!KeSetEvent` at `0x14004cfe0`
- `ntoskrnl!KeSetEvent` at `0x14004d692`
- `ntoskrnl!KeSetEvent` at `0x14004cfe0`
- `ntoskrnl!KeSetEvent` at `0x14004d692`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14004d67a`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14004d67a`
- `FLTMGR!FltFlushBuffers2` at `0x14004d5d8`
- `FLTMGR!FltFlushBuffers2` at `0x14004d5d8`
- `FLTMGR!FltSetInformationFile` at `0x14004d16f`
- `FLTMGR!FltSetInformationFile` at `0x14004d16f`
- `FLTMGR!FltGetFileContext` at `0x14004cc65`
- `FLTMGR!FltGetFileContext` at `0x14004cc65`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004cbcd`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004cbcd`
- `FLTMGR!FltReferenceContext` at `0x14004cd0d`
- `FLTMGR!FltReferenceContext` at `0x14004cd0d`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004d091`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004d091`
- `FLTMGR!FltDeleteContext` at `0x14004d216`
- `FLTMGR!FltDeleteContext` at `0x14004d6c0`
- `FLTMGR!FltDeleteContext` at `0x14004d216`
- `FLTMGR!FltDeleteContext` at `0x14004d6c0`
- `FLTMGR!FltCancelIo` at `0x14004d479`
- `FLTMGR!FltCancelIo` at `0x14004d479`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cc0b`
- `FLTMGR!FltGetRequestorProcess` at `0x14004ccdc`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cee7`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cc0b`
- `FLTMGR!FltGetRequestorProcess` at `0x14004ccdc`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cee7`
- `FLTMGR!FltReleasePushLockEx` at `0x14004d6ac`
- `FLTMGR!FltReleasePushLockEx` at `0x14004d6ac`
- `FLTMGR!FltReleaseContext` at `0x14004cc2b`
- `FLTMGR!FltReleaseContext` at `0x14004cc94`
- `FLTMGR!FltReleaseContext` at `0x14004cd1e`
- `FLTMGR!FltReleaseContext` at `0x14004d6cf`
- `FLTMGR!FltReleaseContext` at `0x14004cc2b`
- `FLTMGR!FltReleaseContext` at `0x14004cc94`
- `FLTMGR!FltReleaseContext` at `0x14004cd1e`
- `FLTMGR!FltReleaseContext` at `0x14004d6cf`

## pseudocode

```c
__int64 __fastcall HsmFltPreCLEANUP(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  void *v3; // r12
  struct _FLT_INSTANCE *v6; // rbx
  struct _FILE_OBJECT *v7; // rdx
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v12; // rcx
  struct _FLT_INSTANCE *v13; // rbx
  struct _FILE_OBJECT *v14; // rdx
  __int64 v15; // r13
  char *v16; // rsi
  unsigned int v17; // ebx
  int v18; // r12d
  PEPROCESS v20; // rax
  PFLT_CONTEXT v21; // rcx
  unsigned __int64 v22; // rbx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  void *v27; // rcx
  unsigned __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // r8
  _DWORD *v31; // r10
  _DWORD *v32; // r11
  __int64 *v33; // r9
  bool v34; // zf
  unsigned __int64 *v35; // rax
  __int64 *v36; // rax
  __int64 v37; // rcx
  char v38; // cl
  PEPROCESS v39; // r8
  FILE_LOCK *FileLock; // rax
  PEPROCESS v41; // r8
  NTSTATUS v42; // r8d
  __int64 v43; // rax
  int v44; // r9d
  PFLT_CALLBACK_DATA v45; // rdx
  char v46; // al
  __int64 v47; // r10
  int v48; // r9d
  struct _FILE_OBJECT *v49; // rdx
  struct _FLT_INSTANCE *v50; // rcx
  NTSTATUS v51; // r12d
  int v52; // eax
  int v53; // ecx
  __int64 v54; // rax
  unsigned int v55; // ecx
  unsigned __int64 v56; // rbx
  unsigned int v57; // r11d
  unsigned int v58; // r10d
  int v59; // eax
  unsigned int v60; // r9d
  unsigned int v61; // r11d
  unsigned int v62; // ecx
  __int64 StreamSize; // rax
  __int64 v64; // rdx
  __int64 v65; // r10
  int v66; // r9d
  int v67; // eax
  __int64 v68; // rbx
  NTSTATUS v69; // [rsp+40h] [rbp-79h]
  __int64 v70; // [rsp+50h] [rbp-69h]
  PFLT_CONTEXT v71; // [rsp+60h] [rbp-59h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-51h] BYREF
  PFLT_CONTEXT v73; // [rsp+70h] [rbp-49h] BYREF
  __int64 v74; // [rsp+78h] [rbp-41h] BYREF
  void *v75; // [rsp+80h] [rbp-39h]
  __int64 *v76; // [rsp+88h] [rbp-31h]
  _DWORD *v77; // [rsp+90h] [rbp-29h]
  unsigned __int64 v78; // [rsp+98h] [rbp-21h] BYREF
  _DWORD *v79; // [rsp+A0h] [rbp-19h]
  unsigned __int64 v80; // [rsp+A8h] [rbp-11h]
  struct _KEVENT Event; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 FileInformation; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v84; // [rsp+130h] [rbp+77h] BYREF
  unsigned int v85; // [rsp+138h] [rbp+7Fh] BYREF

  v3 = 0;
  *a3 = 0;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v7 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  FltGetStreamHandleContext(v6, v7, &Context);
  v9 = Context;
  if ( Context )
  {
    v10 = *((_QWORD *)Context + 2);
    if ( (*(_DWORD *)(v10 + 28) & 1) == 0 )
    {
      FltDeleteContext(Context);
      goto LABEL_6;
    }
    if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 16LL) + 32LL) != v6 )
    {
      v12 = Context;
      goto LABEL_7;
    }
    if ( !CallbackData )
      goto LABEL_8;
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
    {
LABEL_6:
      v12 = Context;
LABEL_7:
      FltReleaseContext(v12);
      v9 = 0;
      Context = 0;
      goto LABEL_8;
    }
    v9 = Context;
  }
LABEL_8:
  if ( v9 )
  {
    v15 = v9[2];
    v16 = *(char **)(v15 + 16);
    v3 = (void *)*((_QWORD *)v16 + 2);
    FltReferenceContext(v16);
  }
  else
  {
    v13 = *(struct _FLT_INSTANCE **)(a2 + 24);
    v14 = *(struct _FILE_OBJECT **)(a2 + 32);
    v15 = 0;
    v73 = 0;
    FltGetFileContext(v13, v14, &v73);
    v16 = (char *)v73;
    if ( !v73 )
      goto LABEL_10;
    if ( *(struct _FLT_INSTANCE **)(*((_QWORD *)v73 + 2) + 32LL) == v13 )
    {
      if ( !CallbackData )
        goto LABEL_24;
      v20 = FltGetRequestorProcess(CallbackData);
      if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(v20) )
      {
        v16 = (char *)v73;
        goto LABEL_24;
      }
      v21 = v73;
    }
    else
    {
      v21 = v73;
    }
    FltReleaseContext(v21);
    v16 = 0;
    v73 = 0;
  }
LABEL_24:
  if ( v16 )
  {
    v22 = *(_QWORD *)(a2 + 32);
    v80 = v22;
    v78 = v22;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v16 + 120), 1u);
    v23 = *((_QWORD *)v16 + 28);
    v74 = v23;
    if ( v23 )
    {
      v28 = *(_QWORD *)(v23 + 96);
      v29 = v23 + 96;
      v84 = v23 + 96;
      v30 = v23 + 96;
      FileInformation = v23 + 96;
      if ( v28 != v23 + 96 )
      {
        do
        {
          if ( *(_QWORD *)(v28 - 64) <= v22 && *(_QWORD *)(v28 - 64) >= v22 )
          {
            if ( *(_QWORD *)(v28 + 8) != v30 || (v43 = *(_QWORD *)v28, *(_QWORD *)(*(_QWORD *)v28 + 8LL) != v28) )
LABEL_78:
              __fastfail(3u);
            *(_QWORD *)v30 = v43;
            *(_QWORD *)(v43 + 8) = v30;
            *(_QWORD *)(v28 + 8) = v28;
            *(_QWORD *)v28 = v28;
            *(_DWORD *)(v28 - 16) = -1073741816;
            KeSetEvent((PRKEVENT)(v28 - 40), 0, 0);
            v29 = v84;
            v30 = *(_QWORD *)(FileInformation + 8);
          }
          v30 = *(_QWORD *)v30;
          FileInformation = v30;
          v28 = *(_QWORD *)v30;
        }
        while ( *(_QWORD *)v30 != v29 );
        v23 = v74;
      }
      v31 = *(_DWORD **)(v23 + 80);
      v32 = (_DWORD *)(v23 + 80);
      v77 = (_DWORD *)(v23 + 80);
      v33 = (__int64 *)(v23 + 80);
      v76 = (__int64 *)(v23 + 80);
      v79 = v31;
      if ( v31 != (_DWORD *)(v23 + 80) )
      {
        LOBYTE(FileInformation) = 0;
        while ( 1 )
        {
          v34 = v31[8] == 0;
          v35 = (unsigned __int64 *)(v31 + 6);
          v75 = v31 + 6;
          if ( v34 )
          {
            if ( *v35 < v22 || *v35 > v22 )
              goto LABEL_44;
            LOBYTE(FileInformation) = 1;
          }
          else
          {
            v55 = v31[5];
            v28 = 0;
            LODWORD(v84) = 0;
            v85 = v55;
            if ( v55 )
            {
              v56 = *v35;
              v57 = 0;
              v58 = v55;
              do
              {
                v59 = HsmiCompareLockOwners(v56 + 8LL * ((v58 + v57) >> 1), &v78, v30, (v58 + v57) >> 1);
                v62 = v60 + 1;
                if ( v59 >= 0 )
                {
                  v62 = v61;
                  v58 = v60;
                }
                v57 = v62;
              }
              while ( v62 < v58 );
              v22 = v80;
              v28 = v62;
              v32 = v77;
              v33 = v76;
              v35 = (unsigned __int64 *)v75;
              LODWORD(v84) = v62;
              v55 = v85;
            }
            if ( (unsigned int)v28 >= v55 )
              goto LABEL_44;
            v75 = (void *)(*v35 + 8LL * (unsigned int)v28);
            if ( (unsigned int)HsmiCompareLockOwners(v75, &v78, v30, v33) )
              goto LABEL_44;
            v28 = v85;
            v38 = 1;
            LOBYTE(FileInformation) = 1;
            if ( v85 > 1 )
            {
              v30 = (unsigned int)v84;
              v31[5] = v85 - 1;
              if ( (unsigned int)v30 >= (int)v28 - 1 )
                goto LABEL_45;
              memmove(v75, (char *)v75 + 8, 8LL * (unsigned int)(v28 - v30 - 1));
              v33 = v76;
              goto LABEL_43;
            }
          }
          v36 = (__int64 *)*v33;
          if ( *(__int64 **)(*v33 + 8) != v33 )
            goto LABEL_78;
          v37 = *v36;
          if ( *(__int64 **)(*v36 + 8) != v36 )
            goto LABEL_78;
          *v33 = v37;
          *(_QWORD *)(v37 + 8) = v33;
          HsmiFreePropertyLock(v31);
          v33 = (__int64 *)v76[1];
LABEL_43:
          v32 = v77;
LABEL_44:
          v38 = FileInformation;
LABEL_45:
          v33 = (__int64 *)*v33;
          v76 = v33;
          v31 = (_DWORD *)*v33;
          v79 = v31;
          if ( v31 == v32 )
          {
            if ( v38 )
              HsmiProcessPropertyLockRequestList(v74, v28, v30);
            break;
          }
        }
      }
    }
    ExReleaseResourceLite((PERESOURCE)(v16 + 120));
    KeLeaveCriticalRegion();
  }
LABEL_10:
  v17 = 1;
  if ( !v9 )
  {
LABEL_11:
    v18 = (int)CallbackData;
    goto LABEL_12;
  }
  v71 = 0;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, 1, (_DWORD)v9, v15);
  v24 = *((_DWORD *)v9 + 10);
  if ( (v24 & 0x1000) == 0 || (v24 & 0x800) != 0 )
  {
LABEL_28:
    HsmpRecallTerminateProgressiveHydration(v9);
    v26 = *(_QWORD *)(v15 + 160);
    if ( v26 && *(_QWORD *)(v26 + 32) )
    {
      v39 = CallbackData ? FltGetRequestorProcess(CallbackData) : 0LL;
      FileLock = (FILE_LOCK *)HsmpGetFileLock(v15, v25, v39);
      v42 = FsRtlFastUnlockAll(FileLock, *(PFILE_OBJECT *)(a2 + 32), v41, 0);
      if ( (int)(v42 + 0x80000000) >= 0
        && v42 != -1073741698
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
          v3,
          v15,
          *(_QWORD *)(a2 + 32),
          *((_QWORD *)v16 + 4),
          CallbackData,
          v42);
      }
    }
    if ( *((_BYTE *)v9 + 45) )
    {
      v67 = FltFlushBuffers2(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), 1, 0);
      if ( v67 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
          v3,
          v15,
          *(_QWORD *)(a2 + 32),
          *((_QWORD *)v16 + 4),
          CallbackData,
          v67);
      }
    }
    if ( (v9[5] & 0x10) != 0 )
    {
      v68 = v9[2];
      LOBYTE(v25) = 1;
      HsmpAcquireReparseUpdateLock(v68, v25);
      if ( (v9[5] & 0x10) != 0 )
      {
        v34 = (*(_DWORD *)(v68 + 112))-- == 1;
        if ( v34 )
        {
          ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(v68 + 120));
          KeSetEvent((PRKEVENT)(v68 + 128), 0, 0);
        }
        *((_DWORD *)v9 + 10) &= ~0x10u;
      }
      FltReleasePushLockEx(*(_QWORD *)(v68 + 16) + 24LL, 0);
    }
LABEL_31:
    *a3 = v9;
    v27 = v71;
    v17 = 0;
    v9 = 0;
    if ( !v71 )
      goto LABEL_11;
LABEL_94:
    HsmpReleaseFileNameLock(v27);
    goto LABEL_11;
  }
  v74 = 0;
  v85 = 0;
  memset(&Event, 0, sizeof(Event));
  LODWORD(v84) = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CallbackData->QueueContext[0] = &Event;
  HsmpCldNotifyPreOperation(
    4,
    CallbackData,
    8 * (*(_DWORD *)(v15 + 28) & 2u),
    0,
    HsmiDeleteOnCloseNotificationCallback,
    CallbackData);
  LODWORD(FileInformation) = FltCancellableWaitForSingleObject(&Event, 0, CallbackData);
  HsmDbgBreakOnStatus(FileInformation);
  v44 = FileInformation;
  if ( (_DWORD)FileInformation == -1073741749 || (_DWORD)FileInformation == -1073741536 )
  {
    FltCancelIo(CallbackData);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    v44 = FileInformation;
  }
  v45 = CallbackData;
  CallbackData->QueueContext[0] = 0;
  if ( v44 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      StreamSize = HsmpGetStreamSize(v15);
      WPP_SF_qqiqLiqdd(
        *(_QWORD *)(v65 + 24),
        *(unsigned int *)(v64 + 24),
        *(_QWORD *)(v15 + 16),
        v3,
        *(_QWORD *)(a2 + 32),
        *(_QWORD *)(*(_QWORD *)(v15 + 16) + 32LL),
        v15,
        *(_DWORD *)(v15 + 28),
        StreamSize,
        v9,
        v66,
        *(_DWORD *)(v64 + 24));
      v45 = CallbackData;
    }
    if ( v45->IoStatus.Status >= 0 )
    {
      v71 = (PFLT_CONTEXT)HsmpAcquireFileNameLock(v3);
      if ( !v71 )
        goto LABEL_11;
      v75 = *(void **)(a2 + 32);
      LODWORD(FileInformation) = HsmiCldGetSyncRootFileIdByFileObject(v3, v75, &v74, &v85, &v84);
      HsmDbgBreakOnStatus(FileInformation);
      v52 = FileInformation;
      if ( (FileInformation & 0x80000000) != 0LL
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          55,
          WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
          v3,
          v15,
          v75,
          FileInformation);
        v52 = FileInformation;
      }
      HsmDbgBreakOnStatus(v52);
      v53 = 0;
      if ( (_DWORD)FileInformation != -1073688813 )
        v53 = FileInformation;
      if ( v53 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qiqiid(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
            v3,
            v15,
            *(_QWORD *)(a2 + 32),
            *(_QWORD *)(*(_QWORD *)(v15 + 16) + 32LL),
            CallbackData,
            v53);
        }
        goto LABEL_93;
      }
      if ( (_DWORD)v84 )
      {
        if ( v85 == 1 )
        {
          v54 = ((__int64 (__fastcall *)(_QWORD))qword_1400296C8)(*(_QWORD *)(v15 + 8));
          if ( v54 == v74 )
          {
            if ( (*(_DWORD *)(v15 + 28) & 2) == 0 )
              HsmpCloseExternalBitmaps(v15);
            LODWORD(FileInformation) = HsmpRpRemove((PFLT_CONTEXT)v15, *(PFILE_OBJECT *)(a2 + 32));
            HsmDbgBreakOnStatus(FileInformation);
            if ( (FileInformation & 0x80000000) != 0LL )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qiqiid(
                  WPP_GLOBAL_Control->AttachedDevice,
                  14,
                  WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
                  v3,
                  v15,
                  *(_QWORD *)(a2 + 32),
                  *(_QWORD *)(*(_QWORD *)(v15 + 16) + 32LL),
                  CallbackData,
                  FileInformation);
              }
LABEL_93:
              v27 = v71;
              goto LABEL_94;
            }
          }
        }
      }
      goto LABEL_28;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v46 = HsmpGetStreamSize(v15);
    LODWORD(v70) = v48;
    WPP_SF_qqiqLiqd(
      *(_QWORD *)(v47 + 24),
      11,
      (unsigned int)WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
      (_DWORD)v3,
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(*(_QWORD *)(v15 + 16) + 32LL),
      v15,
      *(_DWORD *)(v15 + 28),
      v46,
      v9,
      v70);
  }
  v49 = *(struct _FILE_OBJECT **)(a2 + 32);
  v50 = *(struct _FLT_INSTANCE **)(a2 + 24);
  LODWORD(FileInformation) = 8;
  v51 = FltSetInformationFile(v50, v49, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
  HsmDbgBreakOnStatus(v51);
  if ( v51 >= 0 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_11;
  }
  v69 = v51;
  v18 = (int)CallbackData;
  WPP_SF_qiqiid(
    WPP_GLOBAL_Control->AttachedDevice,
    12,
    WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids,
    *(_QWORD *)(*(_QWORD *)(v15 + 16) + 16LL),
    v15,
    *(_QWORD *)(a2 + 32),
    *(_QWORD *)(*(_QWORD *)(v15 + 16) + 32LL),
    CallbackData,
    v69);
LABEL_12:
  if ( v16 )
    FltReleaseContext(v16);
  if ( v9 )
  {
    FltDeleteContext(v9);
    FltReleaseContext(v9);
    HsmpTracePreCallbackExit(v17, v18, *a3, 0, 1);
  }
  return v17;
}

```

## disassembly

```asm
0x14004cb90  mov     [rsp-8+CallbackData], rcx
0x14004cb95  push    rbp
0x14004cb96  push    rbx
0x14004cb97  push    rsi
0x14004cb98  push    rdi
0x14004cb99  push    r12
0x14004cb9b  push    r14
0x14004cb9d  push    r15
0x14004cb9f  lea     rbp, [rsp-27h]
0x14004cba4  sub     rsp, 0E0h
0x14004cbab  xor     r12d, r12d
0x14004cbae  mov     r15, r8
0x14004cbb1  mov     [r8], r12
0x14004cbb4  mov     r14, rdx
0x14004cbb7  mov     rbx, [rdx+18h]
0x14004cbbb  lea     r8, [rbp+57h+Context]; Context
0x14004cbbf  mov     rdx, [rdx+20h]; FileObject
0x14004cbc3  mov     rsi, rcx
0x14004cbc6  mov     rcx, rbx; Instance
0x14004cbc9  mov     [rbp+57h+Context], r12
0x14004cbcd  call    cs:__imp_FltGetStreamHandleContext
0x14004cbd4  nop     dword ptr [rax+rax+00h]
0x14004cbd9  mov     rdi, [rbp+57h+Context]
0x14004cbdd  test    rdi, rdi
0x14004cbe0  jz      short loc_14004CC3E
0x14004cbe2  mov     rcx, [rdi+10h]
0x14004cbe6  mov     eax, [rcx+1Ch]
0x14004cbe9  test    al, 1
0x14004cbeb  jz      loc_14004D20A
0x14004cbf1  mov     rax, [rcx+10h]
0x14004cbf5  mov     rcx, [rax+10h]
0x14004cbf9  cmp     [rcx+20h], rbx
0x14004cbfd  jnz     loc_14004D38B
0x14004cc03  test    rsi, rsi
0x14004cc06  jz      short loc_14004CC3E
0x14004cc08  mov     rcx, rsi; CallbackData
0x14004cc0b  call    cs:__imp_FltGetRequestorProcess
0x14004cc12  nop     dword ptr [rax+rax+00h]
0x14004cc17  mov     rcx, rax
0x14004cc1a  call    HsmOsIsPassThroughModeEnabled
0x14004cc1f  test    al, al
0x14004cc21  jz      loc_14004D393
0x14004cc27  mov     rcx, [rbp+57h+Context]; Context
0x14004cc2b  call    cs:__imp_FltReleaseContext
0x14004cc32  nop     dword ptr [rax+rax+00h]
0x14004cc37  mov     rdi, r12
0x14004cc3a  mov     [rbp+57h+Context], r12
0x14004cc3e  mov     [rsp+110h+var_38], r13
0x14004cc46  test    rdi, rdi
0x14004cc49  jnz     loc_14004CCFE
0x14004cc4f  mov     rbx, [r14+18h]
0x14004cc53  lea     r8, [rbp+57h+var_A0]; Context
0x14004cc57  mov     rdx, [r14+20h]; FileObject
0x14004cc5b  mov     rcx, rbx; Instance
0x14004cc5e  mov     r13, r12
0x14004cc61  mov     [rbp+57h+var_A0], r12
0x14004cc65  call    cs:__imp_FltGetFileContext
0x14004cc6c  nop     dword ptr [rax+rax+00h]
0x14004cc71  mov     rsi, [rbp+57h+var_A0]
0x14004cc75  test    rsi, rsi
0x14004cc78  jnz     short loc_14004CCC6
0x14004cc7a  mov     ebx, 1
0x14004cc7f  test    rdi, rdi
0x14004cc82  jnz     loc_14004CD98
0x14004cc88  mov     r12, [rbp+57h+CallbackData]
0x14004cc8c  test    rsi, rsi
0x14004cc8f  jz      short loc_14004CCA0
0x14004cc91  mov     rcx, rsi; Context
0x14004cc94  call    cs:__imp_FltReleaseContext
0x14004cc9b  nop     dword ptr [rax+rax+00h]
0x14004cca0  test    rdi, rdi
0x14004cca3  jnz     loc_14004D6BD
0x14004cca9  mov     r13, [rsp+110h+var_38]
0x14004ccb1  mov     eax, ebx
0x14004ccb3  add     rsp, 0E0h
0x14004ccba  pop     r15
0x14004ccbc  pop     r14
0x14004ccbe  pop     r12
0x14004ccc0  pop     rdi
0x14004ccc1  pop     rsi
0x14004ccc2  pop     rbx
0x14004ccc3  pop     rbp
0x14004ccc4  retn
0x14004ccc6  mov     rax, [rsi+10h]
0x14004ccca  cmp     [rax+20h], rbx
0x14004ccce  jnz     short loc_14004CD1B
0x14004ccd0  mov     rax, [rbp+57h+CallbackData]
0x14004ccd4  test    rax, rax
0x14004ccd7  jz      short loc_14004CD30
0x14004ccd9  mov     rcx, rax; CallbackData
0x14004ccdc  call    cs:__imp_FltGetRequestorProcess
0x14004cce3  nop     dword ptr [rax+rax+00h]
0x14004cce8  mov     rcx, rax
0x14004cceb  call    HsmOsIsPassThroughModeEnabled
0x14004ccf0  test    al, al
0x14004ccf2  jnz     loc_14004D39C
0x14004ccf8  mov     rsi, [rbp+57h+var_A0]
0x14004ccfc  jmp     short loc_14004CD30
0x14004ccfe  mov     r13, [rdi+10h]
0x14004cd02  mov     rsi, [r13+10h]
0x14004cd06  mov     rcx, rsi; Context
0x14004cd09  mov     r12, [rsi+10h]
0x14004cd0d  call    cs:__imp_FltReferenceContext
0x14004cd14  nop     dword ptr [rax+rax+00h]
0x14004cd19  jmp     short loc_14004CD30
0x14004cd1b  mov     rcx, rsi; Context
0x14004cd1e  call    cs:__imp_FltReleaseContext
0x14004cd25  nop     dword ptr [rax+rax+00h]
0x14004cd2a  xor     esi, esi
0x14004cd2c  mov     [rbp+57h+var_A0], rsi
0x14004cd30  test    rsi, rsi
0x14004cd33  jz      loc_14004CC7A
0x14004cd39  mov     rbx, [r14+20h]
0x14004cd3d  mov     [rbp+57h+var_68], rbx
0x14004cd41  mov     [rbp+57h+var_78], rbx
0x14004cd45  call    cs:__imp_KeEnterCriticalRegion
0x14004cd4c  nop     dword ptr [rax+rax+00h]
0x14004cd51  lea     rcx, [rsi+78h]; Resource
0x14004cd55  mov     dl, 1; Wait
0x14004cd57  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004cd5e  nop     dword ptr [rax+rax+00h]
0x14004cd63  mov     rax, [rsi+0E0h]
0x14004cd6a  mov     [rbp+57h+var_98], rax
0x14004cd6e  test    rax, rax
0x14004cd71  jnz     loc_14004CE0C
0x14004cd77  lea     rcx, [rsi+78h]; Resource
0x14004cd7b  call    cs:__imp_ExReleaseResourceLite
0x14004cd82  nop     dword ptr [rax+rax+00h]
0x14004cd87  call    cs:__imp_KeLeaveCriticalRegion
0x14004cd8e  nop     dword ptr [rax+rax+00h]
0x14004cd93  jmp     loc_14004CC7A
0x14004cd98  mov     rcx, [rbp+57h+CallbackData]
0x14004cd9c  mov     r9, rdi
0x14004cd9f  movzx   r8d, bl
0x14004cda3  mov     [rbp+57h+var_B0], 0
0x14004cdab  xor     edx, edx
0x14004cdad  mov     qword ptr [rsp+110h+FileInformationClass], r13
0x14004cdb2  call    HsmpTracePreCallbackEnter
0x14004cdb7  mov     eax, [rdi+28h]
0x14004cdba  bt      eax, 0Ch
0x14004cdbe  jb      loc_14004D018
0x14004cdc4  mov     rcx, rdi
0x14004cdc7  call    HsmpRecallTerminateProgressiveHydration
0x14004cdcc  mov     rax, [r13+0A0h]
0x14004cdd3  test    rax, rax
0x14004cdd6  jnz     loc_14004CECC
0x14004cddc  movzx   eax, byte ptr [rdi+2Dh]
0x14004cde0  test    al, al
0x14004cde2  jnz     loc_14004D5CA
0x14004cde8  mov     eax, [rdi+28h]
0x14004cdeb  test    al, 10h
0x14004cded  jnz     loc_14004D65B
0x14004cdf3  mov     [r15], rdi
0x14004cdf6  mov     rcx, [rbp+57h+var_B0]
0x14004cdfa  xor     ebx, ebx
0x14004cdfc  xor     edi, edi
0x14004cdfe  test    rcx, rcx
0x14004ce01  jz      loc_14004CC88
0x14004ce07  jmp     loc_14004D323
0x14004ce0c  mov     rdx, [rax+60h]
0x14004ce10  lea     rcx, [rax+60h]
0x14004ce14  mov     [rbp+57h+arg_10], rcx
0x14004ce18  mov     r8, rcx
0x14004ce1b  mov     [rbp+57h+FileInformation], rcx
0x14004ce1f  cmp     rdx, rcx
0x14004ce22  jnz     loc_14004CFA3
0x14004ce28  mov     r10, [rax+50h]
0x14004ce2c  lea     r11, [rax+50h]
0x14004ce30  mov     [rbp+57h+var_80], r11
0x14004ce34  mov     r9, r11
0x14004ce37  mov     [rbp+57h+var_88], r11
0x14004ce3b  mov     [rbp+57h+var_70], r10
0x14004ce3f  cmp     r10, r11
0x14004ce42  jz      loc_14004CD77
0x14004ce48  mov     byte ptr [rbp+57h+FileInformation], 0
0x14004ce4c  cmp     dword ptr [r10+20h], 0
0x14004ce51  lea     rax, [r10+18h]
0x14004ce55  mov     [rbp+57h+var_90], rax
0x14004ce59  jnz     loc_14004D3A5
0x14004ce5f  cmp     [rax], rbx
0x14004ce62  jb      short loc_14004CE9F
0x14004ce64  ja      short loc_14004CE9F
0x14004ce66  mov     byte ptr [rbp+57h+FileInformation], 1
0x14004ce6a  mov     rax, [r9]
0x14004ce6d  cmp     [rax+8], r9
0x14004ce71  jnz     loc_14004D203
0x14004ce77  mov     rcx, [rax]
0x14004ce7a  cmp     [rcx+8], rax
0x14004ce7e  jnz     loc_14004D203
0x14004ce84  mov     [r9], rcx
0x14004ce87  mov     [rcx+8], r9
0x14004ce8b  mov     rcx, r10; P
0x14004ce8e  call    HsmiFreePropertyLock
0x14004ce93  mov     r9, [rbp+57h+var_88]
0x14004ce97  mov     r9, [r9+8]
0x14004ce9b  mov     r11, [rbp+57h+var_80]
0x14004ce9f  movzx   ecx, byte ptr [rbp+57h+FileInformation]
0x14004cea3  mov     r9, [r9]
0x14004cea6  mov     [rbp+57h+var_88], r9
0x14004ceaa  mov     r10, [r9]
0x14004cead  mov     [rbp+57h+var_70], r10
0x14004ceb1  cmp     r10, r11
0x14004ceb4  jnz     short loc_14004CE4C
0x14004ceb6  test    cl, cl
0x14004ceb8  jz      loc_14004CD77
0x14004cebe  mov     rcx, [rbp+57h+var_98]
0x14004cec2  call    HsmiProcessPropertyLockRequestList
0x14004cec7  jmp     loc_14004CD77
0x14004cecc  cmp     qword ptr [rax+20h], 0
0x14004ced1  jz      loc_14004CDDC
0x14004ced7  mov     rax, [rbp+57h+CallbackData]
0x14004cedb  test    rax, rax
0x14004cede  jz      loc_14004D010
0x14004cee4  mov     rcx, rax; CallbackData
0x14004cee7  call    cs:__imp_FltGetRequestorProcess
0x14004ceee  nop     dword ptr [rax+rax+00h]
0x14004cef3  mov     r8, rax
0x14004cef6  mov     rcx, r13
0x14004cef9  call    HsmpGetFileLock
0x14004cefe  mov     rdx, [r14+20h]; FileObject
0x14004cf02  mov     rcx, rax; FileLock
0x14004cf05  xor     r9d, r9d; Context
0x14004cf08  call    cs:__imp_FsRtlFastUnlockAll
0x14004cf0f  nop     dword ptr [rax+rax+00h]
0x14004cf14  mov     r8d, eax
0x14004cf17  mov     eax, 80000000h
0x14004cf1c  lea     ecx, [r8+rax]
0x14004cf20  test    eax, ecx
0x14004cf22  jnz     loc_14004CDDC
0x14004cf28  cmp     r8d, 0C000007Eh
0x14004cf2f  jz      loc_14004CDDC
0x14004cf35  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf3c  lea     rax, WPP_GLOBAL_Control
0x14004cf43  cmp     rcx, rax
0x14004cf46  jz      loc_14004CDDC
0x14004cf4c  mov     eax, [rcx+2Ch]
0x14004cf4f  test    bl, al
0x14004cf51  jz      loc_14004CDDC
0x14004cf57  cmp     byte ptr [rcx+29h], 2
0x14004cf5b  jb      loc_14004CDDC
0x14004cf61  mov     rax, [rbp+57h+CallbackData]
0x14004cf65  mov     edx, 0Fh
0x14004cf6a  mov     rcx, [rcx+18h]
0x14004cf6e  mov     r9, r12
0x14004cf71  mov     dword ptr [rsp+110h+var_D0], r8d
0x14004cf76  lea     r8, WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids
0x14004cf7d  mov     [rsp+110h+var_D8], rax
0x14004cf82  mov     rax, [rsi+20h]
0x14004cf86  mov     [rsp+110h+var_E0], rax
0x14004cf8b  mov     rax, [r14+20h]
0x14004cf8f  mov     [rsp+110h+var_E8], rax
0x14004cf94  mov     qword ptr [rsp+110h+FileInformationClass], r13
0x14004cf99  call    WPP_SF_qiqiid
0x14004cf9e  jmp     loc_14004CDDC
0x14004cfa3  cmp     [rdx-40h], rbx
0x14004cfa7  ja      short loc_14004CFF8
0x14004cfa9  jb      short loc_14004CFF8
0x14004cfab  cmp     [rdx+8], r8
0x14004cfaf  jnz     loc_14004D203
0x14004cfb5  mov     rax, [rdx]
0x14004cfb8  cmp     [rax+8], rdx
0x14004cfbc  jnz     loc_14004D203
0x14004cfc2  mov     [r8], rax
0x14004cfc5  lea     rcx, [rdx-28h]; Event
0x14004cfc9  mov     [rax+8], r8
0x14004cfcd  xor     r8d, r8d; Wait
0x14004cfd0  mov     [rdx+8], rdx
0x14004cfd4  mov     [rdx], rdx
0x14004cfd7  mov     dword ptr [rdx-10h], 0C0000008h
0x14004cfde  xor     edx, edx; Increment
0x14004cfe0  call    cs:__imp_KeSetEvent
0x14004cfe7  nop     dword ptr [rax+rax+00h]
0x14004cfec  mov     r8, [rbp+57h+FileInformation]
0x14004cff0  mov     rcx, [rbp+57h+arg_10]
0x14004cff4  mov     r8, [r8+8]
0x14004cff8  mov     r8, [r8]
0x14004cffb  mov     [rbp+57h+FileInformation], r8
0x14004cfff  mov     rdx, [r8]
0x14004d002  cmp     rdx, rcx
0x14004d005  jnz     short loc_14004CFA3
0x14004d007  mov     rax, [rbp+57h+var_98]
0x14004d00b  jmp     loc_14004CE28
0x14004d010  xor     r8d, r8d
0x14004d013  jmp     loc_14004CEF6
0x14004d018  bt      eax, 0Bh
0x14004d01c  jb      loc_14004CDC4
0x14004d022  xor     eax, eax
0x14004d024  lea     rcx, [rbp+57h+Event]; Event
0x14004d028  xorps   xmm0, xmm0
0x14004d02b  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14004d02f  xor     r8d, r8d; State
0x14004d032  mov     [rbp+57h+var_98], rax
0x14004d036  mov     edx, ebx; Type
0x14004d038  mov     [rbp+57h+arg_18], eax
0x14004d03b  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14004d03f  mov     dword ptr [rbp+57h+arg_10], eax
0x14004d042  call    cs:__imp_KeInitializeEvent
0x14004d049  nop     dword ptr [rax+rax+00h]
0x14004d04e  mov     rax, [rbp+57h+CallbackData]
0x14004d052  lea     rcx, [rbp+57h+Event]
  ... truncated ...
```
