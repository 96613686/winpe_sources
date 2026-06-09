# FltSendMessage

- ea: `0x180019ea0`
- end: `0x18001aa1c`
- name: `FltSendMessage`
- size: `2940`
- prototype: `NTSTATUS __stdcall(PFLT_FILTER Filter, PFLT_PORT *ClientPort, PVOID SenderBuffer, ULONG SenderBufferLength, PVOID ReplyBuffer, PULONG ReplyLength, PLARGE_INTEGER Timeout)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180009f20`
- `0x1800148b0`
- `0x180014cf0`
- `0x180019ea0`
- `0x18001aa30`
- `0x180020180`
- `0x180020de4`
- `0x180024900`
- `0x180024c00`
- `0x18004f01c`
- `0x18004f058`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x18001a4fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a61c`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a786`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a8be`
- `ntoskrnl!ExReleaseFastMutex` at `0x180026413`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a4fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a61c`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a786`
- `ntoskrnl!ExReleaseFastMutex` at `0x18001a8be`
- `ntoskrnl!ExReleaseFastMutex` at `0x180026413`
- `ntoskrnl!ExAcquireFastMutex` at `0x18001a327`
- `ntoskrnl!ExAcquireFastMutex` at `0x18001a4da`
- `ntoskrnl!ExAcquireFastMutex` at `0x1800263f3`
- `ntoskrnl!ExAcquireFastMutex` at `0x18001a327`
- `ntoskrnl!ExAcquireFastMutex` at `0x18001a4da`
- `ntoskrnl!ExAcquireFastMutex` at `0x1800263f3`
- `ntoskrnl!KeInitializeEvent` at `0x18001a2ce`
- `ntoskrnl!KeInitializeEvent` at `0x18001a2ce`
- `ntoskrnl!KeWaitForSingleObject` at `0x180026434`
- `ntoskrnl!KeWaitForSingleObject` at `0x180026434`
- `ntoskrnl!ObfDereferenceObject` at `0x180019fc6`
- `ntoskrnl!ObfDereferenceObject` at `0x18001a47f`
- `ntoskrnl!ObfDereferenceObject` at `0x180019fc6`
- `ntoskrnl!ObfDereferenceObject` at `0x18001a47f`
- `ntoskrnl!ObfReferenceObject` at `0x180019f6e`
- `ntoskrnl!ObfReferenceObject` at `0x18001a303`
- `ntoskrnl!ObfReferenceObject` at `0x180019f6e`
- `ntoskrnl!ObfReferenceObject` at `0x18001a303`
- `ntoskrnl!IoGetStackLimits` at `0x18001a010`
- `ntoskrnl!IoGetStackLimits` at `0x18001a010`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180019f2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180019f2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180019f91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180019f91`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x180019f47`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x180019f47`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180019f85`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180019f85`
- `ntoskrnl!KeClearEvent` at `0x18001a723`
- `ntoskrnl!KeClearEvent` at `0x18001a723`
- `ntoskrnl!IofCompleteRequest` at `0x18001a20f`
- `ntoskrnl!IofCompleteRequest` at `0x18001a50c`
- `ntoskrnl!IofCompleteRequest` at `0x18001a62d`
- `ntoskrnl!IofCompleteRequest` at `0x18001a8dc`
- `ntoskrnl!IofCompleteRequest` at `0x18001a999`
- `ntoskrnl!IofCompleteRequest` at `0x18001a20f`
- `ntoskrnl!IofCompleteRequest` at `0x18001a50c`
- `ntoskrnl!IofCompleteRequest` at `0x18001a62d`
- `ntoskrnl!IofCompleteRequest` at `0x18001a8dc`
- `ntoskrnl!IofCompleteRequest` at `0x18001a999`
- `ntoskrnl!IoAllocateMdl` at `0x18001a1b5`
- `ntoskrnl!IoAllocateMdl` at `0x18001a1b5`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a3a8`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a5d0`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a6c7`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a3a8`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a5d0`
- `ntoskrnl!MmIsKernelAddress` at `0x18001a6c7`
- `ntoskrnl!IoFreeMdl` at `0x180026449`
- `ntoskrnl!IoFreeMdl` at `0x180026449`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a109`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a567`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a671`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a109`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a567`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x18001a671`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18001a13d`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18001a13d`
- `ntoskrnl!MmProbeAndLockProcessPages` at `0x18001a41e`
- `ntoskrnl!MmProbeAndLockProcessPages` at `0x18001a41e`
- `ntoskrnl!IoGetRequestorProcess` at `0x18001a402`
- `ntoskrnl!IoGetRequestorProcess` at `0x18001a402`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18001a37e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18001a37e`
- `ntoskrnl!MmUnlockPages` at `0x18001a95b`
- `ntoskrnl!MmUnlockPages` at `0x18001a95b`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18002646b`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18002646b`
- `HAL!KeQueryPerformanceCounter` at `0x180019f05`
- `HAL!KeQueryPerformanceCounter` at `0x18001a03a`
- `HAL!KeQueryPerformanceCounter` at `0x180019f05`
- `HAL!KeQueryPerformanceCounter` at `0x18001a03a`

