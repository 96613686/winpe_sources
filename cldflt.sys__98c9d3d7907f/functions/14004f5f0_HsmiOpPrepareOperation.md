# HsmiOpPrepareOperation

- ea: `0x14004f5f0`
- end: `0x140050275`
- name: `HsmiOpPrepareOperation`
- size: `3205`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, __int64, unsigned __int8 IsDirectory, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004ded0`

## callees

- `0x140003c50`
- `0x1400090dc`
- `0x14000abb8`
- `0x14000ac28`
- `0x140013104`
- `0x14004f5f0`
- `0x140050280`
- `0x140050ca0`
- `0x1400516f0`
- `0x14005191c`
- `0x140058cbc`
- `0x140058e90`
- `0x140058f70`
- `0x14005f550`
- `0x14006f138`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14004fe7d`
- `ntoskrnl!KeClearEvent` at `0x14004fe7d`
- `ntoskrnl!KeInitializeEvent` at `0x14004fe3e`
- `ntoskrnl!KeInitializeEvent` at `0x14004fe3e`
- `ntoskrnl!KeSetEvent` at `0x14004fef8`
- `ntoskrnl!KeSetEvent` at `0x14004fef8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f77e`
- `FLTMGR!FltIsDirectory` at `0x14004f66b`
- `FLTMGR!FltIsDirectory` at `0x14004f66b`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fac4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fead`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004ff2d`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fac4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fead`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004ff2d`
- `FLTMGR!FltGetRequestorProcess` at `0x14004fa0c`
- `FLTMGR!FltGetRequestorProcess` at `0x14004fa0c`
- `FLTMGR!FltReleasePushLockEx` at `0x14004fe96`
- `FLTMGR!FltReleasePushLockEx` at `0x14004ff0a`
- `FLTMGR!FltReleasePushLockEx` at `0x14004fe96`
- `FLTMGR!FltReleasePushLockEx` at `0x14004ff0a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fe6a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fed6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fe6a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fed6`

## pseudocode

