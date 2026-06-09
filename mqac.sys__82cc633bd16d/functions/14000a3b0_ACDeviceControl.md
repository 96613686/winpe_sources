# ACDeviceControl

- ea: `0x14000a3b0`
- end: `0x14000b283`
- name: `ACDeviceControl`
- size: `3795`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `74`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140001010`
- `0x140001c04`
- `0x140001c34`
- `0x140003d84`
- `0x140003f74`
- `0x1400041ac`
- `0x140004314`
- `0x140004718`
- `0x1400047fc`
- `0x140004990`
- `0x140004a38`
- `0x140004afc`
- `0x140004bc4`
- `0x140004cb4`
- `0x140004d64`
- `0x1400050c8`
- `0x1400051d8`
- `0x14000533c`
- `0x1400057f4`
- `0x1400058fc`
- `0x140005cec`
- `0x140005e1c`
- `0x140005f08`
- `0x1400060c0`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x1400065d0`
- `0x14000669c`
- `0x140006808`
- `0x1400069c8`
- `0x140006a74`
- `0x140006bf0`
- `0x140006c90`
- `0x140006d50`
- `0x140006e88`
- `0x140006fd8`
- `0x14000713c`
- `0x140007460`
- `0x1400075d8`
- `0x140007790`
- `0x140007840`
- `0x1400078f4`
- `0x140007a88`
- `0x140007cb8`
- `0x140007e3c`
- `0x1400082ec`
- `0x1400083b8`
- `0x140008478`
- `0x140008534`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a442`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a442`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a457`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a457`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a514`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a514`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a520`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a520`
- `ntoskrnl!IofCompleteRequest` at `0x14000a503`
- `ntoskrnl!IofCompleteRequest` at `0x14000a503`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000a3cd`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000a3cd`
- `ntoskrnl!ProbeForRead` at `0x14000a833`
- `ntoskrnl!ProbeForRead` at `0x14000a85e`
- `ntoskrnl!ProbeForRead` at `0x14000a876`
- `ntoskrnl!ProbeForRead` at `0x14000ac94`
- `ntoskrnl!ProbeForRead` at `0x14000ad5a`
- `ntoskrnl!ProbeForRead` at `0x14000a833`
- `ntoskrnl!ProbeForRead` at `0x14000a85e`
- `ntoskrnl!ProbeForRead` at `0x14000a876`
- `ntoskrnl!ProbeForRead` at `0x14000ac94`
- `ntoskrnl!ProbeForRead` at `0x14000ad5a`

## pseudocode