## pseudocode

```c
NTSTATUS __stdcall FltSendMessage(
        PFLT_FILTER Filter,
        PFLT_PORT *ClientPort,
        PVOID SenderBuffer,
        ULONG SenderBufferLength,
        PVOID ReplyBuffer,
        PULONG ReplyLength,
        PLARGE_INTEGER Timeout)
{
  PULONG v9; // rdi
  __int64 v10; // rsi
  unsigned int Flink_high; // edi
  __int128 v12; // rtt
  LONGLONG v14; // rbx
  PIO_CSQ v15; // r14
  PLARGE_INTEGER v16; // rsi
  NTSTATUS v17; // eax
  __int64 v18; // rcx
  PIRP v19; // rax
  __int64 v20; // rcx
  IRP *v21; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  ULONG v23; // edx
  char v24; // si
  PMDL *p_MdlAddress; // r14
  PMDL Mdl; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  ULONG v29; // edi
  _DWORD *v30; // rcx
  _QWORD *p_Type; // rdi
  __int64 v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // rsi
  struct _LIST_ENTRY *v35; // rcx
  struct _MDL *v36; // rcx
  _DWORD *MappedSystemVa; // rax
  _DWORD *v38; // rax
  KPROCESSOR_MODE RequestorMode; // si
  struct _MDL *v40; // r14
  struct _KPROCESS *RequestorProcess; // rax
  int v42; // eax
  __int64 v43; // rax
  NTSTATUS v44; // eax
  __int64 v45; // rax
  PLARGE_INTEGER v46; // r9
  unsigned int v47; // eax
  __int64 v48; // rcx
  PULONG v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 *v53; // rdx
  ULONG PeekContext; // [rsp+34h] [rbp-114h] BYREF
  ULONG ULongFromUser; // [rsp+38h] [rbp-110h]
  PIO_CSQ Csq; // [rsp+40h] [rbp-108h]
  PVOID Object; // [rsp+48h] [rbp-100h]
  _DWORD *v58; // [rsp+50h] [rbp-F8h]
  LONGLONG QuadPart; // [rsp+58h] [rbp-F0h] BYREF
  LONGLONG v60; // [rsp+60h] [rbp-E8h]
  PMDL *v61; // [rsp+68h] [rbp-E0h]
  PLARGE_INTEGER v62; // [rsp+70h] [rbp-D8h]
  PVOID ObjectArray[2]; // [rsp+78h] [rbp-D0h] BYREF
  PIRP v64; // [rsp+88h] [rbp-C0h]
  struct _IO_STACK_LOCATION *v65; // [rsp+90h] [rbp-B8h]
  _DWORD *v66; // [rsp+98h] [rbp-B0h]
  PVOID v67; // [rsp+A0h] [rbp-A8h]
  unsigned __int64 HighLimit; // [rsp+A8h] [rbp-A0h] BYREF
  struct _KEVENT v69[3]; // [rsp+B0h] [rbp-98h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+100h] [rbp-48h]

  QuadPart = 0;
  Object = 0;
  memset(v69, 0, sizeof(v69));
  v67 = 0;
  PeekContext = 0;
  *(_OWORD *)ObjectArray = 0;
  ULongFromUser = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v9 = ReplyLength;
  if ( ReplyLength )
  {
    if ( (unsigned __int8)MmIsKernelAddress(ReplyLength) )
    {
      ULongFromUser = *v9;
      *v9 = 0;
    }
    else
    {
      ULongFromUser = RtlReadULongFromUser(v9);
      RtlWriteULongToUser(v9, 0);
    }
  }
  KeEnterCriticalRegion();
  v10 = ExAcquireAutoExpandPushLockShared(&Filter->PortLock, 0);
  if ( *ClientPort )
  {
    Flink_high = 0;
    Object = (PVOID)*((_QWORD *)*ClientPort + 1);
    ObfReferenceObject(Object);
  }
  else
  {
    Flink_high = -1073741769;
  }
  ExReleaseAutoExpandPushLockShared(v10, 0);
  KeLeaveCriticalRegion();
  if ( (int)FltpDbgStatus(Flink_high, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 2007, 0) < 0 )
    goto LABEL_5;
  v14 = 0;
  v60 = 0;
  v66 = 0;
  v15 = (PIO_CSQ)((char *)Object + 96);
  Csq = (PIO_CSQ)((char *)Object + 96);
  PeekContext = SenderBufferLength + 16;
  if ( Timeout )
  {
    v16 = (PLARGE_INTEGER)&QuadPart;
    v62 = (PLARGE_INTEGER)&QuadPart;
    QuadPart = Timeout->QuadPart;
    if ( QuadPart < 0 )
    {
      v14 = MEMORY[0xFFFFF78000000008] - QuadPart;
      v60 = MEMORY[0xFFFFF78000000008] - QuadPart;
    }
  }
  else
  {
    v16 = 0;
    v62 = 0;
  }
  ObjectArray[0] = (char *)Object + 312;
  while ( 1 )
  {
    while ( 1 )
    {
      ObjectArray[1] = &v15[2].CsqPeekNextIrp;
      v17 = FsRtlCancellableWaitForMultipleObjects(2u, ObjectArray, WaitAny, v16, 0, 0);
      Flink_high = v17;
      switch ( v17 )
      {
        case 258:
          if ( (byte_1800404C3 & 1) != 0 )
          {
            v53 = MessageSup_c2079;
            goto LABEL_115;
          }
          goto LABEL_5;
        case 0:
          if ( (byte_1800404C3 & 1) != 0 )
            McTemplateU0s_EtwWriteTransfer(v18, MessageSup_c2092, "FltSendMessage");
          Flink_high = -1073741769;
          goto LABEL_5;
        case -1073741749:
          if ( (byte_1800404C3 & 1) != 0 )
          {
            v53 = MessageSup_c2100;
            goto LABEL_115;
          }
          goto LABEL_5;
      }
      v19 = IoCsqRemoveNextIrp(v15, &PeekContext);
      v21 = v19;
      v64 = v19;
      if ( !v19 )
        goto LABEL_58;
      CurrentStackLocation = v19->Tail.Overlay.CurrentStackLocation;
      v65 = CurrentStackLocation;
      v23 = PeekContext;
      if ( CurrentStackLocation->Parameters.Read.Length < PeekContext )
        break;
      Flink_high = 0;
      if ( (byte_1800404C3 & 1) != 0 )
      {
        McTemplateU0sp_EtwWriteTransfer(v20, MessageSup_c2230, "FltSendMessage", v19);
        v23 = PeekContext;
      }
      v24 = 0;
      p_MdlAddress = &v21->MdlAddress;
      v61 = &v21->MdlAddress;
      if ( v21->MdlAddress )
        goto LABEL_39;
      Mdl = IoAllocateMdl(v21->UserBuffer, v23, 0, 1u, 0);
      *p_MdlAddress = Mdl;
      if ( !Mdl )
        goto LABEL_25;
      RequestorMode = v21->RequestorMode;
      v40 = Mdl;
      RequestorProcess = IoGetRequestorProcess(v21);
      MmProbeAndLockProcessPages(v40, RequestorProcess, RequestorMode, IoWriteAccess);
      v24 = 1;
      v42 = FltpDbgStatus(0, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 2269, 0);
      p_MdlAddress = v61;
      if ( v42 >= 0 )
      {
LABEL_39:
        v36 = *p_MdlAddress;
        if ( ((*p_MdlAddress)->MdlFlags & 5) != 0 )
          MappedSystemVa = v36->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(v36, 0, MmCached, 0, 0, 0x40000010u);
        v58 = MappedSystemVa;
        v66 = MappedSystemVa;
        if ( !MappedSystemVa )
        {
LABEL_25:
          Flink_high = -1073741670;
          goto LABEL_26;
        }
        if ( (unsigned __int8)MmIsKernelAddress(SenderBuffer) )
          memmove(v58 + 4, SenderBuffer, SenderBufferLength);
        else
          RtlCopyFromUser(v58 + 4, SenderBuffer, SenderBufferLength);
        v38 = v58;
        *v58 = 0;
        *((_QWORD *)v38 + 1) = 0;
        v21->IoStatus.Status = 0;
        v21->IoStatus.Information = PeekContext;
      }
LABEL_26:
      if ( (int)FltpDbgStatus(Flink_high, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 2329, 0) >= 0 )
      {
        if ( ReplyBuffer )
        {
          memset(v69, 0, sizeof(v69));
          LODWORD(v69[2].Header.WaitListHead.Blink) = 1;
          v69[0].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)_InterlockedIncrement64((volatile signed __int64 *)Object + 38);
          *(_QWORD *)&v69[2].Header.Lock = ReplyBuffer;
          v29 = ULongFromUser;
          LODWORD(v69[2].Header.WaitListHead.Flink) = ULongFromUser;
          KeInitializeEvent(&v69[1], NotificationEvent, 0);
          v30 = v66;
          *((_QWORD *)v66 + 1) = v69[0].Header.WaitListHead.Blink;
          *v30 = v29 + 16;
          p_Type = &CurrentStackLocation->FileObject->Type;
          v67 = p_Type;
          ObfReferenceObject(p_Type);
          v33 = p_Type[4];
          if ( (byte_1800404C3 & 1) != 0 )
            McTemplateU0sp_EtwWriteTransfer(v32, MessageSup_c2473, "FltSendMessage", v69);
          v34 = v33 + 16;
          ExAcquireFastMutex((PFAST_MUTEX)v34);
          if ( (*(_BYTE *)(v34 + 72) & 1) != 0 )
          {
            ExReleaseFastMutex((PFAST_MUTEX)v34);
            v21->IoStatus.Status = -1073741769;
            v21->IoStatus.Information = 0;
            IofCompleteRequest(v21, 0);
            Flink_high = -1073741769;
            goto LABEL_5;
          }
          *(_DWORD *)(v34 + 72) += 2;
          v35 = *(struct _LIST_ENTRY **)(v34 + 64);
          if ( v35->Flink == (struct _LIST_ENTRY *)(v34 + 56) )
          {
            *(_QWORD *)&v69[0].Header.Lock = v34 + 56;
            v69[0].Header.WaitListHead.Flink = v35;
            v35->Flink = (struct _LIST_ENTRY *)v69;
            *(_QWORD *)(v34 + 64) = v69;
            ExReleaseFastMutex((PFAST_MUTEX)v34);
            IofCompleteRequest(v21, 0);
            ObjectArray[1] = &v69[1];
            v46 = v62;
            if ( v62 )
            {
              if ( v62->HighPart < 0 )
              {
                v50 = MEMORY[0xFFFFF78000000008] - v14;
                v62->QuadPart = MEMORY[0xFFFFF78000000008] - v14;
                if ( v50 > 0 )
                  v46->QuadPart = 0;
              }
            }
            v47 = FsRtlCancellableWaitForMultipleObjects(2u, ObjectArray, WaitAny, v46, 0, 0);
            Flink_high = v47;
            if ( (byte_1800404C3 & 1) != 0 )
              McTemplateU0sd_EtwWriteTransfer(v48, MessageSup_c2526, "FltSendMessage", v47);
            if ( Flink_high != 258 && Flink_high != -1073741749 && Flink_high )
            {
              Flink_high = HIDWORD(v69[2].Header.WaitListHead.Flink);
              v49 = ReplyLength;
              if ( ReplyLength )
              {
                if ( (unsigned __int8)MmIsKernelAddress(ReplyLength) )
                  *v49 = (ULONG)v69[2].Header.WaitListHead.Flink;
                else
                  RtlWriteULongToUser(v49, LODWORD(v69[2].Header.WaitListHead.Flink));
              }
              goto LABEL_5;
            }
            if ( (byte_1800404C3 & 1) != 0 )
              McTemplateU0s_EtwWriteTransfer(v48, MessageSup_c2534, "FltSendMessage");
            if ( !Flink_high )
              Flink_high = -1073741769;
            ExAcquireFastMutex((PFAST_MUTEX)v34);
            if ( !*(_QWORD *)&v69[0].Header.Lock )
            {
              ExReleaseFastMutex((PFAST_MUTEX)v34);
              KeWaitForSingleObject(&v69[1], Executive, 0, 0, 0);
              goto LABEL_5;
            }
            *(_DWORD *)(v34 + 72) -= 2;
            v51 = *(_QWORD *)&v69[0].Header.Lock;
            if ( *(struct _KEVENT **)(*(_QWORD *)&v69[0].Header.Lock + 8LL) == v69 )
            {
              Flink = v69[0].Header.WaitListHead.Flink;
              if ( v69[0].Header.WaitListHead.Flink->Flink == (struct _LIST_ENTRY *)v69 )
              {
                v69[0].Header.WaitListHead.Flink->Flink = *(struct _LIST_ENTRY **)&v69[0].Header.Lock;
                *(_QWORD *)(v51 + 8) = Flink;
                *(_QWORD *)&v69[0].Header.Lock = 0;
                ExReleaseFastMutex((PFAST_MUTEX)v34);
                goto LABEL_5;
              }
            }
          }
          __fastfail(3u);
        }
LABEL_97:
        IofCompleteRequest(v21, 0);
        goto LABEL_5;
      }
      if ( v24 )
      {
        if ( ((*p_MdlAddress)->MdlFlags & 2) != 0 )
          MmUnlockPages(*p_MdlAddress);
        IoFreeMdl(*p_MdlAddress);
        *p_MdlAddress = 0;
      }
      if ( Flink_high == -1073741670 )
      {
        if ( (byte_1800404C3 & 1) != 0 )
          McTemplateU0sp_EtwWriteTransfer(v27, MessageSup_c2349, "FltSendMessage", v21);
        Flink_high = IoCsqInsertIrpEx(Csq, v21, 0, 0);
        if ( (int)FltpDbgStatus(Flink_high, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 2365, 0) >= 0 )
        {
          Flink_high = -1073741670;
          goto LABEL_5;
        }
        v21->IoStatus.Status = Flink_high;
        v21->IoStatus.Information = 0;
        goto LABEL_97;
      }
      v21->IoStatus.Status = Flink_high;
      v21->IoStatus.Information = 0;
      IofCompleteRequest(v21, 0);
      v16 = v62;
      v15 = Csq;
      if ( v62 )
      {
        if ( v62->HighPart < 0 )
        {
          v28 = MEMORY[0xFFFFF78000000008] - v14;
          v62->QuadPart = MEMORY[0xFFFFF78000000008] - v14;
          if ( v28 > 0 )
            v16->QuadPart = 0;
        }
      }
    }
    v19->IoStatus.Status = -1073741789;
    v19->IoStatus.Information = PeekContext;
    ExAcquireFastMutex((PFAST_MUTEX)&v15[1]);
    if ( LODWORD(v15[2].CsqRemoveIrp) > PeekContext )
    {
      LODWORD(v15[2].CsqRemoveIrp) = PeekContext;
      KeClearEvent((PRKEVENT)&v15[2].ReservePointer);
    }
    ExReleaseFastMutex((PFAST_MUTEX)&v15[1]);
    IofCompleteRequest(v21, 0);
    ObjectArray[1] = &v15[2].ReservePointer;
    if ( v16 )
    {
      if ( v16->HighPart < 0 )
      {
        v43 = MEMORY[0xFFFFF78000000008] - v14;
        v16->QuadPart = MEMORY[0xFFFFF78000000008] - v14;
        if ( v43 > 0 )
          v16->QuadPart = 0;
      }
    }
    v44 = FsRtlCancellableWaitForMultipleObjects(2u, ObjectArray, WaitAny, v16, 0, 0);
    Flink_high = v44;
    if ( v44 == 258 )
      break;
    if ( !v44 )
    {
      if ( (byte_1800404C3 & 1) != 0 )
        McTemplateU0s_EtwWriteTransfer(v18, MessageSup_c2189, "FltSendMessage");
      Flink_high = -1073741769;
      goto LABEL_5;
    }
    if ( v44 == -1073741749 )
    {
      if ( (byte_1800404C3 & 1) != 0 )
      {
        v53 = MessageSup_c2197;
LABEL_115:
        McTemplateU0s_EtwWriteTransfer(v18, v53, "FltSendMessage");
      }
      goto LABEL_5;
    }
LABEL_58:
    if ( v16 )
    {
      if ( v16->HighPart < 0 )
      {
        v45 = MEMORY[0xFFFFF78000000008] - v14;
        v16->QuadPart = MEMORY[0xFFFFF78000000008] - v14;
        if ( v45 > 0 )
          v16->QuadPart = 0;
      }
    }
  }
  if ( (byte_1800404C3 & 1) != 0 )
  {
    v53 = MessageSup_c2176;
    goto LABEL_115;
  }
LABEL_5:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v67 )
    ObfDereferenceObject(v67);
  if ( (unsigned int)dword_18003DAA8 > 5 )
  {
    HighLimit = 0;
    ReplyLength = 0;
    IoGetStackLimits((PULONG_PTR)&ReplyLength, &HighLimit);
    if ( (unsigned __int64)((char *)&HighLimit - (char *)ReplyLength) < 0x200 )
    {
      _InterlockedIncrement(&dword_18003FFB0);
    }
    else
    {
      v12 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart);
      FltpTelemetryFltSendMessage(Flink_high, Filter, v12 / PerformanceFrequency.QuadPart, Timeout);
    }
  }
  return Flink_high;
}

```

