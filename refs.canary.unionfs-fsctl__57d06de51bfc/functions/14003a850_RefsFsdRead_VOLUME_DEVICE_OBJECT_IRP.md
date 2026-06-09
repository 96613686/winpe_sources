# RefsFsdRead(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14003a850`
- end: `0x14003b3dd`
- name: `?RefsFsdRead@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2957`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000ab80`
- `0x140039b60`
- `0x14003a520`
- `0x14003a850`
- `0x14003b3f0`
- `0x14003ec10`
- `0x140041a40`
- `0x140041b40`
- `0x14008dbd0`
- `0x14008f8b0`
- `0x14009cb40`
- `0x1400a5fa0`
- `0x1400a648c`
- `0x1400ca788`
- `0x1400ea204`
- `0x1400fac08`
- `0x1400fac44`
- `0x1400fac7c`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x14032aa00`
- `0x1403389e4`
- `0x140338ee4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14003a917`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003a917`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003ae07`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003ae07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003aef3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003b17f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003aef3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003b17f`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14003af0d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14003af0d`
- `ntoskrnl!IoGetStackLimits` at `0x14003afed`
- `ntoskrnl!IoGetStackLimits` at `0x14003afed`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003b158`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003b158`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b164`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b1bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b164`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b1bd`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003ab8f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003aba9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003b315`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003b32f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003ab8f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003aba9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003b315`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003b32f`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003aa14`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003aa50`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003aa14`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003aa50`
- `ntoskrnl!DbgPrintEx` at `0x14003ab29`
- `ntoskrnl!DbgPrintEx` at `0x14003b2af`
- `ntoskrnl!DbgPrintEx` at `0x14003ab29`
- `ntoskrnl!DbgPrintEx` at `0x14003b2af`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003ab55`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003b2db`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003ab55`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003b2db`
- `ntoskrnl!_strnicmp` at `0x14003abd4`
- `ntoskrnl!_strnicmp` at `0x14003b35a`
- `ntoskrnl!_strnicmp` at `0x14003abd4`
- `ntoskrnl!_strnicmp` at `0x14003b35a`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003abb8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003b33e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003abb8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003b33e`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003af5b`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003b13a`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003af5b`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003b13a`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x14003af7f`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x14003af7f`
- `ntoskrnl!IoWithinStackLimits` at `0x14003a92e`
- `ntoskrnl!IoWithinStackLimits` at `0x14003a92e`
- `ntoskrnl!KeInitializeEvent` at `0x14003adbb`
- `ntoskrnl!KeInitializeEvent` at `0x14003adbb`
- `HAL!KeQueryPerformanceCounter` at `0x14003af30`
- `HAL!KeQueryPerformanceCounter` at `0x14003af30`

## string_xrefs

- `0x14003aaf3`: `Read.c`
- `0x14003b097`: `Read.c`
- `0x14003b279`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsFsdRead(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PFILE_OBJECT FileObject; // rdx
  char v4; // cl
  struct _SCB *FsContext; // r15
  _BYTE *FsContext2; // rcx
  __int64 v7; // rcx
  __int64 v8; // r12
  bool v9; // bl
  ULONG_PTR TopLevelIrp; // rdi
  bool v11; // cl
  __int64 v12; // rax
  void *v13; // rsp
  char *NPagedPerProcessorLookaside; // rbx
  struct REFS_IO_CONTEXT *v15; // rsi
  BOOLEAN IsOperationSynchronous; // al
  struct _IRP_CONTEXT *v17; // rax
  volatile unsigned int v18; // ebx
  struct _KPROCESS *v19; // rbx
  PEPROCESS v20; // rax
  const char *v21; // rax
  __int64 v22; // rcx
  _OWORD *v24; // rax
  _OWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned int v29; // eax
  int v30; // ecx
  __int64 v31; // rax
  unsigned int v32; // edi
  int v33; // r12d
  __int64 v34; // r15
  int v35; // edx
  bool v36; // r8
  unsigned int v37; // eax
  struct _IRP *v38; // r8
  struct REFS_IO_CONTEXT *v39; // rdx
  struct _IRP_CONTEXT *v40; // rcx
  volatile unsigned int v41; // ebx
  struct _KPROCESS *v42; // rbx
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v45; // rcx
  char v46; // [rsp+0h] [rbp-680h] BYREF
  char v47; // [rsp+680h] [rbp+0h]
  unsigned int v48; // [rsp+684h] [rbp+4h]
  ULONG v49; // [rsp+688h] [rbp+8h]
  struct _IRP_CONTEXT *v50; // [rsp+690h] [rbp+10h] BYREF
  __int64 v51; // [rsp+698h] [rbp+18h] BYREF
  __int128 v52; // [rsp+6A0h] [rbp+20h] BYREF
  __int64 v53; // [rsp+6B0h] [rbp+30h]
  struct _IRP_CONTEXT *v54; // [rsp+6B8h] [rbp+38h]
  unsigned __int64 HighLimit; // [rsp+6C0h] [rbp+40h] BYREF
  unsigned __int64 LowLimit[2]; // [rsp+6C8h] [rbp+48h] BYREF
  __int64 *v57; // [rsp+6D8h] [rbp+58h]
  ULONG *p_Flags; // [rsp+6E0h] [rbp+60h]
  __int64 v59; // [rsp+6E8h] [rbp+68h]
  _QWORD v60[4]; // [rsp+6F0h] [rbp+70h] BYREF
  _DWORD v61[32]; // [rsp+710h] [rbp+90h] BYREF
  __int64 v62; // [rsp+790h] [rbp+110h]
  __int64 v63; // [rsp+798h] [rbp+118h]
  __int128 v64; // [rsp+7A0h] [rbp+120h]
  _DWORD v65[176]; // [rsp+7B0h] [rbp+130h] BYREF
  __int128 v66; // [rsp+A70h] [rbp+3F0h] BYREF

  LowLimit[1] = (unsigned __int64)a2;
  v52 = 0;
  v53 = 0;
  v51 = 0;
  v66 = 0;
  v60[0] = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v4 = 1;
  FsContext = (struct _SCB *)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = FileObject->FsContext2;
    if ( !FsContext2 )
      goto LABEL_6;
    v4 = FsContext2[80];
  }
  if ( ((v4 - 2) & 0xFC) != 0 || v4 == 3 )
  {
LABEL_108:
    RefsCompleteRequest(0, a2, -1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741808 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741808, "Read.c", 136);
      v41 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741808
        || RefsStatusBreakOnWin32Error && v41 == RtlNtStatusToDosErrorNoTeb(-1073741808) )
      {
        v42 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v42 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (CurrentProcess = IoGetCurrentProcess(),
               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
        {
          __int2c();
        }
      }
      v45 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v45) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v45 + 8) = -1073741808;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v45 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"Read.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v45 + 24) = 136;
    }
    return 3221225488LL;
  }
LABEL_6:
  v7 = *(_QWORD *)(*((_QWORD *)FsContext + 17) + 88LL);
  if ( *(_QWORD *)(v7 + 256) == 1313 && *(_QWORD *)(v7 + 248) == 1024 || !FsContext )
    goto LABEL_108;
  v8 = MsCaptureTopLevelContext();
  v59 = v8;
  v9 = 0;
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
    v9 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
  v11 = 1;
  if ( TopLevelIrp )
  {
    if ( TopLevelIrp > 0xFFFF )
    {
      if ( v9 )
      {
        v12 = *(_QWORD *)(TopLevelIrp + 16);
        if ( !v12 || (*(_DWORD *)(v12 + 4) & 0x200) == 0 )
          goto LABEL_23;
      }
      v11 = TopLevelIrp != 2147483650;
    }
    else
    {
      v11 = 0;
    }
  }
  DWORD1(v52) = 0;
  *((_QWORD *)&v52 + 1) = TopLevelIrp;
  v53 = 0;
  LOBYTE(v52) = v11;
  if ( v9 )
  {
    BYTE1(v52) = 1;
    BYTE2(v52) = *(_BYTE *)(TopLevelIrp + 2);
  }
  else
  {
    *(_WORD *)((char *)&v52 + 1) = 0;
  }
  TopLevelIrp = (ULONG_PTR)&v52;
LABEL_23:
  if ( ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0
     || (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x8000LL) != 0)
    && ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0 && (*((_DWORD *)FsContext + 38) & 0x10) != 0
     || *(struct _SCB **)(*((_QWORD *)FsContext + 18) + 40LL) == FsContext) )
  {
    KeEnterCriticalRegion();
    if ( (__int128 *)TopLevelIrp == &v52 )
      RefsSetTopLevelWithoutIrpContext((struct _TOP_LEVEL_CONTEXT *)TopLevelIrp);
    RefsPagingFileIo(a2, FsContext);
    if ( (__int128 *)TopLevelIrp == &v52 )
      RefsRestoreTopLevelIrpWithoutContext();
    MsRestoreTopLevelContext(v8);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 259);
    }
    return 259;
  }
  else
  {
    if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
    {
      v13 = alloca(1664);
      NPagedPerProcessorLookaside = &v46;
      v47 = 1;
LABEL_31:
      v50 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
      v15 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
      IsOperationSynchronous = IoIsOperationSynchronous(a2);
      RefsInitializeIrpContext(a2, IsOperationSynchronous, 0, &v50);
      v17 = v50;
      if ( v47 )
        *((_QWORD *)v50 + 1) &= ~0x80000uLL;
      else
        *((_QWORD *)v50 + 1) |= 0x80000uLL;
      *((_QWORD *)v17 + 1) |= 0x10uLL;
      *((_WORD *)v17 + 1) = 1664;
      p_Flags = &a2->Flags;
      v49 = a2->Flags & 2;
      memset(v61, 0, 0x40u);
      memset(&v65[112], 0, 0x100u);
      memset(&v61[16], 0, 0x40u);
      v62 = 0;
      v63 = 0;
      v64 = 0;
      memset(v65, 0, 0x1C0u);
      v65[113] = 0;
      v24 = NPagedPerProcessorLookaside + 800;
      v25 = v61;
      v26 = 6;
      do
      {
        *v24 = *v25;
        v24[1] = v25[1];
        v24[2] = v25[2];
        v24[3] = v25[3];
        v24[4] = v25[4];
        v24[5] = v25[5];
        v24[6] = v25[6];
        v24[7] = v25[7];
        v24 += 8;
        v25 += 8;
        --v26;
      }
      while ( v26 );
      *v24 = *v25;
      v24[1] = v25[1];
      v24[2] = v25[2];
      v24[3] = v25[3];
      v24[4] = v25[4];
      v24[5] = v25[5];
      if ( (*((_BYTE *)v50 + 8) & 0x10) != 0 )
        *(_DWORD *)v15 |= 0x20000u;
      if ( v49 )
        *(_DWORD *)v15 |= 2u;
      KeInitializeEvent((PRKEVENT)(NPagedPerProcessorLookaside + 808), NotificationEvent, 0);
      *((_DWORD *)NPagedPerProcessorLookaside + 398) = 0;
      *((_QWORD *)NPagedPerProcessorLookaside + 200) = 0;
      *((_DWORD *)NPagedPerProcessorLookaside + 399) = 1;
      *((_QWORD *)NPagedPerProcessorLookaside + 108) = v50;
      v60[1] = NPagedPerProcessorLookaside + 800;
      if ( !*(_QWORD *)(TopLevelIrp + 16) )
      {
        *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
        *(_QWORD *)(TopLevelIrp + 16) = NPagedPerProcessorLookaside;
        *((_QWORD *)NPagedPerProcessorLookaside + 1) |= 0x100000uLL;
        IoSetTopLevelIrp((PIRP)TopLevelIrp);
      }
      v27 = *(_QWORD *)(TopLevelIrp + 16);
      *((_QWORD *)NPagedPerProcessorLookaside + 13) = v27;
      v57 = (__int64 *)(NPagedPerProcessorLookaside + 672);
      *((_QWORD *)NPagedPerProcessorLookaside + 84) = v8;
      if ( *(_QWORD *)(v27 + 344) )
      {
        MsRestoreTopLevelContext(v8);
        v28 = *((_QWORD *)NPagedPerProcessorLookaside + 1);
        if ( (v28 & 0x100000000LL) != 0 )
        {
          *((_QWORD *)NPagedPerProcessorLookaside + 1) = v28 | 0x200000000LL;
          return 3221227528LL;
        }
        else
        {
          *((_QWORD *)NPagedPerProcessorLookaside + 1) = v28 | 0x8000;
          v29 = (unsigned __int8)NPagedPerProcessorLookaside[40];
          if ( (unsigned __int8)v29 <= 0x12u )
          {
            v30 = 262685;
            if ( _bittest(&v30, v29) )
            {
              v31 = *((_QWORD *)NPagedPerProcessorLookaside + 8);
              if ( v31 )
              {
                if ( *(_BYTE *)(v31 + 10496)
                  && (*((_DWORD *)NPagedPerProcessorLookaside + 1) & 0x400) == 0
                  && (*((_DWORD *)NPagedPerProcessorLookaside + 2) & 0x10000) == 0 )
                {
                  *((_QWORD *)NPagedPerProcessorLookaside + 86) = 7;
                }
              }
            }
          }
          *((_DWORD *)NPagedPerProcessorLookaside + 399) &= ~1u;
          RefsCompleteRequest((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2, -1073739768);
          return 3221227528LL;
        }
      }
      v60[3] = &a2->Flags;
      v54 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
      v60[2] = NPagedPerProcessorLookaside + 672;
      v32 = 0;
      v33 = 0;
      v49 = 0;
      KeEnterCriticalRegion();
      LODWORD(v50) = IoPropagateActivityIdToThread(a2, &v66, v60);
      if ( *(_BYTE *)(*((_QWORD *)FsContext + 18) + 10496LL) )
        *((LARGE_INTEGER *)NPagedPerProcessorLookaside + 86) = KeQueryPerformanceCounter(0);
      v34 = v59;
      while ( 1 )
      {
        if ( v32 == -1073741432 )
        {
          RefsCheckpointForLogFileFull((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside);
        }
        else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v32) )
        {
          LODWORD(v51) = 8;
          HIDWORD(v51) = v32;
          CcErrorCallbackRoutine(&v51);
        }
        if ( !NPagedPerProcessorLookaside )
          goto LABEL_91;
        if ( v33 )
          RefsInitializeIoContext((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v15, v36, (*p_Flags & 2) != 0);
        RefsPreRequestProcessingExtend((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v35);
        *v57 = v34;
        if ( (NPagedPerProcessorLookaside[41] & 4) != 0 )
        {
          v37 = RefsCompleteMdl((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2);
        }
        else
        {
          if ( !RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled )
          {
            v38 = a2;
            v39 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
            v40 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
LABEL_89:
            v37 = RefsCommonRead(v40, v39, v38);
            goto LABEL_90;
          }
          HighLimit = 0;
          LowLimit[0] = 0;
          IoGetStackLimits(LowLimit, &HighLimit);
          v38 = a2;
          v39 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
          v40 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
          if ( (unsigned __int64)&LowLimit[-1] - LowLimit[0] > 0x3000 )
            goto LABEL_89;
          v37 = RefsCommonIoOnNewStack((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v15, a2);
        }
LABEL_90:
        v48 = v37;
        v32 = v37;
LABEL_91:
        if ( v32 )
        {
          v49 = ++v33;
          if ( v32 == -1073741608
            || v32 == -1073741400
            || v32 == -1073741432
            || (unsigned __int8)CcIsCacheManagerCallbackNeeded(v32) )
          {
            continue;
          }
        }
        if ( (int)v50 >= 0 )
          IoClearActivityIdThread(v60[0]);
        KeLeaveCriticalRegion();
        MsRestoreTopLevelContext(v34);
        return v32;
      }
    }
    v47 = 0;
    NPagedPerProcessorLookaside = (char *)RefsAllocateNPagedPerProcessorLookaside(RefsIrpAndIoContextLookasideList);
    if ( NPagedPerProcessorLookaside )
      goto LABEL_31;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221225626LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741670 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741670, "Read.c", 167);
      v18 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741670
        || RefsStatusBreakOnWin32Error && v18 == RtlNtStatusToDosErrorNoTeb(-1073741670) )
      {
        v19 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v19 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v20 = IoGetCurrentProcess(),
               v21 = (const char *)PsGetProcessImageFileName(v20),
               !_strnicmp(&RefsStatusBreakForImage, v21, 0xFu))) )
        {
          __int2c();
        }
      }
      v22 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v22) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v22 + 8) = -1073741670;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v22 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"Read.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v22 + 24) = 167;
    }
    MsRestoreTopLevelContext(v8);
    RefsCompleteReadWriteRequest(0, 0, a2, -1073741670);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14003a850  push    rbp
0x14003a852  push    rbx
0x14003a853  push    rsi
0x14003a854  push    rdi
0x14003a855  push    r12
0x14003a857  push    r13
0x14003a859  push    r14
0x14003a85b  push    r15
0x14003a85d  sub     rsp, 458h
0x14003a864  lea     rbp, [rsp+40h]
0x14003a869  mov     rax, cs:__security_cookie
0x14003a870  xor     rax, rbp
0x14003a873  mov     [rbp+450h+var_50], rax
0x14003a87a  mov     r14, rdx
0x14003a87d  mov     [rbp+450h+var_400], rdx
0x14003a881  xorps   xmm0, xmm0
0x14003a884  xor     eax, eax
0x14003a886  movups  [rbp+450h+var_430], xmm0
0x14003a88a  mov     [rbp+450h+var_420], rax
0x14003a88e  xor     r13d, r13d
0x14003a891  mov     [rbp+450h+var_438], r13
0x14003a895  movups  [rbp+450h+var_60], xmm0
0x14003a89c  mov     [rbp+450h+var_3E0], r13
0x14003a8a0  mov     rax, [rdx+0B8h]
0x14003a8a7  mov     rdx, [rax+30h]
0x14003a8ab  mov     cl, 1
0x14003a8ad  mov     r15, [rdx+18h]
0x14003a8b1  test    r15, r15
0x14003a8b4  jz      short loc_14003A8C3
0x14003a8b6  mov     rcx, [rdx+20h]
0x14003a8ba  test    rcx, rcx
0x14003a8bd  jz      short loc_14003A8D7
0x14003a8bf  movzx   ecx, byte ptr [rcx+50h]
0x14003a8c3  lea     eax, [rcx-2]
0x14003a8c6  test    al, 0FCh
0x14003a8c8  jnz     loc_14003B217
0x14003a8ce  cmp     cl, 3
0x14003a8d1  jz      loc_14003B217
0x14003a8d7  mov     rax, [r15+88h]
0x14003a8de  mov     rcx, [rax+58h]
0x14003a8e2  cmp     qword ptr [rcx+100h], 521h
0x14003a8ed  jnz     short loc_14003A900
0x14003a8ef  cmp     qword ptr [rcx+0F8h], 400h
0x14003a8fa  jz      loc_14003B217
0x14003a900  test    r15, r15
0x14003a903  jz      loc_14003B217
0x14003a909  call    MsCaptureTopLevelContext
0x14003a90e  mov     r12, rax
0x14003a911  mov     [rbp+450h+var_3E8], rax
0x14003a915  xor     bl, bl
0x14003a917  call    cs:__imp_IoGetTopLevelIrp
0x14003a91e  nop     dword ptr [rax+rax+00h]
0x14003a923  mov     rdi, rax
0x14003a926  mov     edx, 18h; RegionSize
0x14003a92b  mov     rcx, rax; RegionStart
0x14003a92e  call    cs:__imp_IoWithinStackLimits
0x14003a935  nop     dword ptr [rax+rax+00h]
0x14003a93a  test    eax, eax
0x14003a93c  jz      short loc_14003A958
0x14003a93e  test    dil, 3
0x14003a942  jnz     short loc_14003A958
0x14003a944  movzx   ebx, bl
0x14003a947  mov     esi, 1
0x14003a94c  cmp     dword ptr [rdi+4], 5346ABBAh
0x14003a953  cmovz   ebx, esi
0x14003a956  jmp     short loc_14003A95D
0x14003a958  mov     esi, 1
0x14003a95d  mov     cl, 1
0x14003a95f  test    rdi, rdi
0x14003a962  jz      short loc_14003A996
0x14003a964  cmp     rdi, 0FFFFh
0x14003a96b  ja      short loc_14003A971
0x14003a96d  xor     cl, cl
0x14003a96f  jmp     short loc_14003A996
0x14003a971  test    bl, bl
0x14003a973  jz      short loc_14003A987
0x14003a975  mov     rax, [rdi+10h]
0x14003a979  test    rax, rax
0x14003a97c  jz      short loc_14003A9BF
0x14003a97e  test    dword ptr [rax+4], 200h
0x14003a985  jz      short loc_14003A9BF
0x14003a987  movzx   ecx, cl
0x14003a98a  mov     eax, 80000002h
0x14003a98f  cmp     rdi, rax
0x14003a992  cmovz   ecx, r13d
0x14003a996  mov     dword ptr [rbp+450h+var_430+4], r13d
0x14003a99a  mov     qword ptr [rbp+450h+var_430+8], rdi
0x14003a99e  mov     [rbp+450h+var_420], r13
0x14003a9a2  mov     byte ptr [rbp+450h+var_430], cl
0x14003a9a5  test    bl, bl
0x14003a9a7  jz      short loc_14003A9B6
0x14003a9a9  mov     byte ptr [rbp+450h+var_430+1], 1
0x14003a9ad  movzx   eax, byte ptr [rdi+2]
0x14003a9b1  mov     byte ptr [rbp+450h+var_430+2], al
0x14003a9b4  jmp     short loc_14003A9BB
0x14003a9b6  mov     word ptr [rbp+450h+var_430+1], r13w
0x14003a9bb  lea     rdi, [rbp+450h+var_430]
0x14003a9bf  mov     rax, [r15+88h]
0x14003a9c6  mov     rcx, [rax+8]
0x14003a9ca  test    cl, 4
0x14003a9cd  jnz     short loc_14003A9E1
0x14003a9cf  mov     rax, [r15+88h]
0x14003a9d6  mov     rcx, [rax+8]
0x14003a9da  bt      rcx, 0Fh
0x14003a9df  jnb     short loc_14003AA11
0x14003a9e1  mov     rax, [r15+88h]
0x14003a9e8  mov     rcx, [rax+8]
0x14003a9ec  test    cl, 4
0x14003a9ef  jz      short loc_14003AA00
0x14003a9f1  mov     eax, [r15+98h]
0x14003a9f8  test    al, 10h
0x14003a9fa  jnz     loc_14003B17F
0x14003aa00  mov     rax, [r15+90h]
0x14003aa07  cmp     [rax+28h], r15
0x14003aa0b  jz      loc_14003B17F
0x14003aa11  mov     rcx, r14; Irp
0x14003aa14  call    cs:__imp_IoIsOperationSynchronous
0x14003aa1b  nop     dword ptr [rax+rax+00h]
0x14003aa20  test    al, al
0x14003aa22  jz      short loc_14003AA89
0x14003aa24  mov     eax, [r14+10h]
0x14003aa28  test    al, 2
0x14003aa2a  jz      short loc_14003AA89
0x14003aa2c  mov     eax, [rsp+490h+var_490]
0x14003aa2f  mov     eax, 680h
0x14003aa34  sub     rsp, rax
0x14003aa37  lea     rbx, [rsp+0B10h+var_AD0]
0x14003aa3c  mov     eax, [rbx]
0x14003aa3e  mov     [rbp+450h+var_450], 1
0x14003aa42  mov     [rbp+450h+var_440], rbx
0x14003aa46  lea     rsi, [rbx+320h]
0x14003aa4d  mov     rcx, r14; Irp
0x14003aa50  call    cs:__imp_IoIsOperationSynchronous
0x14003aa57  nop     dword ptr [rax+rax+00h]
0x14003aa5c  movzx   edx, al; unsigned __int8
0x14003aa5f  lea     r9, [rbp+450h+var_440]; struct _IRP_CONTEXT **
0x14003aa63  xor     r8d, r8d; unsigned __int8
0x14003aa66  mov     rcx, r14; Irp
0x14003aa69  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x14003aa6e  mov     rax, [rbp+450h+var_440]
0x14003aa72  cmp     [rbp+450h+var_450], r13b
0x14003aa76  jz      loc_14003AC4E
0x14003aa7c  and     qword ptr [rax+8], 0FFFFFFFFFFF7FFFFh
0x14003aa84  jmp     loc_14003AC56
0x14003aa89  mov     [rbp+450h+var_450], r13b
0x14003aa8d  mov     rcx, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; struct _NPAGED_LOOKASIDE_LIST *
0x14003aa94  call    ?RefsAllocateNPagedPerProcessorLookaside@@YAPEAXPEAU_NPAGED_LOOKASIDE_LIST@@@Z; RefsAllocateNPagedPerProcessorLookaside(_NPAGED_LOOKASIDE_LIST *)
0x14003aa99  mov     rbx, rax
0x14003aa9c  test    rax, rax
0x14003aa9f  jnz     short loc_14003AA42
0x14003aaa1  lea     rax, WPP_GLOBAL_Control
0x14003aaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aaaf  cmp     rcx, rax
0x14003aab2  jz      short loc_14003AADE
0x14003aab4  test    dword ptr [rcx+2Ch], 100h
0x14003aabb  jz      short loc_14003AADE
0x14003aabd  cmp     byte ptr [rcx+29h], 4
0x14003aac1  jb      short loc_14003AADE
0x14003aac3  mov     edx, 0Bh
0x14003aac8  mov     r9d, 0C000009Ah
0x14003aace  lea     r8, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids
0x14003aad5  mov     rcx, [rcx+18h]
0x14003aad9  call    WPP_SF_d
0x14003aade  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003aae5  test    al, al
0x14003aae7  jz      loc_14003AC2A
0x14003aaed  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x14003aaf3  lea     rdi, aReadC; "Read.c"
0x14003aafa  cmp     eax, 0C000009Ah
0x14003aaff  jnz     short loc_14003AB35
0x14003ab01  mov     r9, gs:188h
0x14003ab0a  mov     [rsp+490h+var_460], 0A7h
0x14003ab12  mov     [rsp+490h+var_468], rdi
0x14003ab17  mov     [rsp+490h+var_470], eax
0x14003ab1b  lea     r8, Format; "th%p %x %s:%i\n"
0x14003ab22  xor     edx, edx; Level
0x14003ab24  mov     ecx, 95h; ComponentId
0x14003ab29  call    cs:__imp_DbgPrintEx
0x14003ab30  nop     dword ptr [rax+rax+00h]
0x14003ab35  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x14003ab3b  mov     ebx, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x14003ab41  cmp     eax, 0C000009Ah
0x14003ab46  jz      short loc_14003AB69
0x14003ab48  test    ebx, ebx
0x14003ab4a  jz      loc_14003ABEC
0x14003ab50  mov     ecx, 0C000009Ah; Status
0x14003ab55  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14003ab5c  nop     dword ptr [rax+rax+00h]
0x14003ab61  cmp     ebx, eax
0x14003ab63  jnz     loc_14003ABEC
0x14003ab69  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x14003ab70  mov     rbx, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x14003ab77  test    rcx, rcx
0x14003ab7a  jz      short loc_14003ABEA
0x14003ab7c  mov     rax, gs:188h
0x14003ab85  cmp     rcx, rax
0x14003ab88  jnz     short loc_14003ABEC
0x14003ab8a  test    rbx, rbx
0x14003ab8d  jz      short loc_14003ABA0
0x14003ab8f  call    cs:__imp_IoGetCurrentProcess
0x14003ab96  nop     dword ptr [rax+rax+00h]
0x14003ab9b  cmp     rbx, rax
0x14003ab9e  jnz     short loc_14003ABEC
0x14003aba0  cmp     cs:?RefsStatusBreakForImage@@3PADA, r13b; char near * RefsStatusBreakForImage
0x14003aba7  jz      short loc_14003ABE4
0x14003aba9  call    cs:__imp_IoGetCurrentProcess
0x14003abb0  nop     dword ptr [rax+rax+00h]
0x14003abb5  mov     rcx, rax
0x14003abb8  call    cs:__imp_PsGetProcessImageFileName
0x14003abbf  nop     dword ptr [rax+rax+00h]
0x14003abc4  mov     rdx, rax; Str2
0x14003abc7  mov     r8d, 0Fh; MaxCount
0x14003abcd  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x14003abd4  call    cs:__imp__strnicmp
0x14003abdb  nop     dword ptr [rax+rax+00h]
0x14003abe0  test    eax, eax
0x14003abe2  jnz     short loc_14003ABEC
0x14003abe4  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x14003abea  int     2Ch; Windows NT - assertion failure
0x14003abec  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, esi; ulong RefsStatusNextQueueEntry
0x14003abf4  lea     ecx, [rsi+1]
0x14003abf7  and     ecx, 0FFFh
0x14003abfd  shl     rcx, 5
0x14003ac01  mov     rax, gs:188h
0x14003ac0a  lea     rdx, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x14003ac11  mov     [rcx+rdx], rax
0x14003ac15  mov     dword ptr [rcx+rdx+8], 0C000009Ah
0x14003ac1d  mov     [rcx+rdx+10h], rdi
0x14003ac22  mov     dword ptr [rcx+rdx+18h], 0A7h
0x14003ac2a  mov     rcx, r12
0x14003ac2d  call    MsRestoreTopLevelContext
0x14003ac32  mov     r9d, 0C000009Ah; int
0x14003ac38  mov     r8, r14; struct _IRP *
0x14003ac3b  xor     edx, edx; struct REFS_IO_CONTEXT *
0x14003ac3d  xor     ecx, ecx; struct _IRP_CONTEXT *
0x14003ac3f  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003ac44  mov     eax, 0C000009Ah
0x14003ac49  jmp     loc_14003B3B9
0x14003ac4e  or      qword ptr [rax+8], 80000h
0x14003ac56  or      qword ptr [rax+8], 10h
0x14003ac5b  mov     word ptr [rax+2], 680h
0x14003ac61  lea     rax, [r14+10h]
0x14003ac65  mov     [rbp+450h+var_3F0], rax
0x14003ac69  mov     eax, [rax]
0x14003ac6b  and     eax, 2
0x14003ac6e  mov     [rbp+450h+var_448], eax
0x14003ac71  xor     eax, eax
0x14003ac73  mov     [rbp+450h+var_3BC], eax
0x14003ac79  mov     [rbp+450h+var_387], eax
0x14003ac7f  mov     [rbp+450h+var_383], ax
0x14003ac86  mov     [rbp+450h+var_381], al
0x14003ac8c  xor     edx, edx; Val
0x14003ac8e  mov     r8d, 40h ; '@'; Size
0x14003ac94  lea     rcx, [rbp+450h+var_3C0]; void *
0x14003ac9b  call    memset
0x14003aca0  xor     edx, edx; Val
0x14003aca2  mov     r8d, 100h; Size
0x14003aca8  lea     rcx, [rbp+450h+var_160]; void *
0x14003acaf  call    memset
0x14003acb4  xor     eax, eax
0x14003acb6  mov     [rbp+450h+var_364], eax
0x14003acbc  mov     [rbp+450h+var_354], eax
0x14003acc2  xor     edx, edx; Val
0x14003acc4  mov     r8d, 40h ; '@'; Size
0x14003acca  lea     rcx, [rbp+450h+var_380]; void *
0x14003acd1  call    memset
0x14003acd6  mov     [rbp+450h+var_340], r13
0x14003acdd  mov     [rbp+450h+var_338], r13
0x14003ace4  xorps   xmm0, xmm0
0x14003ace7  movups  [rbp+450h+var_330], xmm0
0x14003acee  xor     edx, edx; Val
0x14003acf0  mov     r8d, 1C0h; Size
0x14003acf6  lea     rcx, [rbp+450h+var_320]; void *
0x14003acfd  call    memset
0x14003ad02  xor     eax, eax
0x14003ad04  mov     [rbp+450h+var_15C], eax
0x14003ad0a  mov     rax, rsi
0x14003ad0d  lea     rcx, [rbp+450h+var_3C0]
0x14003ad14  mov     edx, 6
0x14003ad19  movups  xmm0, xmmword ptr [rcx]
0x14003ad1c  movups  xmmword ptr [rax], xmm0
0x14003ad1f  movups  xmm1, xmmword ptr [rcx+10h]
0x14003ad23  movups  xmmword ptr [rax+10h], xmm1
0x14003ad27  movups  xmm0, xmmword ptr [rcx+20h]
0x14003ad2b  movups  xmmword ptr [rax+20h], xmm0
0x14003ad2f  movups  xmm1, xmmword ptr [rcx+30h]
0x14003ad33  movups  xmmword ptr [rax+30h], xmm1
0x14003ad37  movups  xmm0, xmmword ptr [rcx+40h]
0x14003ad3b  movups  xmmword ptr [rax+40h], xmm0
0x14003ad3f  movups  xmm1, xmmword ptr [rcx+50h]
0x14003ad43  movups  xmmword ptr [rax+50h], xmm1
0x14003ad47  movups  xmm0, xmmword ptr [rcx+60h]
0x14003ad4b  movups  xmmword ptr [rax+60h], xmm0
0x14003ad4f  movups  xmm1, xmmword ptr [rcx+70h]
0x14003ad53  movups  xmmword ptr [rax+70h], xmm1
0x14003ad57  lea     rax, [rax+80h]
0x14003ad5e  lea     rcx, [rcx+80h]
0x14003ad65  sub     rdx, 1
0x14003ad69  jnz     short loc_14003AD19
0x14003ad6b  movups  xmm0, xmmword ptr [rcx]
  ... truncated ...
```