```c
__int64 __fastcall ACDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int LowPart; // ebx
  unsigned int Options; // r14d
  __int64 Length; // rsi
  void **UserBuffer; // r12
  char *DeviceExtension; // rdi
  PEPROCESS *v9; // rcx
  PEPROCESS v10; // r9
  __int64 v11; // rdx
  struct CQueueBase *FsContext; // rdi
  int v13; // ebx
  unsigned int v15; // ebx
  bool v16; // zf
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  int Information; // eax
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  const struct CQueueBase *v29; // rdx
  void *v30; // r14
  void *v31; // rsi
  volatile void *v32; // rdi
  volatile void *v33; // rbx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  unsigned int v46; // ebx
  unsigned int v47; // ebx
  unsigned int v48; // ebx
  unsigned int v49; // ebx
  __int64 v50; // rcx
  unsigned int v51; // ebx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  unsigned int v54; // ebx
  unsigned int v55; // ebx
  unsigned int v56; // ebx
  unsigned int v57; // ebx
  unsigned int v58; // ebx
  unsigned int v59; // ebx
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  unsigned int v62; // ebx
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  unsigned int v65; // ebx
  unsigned int v66; // ebx
  unsigned int v67; // ebx
  unsigned int v68; // ebx
  unsigned int v69; // ebx
  unsigned int v70; // ebx
  unsigned int v71; // ebx
  unsigned int v72; // ebx
  unsigned int v73; // ebx
  unsigned int v74; // ebx
  unsigned int v75; // ebx
  unsigned int v76; // ebx
  unsigned int v77; // ebx
  unsigned int v78; // ebx
  unsigned int v79; // ebx
  unsigned int v80; // ebx
  unsigned int v81; // ebx
  unsigned int v82; // ebx
  PEPROCESS RequestorProcess; // [rsp+38h] [rbp-70h]
  IO_STATUS_BLOCK *p_IoStatus; // [rsp+40h] [rbp-68h]
  struct _FILE_OBJECT *FileObject; // [rsp+48h] [rbp-60h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+50h] [rbp-58h]
  const struct CQueueBase **v87; // [rsp+58h] [rbp-50h]
  struct _FAST_MUTEX *FastMutex; // [rsp+60h] [rbp-48h]
  unsigned int v89; // [rsp+B0h] [rbp+8h]
  PNAMED_PIPE_CREATE_PARAMETERS Address; // [rsp+C0h] [rbp+18h]
  struct _IRP *MasterIrp; // [rsp+C8h] [rbp+20h]

  RequestorProcess = IoGetRequestorProcess(a2);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v89 = (LowPart >> 2) & 0xFFF;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  UserBuffer = (void **)a2->UserBuffer;
  Address = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  DeviceExtension = (char *)a1->DeviceExtension;
  v87 = (const struct CQueueBase **)DeviceExtension;
  p_IoStatus = &a2->IoStatus;
  a2->IoStatus.Status = 259;
  KeEnterCriticalRegion();
  FastMutex = (struct _FAST_MUTEX *)(DeviceExtension + 8);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  v9 = (PEPROCESS *)(DeviceExtension + 80);
  v10 = RequestorProcess;
  if ( v89 > 0x401 && *v9 != RequestorProcess
    || (v11 = LowPart & 0x3FFC, (unsigned int)v11 < 0x1004) && !*v9
    || (FsContext = (struct CQueueBase *)FileObject->FsContext, (_DWORD)v11 == 4100) && *v9 )
  {
    v13 = -1073741808;
    goto LABEL_8;
  }
  if ( LowPart > 0x1965148F )
  {
    if ( LowPart <= 0x1965408F )
    {
      if ( LowPart != 426066063 )
      {
        v50 = 426054875;
        if ( LowPart <= 0x196514DB )
        {
          if ( LowPart == 426054875 )
          {
            Information = ACXactPrepareDefaultCommit(a2, (CTransaction *)FileObject->FsContext);
            goto LABEL_236;
          }
          v51 = LowPart - 426054803;
          if ( !v51 )
          {
            Information = ACCancelRequest((struct CQueueBase *)FileObject->FsContext, Options, Length);
            goto LABEL_236;
          }
          v52 = v51 - 4;
          if ( !v52 )
          {
            if ( Options == 8 )
            {
              ProbeForRead(Address, 8u, 1u);
              v13 = ACPutRemotePacket(a1, FsContext);
              goto LABEL_237;
            }
            goto LABEL_35;
          }
          v53 = v52 - 4;
          if ( !v53 )
          {
            if ( Options == 8 )
            {
              Information = ACCreateRemoteCursor(a1, (CProxy *)FileObject->FsContext, Address);
              goto LABEL_236;
            }
            goto LABEL_35;
          }
          v54 = v53 - 4;
          if ( v54 )
          {
            v55 = v54 - 40;
            if ( !v55 )
            {
              if ( (_DWORD)Length == 16 )
              {
                Information = ACCreateTransaction(a1);
                goto LABEL_236;
              }
              goto LABEL_35;
            }
            v56 = v55 - 4;
            if ( !v56 )
            {
              Information = ACXactCommit1(a2, (CTransaction *)FileObject->FsContext);
              goto LABEL_236;
            }
            v57 = v56 - 4;
            if ( !v57 )
            {
              Information = ACXactCommit2(a2, (CTransaction *)FileObject->FsContext);
              goto LABEL_236;
            }
            v58 = v57 - 4;
            if ( !v58 )
            {
              Information = ACXactAbort1(a2, (CTransaction *)FileObject->FsContext);
              goto LABEL_236;
            }
            if ( v58 == 4 )
            {
              Information = ACXactPrepare(a2, (CTransaction *)FileObject->FsContext);
              goto LABEL_236;
            }
            goto LABEL_220;
          }
          if ( Options != 8 )
            goto LABEL_35;
          ProbeForRead(Address, 8u, 1u);
          v13 = CQueueBase::Validate(FsContext);
          if ( v13 >= 0 )
            v13 = ACCompleteRemoteRequest(FsContext);
          goto LABEL_237;
        }
        v59 = LowPart - 426054887;
        if ( !v59 )
        {
          if ( (_DWORD)Length == 8 )
          {
            Information = ACXactGetInformation((struct CQueueBase *)FileObject->FsContext, UserBuffer);
            goto LABEL_236;
          }
          goto LABEL_35;
        }
        v60 = v59 - 4;
        if ( !v60 )
        {
          Information = ACFreePacket1(a1, UserBuffer, (unsigned __int16)Length, RequestorProcess);
          goto LABEL_236;
        }
        v61 = v60 - 4;
        if ( !v61 )
        {
          Information = ACArmPacketTimer(a1, UserBuffer, (unsigned int)Length, Options);
          goto LABEL_236;
        }
        v62 = v61 - 4;
        if ( !v62 )
        {
          Information = ACXactCommit3((struct CQueueBase *)FileObject->FsContext);
          goto LABEL_236;
        }
        v63 = v62 - 4;
        if ( !v63 )
        {
          Information = ACXactAbort2((struct CQueueBase *)FileObject->FsContext);
          goto LABEL_236;
        }
        v64 = v63 - 4;
        if ( !v64 )
        {
          Information = ACFreePacket2(a1, UserBuffer, (unsigned __int16)Length, RequestorProcess);
          goto LABEL_236;
        }
        v65 = v64 - 11085;
        if ( !v65 )
        {
          if ( Options == 436 )
          {
            Information = ACReceiveMessage_32(a1, (__int64)MasterIrp);
            goto LABEL_236;
          }
          goto LABEL_35;
        }
        v66 = v65 - 11;
        if ( v66 )
        {
          if ( v66 != 49 )
            goto LABEL_220;
LABEL_172:
          if ( (_DWORD)Length == 4 )
          {
            Information = ACCreateCursor(v50, a2, FileObject, FileObject->FsContext);
            goto LABEL_236;
          }
          goto LABEL_35;
        }
LABEL_202:
        Information = ACPurgeQueue(FileObject, FileObject->FsContext, p_IoStatus, RequestorProcess);
        goto LABEL_236;
      }
      goto LABEL_198;
    }
    v50 = 426070179;
    if ( LowPart > 0x196550A3 )
    {
      v75 = LowPart - 426071056;
      if ( !v75 )
      {
        if ( (_DWORD)Length == 16 )
        {
          Information = ACGetPacket(a2, FileObject->FsContext, p_IoStatus, RequestorProcess);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v76 = v75 - 11319;
      if ( !v76 )
      {
        if ( (_DWORD)Length == 364 )
        {
          Information = ACSendMessage_32((int)a1, (int)a2, Options, (int)FsContext, UserBuffer);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v77 = v76 - 192;
      if ( !v77 )
      {
        if ( (_DWORD)Length == 704 )
        {
          Information = ACSendMessage(a1, a2, Options, FsContext, UserBuffer);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v78 = v77 - 3924;
      if ( !v78 )
      {
        Information = ACPutRestoredPacket(a1, (CQueue *)FileObject->FsContext);
        goto LABEL_236;
      }
      v79 = v78 - 948;
      if ( !v79 )
      {
        Information = ACPutPacket(a1, a2, FileObject->FsContext, UserBuffer);
        goto LABEL_236;
      }
      v80 = v79 - 68;
      if ( !v80 )
      {
        Information = ACFreeOrDeadletterPacket(a1, FileObject->FsContext, UserBuffer, (unsigned __int16)Length);
        goto LABEL_236;
      }
      v81 = v80 - 4;
      if ( !v81 )
      {
        Information = ACFreeDetachedPacket(a1, UserBuffer, (unsigned __int16)Length, RequestorProcess);
        goto LABEL_236;
      }
      v82 = v81 - 4;
      if ( !v82 )
      {
        Information = ACDetachPacket(a1, UserBuffer, p_IoStatus, RequestorProcess);
        goto LABEL_236;
      }
      if ( v82 == 132 )
      {
        Information = ACPutPacket1(a1);
        goto LABEL_236;
      }
      goto LABEL_220;
    }
    if ( LowPart == 426070179 )
    {
      if ( (_DWORD)Length == 16 )
      {
        Information = ACGetPacketByCookie(a1, UserBuffer);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    v67 = LowPart - 426066064;
    if ( !v67 )
    {
      if ( Options == 436 )
      {
        Information = ACReceiveMessageByLookupId_32(a1, (__int64)MasterIrp);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    v68 = v67 - 8;
    if ( v68 )
    {
      v69 = v68 - 112;
      if ( !v69 )
      {
        if ( Options == 824 )
        {
          Information = ACReceiveMessage(a1, (__int64)MasterIrp);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v70 = v69 - 11;
      if ( !v70 )
        goto LABEL_202;
      v71 = v70 - 49;
      if ( !v71 )
        goto LABEL_172;
      v72 = v71 - 11;
      if ( !v72 )
      {
LABEL_198:
        if ( !FileObject->DeleteAccess )
        {
          v13 = -1073741790;
          goto LABEL_237;
        }
        if ( Options == 36 )
        {
          Information = ACMoveToSubqueue(a1, a2, FileObject->FsContext, Address);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v73 = v72 - 1;
      if ( !v73 )
      {
        if ( Options == 824 )
        {
          Information = ACReceiveMessageByLookupId(a1, (__int64)MasterIrp);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v74 = v73 - 8;
      if ( v74 )
      {
        if ( v74 == 3847 )
        {
          if ( (_DWORD)Length == 16 )
          {
            Information = ACGetRestoredPacket(a1, UserBuffer, p_IoStatus, RequestorProcess);
            goto LABEL_236;
          }
          goto LABEL_35;
        }
        goto LABEL_220;
      }
    }
    if ( Options == 12 )
    {
      Information = ACSetUserAcknowledgementClass(a2, FileObject, FileObject->FsContext, MasterIrp);
      goto LABEL_236;
    }
    goto LABEL_35;
  }
  if ( LowPart == 426054799 )
  {
    if ( (_DWORD)Length == 72 )
    {
      Information = ACEndGetPacket2Remote(a1);
      goto LABEL_236;
    }
    goto LABEL_35;
  }
  if ( LowPart > 0x19651053 )
  {
    if ( LowPart > 0x1965109F )
    {
      v42 = LowPart - 426053799;
      if ( !v42 )
      {
        if ( (_DWORD)Length == 56 )
        {
          Information = ACCreateDistribution(a1, UserBuffer);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v43 = v42 - 32;
      if ( !v43 )
      {
        Information = ACPurgeQueue_0((struct CQueueBase *)FileObject->FsContext);
        goto LABEL_236;
      }
      v44 = v43 - 4;
      if ( !v44 )
      {
        Information = ACGetUsedQuota(a1, UserBuffer, p_IoStatus, RequestorProcess);
        goto LABEL_236;
      }
      v45 = v44 - 8;
      if ( !v45 )
      {
        if ( (_DWORD)Length == 24 )
        {
          Information = ACGetSubqueueNames(
                          (struct CQueueBase *)FileObject->FsContext,
                          (struct CACGetSubqueueNames *)UserBuffer);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v46 = v45 - 820;
      if ( !v46 )
      {
        Information = ACAllocatePacket(a1, UserBuffer, (__int64)p_IoStatus);
        goto LABEL_236;
      }
      v47 = v46 - 4;
      if ( !v47 )
      {
        Information = ACFreePacket(a1, UserBuffer, (unsigned __int16)Length, RequestorProcess);
        goto LABEL_236;
      }
      v48 = v47 - 68;
      if ( !v48 )
      {
        Information = ACMoveQueueToGroup((struct CQueueBase *)FileObject->FsContext, UserBuffer);
        goto LABEL_236;
      }
      v49 = v48 - 56;
      if ( !v49 )
      {
        if ( (_DWORD)Length == 24 )
        {
          Information = ACCreateRemoteProxy(a1, FileObject, UserBuffer);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      if ( v49 == 1 )
      {
        if ( (_DWORD)Length == 16 && MasterIrp && Options == 72 )
        {
          Information = ACBeginGetPacket2Remote(a1, (__int64)MasterIrp);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      goto LABEL_220;
    }
    if ( LowPart == 426053791 )
    {
      if ( (_DWORD)Length == 16 )
      {
        Information = ACSetSequenceAck((struct CQueueBase *)FileObject->FsContext, UserBuffer);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    v34 = LowPart - 426053719;
    if ( !v34 )
    {
      if ( (int)CQueueBase::Validate(v87[120]) < 0 || (_DWORD)Length != 48 )
        goto LABEL_35;
      v29 = v87[120];
      goto LABEL_56;
    }
    v35 = v34 - 12;
    if ( !v35 )
    {
      Information = ACRestorePackets(a1, Address, UserBuffer, (unsigned int)Length, Options);
      goto LABEL_236;
    }
    v36 = v35 - 4;
    if ( v36 )
    {
      v37 = v36 - 28;
      if ( !v37 )
      {
        if ( (_DWORD)Length == 56 )
        {
          Information = ACCreateQueue(a1, FileObject, (const struct CACCreateQueueParameters *)UserBuffer, 0, 1);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v38 = v37 - 4;
      if ( !v38 )
      {
        Information = ACCreateGroup(a1, FileObject, Options, RequestorProcess);
        goto LABEL_236;
      }
      v39 = v38 - 8;
      if ( !v39 )
      {
        CSMAllocator::ReleaseFreeHeaps(*((CSMAllocator **)a1->DeviceExtension + 40));
        v13 = 0;
        goto LABEL_237;
      }
      v40 = v39 - 4;
      if ( !v40 )
      {
        if ( (_DWORD)Length == 40 )
        {
          Information = ACGetQueueProperties((struct CQueueBase *)FileObject->FsContext);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      v41 = v40 - 4;
      if ( !v41 )
      {
        Information = ACConvertPacket(a1, a2, UserBuffer, Options);
        goto LABEL_236;
      }
      if ( v41 == 4 )
      {
        Information = ACIsSequenceOnHold(a1, (CQueue *)FileObject->FsContext, (struct CPacket *)UserBuffer);
        goto LABEL_236;
      }
      goto LABEL_220;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->Queue.ListEntry.Blink, v11, p_IoStatus, (unsigned int)Length);
    }
    *(_DWORD *)(*((_QWORD *)a1->DeviceExtension + 40) + 208LL) = Length;
LABEL_76:
    v13 = 0;
    goto LABEL_237;
  }
  if ( LowPart == 426053715 )
  {
    if ( (_DWORD)Length != 48 )
      goto LABEL_35;
    v29 = (const struct CQueueBase *)*((_QWORD *)FsContext + 19);
    goto LABEL_56;
  }
  if ( LowPart <= 0x19651007 )
  {
    if ( LowPart == 426053639 )
    {
      if ( (_DWORD)Length == 72 )
      {
        Information = ACConnect(
                        a1,
                        (const struct CACConnectParameters *)UserBuffer,
                        CurrentStackLocation->FileObject,
                        RequestorProcess);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    if ( LowPart > 0x1965010F )
    {
      v17 = LowPart - 426049815;
      v16 = v17 == 0;
    }
    else
    {
      if ( LowPart == 426049807 || (v15 = LowPart - 426049615) == 0 )
      {
        if ( !Address || Options != 4 )
          goto LABEL_35;
        if ( UserBuffer )
        {
          if ( !(_DWORD)Length )
            goto LABEL_35;
        }
        else if ( (_DWORD)Length )
        {
          goto LABEL_35;
        }
        Information = ACHandleToFormatName((struct CQueueBase *)FileObject->FsContext, UserBuffer, Length, Address);
        goto LABEL_236;
      }
      v17 = v15 - 8;
      v16 = v17 == 0;
    }
    if ( v16 )
    {
      if ( Options == 16 )
      {
        Information = ACOpenQueue(a1, a2, FileObject, Address);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    v18 = v17 - 52;
    if ( !v18 )
    {
      Information = ACCloseCursor(a1);
      goto LABEL_236;
    }
    v19 = v18 - 12;
    if ( !v19 )
    {
      if ( (_DWORD)Length == 36 )
      {
        Information = ACGetQueueHandleProperties(FileObject, FileObject->FsContext, UserBuffer, RequestorProcess);
        goto LABEL_236;
      }
      goto LABEL_35;
    }
    if ( v19 == 8 )
    {
      if ( Options == 64 )
      {
        Information = ACAttachSecurityContextToQueue(FileObject, Address, p_IoStatus, RequestorProcess);
LABEL_236:
        v13 = Information;
        goto LABEL_237;
      }
LABEL_35:
      v13 = -1073741808;
      goto LABEL_237;
    }
    goto LABEL_220;
  }
  v21 = LowPart - 426053643;
  if ( !v21 )
  {
    ProbeForRead(UserBuffer, 0x20u, 1u);
    v30 = *UserBuffer;
    v31 = UserBuffer[1];
    v32 = UserBuffer[2];
    v33 = UserBuffer[3];
    ProbeForRead(v32, 0x10u, 1u);
    ProbeForRead(v33, 0x58u, 1u);
    v13 = ACpSetPerformanceBuffer(a1, v30, v31, (struct QueueCounters *)v32, (struct _QmCounters *)v33);
    goto LABEL_237;
  }
  v22 = v21 - 4;
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        17,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)Length);
    }
    *((_QWORD *)a1->DeviceExtension + 126) = Length << 10;
    goto LABEL_76;
  }
  v23 = v22 - 4;
  if ( v23 )
  {
    v24 = v23 - 4;
    if ( !v24 )
    {
      Information = ACCreatePacketCompleted(a1, a2);
      goto LABEL_236;
    }
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 7;
      if ( !v26 )
      {
        Information = ACAckingCompleted(a1, UserBuffer, p_IoStatus, RequestorProcess);
        goto LABEL_236;
      }
      v27 = v26 - 40;
      if ( !v27 )
      {
        Information = ACPrepareQueueForClose((struct CQueueBase *)FileObject->FsContext);
        goto LABEL_236;
      }
      v28 = v27 - 4;
      if ( !v28 )
      {
        if ( (_DWORD)Length == 40 )
        {
          Information = ACSetQueueProperties((struct CQueueBase *)FileObject->FsContext);
          goto LABEL_236;
        }
        goto LABEL_35;
      }
      if ( v28 == 4 )
      {
        if ( (_DWORD)Length != 48 )
          goto LABEL_35;
        v29 = (const struct CQueueBase *)FileObject->FsContext;
LABEL_56:
        Information = ACAssociateQueue(a1, v29, UserBuffer, v10);
        goto LABEL_236;
      }
LABEL_220:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 226, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v89);
      }
      v13 = -1073741808;
      goto LABEL_237;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 130, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    CStorageComplete::HoldNotification((CStorageComplete *)((char *)a1->DeviceExtension + 384), a2);
    v13 = 259;
  }
  else
  {
    if ( !a2->UserBuffer || (unsigned int)Length < 8 )
      goto LABEL_35;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 125, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    v13 = CQMInterface::ProcessService((CQMInterface *)((char *)a1->DeviceExtension + 72), a2);
  }
LABEL_237:
  if ( v13 != 259 )
  {
LABEL_8:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        229,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        a2,
        v13);
    }
    p_IoStatus->Status = v13;
    IofCompleteRequest(a2, 0);
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 228, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a2);
  }
LABEL_12:
  ExReleaseFastMutexUnsafe(FastMutex);
  KeLeaveCriticalRegion();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000a3b0  mov     [rsp+arg_8], rdx
0x14000a3b5  push    rbx
0x14000a3b6  push    rsi
0x14000a3b7  push    rdi
0x14000a3b8  push    r12
0x14000a3ba  push    r13
0x14000a3bc  push    r14
0x14000a3be  push    r15
0x14000a3c0  sub     rsp, 70h
0x14000a3c4  mov     r13, rdx
0x14000a3c7  mov     r15, rcx
0x14000a3ca  mov     rcx, rdx; Irp
0x14000a3cd  call    cs:__imp_IoGetRequestorProcess
0x14000a3d4  nop     dword ptr [rax+rax+00h]
0x14000a3d9  mov     [rsp+0A8h+var_70], rax
0x14000a3de  mov     rdx, [r13+0B8h]
0x14000a3e5  mov     [rsp+0A8h+var_58], rdx
0x14000a3ea  mov     rcx, [rdx+30h]
0x14000a3ee  mov     [rsp+0A8h+var_60], rcx
0x14000a3f3  mov     ebx, [rdx+18h]
0x14000a3f6  mov     eax, ebx
0x14000a3f8  shr     eax, 2
0x14000a3fb  and     eax, 0FFFh
0x14000a400  mov     [rsp+0A8h+arg_0], eax
0x14000a407  mov     r14d, [rdx+10h]
0x14000a40b  mov     esi, [rdx+8]
0x14000a40e  mov     rax, [r13+18h]
0x14000a412  mov     [rsp+0A8h+arg_18], rax
0x14000a41a  mov     r12, [r13+70h]
0x14000a41e  mov     rax, [rdx+20h]
0x14000a422  mov     [rsp+0A8h+Address], rax
0x14000a42a  mov     rdi, [r15+40h]
0x14000a42e  mov     [rsp+0A8h+var_50], rdi
0x14000a433  lea     rax, [r13+30h]
0x14000a437  mov     [rsp+0A8h+var_68], rax
0x14000a43c  mov     dword ptr [rax], 103h
0x14000a442  call    cs:__imp_KeEnterCriticalRegion
0x14000a449  nop     dword ptr [rax+rax+00h]
0x14000a44e  lea     rcx, [rdi+8]; FastMutex
0x14000a452  mov     [rsp+0A8h+FastMutex], rcx
0x14000a457  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000a45e  nop     dword ptr [rax+rax+00h]
0x14000a463  lea     rcx, [rdi+50h]
0x14000a467  mov     r10d, [rsp+0A8h+arg_0]
0x14000a46f  mov     r9, [rsp+0A8h+var_70]; struct _EPROCESS *
0x14000a474  cmp     r10d, 401h
0x14000a47b  jbe     short loc_14000A482
0x14000a47d  cmp     [rcx], r9
0x14000a480  jnz     short loc_14000A4BC
0x14000a482  mov     edx, ebx
0x14000a484  and     edx, 3FFCh
0x14000a48a  mov     r11d, 1004h
0x14000a490  cmp     edx, r11d
0x14000a493  jnb     short loc_14000A49B
0x14000a495  cmp     qword ptr [rcx], 0
0x14000a499  jz      short loc_14000A4BC
0x14000a49b  mov     r8, [rsp+0A8h+var_68]
0x14000a4a0  mov     rax, [rsp+0A8h+var_60]
0x14000a4a5  mov     rdi, [rax+18h]
0x14000a4a9  cmp     edx, r11d
0x14000a4ac  jnz     loc_14000A53F
0x14000a4b2  cmp     qword ptr [rcx], 0
0x14000a4b6  jz      loc_14000A53F
0x14000a4bc  mov     ebx, 0C0000010h
0x14000a4c1  lea     rdi, WPP_GLOBAL_Control
0x14000a4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4cf  cmp     rcx, rdi
0x14000a4d2  jz      short loc_14000A4F7
0x14000a4d4  mov     eax, [rcx+6Ch]
0x14000a4d7  test    al, 4
0x14000a4d9  jz      short loc_14000A4F7
0x14000a4db  mov     edx, 0E5h
0x14000a4e0  mov     dword ptr [rsp+0A8h+var_88], ebx
0x14000a4e4  mov     r9, r13
0x14000a4e7  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a4ee  mov     rcx, [rcx+58h]
0x14000a4f2  call    WPP_SF_qD
0x14000a4f7  mov     rax, [rsp+0A8h+var_68]
0x14000a4fc  mov     [rax], ebx
0x14000a4fe  xor     edx, edx; PriorityBoost
0x14000a500  mov     rcx, r13; Irp
0x14000a503  call    cs:__imp_IofCompleteRequest
0x14000a50a  nop     dword ptr [rax+rax+00h]
0x14000a50f  mov     rcx, [rsp+0A8h+FastMutex]; FastMutex
0x14000a514  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000a51b  nop     dword ptr [rax+rax+00h]
0x14000a520  call    cs:__imp_KeLeaveCriticalRegion
0x14000a527  nop     dword ptr [rax+rax+00h]
0x14000a52c  mov     eax, ebx
0x14000a52e  add     rsp, 70h
0x14000a532  pop     r15
0x14000a534  pop     r14
0x14000a536  pop     r13
0x14000a538  pop     r12
0x14000a53a  pop     rdi
0x14000a53b  pop     rsi
0x14000a53c  pop     rbx
0x14000a53d  retn
0x14000a53f  mov     ecx, 1965148Fh
0x14000a544  cmp     ebx, ecx
0x14000a546  ja      loc_14000ABB6
0x14000a54c  jz      loc_14000AB9D
0x14000a552  mov     ecx, 19651053h
0x14000a557  cmp     ebx, ecx
0x14000a559  ja      loc_14000A8CB
0x14000a55f  jz      loc_14000A8B6
0x14000a565  mov     ecx, 19651007h
0x14000a56a  cmp     ebx, ecx
0x14000a56c  ja      loc_14000A688
0x14000a572  jz      loc_14000A66A
0x14000a578  mov     ecx, 1965010Fh
0x14000a57d  cmp     ebx, ecx
0x14000a57f  ja      loc_14000A613
0x14000a585  jz      short loc_14000A5CA
0x14000a587  sub     ebx, 1965004Fh
0x14000a58d  jz      short loc_14000A5CA
0x14000a58f  sub     ebx, 8
0x14000a592  jz      loc_14000A649
0x14000a598  sub     ebx, 34h ; '4'
0x14000a59b  jz      loc_14000A636
0x14000a5a1  sub     ebx, 0Ch
0x14000a5a4  jz      short loc_14000A61E
0x14000a5a6  cmp     ebx, 8
0x14000a5a9  jnz     loc_14000B0D7
0x14000a5af  cmp     r14d, 40h ; '@'
0x14000a5b3  jnz     short loc_14000A5EF
0x14000a5b5  mov     rdx, [rsp+0A8h+Address]
0x14000a5bd  mov     rcx, rax
0x14000a5c0  call    ACAttachSecurityContextToQueue
0x14000a5c5  jmp     loc_14000B1EB
0x14000a5ca  mov     rax, [rsp+0A8h+Address]
0x14000a5d2  test    rax, rax
0x14000a5d5  jz      short loc_14000A5EF
0x14000a5d7  cmp     r14d, 4
0x14000a5db  jnz     short loc_14000A5EF
0x14000a5dd  test    r12, r12
0x14000a5e0  jz      short loc_14000A5EB
0x14000a5e2  test    esi, esi
0x14000a5e4  jz      short loc_14000A5EF
0x14000a5e6  test    r12, r12
0x14000a5e9  jnz     short loc_14000A5FD
0x14000a5eb  test    esi, esi
0x14000a5ed  jz      short loc_14000A5FD
0x14000a5ef  mov     ebx, 0C0000010h
0x14000a5f4  mov     [rsp+0A8h+var_78], ebx
0x14000a5f8  jmp     loc_14000B1F1
0x14000a5fd  mov     r9, rax; Address
0x14000a600  mov     r8d, esi; unsigned int
0x14000a603  mov     rdx, r12; void *
0x14000a606  mov     rcx, rdi; struct CQueueBase *
0x14000a609  call    ACHandleToFormatName
0x14000a60e  jmp     loc_14000B1EB
0x14000a613  sub     ebx, 19650117h
0x14000a619  jmp     loc_14000A592
0x14000a61e  cmp     esi, 24h ; '$'
0x14000a621  jnz     short loc_14000A5EF
0x14000a623  mov     r8, r12
0x14000a626  mov     rdx, rdi
0x14000a629  mov     rcx, rax
0x14000a62c  call    ACGetQueueHandleProperties
0x14000a631  jmp     loc_14000B1EB
0x14000a636  mov     r8d, r12d
0x14000a639  mov     rdx, rax
0x14000a63c  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14000a63f  call    ACCloseCursor
0x14000a644  jmp     loc_14000B1EB
0x14000a649  cmp     r14d, 10h
0x14000a64d  jnz     short loc_14000A5EF
0x14000a64f  mov     r9, [rsp+0A8h+Address]
0x14000a657  mov     r8, rax
0x14000a65a  mov     rdx, r13
0x14000a65d  mov     rcx, r15
0x14000a660  call    ACOpenQueue
0x14000a665  jmp     loc_14000B1EB
0x14000a66a  cmp     esi, 48h ; 'H'
0x14000a66d  jnz     short loc_14000A5EF
0x14000a66f  mov     r8, [rsp+0A8h+var_58]
0x14000a674  mov     r8, [r8+30h]; struct _FILE_OBJECT *
0x14000a678  mov     rdx, r12; Address
0x14000a67b  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14000a67e  call    ?ACConnect@@YAJPEAU_DEVICE_OBJECT@@PEBVCACConnectParameters@@PEAU_FILE_OBJECT@@PEAU_EPROCESS@@@Z; ACConnect(_DEVICE_OBJECT *,CACConnectParameters const *,_FILE_OBJECT *,_EPROCESS *)
0x14000a683  jmp     loc_14000B1EB
0x14000a688  sub     ebx, 1965100Bh
0x14000a68e  jz      loc_14000A827
0x14000a694  sub     ebx, 4
0x14000a697  jz      loc_14000A7D8
0x14000a69d  sub     ebx, 4
0x14000a6a0  jz      loc_14000A77A
0x14000a6a6  sub     ebx, 4
0x14000a6a9  jz      loc_14000A76A
0x14000a6af  sub     ebx, 1
0x14000a6b2  jz      short loc_14000A71E
0x14000a6b4  sub     ebx, 7
0x14000a6b7  jz      short loc_14000A70E
0x14000a6b9  sub     ebx, 28h ; '('
0x14000a6bc  jz      short loc_14000A701
0x14000a6be  sub     ebx, 4
0x14000a6c1  jz      short loc_14000A6E8
0x14000a6c3  cmp     ebx, 4
0x14000a6c6  jnz     loc_14000B0D7
0x14000a6cc  cmp     esi, 30h ; '0'
0x14000a6cf  jnz     loc_14000A5EF
0x14000a6d5  mov     rdx, rdi
0x14000a6d8  mov     r8, r12
0x14000a6db  mov     rcx, r15
0x14000a6de  call    ACAssociateQueue
0x14000a6e3  jmp     loc_14000B1EB
0x14000a6e8  cmp     esi, 28h ; '('
0x14000a6eb  jnz     loc_14000A5EF
0x14000a6f1  mov     rdx, r12
0x14000a6f4  mov     rcx, rdi; struct CQueueBase *
0x14000a6f7  call    ACSetQueueProperties
0x14000a6fc  jmp     loc_14000B1EB
0x14000a701  mov     rcx, rdi; struct CQueueBase *
0x14000a704  call    ACPrepareQueueForClose
0x14000a709  jmp     loc_14000B1EB
0x14000a70e  mov     rdx, r12
0x14000a711  mov     rcx, r15
0x14000a714  call    ACAckingCompleted
0x14000a719  jmp     loc_14000B1EB
0x14000a71e  lea     rdi, WPP_GLOBAL_Control
0x14000a725  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a72c  cmp     rcx, rdi
0x14000a72f  jz      short loc_14000A74D
0x14000a731  mov     eax, [rcx+6Ch]
0x14000a734  test    al, 4
0x14000a736  jz      short loc_14000A74D
0x14000a738  mov     edx, 82h
0x14000a73d  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a744  mov     rcx, [rcx+58h]
0x14000a748  call    WPP_SF_
0x14000a74d  mov     rcx, [r15+40h]
0x14000a751  add     rcx, 180h; this
0x14000a758  mov     rdx, r13; struct _IRP *
0x14000a75b  call    ?HoldNotification@CStorageComplete@@QEAAXPEAU_IRP@@@Z; CStorageComplete::HoldNotification(_IRP *)
0x14000a760  mov     ebx, 103h
0x14000a765  jmp     loc_14000A81E
0x14000a76a  mov     rdx, r13; struct _IRP *
0x14000a76d  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14000a770  call    ACCreatePacketCompleted
0x14000a775  jmp     loc_14000B1EB
0x14000a77a  cmp     qword ptr [r13+70h], 0
0x14000a77f  jz      loc_14000A5EF
0x14000a785  cmp     esi, 8
0x14000a788  jb      loc_14000A5EF
0x14000a78e  lea     rdi, WPP_GLOBAL_Control
0x14000a795  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a79c  cmp     rcx, rdi
0x14000a79f  jz      short loc_14000A7BD
0x14000a7a1  mov     eax, [rcx+6Ch]
0x14000a7a4  test    al, 4
0x14000a7a6  jz      short loc_14000A7BD
0x14000a7a8  mov     edx, 7Dh ; '}'
0x14000a7ad  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a7b4  mov     rcx, [rcx+58h]
0x14000a7b8  call    WPP_SF_
0x14000a7bd  mov     rcx, [r15+40h]
0x14000a7c1  add     rcx, 48h ; 'H'; this
0x14000a7c5  mov     rdx, r13; struct _IRP *
0x14000a7c8  call    ?ProcessService@CQMInterface@@QEAAJPEAU_IRP@@@Z; CQMInterface::ProcessService(_IRP *)
0x14000a7cd  mov     ebx, eax
0x14000a7cf  mov     [rsp+0A8h+var_78], eax
0x14000a7d3  jmp     loc_14000B1F8
0x14000a7d8  lea     rdi, WPP_GLOBAL_Control
0x14000a7df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7e6  cmp     rcx, rdi
0x14000a7e9  jz      short loc_14000A80A
0x14000a7eb  mov     eax, [rcx+6Ch]
0x14000a7ee  test    al, 4
0x14000a7f0  jz      short loc_14000A80A
0x14000a7f2  mov     edx, 11h
0x14000a7f7  mov     r9d, esi
0x14000a7fa  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a801  mov     rcx, [rcx+58h]
0x14000a805  call    WPP_SF_d
0x14000a80a  mov     rcx, rsi
0x14000a80d  shl     rcx, 0Ah
0x14000a811  mov     rax, [r15+40h]
0x14000a815  mov     [rax+3F0h], rcx
0x14000a81c  xor     ebx, ebx
0x14000a81e  mov     [rsp+0A8h+var_78], ebx
0x14000a822  jmp     loc_14000B1F8
0x14000a827  mov     edx, 20h ; ' '; Length
0x14000a82c  lea     r8d, [rdx-1Fh]; Alignment
0x14000a830  mov     rcx, r12; Address
0x14000a833  call    cs:__imp_ProbeForRead
0x14000a83a  nop     dword ptr [rax+rax+00h]
0x14000a83f  mov     r14, [r12]
0x14000a843  mov     rsi, [r12+8]
0x14000a848  mov     rdi, [r12+10h]
0x14000a84d  mov     rbx, [r12+18h]
0x14000a852  mov     edx, 10h; Length
0x14000a857  lea     r8d, [rdx-0Fh]; Alignment
0x14000a85b  mov     rcx, rdi; Address
0x14000a85e  call    cs:__imp_ProbeForRead
0x14000a865  nop     dword ptr [rax+rax+00h]
0x14000a86a  mov     edx, 58h ; 'X'; Length
0x14000a86f  lea     r8d, [rdx-57h]; Alignment
0x14000a873  mov     rcx, rbx; Address
0x14000a876  call    cs:__imp_ProbeForRead
  ... truncated ...
```
