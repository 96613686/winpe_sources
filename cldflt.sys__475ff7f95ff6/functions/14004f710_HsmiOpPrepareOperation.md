# HsmiOpPrepareOperation

- ea: `0x14004f710`
- end: `0x140050395`
- name: `HsmiOpPrepareOperation`
- size: `3205`
- prototype: `__int64(PFLT_CALLBACK_DATA CallbackData, int, char, struct _KEVENT *, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004dff0`

## callees

- `0x140003c50`
- `0x1400090dc`
- `0x14000abb8`
- `0x14000ac28`
- `0x140013184`
- `0x14004f710`
- `0x1400503a0`
- `0x140050dc0`
- `0x140051810`
- `0x140051a3c`
- `0x140058ddc`
- `0x140058fb0`
- `0x140059090`
- `0x14005f670`
- `0x14006f258`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14004ff9d`
- `ntoskrnl!KeClearEvent` at `0x14004ff9d`
- `ntoskrnl!KeInitializeEvent` at `0x14004ff5e`
- `ntoskrnl!KeInitializeEvent` at `0x14004ff5e`
- `ntoskrnl!KeSetEvent` at `0x140050018`
- `ntoskrnl!KeSetEvent` at `0x140050018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f89e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f89e`
- `FLTMGR!FltIsDirectory` at `0x14004f78b`
- `FLTMGR!FltIsDirectory` at `0x14004f78b`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fbe4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004ffcd`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005004d`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004fbe4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004ffcd`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005004d`
- `FLTMGR!FltGetRequestorProcess` at `0x14004fb2c`
- `FLTMGR!FltGetRequestorProcess` at `0x14004fb2c`
- `FLTMGR!FltReleasePushLockEx` at `0x14004ffb6`
- `FLTMGR!FltReleasePushLockEx` at `0x14005002a`
- `FLTMGR!FltReleasePushLockEx` at `0x14004ffb6`
- `FLTMGR!FltReleasePushLockEx` at `0x14005002a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004ff8a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fff6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004ff8a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14004fff6`

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
  int SyncRootFileId; // ebx
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
  SyncRootFileId = FltIsDirectory(TargetFileObject, TargetInstance, (PBOOLEAN)IsDirectorya);
  HsmDbgBreakOnStatus(SyncRootFileId);
  if ( SyncRootFileId < 0 )
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
    SyncRootFileId = -1073688808;
    HsmDbgBreakOnStatus(-1073688808);
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
    || (SyncRootFileId = HsmpAccessCheck((__int64)a4, TargetFileObject, 2u),
        HsmDbgBreakOnStatus(SyncRootFileId),
        SyncRootFileId >= 0) )
  {
    if ( (v15 & 0x40) != 0 )
    {
      SyncRootFileId = HsmpAccessCheck((__int64)a4, TargetFileObject, 1u);
      HsmDbgBreakOnStatus(SyncRootFileId);
      if ( SyncRootFileId < 0 )
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
        SyncRootFileId = -1073688825;
        HsmDbgBreakOnStatus(-1073688825);
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
        SyncRootFileId = HsmpRpCheckState();
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
        SyncRootFileId = -1073688821;
        HsmDbgBreakOnStatus(-1073688821);
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
        SyncRootFileId = -1073688821;
        HsmDbgBreakOnStatus(-1073688821);
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
          SyncRootFileId = FltCancellableWaitForSingleObject(&a4[5], &Timeout, CallbackData);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( !SyncRootFileId )
          {
            *v12 |= 1u;
            goto LABEL_67;
          }
          FltAcquirePushLockExclusiveEx(&a4[4].Header.WaitListHead.Blink, 0);
          if ( a4[7].Header.SignalState-- == 1 )
            KeSetEvent(a4 + 6, 0, 0);
          FltReleasePushLockEx(&a4[4].Header.WaitListHead.Blink, 0);
          if ( SyncRootFileId != 258 )
            goto LABEL_152;
          SyncRootFileId = FltCancellableWaitForSingleObject(&Event, &v53, CallbackData);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( SyncRootFileId != 258 )
            goto LABEL_152;
        }
        if ( SyncRootFileId == 258 )
        {
          SyncRootFileId = -1073741267;
          HsmDbgBreakOnStatus(-1073741267);
          goto LABEL_153;
        }
LABEL_152:
        if ( SyncRootFileId >= 0 )
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
      SyncRootFileId = FltCancellableWaitForSingleObject((PVOID)(v33 + 96), 0, CallbackData);
      HsmDbgBreakOnStatus(SyncRootFileId);
      if ( SyncRootFileId < 0 )
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
          SyncRootFileId = HsmpCldGetSyncRootFileIdEx(
                             (_DWORD)a4,
                             a6,
                             (_DWORD)TargetFileObject,
                             (unsigned int)&v50,
                             0,
                             0);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( SyncRootFileId < 0 )
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
        SyncRootFileId = HsmiCldGetSyncRootFileIdByFileObject(a4, TargetFileObject, &v50, &v49, (_DWORD **)va1);
        HsmDbgBreakOnStatus(SyncRootFileId);
        if ( SyncRootFileId < 0
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
          HsmDbgBreakOnStatus(SyncRootFileId);
          goto LABEL_158;
        }
        HsmDbgBreakOnStatus(SyncRootFileId);
        if ( SyncRootFileId < 0 )
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
        SyncRootFileId = HsmiQueryFullFilePath(a4[1].Header.WaitListHead.Flink, v36, TargetFileObject, 258, P);
        HsmDbgBreakOnStatus(SyncRootFileId);
        if ( SyncRootFileId < 0 )
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
          SyncRootFileId = HsmpCldGetSyncPolicyByPath(a4, P, &v48);
          HsmDbgBreakOnStatus(SyncRootFileId);
          if ( SyncRootFileId < 0 )
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
                SyncRootFileId = -1073688807;
                HsmDbgBreakOnStatus(-1073688807);
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
                SyncRootFileId = -1073688808;
                HsmDbgBreakOnStatus(-1073688808);
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
                SyncRootFileId = 0;
                goto LABEL_20;
              }
              if ( v13 )
              {
LABEL_80:
                SyncRootFileId = HsmpCtxGetOrCreateFileContext(CallbackData, a4, TargetFileObject, v13, v6);
                HsmDbgBreakOnStatus(SyncRootFileId);
                if ( SyncRootFileId < 0 )
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
              SyncRootFileId = HsmpCldGetSyncRootFileIdEx(
                                 (_DWORD)a4,
                                 a6,
                                 (_DWORD)TargetFileObject,
                                 (unsigned int)&v50,
                                 0,
                                 0);
              HsmDbgBreakOnStatus(SyncRootFileId);
              if ( SyncRootFileId >= 0 )
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
            SyncRootFileId = -1073688807;
            HsmDbgBreakOnStatus(-1073688807);
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
    SyncRootFileId = HsmpCldCheckSyncProviderAccess(
                       (_DWORD)a4,
                       a6,
                       (_DWORD)TargetFileObject,
                       RequestorProcess,
                       (__int64)va1);
    HsmDbgBreakOnStatus(SyncRootFileId);
    if ( SyncRootFileId >= 0 )
    {
      if ( (_BYTE)v63 )
        goto LABEL_9;
      SyncRootFileId = -1073688808;
      HsmDbgBreakOnStatus(-1073688808);
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
0x14004f710  mov     rax, rsp
0x14004f713  mov     [rax+20h], r9
0x14004f717  mov     [rax+18h], r8d
0x14004f71b  mov     [rax+10h], edx
0x14004f71e  push    rbp
0x14004f71f  push    rbx
0x14004f720  lea     rbp, [rax-37h]
0x14004f724  sub     rsp, 0E8h
0x14004f72b  mov     [rax-18h], rsi
0x14004f72f  mov     rsi, [rbp+2Fh+IsDirectory]
0x14004f733  mov     [rax-20h], rdi
0x14004f737  mov     [rax-28h], r12
0x14004f73b  mov     [rax-30h], r13
0x14004f73f  mov     [rax-38h], r14
0x14004f743  mov     [rax-40h], r15
0x14004f747  mov     r15, rcx
0x14004f74a  mov     rax, [rcx+10h]
0x14004f74e  mov     r14, [rax+8]
0x14004f752  mov     rdx, [rax+10h]; Instance
0x14004f756  mov     rax, [rsi]
0x14004f759  test    rax, rax
0x14004f75c  jz      loc_14004FACD
0x14004f762  mov     rdi, [rax+20h]
0x14004f766  mov     r12, [rbp+2Fh+arg_40]
0x14004f76a  lea     r8, [rbp+2Fh+IsDirectory]; IsDirectory
0x14004f76e  xor     r13d, r13d
0x14004f771  mov     [rbp+2Fh+var_A0], rdi
0x14004f775  xorps   xmm0, xmm0
0x14004f778  mov     [rbp+2Fh+var_90], r13
0x14004f77c  mov     rcx, r14; FileObject
0x14004f77f  mov     byte ptr [rbp+2Fh+IsDirectory], r13b
0x14004f783  mov     [r12], r13d
0x14004f787  movups  xmmword ptr [rbp+2Fh+P], xmm0
0x14004f78b  call    cs:__imp_FltIsDirectory
0x14004f792  nop     dword ptr [rax+rax+00h]
0x14004f797  mov     ecx, eax
0x14004f799  mov     ebx, eax
0x14004f79b  call    HsmDbgBreakOnStatus
0x14004f7a0  test    ebx, ebx
0x14004f7a2  js      loc_14004FA69
0x14004f7a8  mov     edi, dword ptr [rbp+2Fh+arg_38]
0x14004f7ab  test    dil, 1
0x14004f7af  jnz     loc_14004FDFD
0x14004f7b5  test    dil, dil
0x14004f7b8  js      loc_14004F8B7
0x14004f7be  test    dil, 40h
0x14004f7c2  jz      short loc_14004F7E7
0x14004f7c4  mov     rcx, [rbp+2Fh+arg_18]
0x14004f7c8  mov     r8d, 1
0x14004f7ce  mov     rdx, r14
0x14004f7d1  call    HsmpAccessCheck
0x14004f7d6  mov     ecx, eax
0x14004f7d8  mov     ebx, eax
0x14004f7da  call    HsmDbgBreakOnStatus
0x14004f7df  test    ebx, ebx
0x14004f7e1  js      loc_14004FAD4
0x14004f7e7  test    dil, 10h
0x14004f7eb  jnz     loc_14004FB25
0x14004f7f1  test    dil, 2
0x14004f7f5  jnz     loc_14004F9DC
0x14004f7fb  test    dil, 4
0x14004f7ff  jnz     loc_14004F942
0x14004f805  test    dil, 8
0x14004f809  jnz     loc_14004FD42
0x14004f80f  test    dil, 20h
0x14004f813  jnz     loc_14004FE72
0x14004f819  test    [rbp+2Fh+arg_10], 10h
0x14004f81d  jnz     short loc_14004F83B
0x14004f81f  mov     eax, edi
0x14004f821  and     eax, 400h
0x14004f826  mov     [rbp+2Fh+var_88], eax
0x14004f829  bt      edi, 9
0x14004f82d  jb      loc_14004FBC3
0x14004f833  test    eax, eax
0x14004f835  jnz     loc_14004FBC3
0x14004f83b  mov     eax, [rbp+2Fh+arg_8]
0x14004f83e  add     eax, 10000000h
0x14004f843  cmp     eax, 0FFFFh
0x14004f848  jbe     loc_140050327
0x14004f84e  bt      edi, 8
0x14004f852  jnb     short loc_14004F85E
0x14004f854  cmp     qword ptr [rsi], 0
0x14004f858  jz      loc_14004FD08
0x14004f85e  xor     ebx, ebx
0x14004f860  mov     rcx, [rbp+2Fh+P+8]; P
0x14004f864  mov     r15, [rsp+0F0h+var_38]
0x14004f86c  mov     r14, [rsp+0F0h+var_30]
0x14004f874  mov     r13, [rsp+0F0h+var_28]
0x14004f87c  mov     r12, [rsp+0F0h+var_20]
0x14004f884  mov     rdi, [rsp+0F0h+var_18]
0x14004f88c  mov     rsi, [rsp+0E0h]
0x14004f894  test    rcx, rcx
0x14004f897  jz      short loc_14004F8AA
0x14004f899  mov     edx, 73557348h; Tag
0x14004f89e  call    cs:__imp_ExFreePoolWithTag
0x14004f8a5  nop     dword ptr [rax+rax+00h]
0x14004f8aa  mov     eax, ebx
0x14004f8ac  add     rsp, 0E8h
0x14004f8b3  pop     rbx
0x14004f8b4  pop     rbp
0x14004f8b5  retn
0x14004f8b7  mov     rcx, [rbp+2Fh+arg_18]
0x14004f8bb  mov     r8d, 2
0x14004f8c1  mov     rdx, r14
0x14004f8c4  call    HsmpAccessCheck
0x14004f8c9  mov     ecx, eax
0x14004f8cb  mov     ebx, eax
0x14004f8cd  call    HsmDbgBreakOnStatus
0x14004f8d2  test    ebx, ebx
0x14004f8d4  jns     loc_14004F7BE
0x14004f8da  mov     r8, cs:WPP_GLOBAL_Control
0x14004f8e1  lea     rax, WPP_GLOBAL_Control
0x14004f8e8  cmp     r8, rax
0x14004f8eb  jz      loc_14004F860
0x14004f8f1  mov     eax, [r8+2Ch]
0x14004f8f5  test    al, 1
0x14004f8f7  jz      loc_14004F860
0x14004f8fd  cmp     byte ptr [r8+29h], 2
0x14004f902  jb      loc_14004F860
0x14004f908  mov     rcx, [rbp+2Fh+arg_28]
0x14004f90c  test    rcx, rcx
0x14004f90f  jz      loc_1400501BF
0x14004f915  call    HsmpGetStreamSize
0x14004f91a  mov     r10d, [rcx+1Ch]
0x14004f91e  mov     r9, rax
0x14004f921  mov     edx, 0Ch
0x14004f926  mov     rax, [rbp+2Fh+arg_20]
0x14004f92a  mov     [rsp+48h], ebx
0x14004f92e  mov     qword ptr [rsp+0F0h+var_B0], rax
0x14004f933  mov     [rsp+0F0h+var_B8], r9
0x14004f938  mov     dword ptr [rsp+0F0h+var_C0], r10d
0x14004f93d  jmp     loc_14004FA4A
0x14004f942  mov     rcx, [rbp+2Fh+arg_28]
0x14004f946  test    rcx, rcx
0x14004f949  jz      loc_14004F805
0x14004f94f  mov     eax, [rcx+1Ch]
0x14004f952  test    al, 4
0x14004f954  jz      loc_14004F805
0x14004f95a  call    HsmpRpCheckState
0x14004f95f  mov     ecx, eax
0x14004f961  mov     ebx, eax
0x14004f963  call    HsmDbgBreakOnStatus
0x14004f968  mov     r10, cs:WPP_GLOBAL_Control
0x14004f96f  lea     rax, WPP_GLOBAL_Control
0x14004f976  cmp     r10, rax
0x14004f979  jz      loc_14004F860
0x14004f97f  mov     eax, [r10+2Ch]
0x14004f983  test    al, 1
0x14004f985  jz      loc_14004F860
0x14004f98b  cmp     byte ptr [r10+29h], 2
0x14004f990  jb      loc_14004F860
0x14004f996  mov     rcx, [rbp+2Fh+arg_28]
0x14004f99a  call    HsmpGetStreamSize
0x14004f99f  mov     r8, [rbp+2Fh+arg_20]
0x14004f9a3  mov     edx, 10h
0x14004f9a8  mov     [rsp+48h], ebx
0x14004f9ac  mov     r9, r15
0x14004f9af  mov     qword ptr [rsp+0F0h+var_B0], r8
0x14004f9b4  mov     [rsp+0F0h+var_B8], rax
0x14004f9b9  mov     eax, [rcx+1Ch]
0x14004f9bc  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14004f9c0  mov     rax, [rbp+2Fh+var_A0]
0x14004f9c4  mov     [rsp+0F0h+var_C8], rax
0x14004f9c9  mov     [rsp+0F0h+var_D0], rcx
0x14004f9ce  mov     rcx, [r10+18h]
0x14004f9d2  call    WPP_SF_qqiLiqd
0x14004f9d7  jmp     loc_14004F860
0x14004f9dc  cmp     [rbp+2Fh+arg_20], r13
0x14004f9e0  jnz     loc_14004F7FB
0x14004f9e6  mov     ebx, 0C000CF07h
0x14004f9eb  mov     ecx, ebx
0x14004f9ed  call    HsmDbgBreakOnStatus
0x14004f9f2  mov     r8, cs:WPP_GLOBAL_Control
0x14004f9f9  lea     rax, WPP_GLOBAL_Control
0x14004fa00  cmp     r8, rax
0x14004fa03  jz      loc_14004F860
0x14004fa09  mov     eax, [r8+2Ch]
0x14004fa0d  test    al, 1
0x14004fa0f  jz      loc_14004F860
0x14004fa15  cmp     byte ptr [r8+29h], 2
0x14004fa1a  jb      loc_14004F860
0x14004fa20  mov     rcx, [rbp+2Fh+arg_28]
0x14004fa24  test    rcx, rcx
0x14004fa27  jnz     loc_14004FE64
0x14004fa2d  xor     eax, eax
0x14004fa2f  xor     r9d, r9d
0x14004fa32  mov     [rsp+48h], ebx
0x14004fa36  mov     edx, 0Fh
0x14004fa3b  mov     qword ptr [rsp+0F0h+var_B0], r13
0x14004fa40  mov     [rsp+0F0h+var_B8], rax
0x14004fa45  mov     dword ptr [rsp+0F0h+var_C0], r9d
0x14004fa4a  mov     rax, [rbp+2Fh+var_A0]
0x14004fa4e  mov     r9, r15
0x14004fa51  mov     [rsp+0F0h+var_C8], rax
0x14004fa56  mov     [rsp+0F0h+var_D0], rcx
0x14004fa5b  mov     rcx, [r8+18h]
0x14004fa5f  call    WPP_SF_qqiLiqd
0x14004fa64  jmp     loc_14004F860
0x14004fa69  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa70  lea     rax, WPP_GLOBAL_Control
0x14004fa77  cmp     rcx, rax
0x14004fa7a  jz      loc_14004F860
0x14004fa80  mov     eax, [rcx+2Ch]
0x14004fa83  test    al, 1
0x14004fa85  jz      loc_14004F860
0x14004fa8b  cmp     byte ptr [rcx+29h], 2
0x14004fa8f  jb      loc_14004F860
0x14004fa95  mov     rax, [rbp+2Fh+arg_20]
0x14004fa99  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14004faa0  mov     rcx, [rcx+18h]
0x14004faa4  mov     edx, 0Ah
0x14004faa9  mov     dword ptr [rsp+0F0h+var_B8], ebx
0x14004faad  mov     r9, r15
0x14004fab0  mov     [rsp+0F0h+var_C0], rax
0x14004fab5  mov     rax, [rbp+2Fh+arg_28]
0x14004fab9  mov     [rsp+0F0h+var_C8], rdi
0x14004fabe  mov     [rsp+0F0h+var_D0], rax
0x14004fac3  call    WPP_SF_qqiqd
0x14004fac8  jmp     loc_14004F860
0x14004facd  xor     edi, edi
0x14004facf  jmp     loc_14004F766
0x14004fad4  mov     r8, cs:WPP_GLOBAL_Control
0x14004fadb  lea     rax, WPP_GLOBAL_Control
0x14004fae2  cmp     r8, rax
0x14004fae5  jz      loc_14004F860
0x14004faeb  mov     eax, [r8+2Ch]
0x14004faef  test    al, 1
0x14004faf1  jz      loc_14004F860
0x14004faf7  cmp     byte ptr [r8+29h], 2
0x14004fafc  jb      loc_14004F860
0x14004fb02  mov     rcx, [rbp+2Fh+arg_28]
0x14004fb06  test    rcx, rcx
0x14004fb09  jz      loc_1400501CA
0x14004fb0f  call    HsmpGetStreamSize
0x14004fb14  mov     r10d, [rcx+1Ch]
0x14004fb18  mov     r9, rax
0x14004fb1b  mov     edx, 0Dh
0x14004fb20  jmp     loc_14004F926
0x14004fb25  mov     rcx, r15; CallbackData
0x14004fb28  mov     byte ptr [rbp+2Fh+arg_40], r13b
0x14004fb2c  call    cs:__imp_FltGetRequestorProcess
0x14004fb33  nop     dword ptr [rax+rax+00h]
0x14004fb38  mov     rdx, [rbp+2Fh+arg_28]
0x14004fb3c  mov     r8, r14
0x14004fb3f  mov     rcx, [rbp+2Fh+arg_18]
0x14004fb43  mov     r9, rax
0x14004fb46  lea     rax, [rbp+2Fh+arg_40]
0x14004fb4a  mov     [rsp+0F0h+var_D0], rax
0x14004fb4f  call    HsmpCldCheckSyncProviderAccess
0x14004fb54  mov     ecx, eax
0x14004fb56  mov     ebx, eax
0x14004fb58  call    HsmDbgBreakOnStatus
0x14004fb5d  test    ebx, ebx
0x14004fb5f  js      short loc_14004FB77
0x14004fb61  cmp     byte ptr [rbp+2Fh+arg_40], r13b
0x14004fb65  jnz     loc_14004F7F1
0x14004fb6b  mov     ebx, 0C000CF18h
0x14004fb70  mov     ecx, ebx
0x14004fb72  call    HsmDbgBreakOnStatus
0x14004fb77  mov     r8, cs:WPP_GLOBAL_Control
0x14004fb7e  lea     rax, WPP_GLOBAL_Control
0x14004fb85  cmp     r8, rax
0x14004fb88  jz      loc_14004F860
0x14004fb8e  mov     eax, [r8+2Ch]
0x14004fb92  test    al, 1
0x14004fb94  jz      loc_14004F860
0x14004fb9a  cmp     byte ptr [r8+29h], 2
0x14004fb9f  jb      loc_14004F860
0x14004fba5  mov     rcx, [rbp+2Fh+arg_28]
0x14004fba9  test    rcx, rcx
0x14004fbac  jz      loc_1400501D5
0x14004fbb2  call    HsmpGetStreamSize
0x14004fbb7  mov     r10d, [rcx+1Ch]
0x14004fbbb  mov     r9, rax
0x14004fbbe  jmp     loc_1400501DB
0x14004fbc3  mov     rcx, [rsi]
0x14004fbc6  mov     [rbp+2Fh+var_94], r13d
0x14004fbca  mov     dword ptr [rbp+2Fh+arg_40], r13d
0x14004fbce  mov     [rbp+2Fh+var_98], r13d
0x14004fbd2  test    rcx, rcx
0x14004fbd5  jz      loc_14004FF40
0x14004fbdb  add     rcx, 60h ; '`'; Object
0x14004fbdf  mov     r8, r15; CallbackData
0x14004fbe2  xor     edx, edx; Timeout
0x14004fbe4  call    cs:__imp_FltCancellableWaitForSingleObject
0x14004fbeb  nop     dword ptr [rax+rax+00h]
0x14004fbf0  mov     ecx, eax
0x14004fbf2  mov     ebx, eax
0x14004fbf4  call    HsmDbgBreakOnStatus
0x14004fbf9  test    ebx, ebx
0x14004fbfb  js      loc_1400501E5
0x14004fc01  or      dword ptr [r12], 2
0x14004fc06  cmp     byte ptr [rbp+2Fh+IsDirectory], 0
0x14004fc0a  jnz     short loc_14004FC12
0x14004fc0c  cmp     [rbp+2Fh+var_88], 0
0x14004fc10  jnz     short loc_14004FC54
0x14004fc12  mov     r13, [rbp+2Fh+arg_28]
0x14004fc16  lea     r9, [rbp+2Fh+var_90]
0x14004fc1a  mov     rcx, [rbp+2Fh+arg_18]
0x14004fc1e  mov     rdx, r13
  ... truncated ...
```