## disassembly

```asm
0x180019ea0  mov     dword ptr [rsp+Size], r9d
0x180019ea5  mov     [rsp+Src], r8
0x180019eaa  mov     [rsp+arg_0], rcx
0x180019eaf  push    rbx
0x180019eb0  push    rsi
0x180019eb1  push    rdi
0x180019eb2  push    r12
0x180019eb4  push    r13
0x180019eb6  push    r14
0x180019eb8  push    r15
0x180019eba  sub     rsp, 110h
0x180019ec1  mov     r13d, r9d
0x180019ec4  mov     rbx, rdx
0x180019ec7  xor     r15d, r15d
0x180019eca  mov     [rsp+148h+var_F0], r15
0x180019ecf  mov     [rsp+148h+Object], r15
0x180019ed4  xor     edx, edx; Val
0x180019ed6  mov     r8d, 48h ; 'H'; Size
0x180019edc  lea     rcx, [rsp+148h+var_98]; void *
0x180019ee4  call    memset
0x180019ee9  mov     [rsp+148h+var_A8], r15
0x180019ef1  mov     [rsp+148h+PeekContext], r15d
0x180019ef6  xorps   xmm0, xmm0
0x180019ef9  movups  xmmword ptr [rsp+148h+ObjectArray], xmm0
0x180019efe  mov     [rsp+148h+var_110], r15d
0x180019f03  xor     ecx, ecx; PerformanceFrequency
0x180019f05  call    cs:__imp_KeQueryPerformanceCounter
0x180019f0c  nop     dword ptr [rax+rax+00h]
0x180019f11  mov     [rsp+148h+var_48], rax
0x180019f19  mov     rdi, [rsp+148h+ReplyLength]
0x180019f21  test    rdi, rdi
0x180019f24  jnz     loc_18001A5CD
0x180019f2a  call    cs:__imp_KeEnterCriticalRegion
0x180019f31  nop     dword ptr [rax+rax+00h]
0x180019f36  mov     rcx, [rsp+148h+arg_0]
0x180019f3e  add     rcx, 2B0h
0x180019f45  xor     edx, edx
0x180019f47  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x180019f4e  nop     dword ptr [rax+rax+00h]
0x180019f53  mov     rsi, rax
0x180019f56  mov     rcx, [rbx]
0x180019f59  test    rcx, rcx
0x180019f5c  jz      loc_18001A7BC
0x180019f62  mov     edi, r15d
0x180019f65  mov     rcx, [rcx+8]; Object
0x180019f69  mov     [rsp+148h+Object], rcx
0x180019f6e  call    cs:__imp_ObfReferenceObject
0x180019f75  nop     dword ptr [rax+rax+00h]
0x180019f7a  mov     r12d, 0C0000037h
0x180019f80  xor     edx, edx
0x180019f82  mov     rcx, rsi
0x180019f85  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x180019f8c  nop     dword ptr [rax+rax+00h]
0x180019f91  call    cs:__imp_KeLeaveCriticalRegion
0x180019f98  nop     dword ptr [rax+rax+00h]
0x180019f9d  mov     r8d, 7D7h
0x180019fa3  xor     r9d, r9d
0x180019fa6  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180019fad  mov     ecx, edi
0x180019faf  call    FltpDbgStatus
0x180019fb4  test    eax, eax
0x180019fb6  jns     loc_18001A08E
0x180019fbc  mov     rcx, [rsp+148h+Object]; Object
0x180019fc1  test    rcx, rcx
0x180019fc4  jz      short loc_180019FD2
0x180019fc6  call    cs:__imp_ObfDereferenceObject
0x180019fcd  nop     dword ptr [rax+rax+00h]
0x180019fd2  mov     rcx, [rsp+148h+var_A8]; Object
0x180019fda  test    rcx, rcx
0x180019fdd  jnz     loc_18001A47F
0x180019fe3  cmp     cs:dword_18003DAA8, 5
0x180019fea  jbe     loc_18001A078
0x180019ff0  mov     [rsp+148h+HighLimit], r15
0x180019ff8  mov     [rsp+148h+ReplyLength], r15
0x18001a000  lea     rdx, [rsp+148h+HighLimit]; HighLimit
0x18001a008  lea     rcx, [rsp+148h+ReplyLength]; LowLimit
0x18001a010  call    cs:__imp_IoGetStackLimits
0x18001a017  nop     dword ptr [rax+rax+00h]
0x18001a01c  lea     rax, [rsp+148h+HighLimit]
0x18001a024  sub     rax, [rsp+148h+ReplyLength]
0x18001a02c  cmp     rax, 200h
0x18001a032  jb      loc_18001AA10
0x18001a038  xor     ecx, ecx; PerformanceFrequency
0x18001a03a  call    cs:__imp_KeQueryPerformanceCounter
0x18001a041  nop     dword ptr [rax+rax+00h]
0x18001a046  sub     rax, [rsp+148h+var_48]
0x18001a04e  imul    rax, 3E8h
0x18001a055  cqo
0x18001a057  idiv    qword ptr cs:PerformanceFrequency
0x18001a05e  mov     r8, rax
0x18001a061  mov     r9, [rsp+148h+Timeout]
0x18001a069  mov     rdx, [rsp+148h+arg_0]
0x18001a071  mov     ecx, edi
0x18001a073  call    FltpTelemetryFltSendMessage
0x18001a078  mov     eax, edi
0x18001a07a  add     rsp, 110h
0x18001a081  pop     r15
0x18001a083  pop     r14
0x18001a085  pop     r13
0x18001a087  pop     r12
0x18001a089  pop     rdi
0x18001a08a  pop     rsi
0x18001a08b  pop     rbx
0x18001a08c  retn
0x18001a08e  mov     rbx, r15
0x18001a091  mov     [rsp+148h+var_E8], rbx
0x18001a096  mov     [rsp+148h+var_B0], r15
0x18001a09e  mov     r14, [rsp+148h+Object]
0x18001a0a3  add     r14, 60h ; '`'
0x18001a0a7  mov     [rsp+148h+Csq], r14
0x18001a0ac  lea     eax, [r13+10h]
0x18001a0b0  mov     [rsp+148h+PeekContext], eax
0x18001a0b4  mov     rax, [rsp+148h+Timeout]
0x18001a0bc  test    rax, rax
0x18001a0bf  jnz     loc_18001A490
0x18001a0c5  mov     rsi, r15
0x18001a0c8  mov     [rsp+148h+var_D8], r15
0x18001a0cd  mov     rax, [rsp+148h+Object]
0x18001a0d2  add     rax, 138h
0x18001a0d8  mov     [rsp+148h+ObjectArray], rax
0x18001a0dd  lea     rax, [r14+98h]
0x18001a0e4  mov     [rsp+148h+ObjectArray+8], rax
0x18001a0ec  mov     [rsp+148h+Irp], r15; Irp
0x18001a0f1  mov     [rsp+148h+WaitBlockArray], r15; WaitBlockArray
0x18001a0f6  mov     r9, rsi; Timeout
0x18001a0f9  mov     r8d, 1; WaitType
0x18001a0ff  lea     rdx, [rsp+148h+ObjectArray]; ObjectArray
0x18001a104  mov     ecx, 2; Count
0x18001a109  call    cs:__imp_FsRtlCancellableWaitForMultipleObjects
0x18001a110  nop     dword ptr [rax+rax+00h]
0x18001a115  mov     edi, eax
0x18001a117  cmp     eax, 102h
0x18001a11c  jz      loc_18001A7CA
0x18001a122  test    eax, eax
0x18001a124  jz      loc_18001A7EA
0x18001a12a  cmp     eax, 0C000004Bh
0x18001a12f  jz      loc_18001A810
0x18001a135  lea     rdx, [rsp+148h+PeekContext]; PeekContext
0x18001a13a  mov     rcx, r14; Csq
0x18001a13d  call    cs:__imp_IoCsqRemoveNextIrp
0x18001a144  nop     dword ptr [rax+rax+00h]
0x18001a149  mov     r13, rax
0x18001a14c  mov     [rsp+148h+var_C0], rax
0x18001a154  test    rax, rax
0x18001a157  jz      loc_18001A599
0x18001a15d  mov     r12, [rax+0B8h]
0x18001a164  mov     [rsp+148h+var_B8], r12
0x18001a16c  mov     edx, [rsp+148h+PeekContext]; Length
0x18001a170  cmp     [r12+8], edx
0x18001a175  jb      loc_18001A4C7
0x18001a17b  mov     edi, r15d
0x18001a17e  test    cs:byte_1800404C3, 1
0x18001a185  jnz     loc_18001A830
0x18001a18b  xor     sil, sil
0x18001a18e  mov     [rsp+148h+var_118], sil
0x18001a193  lea     r14, [r13+8]
0x18001a197  mov     [rsp+148h+var_E0], r14
0x18001a19c  cmp     qword ptr [r14], 0
0x18001a1a0  jnz     loc_18001A359
0x18001a1a6  mov     [rsp+148h+WaitBlockArray], r15; Irp
0x18001a1ab  mov     r9b, 1; ChargeQuota
0x18001a1ae  xor     r8d, r8d; SecondaryBuffer
0x18001a1b1  mov     rcx, [r13+70h]; VirtualAddress
0x18001a1b5  call    cs:__imp_IoAllocateMdl
0x18001a1bc  nop     dword ptr [rax+rax+00h]
0x18001a1c1  mov     [r14], rax
0x18001a1c4  test    rax, rax
0x18001a1c7  jnz     loc_18001A3F7
0x18001a1cd  mov     edi, 0C000009Ah
0x18001a1d2  xor     r9d, r9d
0x18001a1d5  mov     r8d, 919h
0x18001a1db  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18001a1e2  mov     ecx, edi
0x18001a1e4  call    FltpDbgStatus
0x18001a1e9  test    eax, eax
0x18001a1eb  jns     short loc_18001A25F
0x18001a1ed  test    sil, sil
0x18001a1f0  jnz     loc_18001A94E
0x18001a1f6  cmp     edi, 0C000009Ah
0x18001a1fc  jz      loc_18001A96D
0x18001a202  mov     [r13+30h], edi
0x18001a206  mov     [r13+38h], r15
0x18001a20a  xor     edx, edx; PriorityBoost
0x18001a20c  mov     rcx, r13; Irp
0x18001a20f  call    cs:__imp_IofCompleteRequest
0x18001a216  nop     dword ptr [rax+rax+00h]
0x18001a21b  mov     rsi, [rsp+148h+var_D8]
0x18001a220  test    rsi, rsi
0x18001a223  mov     r14, [rsp+148h+Csq]
0x18001a228  mov     r12d, 0C0000037h
0x18001a22e  jz      loc_18001A0DD
0x18001a234  cmp     dword ptr [rsi+4], 0
0x18001a238  jge     loc_18001A0DD
0x18001a23e  mov     rax, ds:0FFFFF78000000008h
0x18001a248  sub     rax, rbx
0x18001a24b  mov     [rsi], rax
0x18001a24e  test    rax, rax
0x18001a251  jle     loc_18001A0DD
0x18001a257  mov     [rsi], r15
0x18001a25a  jmp     loc_18001A0DD
0x18001a25f  mov     rsi, [rsp+148h+ReplyBuffer]
0x18001a267  xor     edx, edx; Val
0x18001a269  test    rsi, rsi
0x18001a26c  jz      loc_18001A996
0x18001a272  mov     r8d, 48h ; 'H'; Size
0x18001a278  lea     rcx, [rsp+148h+var_98]; void *
0x18001a280  call    memset
0x18001a285  mov     [rsp+148h+var_58], 1
0x18001a290  mov     rax, [rsp+148h+Object]
0x18001a295  mov     ecx, 1
0x18001a29a  lock xadd [rax+130h], rcx
0x18001a2a3  inc     rcx
0x18001a2a6  mov     [rsp+148h+var_88], rcx
0x18001a2ae  mov     [rsp+148h+var_68], rsi
0x18001a2b6  mov     edi, [rsp+148h+var_110]
0x18001a2ba  mov     [rsp+148h+var_60], edi
0x18001a2c1  xor     r8d, r8d; State
0x18001a2c4  xor     edx, edx; Type
0x18001a2c6  lea     rcx, [rsp+148h+Event]; Event
0x18001a2ce  call    cs:__imp_KeInitializeEvent
0x18001a2d5  nop     dword ptr [rax+rax+00h]
0x18001a2da  mov     rcx, [rsp+148h+var_B0]
0x18001a2e2  mov     rax, [rsp+148h+var_88]
0x18001a2ea  mov     [rcx+8], rax
0x18001a2ee  lea     eax, [rdi+10h]
0x18001a2f1  mov     [rcx], eax
0x18001a2f3  mov     rdi, [r12+30h]
0x18001a2f8  mov     [rsp+148h+var_A8], rdi
0x18001a300  mov     rcx, rdi; Object
0x18001a303  call    cs:__imp_ObfReferenceObject
0x18001a30a  nop     dword ptr [rax+rax+00h]
0x18001a30f  mov     rsi, [rdi+20h]
0x18001a313  test    cs:byte_1800404C3, 1
0x18001a31a  jnz     loc_18001A89B
0x18001a320  add     rsi, 10h
0x18001a324  mov     rcx, rsi; FastMutex
0x18001a327  call    cs:__imp_ExAcquireFastMutex
0x18001a32e  nop     dword ptr [rax+rax+00h]
0x18001a333  test    byte ptr [rsi+48h], 1
0x18001a337  jnz     loc_18001A8BB
0x18001a33d  add     dword ptr [rsi+48h], 2
0x18001a341  lea     rax, [rsi+38h]
0x18001a345  mov     rcx, [rax+8]
0x18001a349  cmp     [rcx], rax
0x18001a34c  jz      loc_18001A5F2
0x18001a352  mov     ecx, 3
0x18001a357  int     29h; Win8: RtlFailFast(ecx)
0x18001a359  mov     rcx, [r14]; MemoryDescriptorList
0x18001a35c  test    byte ptr [rcx+0Ah], 5
0x18001a360  jnz     loc_18001A734
0x18001a366  mov     dword ptr [rsp+148h+Irp], 40000010h; Priority
0x18001a36e  mov     dword ptr [rsp+148h+WaitBlockArray], r15d; BugCheckOnFailure
0x18001a373  xor     r9d, r9d; RequestedAddress
0x18001a376  xor     edx, edx; AccessMode
0x18001a378  mov     r8d, 1; CacheType
0x18001a37e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18001a385  nop     dword ptr [rax+rax+00h]
0x18001a38a  mov     [rsp+148h+var_F8], rax
0x18001a38f  mov     [rsp+148h+var_B0], rax
0x18001a397  test    rax, rax
0x18001a39a  jz      loc_18001A1CD
0x18001a3a0  mov     rcx, [rsp+148h+Src]
0x18001a3a8  call    cs:__imp_MmIsKernelAddress
0x18001a3af  nop     dword ptr [rax+rax+00h]
0x18001a3b4  test    al, al
0x18001a3b6  jz      loc_18001A84F
0x18001a3bc  mov     r8d, dword ptr [rsp+148h+Size]; Size
0x18001a3c4  mov     rcx, [rsp+148h+var_F8]
0x18001a3c9  add     rcx, 10h; void *
0x18001a3cd  mov     rdx, [rsp+148h+Src]; Src
0x18001a3d5  call    memmove
0x18001a3da  mov     rax, [rsp+148h+var_F8]
0x18001a3df  mov     [rax], r15d
0x18001a3e2  mov     [rax+8], r15
0x18001a3e6  mov     [r13+30h], r15d
0x18001a3ea  mov     eax, [rsp+148h+PeekContext]
0x18001a3ee  mov     [r13+38h], rax
0x18001a3f2  jmp     loc_18001A1D2
0x18001a3f7  movzx   esi, byte ptr [r13+40h]
0x18001a3fc  mov     r14, rax
0x18001a3ff  mov     rcx, r13; Irp
0x18001a402  call    cs:__imp_IoGetRequestorProcess
0x18001a409  nop     dword ptr [rax+rax+00h]
0x18001a40e  mov     rdx, rax; Process
0x18001a411  mov     r9d, 1; Operation
0x18001a417  movzx   r8d, sil; AccessMode
0x18001a41b  mov     rcx, r14; MemoryDescriptorList
0x18001a41e  call    cs:__imp_MmProbeAndLockProcessPages
0x18001a425  nop     dword ptr [rax+rax+00h]
0x18001a42a  mov     eax, 8DDh
0x18001a42f  jmp     short loc_18001A450
0x18001a431  mov     edi, eax
0x18001a433  xor     r15d, r15d
0x18001a436  mov     eax, 8DDh
0x18001a43b  mov     rbx, [rsp+148h+var_E8]
0x18001a440  mov     r13, [rsp+148h+var_C0]
0x18001a448  mov     r12, [rsp+148h+var_B8]
0x18001a450  mov     sil, 1
0x18001a453  mov     [rsp+148h+var_118], sil
0x18001a458  xor     r9d, r9d
  ... truncated ...
```