```c
__int64 HsmiOpPrepareOperation(
        PFLT_CALLBACK_DATA CallbackData,
        int a2,
        char a3,
        struct _KEVENT *a4,
        __int64 a5,
        __int64 a6,
        ...)
{
  __int64 *v6; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FILE_OBJECT *TargetFileObject; // r14
  struct _FLT_INSTANCE *TargetInstance; // rdx
  __int64 v11; // rdi
  _DWORD *v12; // r12
  __int64 v13; // r13
  __int64 SyncRootFileId; // rbx
  __int16 v15; // di
  PDEVICE_OBJECT v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r10d
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r10
  __int64 v25; // rcx
  PDEVICE_OBJECT v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // r9d
  __int64 v30; // rax
  unsigned int RequestorProcess; // eax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r13
  int v35; // edx
  __int64 v36; // rdx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  __int64 StreamSize; // rax
  int i; // eax
  __int64 v42; // rdi
  __int64 v43; // rax
  __int64 v44; // [rsp+28h] [rbp-A1h]
  __int64 v45; // [rsp+30h] [rbp-99h]
  int v46; // [rsp+38h] [rbp-91h]
  __int64 v47; // [rsp+58h] [rbp-71h]
  int v48; // [rsp+60h] [rbp-69h] BYREF
  int v49; // [rsp+64h] [rbp-65h] BYREF
  __int64 v50; // [rsp+68h] [rbp-61h] BYREF
  int v51; // [rsp+70h] [rbp-59h]
  union _LARGE_INTEGER Timeout; // [rsp+78h] [rbp-51h] BYREF
  union _LARGE_INTEGER v53; // [rsp+80h] [rbp-49h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-41h] BYREF
  struct _KEVENT Event; // [rsp+98h] [rbp-31h] BYREF
  int v56; // [rsp+108h] [rbp+3Fh]
  __int64 *IsDirectory; // [rsp+138h] [rbp+6Fh] BYREF
  va_list IsDirectorya; // [rsp+138h] [rbp+6Fh]
  __int64 v62; // [rsp+140h] [rbp+77h]
  _DWORD *v63; // [rsp+148h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+148h] [rbp+7Fh]
  va_list va2; // [rsp+150h] [rbp+87h] BYREF

  va_start(va2, a6);
  va_start(va1, a6);
  va_start(IsDirectorya, a6);
  IsDirectory = va_arg(va1, __int64 *);
  v62 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v63 = va_arg(va2, _DWORD *);
  v6 = IsDirectory;
  Iopb = CallbackData->Iopb;
  TargetFileObject = Iopb->TargetFileObject;
  TargetInstance = Iopb->TargetInstance;
  if ( *IsDirectory )
    v11 = *(_QWORD *)(*IsDirectory + 32);
  else
    v11 = 0;
  v12 = v63;
  v13 = 0;
  v47 = v11;
  v50 = 0;
  LOBYTE(IsDirectory) = 0;
  *v63 = 0;
  *(_OWORD *)P = 0;
  SyncRootFileId = (unsigned int)FltIsDirectory(TargetFileObject, TargetInstance, (PBOOLEAN)IsDirectorya);
  HsmDbgBreakOnStatus(SyncRootFileId);
  if ( (int)SyncRootFileId < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        CallbackData,
        a6,
        v11,
        a5,
        SyncRootFileId);
    }
    goto LABEL_20;
  }
  v15 = v62;
  if ( (v62 & 1) != 0 && CallbackData->RequestorMode )
  {
    LODWORD(SyncRootFileId) = -1073688808;
    HsmDbgBreakOnStatus(3221278488LL);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v18 = a6;
      if ( a6 )
      {
        StreamSize = HsmpGetStreamSize(a6);
        v20 = *(_DWORD *)(v18 + 28);
        v21 = StreamSize;
      }
      else
      {
        v21 = 0;
        v20 = 0;
      }
      v22 = 11;
LABEL_30:
      WPP_SF_qqiLiqd(v17->AttachedDevice, v22, v17, CallbackData, v18, v47, v20, v21, a5, SyncRootFileId);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  if ( (v62 & 0x80u) == 0LL
    || (SyncRootFileId = (unsigned int)HsmpAccessCheck((__int64)a4, TargetFileObject, 2u),
        HsmDbgBreakOnStatus(SyncRootFileId),
        (int)SyncRootFileId >= 0) )
  {
    if ( (v15 & 0x40) != 0 )
    {
      SyncRootFileId = (unsigned int)HsmpAccessCheck((__int64)a4, TargetFileObject, 1u);
      HsmDbgBreakOnStatus(SyncRootFileId);
      if ( (int)SyncRootFileId < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v18 = a6;
          if ( a6 )
          {
            v30 = HsmpGetStreamSize(a6);
            v20 = *(_DWORD *)(v18 + 28);
            v21 = v30;
          }
          else
          {
            v21 = 0;
            v20 = 0;
          }
          v22 = 13;
          goto LABEL_30;
        }
        goto LABEL_20;
      }
    }
    if ( (v15 & 0x10) == 0 )
    {
LABEL_9:
      if ( (v15 & 2) != 0 && !a5 )
      {
        LODWORD(SyncRootFileId) = -1073688825;
        HsmDbgBreakOnStatus(3221278471LL);
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v27 = a6;
          if ( a6 )
          {
            v28 = HsmpGetStreamSize(a6);
            v29 = *(_DWORD *)(v27 + 28);
          }
          else
          {
            v28 = 0;
            v29 = 0;
          }
          WPP_SF_qqiLiqd(v26->AttachedDevice, 15, v26, CallbackData, v27, v47, v29, v28, 0, -1073688825);
        }
        goto LABEL_20;
      }
      if ( (v15 & 4) != 0 && a6 && (*(_DWORD *)(a6 + 28) & 4) != 0 )
      {
        SyncRootFileId = (unsigned int)HsmpRpCheckState();
        HsmDbgBreakOnStatus(SyncRootFileId);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v23 = HsmpGetStreamSize(a6);
          WPP_SF_qqiLiqd(
            *(_QWORD *)(v24 + 24),
            16,
            a5,
            CallbackData,
            v25,
            v47,
            *(_DWORD *)(v25 + 28),
            v23,
            a5,
            SyncRootFileId);
        }
        goto LABEL_20;
      }
      if ( (v15 & 8) != 0 && !(_BYTE)IsDirectory )
      {
        LODWORD(SyncRootFileId) = -1073688821;
        HsmDbgBreakOnStatus(3221278475LL);
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_20;
        }
        v38 = 17;
        goto LABEL_105;
      }
      if ( (v15 & 0x20) != 0 && (_BYTE)IsDirectory )
      {
        LODWORD(SyncRootFileId) = -1073688821;
        HsmDbgBreakOnStatus(3221278475LL);
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_20;
        }
        v38 = 18;
        goto LABEL_105;
      }
      if ( (a3 & 0x10) != 0 )
        goto LABEL_16;
      v51 = v15 & 0x400;
      if ( (v15 & 0x200) == 0 && (v15 & 0x400) == 0 )
        goto LABEL_16;
      v33 = *v6;
      v49 = 0;
      LODWORD(v63) = 0;
      v48 = 0;
      if ( !v33 )
      {
        v53.QuadPart = -150000;
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, NotificationEvent, 0);
        for ( i = 0; ; i = v56 + 1 )
        {
          v56 = i;
          if ( i >= 5 )
            break;
          Timeout.QuadPart = 0;
          FltAcquirePushLockExclusiveEx(&a4[4].Header.WaitListHead.Blink, 0);
          KeClearEvent(a4 + 6);
          ++a4[7].Header.SignalState;
          FltReleasePushLockEx(&a4[4].Header.WaitListHead.Blink, 0);
          LODWORD(SyncRootFileId) = FltCancellableWaitForSingleObject(&a4[5], &Timeout, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
          if ( !(_DWORD)SyncRootFileId )
          {
            *v12 |= 1u;
            goto LABEL_67;
          }
          FltAcquirePushLockExclusiveEx(&a4[4].Header.WaitListHead.Blink, 0);
          if ( a4[7].Header.SignalState-- == 1 )
            KeSetEvent(a4 + 6, 0, 0);
          FltReleasePushLockEx(&a4[4].Header.WaitListHead.Blink, 0);
          if ( (_DWORD)SyncRootFileId != 258 )
            goto LABEL_152;
          LODWORD(SyncRootFileId) = FltCancellableWaitForSingleObject(&Event, &v53, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
          if ( (_DWORD)SyncRootFileId != 258 )
            goto LABEL_152;
        }
        if ( (_DWORD)SyncRootFileId == 258 )
        {
          LODWORD(SyncRootFileId) = -1073741267;
          HsmDbgBreakOnStatus(3221226029LL);
          goto LABEL_153;
        }
LABEL_152:
        if ( (int)SyncRootFileId >= 0 )
          goto LABEL_67;
LABEL_153:
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_20;
        }
        v38 = 20;
        goto LABEL_105;
      }
      LODWORD(SyncRootFileId) = FltCancellableWaitForSingleObject((PVOID)(v33 + 96), 0, CallbackData);
      HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
      if ( (int)SyncRootFileId < 0 )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_20;
        }
        v38 = 19;
      }
      else
      {
        *v12 |= 2u;
LABEL_67:
        if ( (_BYTE)IsDirectory || !v51 )
        {
          v34 = a6;
          SyncRootFileId = (unsigned int)HsmpCldGetSyncRootFileIdEx(
                                           (_DWORD)a4,
                                           a6,
                                           (_DWORD)TargetFileObject,
                                           (unsigned int)&v50,
                                           0,
                                           0);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( (int)SyncRootFileId < 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_20;
            }
            v38 = 21;
            goto LABEL_111;
          }
          v35 = (int)v63;
          goto LABEL_77;
        }
        LODWORD(SyncRootFileId) = HsmiCldGetSyncRootFileIdByFileObject(a4, TargetFileObject, &v50, &v49, (_DWORD **)va1);
        HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
        if ( (int)SyncRootFileId < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v42 = a6;
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
            a4,
            a6,
            TargetFileObject,
            SyncRootFileId);
          HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
          goto LABEL_158;
        }
        HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
        if ( (int)SyncRootFileId < 0 )
        {
          v42 = a6;
LABEL_158:
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_20;
          }
          v38 = 22;
          v46 = SyncRootFileId;
          v45 = v47;
          v44 = v42;
LABEL_112:
          WPP_SF_qqqd(
            v37->AttachedDevice,
            v38,
            WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            CallbackData,
            v44,
            v45,
            v46);
          goto LABEL_20;
        }
        SyncRootFileId = (unsigned int)HsmiQueryFullFilePath(
                                         a4[1].Header.WaitListHead.Flink,
                                         v36,
                                         TargetFileObject,
                                         258,
                                         P);
        HsmDbgBreakOnStatus(SyncRootFileId);
        if ( (int)SyncRootFileId < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_20;
          }
          v38 = 23;
        }
        else
        {
          SyncRootFileId = (unsigned int)HsmpCldGetSyncPolicyByPath(a4, P, &v48);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( (int)SyncRootFileId < 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_20;
            }
            v38 = 24;
          }
          else
          {
            v35 = (int)v63;
            if ( (v48 & 0x200000) != 0 || (unsigned int)((_DWORD)v63 + v49) <= 1 )
            {
              v34 = a6;
LABEL_77:
              if ( (a3 & 2) != 0 && v35 )
              {
                LODWORD(SyncRootFileId) = -1073688807;
                HsmDbgBreakOnStatus(3221278489LL);
                v37 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_20;
                }
                v38 = 26;
                goto LABEL_111;
              }
              v13 = v50;
LABEL_16:
              if ( (unsigned int)(a2 + 0x10000000) <= 0xFFFF && !(unsigned __int8)HsmOsIsTestSigningEnabled() )
              {
                LODWORD(SyncRootFileId) = -1073688808;
                HsmDbgBreakOnStatus(3221278488LL);
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v18 = a6;
                  if ( a6 )
                  {
                    v43 = HsmpGetStreamSize(a6);
                    v20 = *(_DWORD *)(v18 + 28);
                    v21 = v43;
                  }
                  else
                  {
                    v21 = 0;
                    v20 = 0;
                  }
                  v22 = 27;
                  goto LABEL_30;
                }
                goto LABEL_20;
              }
              if ( (v15 & 0x100) == 0 || *v6 )
              {
LABEL_19:
                LODWORD(SyncRootFileId) = 0;
                goto LABEL_20;
              }
              if ( v13 )
              {
LABEL_80:
                LODWORD(SyncRootFileId) = HsmpCtxGetOrCreateFileContext(CallbackData, a4, TargetFileObject, v13, v6);
                HsmDbgBreakOnStatus((unsigned int)SyncRootFileId);
                if ( (int)SyncRootFileId < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qqqd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      29,
                      WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
                      a4,
                      TargetFileObject,
                      v47,
                      SyncRootFileId);
                  }
                  goto LABEL_20;
                }
                *v12 |= 4u;
                goto LABEL_19;
              }
              v34 = a6;
              SyncRootFileId = (unsigned int)HsmpCldGetSyncRootFileIdEx(
                                               (_DWORD)a4,
                                               a6,
                                               (_DWORD)TargetFileObject,
                                               (unsigned int)&v50,
                                               0,
                                               0);
              HsmDbgBreakOnStatus(SyncRootFileId);
              if ( (int)SyncRootFileId >= 0 )
              {
                v13 = v50;
                goto LABEL_80;
              }
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
              {
                goto LABEL_20;
              }
              v38 = 28;
LABEL_111:
              v46 = SyncRootFileId;
              v45 = v47;
              v44 = v34;
              goto LABEL_112;
            }
            LODWORD(SyncRootFileId) = -1073688807;
            HsmDbgBreakOnStatus(3221278489LL);
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_20;
            }
            v38 = 25;
          }
        }
      }
LABEL_105:
      v46 = SyncRootFileId;
      v45 = v47;
      v44 = a6;
      goto LABEL_112;
    }
    LOBYTE(v63) = 0;
    RequestorProcess = (unsigned int)FltGetRequestorProcess(CallbackData);
    SyncRootFileId = (unsigned int)HsmpCldCheckSyncProviderAccess(
                                     (_DWORD)a4,
                                     a6,
                                     (_DWORD)TargetFileObject,
                                     RequestorProcess,
                                     (__int64)va1);
    HsmDbgBreakOnStatus(SyncRootFileId);
    if ( (int)SyncRootFileId >= 0 )
    {
      if ( (_BYTE)v63 )
        goto LABEL_9;
      LODWORD(SyncRootFileId) = -1073688808;
      HsmDbgBreakOnStatus(3221278488LL);
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v18 = a6;
      if ( a6 )
      {
        v32 = HsmpGetStreamSize(a6);
        v20 = *(_DWORD *)(v18 + 28);
        v21 = v32;
      }
      else
      {
        v21 = 0;
        v20 = 0;
      }
      v22 = 14;
      goto LABEL_30;
    }
    goto LABEL_20;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v18 = a6;
    if ( a6 )
    {
      v19 = HsmpGetStreamSize(a6);
      v20 = *(_DWORD *)(v18 + 28);
      v21 = v19;
    }
    else
    {
      v21 = 0;
      v20 = 0;
    }
    v22 = 12;
    goto LABEL_30;
  }
LABEL_20:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  return (unsigned int)SyncRootFileId;
}

```

