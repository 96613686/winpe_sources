# HsmFltPreCLEANUP

- ea: `0x14004caa0`
- end: `0x14004d605`
- name: `HsmFltPreCLEANUP`
- size: `2917`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
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
- `0x14001b210`
- `0x14001e220`
- `0x14001e280`
- `0x140036178`
- `0x14004c5c0`
- `0x14004caa0`
- `0x14004d60c`
- `0x14004d6a0`
- `0x14004d6fc`
- `0x1400520d0`
- `0x1400547cc`
- `0x140054a04`
- `0x140058cbc`
- `0x140058f70`
- `0x14006f16c`
- `0x14007444c`
- `0x14007634c`

## import_xrefs

- `ntoskrnl!FsRtlFastUnlockAll` at `0x14004ce18`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14004ce18`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cc97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cc97`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cc8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cc8b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cc67`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cc67`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cc55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cc55`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004d3aa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004d3aa`
- `ntoskrnl!KeInitializeEvent` at `0x14004cf52`
- `ntoskrnl!KeInitializeEvent` at `0x14004cf52`
- `ntoskrnl!KeSetEvent` at `0x14004cef0`
- `ntoskrnl!KeSetEvent` at `0x14004d5a2`
- `ntoskrnl!KeSetEvent` at `0x14004cef0`
- `ntoskrnl!KeSetEvent` at `0x14004d5a2`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14004d58a`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14004d58a`
- `FLTMGR!FltFlushBuffers2` at `0x14004d4e8`
- `FLTMGR!FltFlushBuffers2` at `0x14004d4e8`
- `FLTMGR!FltSetInformationFile` at `0x14004d07f`
- `FLTMGR!FltSetInformationFile` at `0x14004d07f`
- `FLTMGR!FltGetFileContext` at `0x14004cb75`
- `FLTMGR!FltGetFileContext` at `0x14004cb75`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004cadd`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004cadd`
- `FLTMGR!FltReferenceContext` at `0x14004cc1d`
- `FLTMGR!FltReferenceContext` at `0x14004cc1d`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004cfa1`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004cfa1`
- `FLTMGR!FltDeleteContext` at `0x14004d126`
- `FLTMGR!FltDeleteContext` at `0x14004d5d0`
- `FLTMGR!FltDeleteContext` at `0x14004d126`
- `FLTMGR!FltDeleteContext` at `0x14004d5d0`
- `FLTMGR!FltCancelIo` at `0x14004d389`
- `FLTMGR!FltCancelIo` at `0x14004d389`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cb1b`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cbec`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cdf7`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cb1b`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cbec`
- `FLTMGR!FltGetRequestorProcess` at `0x14004cdf7`
- `FLTMGR!FltReleasePushLockEx` at `0x14004d5bc`
- `FLTMGR!FltReleasePushLockEx` at `0x14004d5bc`
- `FLTMGR!FltReleaseContext` at `0x14004cb3b`
- `FLTMGR!FltReleaseContext` at `0x14004cba4`
- `FLTMGR!FltReleaseContext` at `0x14004cc2e`
- `FLTMGR!FltReleaseContext` at `0x14004d5df`
- `FLTMGR!FltReleaseContext` at `0x14004cb3b`
- `FLTMGR!FltReleaseContext` at `0x14004cba4`
- `FLTMGR!FltReleaseContext` at `0x14004cc2e`
- `FLTMGR!FltReleaseContext` at `0x14004d5df`

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
  unsigned int v52; // eax
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
    4u,
    CallbackData,
    8 * (*(_DWORD *)(v15 + 28) & 2),
    0,
    (void (__fastcall *)(__int64, _QWORD, _QWORD))HsmiDeleteOnCloseNotificationCallback,
    (__int64)CallbackData);
  LODWORD(FileInformation) = FltCancellableWaitForSingleObject(&Event, 0, CallbackData);
  HsmDbgBreakOnStatus((unsigned int)FileInformation);
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
      HsmDbgBreakOnStatus((unsigned int)FileInformation);
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
            HsmDbgBreakOnStatus((unsigned int)FileInformation);
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
  HsmDbgBreakOnStatus((unsigned int)v51);
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
0x14004caa0  mov     [rsp-8+CallbackData], rcx
0x14004caa5  push    rbp
0x14004caa6  push    rbx
0x14004caa7  push    rsi
0x14004caa8  push    rdi
0x14004caa9  push    r12
0x14004caab  push    r14
0x14004caad  push    r15
0x14004caaf  lea     rbp, [rsp-27h]
0x14004cab4  sub     rsp, 0E0h
0x14004cabb  xor     r12d, r12d
0x14004cabe  mov     r15, r8
0x14004cac1  mov     [r8], r12
0x14004cac4  mov     r14, rdx
0x14004cac7  mov     rbx, [rdx+18h]
0x14004cacb  lea     r8, [rbp+57h+Context]; Context
0x14004cacf  mov     rdx, [rdx+20h]; FileObject
0x14004cad3  mov     rsi, rcx
0x14004cad6  mov     rcx, rbx; Instance
0x14004cad9  mov     [rbp+57h+Context], r12
0x14004cadd  call    cs:__imp_FltGetStreamHandleContext
0x14004cae4  nop     dword ptr [rax+rax+00h]
0x14004cae9  mov     rdi, [rbp+57h+Context]
0x14004caed  test    rdi, rdi
0x14004caf0  jz      short loc_14004CB4E
0x14004caf2  mov     rcx, [rdi+10h]
0x14004caf6  mov     eax, [rcx+1Ch]
0x14004caf9  test    al, 1
0x14004cafb  jz      loc_14004D11A
0x14004cb01  mov     rax, [rcx+10h]
0x14004cb05  mov     rcx, [rax+10h]
0x14004cb09  cmp     [rcx+20h], rbx
0x14004cb0d  jnz     loc_14004D29B
0x14004cb13  test    rsi, rsi
0x14004cb16  jz      short loc_14004CB4E
0x14004cb18  mov     rcx, rsi; CallbackData
0x14004cb1b  call    cs:__imp_FltGetRequestorProcess
0x14004cb22  nop     dword ptr [rax+rax+00h]
0x14004cb27  mov     rcx, rax
0x14004cb2a  call    HsmOsIsPassThroughModeEnabled
0x14004cb2f  test    al, al
0x14004cb31  jz      loc_14004D2A3
0x14004cb37  mov     rcx, [rbp+57h+Context]; Context
0x14004cb3b  call    cs:__imp_FltReleaseContext
0x14004cb42  nop     dword ptr [rax+rax+00h]
0x14004cb47  mov     rdi, r12
0x14004cb4a  mov     [rbp+57h+Context], r12
0x14004cb4e  mov     [rsp+110h+var_38], r13
0x14004cb56  test    rdi, rdi
0x14004cb59  jnz     loc_14004CC0E
0x14004cb5f  mov     rbx, [r14+18h]
0x14004cb63  lea     r8, [rbp+57h+var_A0]; Context
0x14004cb67  mov     rdx, [r14+20h]; FileObject
0x14004cb6b  mov     rcx, rbx; Instance
0x14004cb6e  mov     r13, r12
0x14004cb71  mov     [rbp+57h+var_A0], r12
0x14004cb75  call    cs:__imp_FltGetFileContext
0x14004cb7c  nop     dword ptr [rax+rax+00h]
0x14004cb81  mov     rsi, [rbp+57h+var_A0]
0x14004cb85  test    rsi, rsi
0x14004cb88  jnz     short loc_14004CBD6
0x14004cb8a  mov     ebx, 1
0x14004cb8f  test    rdi, rdi
0x14004cb92  jnz     loc_14004CCA8
0x14004cb98  mov     r12, [rbp+57h+CallbackData]
0x14004cb9c  test    rsi, rsi
0x14004cb9f  jz      short loc_14004CBB0
0x14004cba1  mov     rcx, rsi; Context
0x14004cba4  call    cs:__imp_FltReleaseContext
0x14004cbab  nop     dword ptr [rax+rax+00h]
0x14004cbb0  test    rdi, rdi
0x14004cbb3  jnz     loc_14004D5CD
0x14004cbb9  mov     r13, [rsp+110h+var_38]
0x14004cbc1  mov     eax, ebx
0x14004cbc3  add     rsp, 0E0h
0x14004cbca  pop     r15
0x14004cbcc  pop     r14
0x14004cbce  pop     r12
0x14004cbd0  pop     rdi
0x14004cbd1  pop     rsi
0x14004cbd2  pop     rbx
0x14004cbd3  pop     rbp
0x14004cbd4  retn
0x14004cbd6  mov     rax, [rsi+10h]
0x14004cbda  cmp     [rax+20h], rbx
0x14004cbde  jnz     short loc_14004CC2B
0x14004cbe0  mov     rax, [rbp+57h+CallbackData]
0x14004cbe4  test    rax, rax
0x14004cbe7  jz      short loc_14004CC40
0x14004cbe9  mov     rcx, rax; CallbackData
0x14004cbec  call    cs:__imp_FltGetRequestorProcess
0x14004cbf3  nop     dword ptr [rax+rax+00h]
0x14004cbf8  mov     rcx, rax
0x14004cbfb  call    HsmOsIsPassThroughModeEnabled
0x14004cc00  test    al, al
0x14004cc02  jnz     loc_14004D2AC
0x14004cc08  mov     rsi, [rbp+57h+var_A0]
0x14004cc0c  jmp     short loc_14004CC40
0x14004cc0e  mov     r13, [rdi+10h]
0x14004cc12  mov     rsi, [r13+10h]
0x14004cc16  mov     rcx, rsi; Context
0x14004cc19  mov     r12, [rsi+10h]
0x14004cc1d  call    cs:__imp_FltReferenceContext
0x14004cc24  nop     dword ptr [rax+rax+00h]
0x14004cc29  jmp     short loc_14004CC40
0x14004cc2b  mov     rcx, rsi; Context
0x14004cc2e  call    cs:__imp_FltReleaseContext
0x14004cc35  nop     dword ptr [rax+rax+00h]
0x14004cc3a  xor     esi, esi
0x14004cc3c  mov     [rbp+57h+var_A0], rsi
0x14004cc40  test    rsi, rsi
0x14004cc43  jz      loc_14004CB8A
0x14004cc49  mov     rbx, [r14+20h]
0x14004cc4d  mov     [rbp+57h+var_68], rbx
0x14004cc51  mov     [rbp+57h+var_78], rbx
0x14004cc55  call    cs:__imp_KeEnterCriticalRegion
0x14004cc5c  nop     dword ptr [rax+rax+00h]
0x14004cc61  lea     rcx, [rsi+78h]; Resource
0x14004cc65  mov     dl, 1; Wait
0x14004cc67  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004cc6e  nop     dword ptr [rax+rax+00h]
0x14004cc73  mov     rax, [rsi+0E0h]
0x14004cc7a  mov     [rbp+57h+var_98], rax
0x14004cc7e  test    rax, rax
0x14004cc81  jnz     loc_14004CD1C
0x14004cc87  lea     rcx, [rsi+78h]; Resource
0x14004cc8b  call    cs:__imp_ExReleaseResourceLite
0x14004cc92  nop     dword ptr [rax+rax+00h]
0x14004cc97  call    cs:__imp_KeLeaveCriticalRegion
0x14004cc9e  nop     dword ptr [rax+rax+00h]
0x14004cca3  jmp     loc_14004CB8A
0x14004cca8  mov     rcx, [rbp+57h+CallbackData]
0x14004ccac  mov     r9, rdi
0x14004ccaf  movzx   r8d, bl
0x14004ccb3  mov     [rbp+57h+var_B0], 0
0x14004ccbb  xor     edx, edx
0x14004ccbd  mov     qword ptr [rsp+110h+FileInformationClass], r13
0x14004ccc2  call    HsmpTracePreCallbackEnter
0x14004ccc7  mov     eax, [rdi+28h]
0x14004ccca  bt      eax, 0Ch
0x14004ccce  jb      loc_14004CF28
0x14004ccd4  mov     rcx, rdi
0x14004ccd7  call    HsmpRecallTerminateProgressiveHydration
0x14004ccdc  mov     rax, [r13+0A0h]
0x14004cce3  test    rax, rax
0x14004cce6  jnz     loc_14004CDDC
0x14004ccec  movzx   eax, byte ptr [rdi+2Dh]
0x14004ccf0  test    al, al
0x14004ccf2  jnz     loc_14004D4DA
0x14004ccf8  mov     eax, [rdi+28h]
0x14004ccfb  test    al, 10h
0x14004ccfd  jnz     loc_14004D56B
0x14004cd03  mov     [r15], rdi
0x14004cd06  mov     rcx, [rbp+57h+var_B0]
0x14004cd0a  xor     ebx, ebx
0x14004cd0c  xor     edi, edi
0x14004cd0e  test    rcx, rcx
0x14004cd11  jz      loc_14004CB98
0x14004cd17  jmp     loc_14004D233
0x14004cd1c  mov     rdx, [rax+60h]
0x14004cd20  lea     rcx, [rax+60h]
0x14004cd24  mov     [rbp+57h+arg_10], rcx
0x14004cd28  mov     r8, rcx
0x14004cd2b  mov     [rbp+57h+FileInformation], rcx
0x14004cd2f  cmp     rdx, rcx
0x14004cd32  jnz     loc_14004CEB3
0x14004cd38  mov     r10, [rax+50h]
0x14004cd3c  lea     r11, [rax+50h]
0x14004cd40  mov     [rbp+57h+var_80], r11
0x14004cd44  mov     r9, r11
0x14004cd47  mov     [rbp+57h+var_88], r11
0x14004cd4b  mov     [rbp+57h+var_70], r10
0x14004cd4f  cmp     r10, r11
0x14004cd52  jz      loc_14004CC87
0x14004cd58  mov     byte ptr [rbp+57h+FileInformation], 0
0x14004cd5c  cmp     dword ptr [r10+20h], 0
0x14004cd61  lea     rax, [r10+18h]
0x14004cd65  mov     [rbp+57h+var_90], rax
0x14004cd69  jnz     loc_14004D2B5
0x14004cd6f  cmp     [rax], rbx
0x14004cd72  jb      short loc_14004CDAF
0x14004cd74  ja      short loc_14004CDAF
0x14004cd76  mov     byte ptr [rbp+57h+FileInformation], 1
0x14004cd7a  mov     rax, [r9]
0x14004cd7d  cmp     [rax+8], r9
0x14004cd81  jnz     loc_14004D113
0x14004cd87  mov     rcx, [rax]
0x14004cd8a  cmp     [rcx+8], rax
0x14004cd8e  jnz     loc_14004D113
0x14004cd94  mov     [r9], rcx
0x14004cd97  mov     [rcx+8], r9
0x14004cd9b  mov     rcx, r10; P
0x14004cd9e  call    HsmiFreePropertyLock
0x14004cda3  mov     r9, [rbp+57h+var_88]
0x14004cda7  mov     r9, [r9+8]
0x14004cdab  mov     r11, [rbp+57h+var_80]
0x14004cdaf  movzx   ecx, byte ptr [rbp+57h+FileInformation]
0x14004cdb3  mov     r9, [r9]
0x14004cdb6  mov     [rbp+57h+var_88], r9
0x14004cdba  mov     r10, [r9]
0x14004cdbd  mov     [rbp+57h+var_70], r10
0x14004cdc1  cmp     r10, r11
0x14004cdc4  jnz     short loc_14004CD5C
0x14004cdc6  test    cl, cl
0x14004cdc8  jz      loc_14004CC87
0x14004cdce  mov     rcx, [rbp+57h+var_98]
0x14004cdd2  call    HsmiProcessPropertyLockRequestList
0x14004cdd7  jmp     loc_14004CC87
0x14004cddc  cmp     qword ptr [rax+20h], 0
0x14004cde1  jz      loc_14004CCEC
0x14004cde7  mov     rax, [rbp+57h+CallbackData]
0x14004cdeb  test    rax, rax
0x14004cdee  jz      loc_14004CF20
0x14004cdf4  mov     rcx, rax; CallbackData
0x14004cdf7  call    cs:__imp_FltGetRequestorProcess
0x14004cdfe  nop     dword ptr [rax+rax+00h]
0x14004ce03  mov     r8, rax
0x14004ce06  mov     rcx, r13
0x14004ce09  call    HsmpGetFileLock
0x14004ce0e  mov     rdx, [r14+20h]; FileObject
0x14004ce12  mov     rcx, rax; FileLock
0x14004ce15  xor     r9d, r9d; Context
0x14004ce18  call    cs:__imp_FsRtlFastUnlockAll
0x14004ce1f  nop     dword ptr [rax+rax+00h]
0x14004ce24  mov     r8d, eax
0x14004ce27  mov     eax, 80000000h
0x14004ce2c  lea     ecx, [r8+rax]
0x14004ce30  test    eax, ecx
0x14004ce32  jnz     loc_14004CCEC
0x14004ce38  cmp     r8d, 0C000007Eh
0x14004ce3f  jz      loc_14004CCEC
0x14004ce45  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ce4c  lea     rax, WPP_GLOBAL_Control
0x14004ce53  cmp     rcx, rax
0x14004ce56  jz      loc_14004CCEC
0x14004ce5c  mov     eax, [rcx+2Ch]
0x14004ce5f  test    bl, al
0x14004ce61  jz      loc_14004CCEC
0x14004ce67  cmp     byte ptr [rcx+29h], 2
0x14004ce6b  jb      loc_14004CCEC
0x14004ce71  mov     rax, [rbp+57h+CallbackData]
0x14004ce75  mov     edx, 0Fh
0x14004ce7a  mov     rcx, [rcx+18h]
0x14004ce7e  mov     r9, r12
0x14004ce81  mov     dword ptr [rsp+110h+var_D0], r8d
0x14004ce86  lea     r8, WPP_e3630ce7b3b33dbc51129e886b811c0d_Traceguids
0x14004ce8d  mov     [rsp+110h+var_D8], rax
0x14004ce92  mov     rax, [rsi+20h]
0x14004ce96  mov     [rsp+110h+var_E0], rax
0x14004ce9b  mov     rax, [r14+20h]
0x14004ce9f  mov     [rsp+110h+var_E8], rax
0x14004cea4  mov     qword ptr [rsp+110h+FileInformationClass], r13
0x14004cea9  call    WPP_SF_qiqiid
0x14004ceae  jmp     loc_14004CCEC
0x14004ceb3  cmp     [rdx-40h], rbx
0x14004ceb7  ja      short loc_14004CF08
0x14004ceb9  jb      short loc_14004CF08
0x14004cebb  cmp     [rdx+8], r8
0x14004cebf  jnz     loc_14004D113
0x14004cec5  mov     rax, [rdx]
0x14004cec8  cmp     [rax+8], rdx
0x14004cecc  jnz     loc_14004D113
0x14004ced2  mov     [r8], rax
0x14004ced5  lea     rcx, [rdx-28h]; Event
0x14004ced9  mov     [rax+8], r8
0x14004cedd  xor     r8d, r8d; Wait
0x14004cee0  mov     [rdx+8], rdx
0x14004cee4  mov     [rdx], rdx
0x14004cee7  mov     dword ptr [rdx-10h], 0C0000008h
0x14004ceee  xor     edx, edx; Increment
0x14004cef0  call    cs:__imp_KeSetEvent
0x14004cef7  nop     dword ptr [rax+rax+00h]
0x14004cefc  mov     r8, [rbp+57h+FileInformation]
0x14004cf00  mov     rcx, [rbp+57h+arg_10]
0x14004cf04  mov     r8, [r8+8]
0x14004cf08  mov     r8, [r8]
0x14004cf0b  mov     [rbp+57h+FileInformation], r8
0x14004cf0f  mov     rdx, [r8]
0x14004cf12  cmp     rdx, rcx
0x14004cf15  jnz     short loc_14004CEB3
0x14004cf17  mov     rax, [rbp+57h+var_98]
0x14004cf1b  jmp     loc_14004CD38
0x14004cf20  xor     r8d, r8d
0x14004cf23  jmp     loc_14004CE06
0x14004cf28  bt      eax, 0Bh
0x14004cf2c  jb      loc_14004CCD4
0x14004cf32  xor     eax, eax
0x14004cf34  lea     rcx, [rbp+57h+Event]; Event
0x14004cf38  xorps   xmm0, xmm0
0x14004cf3b  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14004cf3f  xor     r8d, r8d; State
0x14004cf42  mov     [rbp+57h+var_98], rax
0x14004cf46  mov     edx, ebx; Type
0x14004cf48  mov     [rbp+57h+arg_18], eax
0x14004cf4b  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14004cf4f  mov     dword ptr [rbp+57h+arg_10], eax
0x14004cf52  call    cs:__imp_KeInitializeEvent
0x14004cf59  nop     dword ptr [rax+rax+00h]
0x14004cf5e  mov     rax, [rbp+57h+CallbackData]
0x14004cf62  lea     rcx, [rbp+57h+Event]
  ... truncated ...
```