## disassembly

```asm
0x14004f5f0  mov     rax, rsp
0x14004f5f3  mov     [rax+20h], r9
0x14004f5f7  mov     [rax+18h], r8d
0x14004f5fb  mov     [rax+10h], edx
0x14004f5fe  push    rbp
0x14004f5ff  push    rbx
0x14004f600  lea     rbp, [rax-37h]
0x14004f604  sub     rsp, 0E8h
0x14004f60b  mov     [rax-18h], rsi
0x14004f60f  mov     rsi, [rbp+2Fh+IsDirectory]
0x14004f613  mov     [rax-20h], rdi
0x14004f617  mov     [rax-28h], r12
0x14004f61b  mov     [rax-30h], r13
0x14004f61f  mov     [rax-38h], r14
0x14004f623  mov     [rax-40h], r15
0x14004f627  mov     r15, rcx
0x14004f62a  mov     rax, [rcx+10h]
0x14004f62e  mov     r14, [rax+8]
0x14004f632  mov     rdx, [rax+10h]; Instance
0x14004f636  mov     rax, [rsi]
0x14004f639  test    rax, rax
0x14004f63c  jz      loc_14004F9AD
0x14004f642  mov     rdi, [rax+20h]
0x14004f646  mov     r12, [rbp+2Fh+arg_40]
0x14004f64a  lea     r8, [rbp+2Fh+IsDirectory]; IsDirectory
0x14004f64e  xor     r13d, r13d
0x14004f651  mov     [rbp+2Fh+var_A0], rdi
0x14004f655  xorps   xmm0, xmm0
0x14004f658  mov     [rbp+2Fh+var_90], r13
0x14004f65c  mov     rcx, r14; FileObject
0x14004f65f  mov     byte ptr [rbp+2Fh+IsDirectory], r13b
0x14004f663  mov     [r12], r13d
0x14004f667  movups  xmmword ptr [rbp+2Fh+P], xmm0
0x14004f66b  call    cs:__imp_FltIsDirectory
0x14004f672  nop     dword ptr [rax+rax+00h]
0x14004f677  mov     ecx, eax
0x14004f679  mov     ebx, eax
0x14004f67b  call    HsmDbgBreakOnStatus
0x14004f680  test    ebx, ebx
0x14004f682  js      loc_14004F949
0x14004f688  mov     edi, dword ptr [rbp+2Fh+arg_38]
0x14004f68b  test    dil, 1
0x14004f68f  jnz     loc_14004FCDD
0x14004f695  test    dil, dil
0x14004f698  js      loc_14004F797
0x14004f69e  test    dil, 40h
0x14004f6a2  jz      short loc_14004F6C7
0x14004f6a4  mov     rcx, [rbp+2Fh+arg_18]
0x14004f6a8  mov     r8d, 1
0x14004f6ae  mov     rdx, r14
0x14004f6b1  call    HsmpAccessCheck
0x14004f6b6  mov     ecx, eax
0x14004f6b8  mov     ebx, eax
0x14004f6ba  call    HsmDbgBreakOnStatus
0x14004f6bf  test    ebx, ebx
0x14004f6c1  js      loc_14004F9B4
0x14004f6c7  test    dil, 10h
0x14004f6cb  jnz     loc_14004FA05
0x14004f6d1  test    dil, 2
0x14004f6d5  jnz     loc_14004F8BC
0x14004f6db  test    dil, 4
0x14004f6df  jnz     loc_14004F822
0x14004f6e5  test    dil, 8
0x14004f6e9  jnz     loc_14004FC22
0x14004f6ef  test    dil, 20h
0x14004f6f3  jnz     loc_14004FD52
0x14004f6f9  test    [rbp+2Fh+arg_10], 10h
0x14004f6fd  jnz     short loc_14004F71B
0x14004f6ff  mov     eax, edi
0x14004f701  and     eax, 400h
0x14004f706  mov     [rbp+2Fh+var_88], eax
0x14004f709  bt      edi, 9
0x14004f70d  jb      loc_14004FAA3
0x14004f713  test    eax, eax
0x14004f715  jnz     loc_14004FAA3
0x14004f71b  mov     eax, [rbp+2Fh+arg_8]
0x14004f71e  add     eax, 10000000h
0x14004f723  cmp     eax, 0FFFFh
0x14004f728  jbe     loc_140050207
0x14004f72e  bt      edi, 8
0x14004f732  jnb     short loc_14004F73E
0x14004f734  cmp     qword ptr [rsi], 0
0x14004f738  jz      loc_14004FBE8
0x14004f73e  xor     ebx, ebx
0x14004f740  mov     rcx, [rbp+2Fh+P+8]; P
0x14004f744  mov     r15, [rsp+0F0h+var_38]
0x14004f74c  mov     r14, [rsp+0F0h+var_30]
0x14004f754  mov     r13, [rsp+0F0h+var_28]
0x14004f75c  mov     r12, [rsp+0F0h+var_20]
0x14004f764  mov     rdi, [rsp+0F0h+var_18]
0x14004f76c  mov     rsi, [rsp+0E0h]
0x14004f774  test    rcx, rcx
0x14004f777  jz      short loc_14004F78A
0x14004f779  mov     edx, 73557348h; Tag
0x14004f77e  call    cs:__imp_ExFreePoolWithTag
0x14004f785  nop     dword ptr [rax+rax+00h]
0x14004f78a  mov     eax, ebx
0x14004f78c  add     rsp, 0E8h
0x14004f793  pop     rbx
0x14004f794  pop     rbp
0x14004f795  retn
0x14004f797  mov     rcx, [rbp+2Fh+arg_18]
0x14004f79b  mov     r8d, 2
0x14004f7a1  mov     rdx, r14
0x14004f7a4  call    HsmpAccessCheck
0x14004f7a9  mov     ecx, eax
0x14004f7ab  mov     ebx, eax
0x14004f7ad  call    HsmDbgBreakOnStatus
0x14004f7b2  test    ebx, ebx
0x14004f7b4  jns     loc_14004F69E
0x14004f7ba  mov     r8, cs:WPP_GLOBAL_Control
0x14004f7c1  lea     rax, WPP_GLOBAL_Control
0x14004f7c8  cmp     r8, rax
0x14004f7cb  jz      loc_14004F740
0x14004f7d1  mov     eax, [r8+2Ch]
0x14004f7d5  test    al, 1
0x14004f7d7  jz      loc_14004F740
0x14004f7dd  cmp     byte ptr [r8+29h], 2
0x14004f7e2  jb      loc_14004F740
0x14004f7e8  mov     rcx, [rbp+2Fh+arg_28]
0x14004f7ec  test    rcx, rcx
0x14004f7ef  jz      loc_14005009F
0x14004f7f5  call    HsmpGetStreamSize
0x14004f7fa  mov     r10d, [rcx+1Ch]
0x14004f7fe  mov     r9, rax
0x14004f801  mov     edx, 0Ch
0x14004f806  mov     rax, [rbp+2Fh+arg_20]
0x14004f80a  mov     [rsp+48h], ebx
0x14004f80e  mov     qword ptr [rsp+0F0h+var_B0], rax
0x14004f813  mov     [rsp+0F0h+var_B8], r9
0x14004f818  mov     dword ptr [rsp+0F0h+var_C0], r10d
0x14004f81d  jmp     loc_14004F92A
0x14004f822  mov     rcx, [rbp+2Fh+arg_28]
0x14004f826  test    rcx, rcx
0x14004f829  jz      loc_14004F6E5
0x14004f82f  mov     eax, [rcx+1Ch]
0x14004f832  test    al, 4
0x14004f834  jz      loc_14004F6E5
0x14004f83a  call    HsmpRpCheckState
0x14004f83f  mov     ecx, eax
0x14004f841  mov     ebx, eax
0x14004f843  call    HsmDbgBreakOnStatus
0x14004f848  mov     r10, cs:WPP_GLOBAL_Control
0x14004f84f  lea     rax, WPP_GLOBAL_Control
0x14004f856  cmp     r10, rax
0x14004f859  jz      loc_14004F740
0x14004f85f  mov     eax, [r10+2Ch]
0x14004f863  test    al, 1
0x14004f865  jz      loc_14004F740
0x14004f86b  cmp     byte ptr [r10+29h], 2
0x14004f870  jb      loc_14004F740
0x14004f876  mov     rcx, [rbp+2Fh+arg_28]
0x14004f87a  call    HsmpGetStreamSize
0x14004f87f  mov     r8, [rbp+2Fh+arg_20]
0x14004f883  mov     edx, 10h
0x14004f888  mov     [rsp+48h], ebx
0x14004f88c  mov     r9, r15
0x14004f88f  mov     qword ptr [rsp+0F0h+var_B0], r8
0x14004f894  mov     [rsp+0F0h+var_B8], rax
0x14004f899  mov     eax, [rcx+1Ch]
0x14004f89c  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14004f8a0  mov     rax, [rbp+2Fh+var_A0]
0x14004f8a4  mov     [rsp+0F0h+var_C8], rax
0x14004f8a9  mov     [rsp+0F0h+var_D0], rcx
0x14004f8ae  mov     rcx, [r10+18h]
0x14004f8b2  call    WPP_SF_qqiLiqd
0x14004f8b7  jmp     loc_14004F740
0x14004f8bc  cmp     [rbp+2Fh+arg_20], r13
0x14004f8c0  jnz     loc_14004F6DB
0x14004f8c6  mov     ebx, 0C000CF07h
0x14004f8cb  mov     ecx, ebx
0x14004f8cd  call    HsmDbgBreakOnStatus
0x14004f8d2  mov     r8, cs:WPP_GLOBAL_Control
0x14004f8d9  lea     rax, WPP_GLOBAL_Control
0x14004f8e0  cmp     r8, rax
0x14004f8e3  jz      loc_14004F740
0x14004f8e9  mov     eax, [r8+2Ch]
0x14004f8ed  test    al, 1
0x14004f8ef  jz      loc_14004F740
0x14004f8f5  cmp     byte ptr [r8+29h], 2
0x14004f8fa  jb      loc_14004F740
0x14004f900  mov     rcx, [rbp+2Fh+arg_28]
0x14004f904  test    rcx, rcx
0x14004f907  jnz     loc_14004FD44
0x14004f90d  xor     eax, eax
0x14004f90f  xor     r9d, r9d
0x14004f912  mov     [rsp+48h], ebx
0x14004f916  mov     edx, 0Fh
0x14004f91b  mov     qword ptr [rsp+0F0h+var_B0], r13
0x14004f920  mov     [rsp+0F0h+var_B8], rax
0x14004f925  mov     dword ptr [rsp+0F0h+var_C0], r9d
0x14004f92a  mov     rax, [rbp+2Fh+var_A0]
0x14004f92e  mov     r9, r15
0x14004f931  mov     [rsp+0F0h+var_C8], rax
0x14004f936  mov     [rsp+0F0h+var_D0], rcx
0x14004f93b  mov     rcx, [r8+18h]
0x14004f93f  call    WPP_SF_qqiLiqd
0x14004f944  jmp     loc_14004F740
0x14004f949  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f950  lea     rax, WPP_GLOBAL_Control
0x14004f957  cmp     rcx, rax
0x14004f95a  jz      loc_14004F740
0x14004f960  mov     eax, [rcx+2Ch]
0x14004f963  test    al, 1
0x14004f965  jz      loc_14004F740
0x14004f96b  cmp     byte ptr [rcx+29h], 2
0x14004f96f  jb      loc_14004F740
0x14004f975  mov     rax, [rbp+2Fh+arg_20]
0x14004f979  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14004f980  mov     rcx, [rcx+18h]
0x14004f984  mov     edx, 0Ah
0x14004f989  mov     dword ptr [rsp+0F0h+var_B8], ebx
0x14004f98d  mov     r9, r15
0x14004f990  mov     [rsp+0F0h+var_C0], rax
0x14004f995  mov     rax, [rbp+2Fh+arg_28]
0x14004f999  mov     [rsp+0F0h+var_C8], rdi
0x14004f99e  mov     [rsp+0F0h+var_D0], rax
0x14004f9a3  call    WPP_SF_qqiqd
0x14004f9a8  jmp     loc_14004F740
0x14004f9ad  xor     edi, edi
0x14004f9af  jmp     loc_14004F646
0x14004f9b4  mov     r8, cs:WPP_GLOBAL_Control
0x14004f9bb  lea     rax, WPP_GLOBAL_Control
0x14004f9c2  cmp     r8, rax
0x14004f9c5  jz      loc_14004F740
0x14004f9cb  mov     eax, [r8+2Ch]
0x14004f9cf  test    al, 1
0x14004f9d1  jz      loc_14004F740
0x14004f9d7  cmp     byte ptr [r8+29h], 2
0x14004f9dc  jb      loc_14004F740
0x14004f9e2  mov     rcx, [rbp+2Fh+arg_28]
0x14004f9e6  test    rcx, rcx
0x14004f9e9  jz      loc_1400500AA
0x14004f9ef  call    HsmpGetStreamSize
0x14004f9f4  mov     r10d, [rcx+1Ch]
0x14004f9f8  mov     r9, rax
0x14004f9fb  mov     edx, 0Dh
0x14004fa00  jmp     loc_14004F806
0x14004fa05  mov     rcx, r15; CallbackData
0x14004fa08  mov     byte ptr [rbp+2Fh+arg_40], r13b
0x14004fa0c  call    cs:__imp_FltGetRequestorProcess
0x14004fa13  nop     dword ptr [rax+rax+00h]
0x14004fa18  mov     rdx, [rbp+2Fh+arg_28]
0x14004fa1c  mov     r8, r14
0x14004fa1f  mov     rcx, [rbp+2Fh+arg_18]
0x14004fa23  mov     r9, rax
0x14004fa26  lea     rax, [rbp+2Fh+arg_40]
0x14004fa2a  mov     [rsp+0F0h+var_D0], rax
0x14004fa2f  call    HsmpCldCheckSyncProviderAccess
0x14004fa34  mov     ecx, eax
0x14004fa36  mov     ebx, eax
0x14004fa38  call    HsmDbgBreakOnStatus
0x14004fa3d  test    ebx, ebx
0x14004fa3f  js      short loc_14004FA57
0x14004fa41  cmp     byte ptr [rbp+2Fh+arg_40], r13b
0x14004fa45  jnz     loc_14004F6D1
0x14004fa4b  mov     ebx, 0C000CF18h
0x14004fa50  mov     ecx, ebx
0x14004fa52  call    HsmDbgBreakOnStatus
0x14004fa57  mov     r8, cs:WPP_GLOBAL_Control
0x14004fa5e  lea     rax, WPP_GLOBAL_Control
0x14004fa65  cmp     r8, rax
0x14004fa68  jz      loc_14004F740
0x14004fa6e  mov     eax, [r8+2Ch]
0x14004fa72  test    al, 1
0x14004fa74  jz      loc_14004F740
0x14004fa7a  cmp     byte ptr [r8+29h], 2
0x14004fa7f  jb      loc_14004F740
0x14004fa85  mov     rcx, [rbp+2Fh+arg_28]
0x14004fa89  test    rcx, rcx
0x14004fa8c  jz      loc_1400500B5
0x14004fa92  call    HsmpGetStreamSize
0x14004fa97  mov     r10d, [rcx+1Ch]
0x14004fa9b  mov     r9, rax
0x14004fa9e  jmp     loc_1400500BB
0x14004faa3  mov     rcx, [rsi]
0x14004faa6  mov     [rbp+2Fh+var_94], r13d
0x14004faaa  mov     dword ptr [rbp+2Fh+arg_40], r13d
0x14004faae  mov     [rbp+2Fh+var_98], r13d
0x14004fab2  test    rcx, rcx
0x14004fab5  jz      loc_14004FE20
0x14004fabb  add     rcx, 60h ; '`'; Object
0x14004fabf  mov     r8, r15; CallbackData
0x14004fac2  xor     edx, edx; Timeout
0x14004fac4  call    cs:__imp_FltCancellableWaitForSingleObject
0x14004facb  nop     dword ptr [rax+rax+00h]
0x14004fad0  mov     ecx, eax
0x14004fad2  mov     ebx, eax
0x14004fad4  call    HsmDbgBreakOnStatus
0x14004fad9  test    ebx, ebx
0x14004fadb  js      loc_1400500C5
0x14004fae1  or      dword ptr [r12], 2
0x14004fae6  cmp     byte ptr [rbp+2Fh+IsDirectory], 0
0x14004faea  jnz     short loc_14004FAF2
0x14004faec  cmp     [rbp+2Fh+var_88], 0
0x14004faf0  jnz     short loc_14004FB34
0x14004faf2  mov     r13, [rbp+2Fh+arg_28]
0x14004faf6  lea     r9, [rbp+2Fh+var_90]
0x14004fafa  mov     rcx, [rbp+2Fh+arg_18]
0x14004fafe  mov     rdx, r13
  ... truncated ...
```
