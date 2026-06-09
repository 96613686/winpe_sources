# RxCreateTreeConnect

- ea: `0x140052bb0`
- end: `0x1400533f5`
- name: `RxCreateTreeConnect`
- size: `2117`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140053400`

## callees

- `0x14000d450`
- `0x14000d690`
- `0x14000e910`
- `0x140014e40`
- `0x140016e20`
- `0x140017280`
- `0x140017310`
- `0x140018748`
- `0x14001ec2c`
- `0x140025be6`
- `0x140025c20`
- `0x140025d00`
- `0x140025d80`
- `0x140052bb0`
- `0x140053f50`
- `0x1400548f0`
- `0x140058f00`
- `0x14005c6c0`
- `0x14005f110`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140053363`
- `ntoskrnl!ExAllocatePool2` at `0x14007be94`
- `ntoskrnl!ExAllocatePool2` at `0x140053363`
- `ntoskrnl!ExAllocatePool2` at `0x14007be94`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007be67`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007bed1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007bee5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007be67`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007bed1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007bee5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007be53`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007be53`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140052d39`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140052d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bf28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c224`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c25b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bf28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c224`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c25b`
- `MUP!MupPinKnownPrefix` at `0x14007c0a1`
- `MUP!MupPinKnownPrefix` at `0x14007c136`
- `MUP!MupPinKnownPrefix` at `0x14007c0a1`
- `MUP!MupPinKnownPrefix` at `0x14007c136`
- `MUP!MupUnpinKnownPrefix` at `0x14007c20b`
- `MUP!MupUnpinKnownPrefix` at `0x14007c291`
- `MUP!MupUnpinKnownPrefix` at `0x14007c20b`
- `MUP!MupUnpinKnownPrefix` at `0x14007c291`

## pseudocode

```c
__int64 __fastcall RxCreateTreeConnect(PRX_CONTEXT RxContext, char *Irp)
{
  struct _IO_STACK_LOCATION *v2; // rdi
  __int64 v3; // r13
  bool v4; // zf
  char v7; // r12
  int v8; // eax
  unsigned int v9; // r14d
  char v10; // cl
  char v11; // r14
  char v12; // al
  ULONG PipeType; // eax
  ULONG EaLength; // eax
  int v15; // edi
  struct _MRX_FOBX_ *FcbObject; // r15
  int v17; // esi
  struct _MRX_SRV_OPEN_ *v18; // r12
  char v19; // r14
  struct _MRX_SRV_OPEN_ *v20; // rax
  PNON_PAGED_FCB v21; // rdx
  PFILE_OBJECT v22; // rax
  struct _IRP *v24; // r13
  const char *i; // rdi
  char v26; // cl
  __int64 v27; // rax
  PSZ FileName; // rax
  __int64 Pool2; // rax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // eax
  unsigned int v37; // edi
  PNON_PAGED_FCB NonPagedFcb; // rdx
  PNON_PAGED_FCB v39; // rcx
  NTSTATUS StoredStatus; // r14d
  int v41; // r8d
  int v42; // r8d
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rdx
  void *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rdx
  char v49; // [rsp+40h] [rbp-79h]
  char v50; // [rsp+41h] [rbp-78h] BYREF
  char v51; // [rsp+42h] [rbp-77h]
  char v52; // [rsp+43h] [rbp-76h]
  UNICODE_STRING Destination; // [rsp+48h] [rbp-71h] BYREF
  struct _MRX_SRV_OPEN_ *v54; // [rsp+58h] [rbp-61h]
  PVOID P; // [rsp+60h] [rbp-59h]
  UNICODE_STRING Source; // [rsp+68h] [rbp-51h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING CanonicalName; // [rsp+88h] [rbp-31h] BYREF
  UNICODE_STRING SymbolicLinkName; // [rsp+98h] [rbp-21h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-11h]
  char v61; // [rsp+B0h] [rbp-9h] BYREF

  v2 = (struct _IO_STACK_LOCATION *)*((_QWORD *)Irp + 23);
  v3 = 0;
  v4 = (BYTE6(RxContext->TrackerHistory[4].FileName) & 4) == 0;
  FileObject = v2->FileObject;
  CanonicalName = 0;
  v50 = 4;
  *(_QWORD *)&Source.Length = 0;
  Source.Buffer = 0;
  SymbolicLinkName.Buffer = (wchar_t *)&v61;
  *(_OWORD *)Src = 0;
  *(_QWORD *)&SymbolicLinkName.Length = 1703936;
  v7 = !v4 && (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x20) != 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      51,
      WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      &FileObject->FileName);
  }
  if ( (RxContext->Create.PipeType & 4) != 0
    && (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x10000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, 3221225659LL);
    }
    return 3221225659LL;
  }
  *(_DWORD *)&CanonicalName.Length = 0;
  CanonicalName.Buffer = 0;
  v8 = RxFirstCanonicalize((__int64)RxContext, Irp, &FileObject->FileName, &CanonicalName, &v50);
  v9 = v8;
  if ( v8 >= 0 )
  {
    *(_QWORD *)&Destination.Length = 0;
    v54 = 0;
    v10 = 0;
    P = 0;
    v11 = 0;
    v52 = 0;
    v12 = BYTE5(RxContext->TrackerHistory[4].FileName) & 0xCF;
    v51 = 0;
    BYTE5(RxContext->TrackerHistory[4].FileName) = v12 | 8;
    PipeType = RxContext->Create.PipeType;
    if ( (PipeType & 0x4000) != 0 )
    {
      *((_DWORD *)RxContext->TrackerHistory[1].FileName + 2) = 3;
    }
    else if ( (PipeType & 0x8000) != 0 )
    {
      FileName = RxContext->TrackerHistory[1].FileName;
      if ( *((int *)FileName + 2) < 3 )
        *((_DWORD *)FileName + 2) = 2;
    }
    EaLength = v2->Parameters.Create.EaLength;
    if ( EaLength )
    {
      v24 = (struct _IRP *)*((_QWORD *)Irp + 3);
      v49 = 0;
      RxContext->TrackerHistory[3].AcquireRelease = EaLength;
      RxContext->TrackerHistory[2].FileName = (PSZ)v24;
      for ( i = (const char *)&v24->MdlAddress; ; i += v27 )
      {
        if ( !strcmp_0(i, "NoConnect") )
        {
          v26 = 1;
          v49 = 1;
        }
        else
        {
          if ( !strcmp_0(i, "UserName")
            || !strcmp_0(i, "Password")
            || !strcmp_0(i, "Domain")
            || !strcmp_0(i, "AuthIdentity") )
          {
            v11 = 1;
          }
          else if ( !strcmp_0(i, "LocalDevice") )
          {
            Source.Buffer = (wchar_t *)((char *)&v24->MdlAddress + *((unsigned __int8 *)&v24->Size + 3) + 1);
            Source.MaximumLength = *(&v24->Size + 2);
            Source.Length = Source.MaximumLength;
          }
          v26 = v49;
        }
        v27 = *(unsigned int *)&v24->Type;
        if ( !(_DWORD)v27 )
          break;
        v24 = (struct _IRP *)((char *)v24 + v27);
      }
      v3 = *(_QWORD *)&Destination.Length;
      v4 = v11 == 0;
      v11 = 0;
      if ( v4 && v26 )
        BYTE5(RxContext->TrackerHistory[4].FileName) |= 0x10u;
      v10 = 0;
    }
    if ( (RxContext->Create.PipeType & 4) == 0 )
      goto LABEL_10;
    v11 = RxContext->Create.PipeCompletionMode == 1;
    if ( RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[41].Flink )
    {
      if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
      {
        v15 = -1073741536;
        goto LABEL_111;
      }
      *(_OWORD *)&RxContext->MRxContext[2] = 0;
      *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
      RxContext->ResumeRoutine = 0;
      v36 = ((__int64 (__fastcall *)(PRX_CONTEXT))RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[41].Flink)(RxContext);
      v15 = v36;
      if ( v36 != -1073741822 )
      {
        if ( v36 >= 0 )
        {
          v10 = 1;
          v51 = 1;
LABEL_10:
          if ( Source.Length )
          {
            Destination = 0;
            if ( !v10 )
            {
              v15 = -1073741811;
              v17 = 3655;
              goto LABEL_36;
            }
            if ( Source.Length != 4 || Source.Buffer[1] != 58 )
            {
              v15 = -1073741767;
              v17 = 3668;
              goto LABEL_36;
            }
            RtlAppendUnicodeToString(&SymbolicLinkName, L"\\GLOBAL??\\");
            RtlAppendUnicodeStringToString(&SymbolicLinkName, &Source);
            v37 = LOWORD(RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql) + CanonicalName.Length + 4;
            Destination.Buffer = (wchar_t *)ExAllocatePool2(258, v37, 1934456914);
            if ( !Destination.Buffer )
            {
              v15 = -1073741670;
              v17 = 3681;
              goto LABEL_36;
            }
            NonPagedFcb = RxContext->NonPagedFcb;
            Destination.MaximumLength = v37;
            Destination.Length = 0;
            RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql);
            RtlAppendUnicodeStringToString(&Destination, &CanonicalName);
            Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
            Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 2] = 0;
            v15 = RxCreateDosDeviceSymbolicLink(&SymbolicLinkName, &Destination);
            ExFreePoolWithTag(Destination.Buffer, 0);
            if ( v15 < 0 )
            {
              v17 = 3697;
              goto LABEL_36;
            }
            v52 = 1;
          }
          v15 = RxFindOrConstructVirtualNetRootWithRetry(RxContext, (PIRP)Irp, &CanonicalName, v7, v11, (__int64)Src);
          if ( v15 < 0 )
          {
            FcbObject = (struct _MRX_FOBX_ *)P;
            v17 = 3715;
            v18 = (struct _MRX_SRV_OPEN_ *)P;
            v19 = 0;
LABEL_13:
            if ( v52 )
              IoDeleteSymbolicLink(&SymbolicLinkName);
            if ( FcbObject )
            {
              if ( LOBYTE(FcbObject[2].pSrvOpen) )
              {
                v43 = *(_QWORD *)(v3 + 32);
                v44 = *(_QWORD *)(*(_QWORD *)(v43 + 32) + 88LL);
                if ( v44 )
                  v45 = *(_QWORD *)(v44 + 40);
                else
                  v45 = 0;
                MupUnpinKnownPrefix(*(_QWORD *)(v43 + 88), v45);
                LOBYTE(FcbObject[2].pSrvOpen) = 0;
              }
              ExFreePoolWithTag(FcbObject, 0);
            }
            if ( v18 )
            {
              v46 = *(void **)&v18->DesiredAccess;
              if ( v46 )
              {
                ExFreePoolWithTag(v46, 0);
                *(_QWORD *)&v18->DesiredAccess = 0;
              }
              ExFreePoolWithTag(v18, 0);
            }
            if ( v19 )
            {
              v47 = *(_QWORD *)(v3 + 32);
              *(_BYTE *)(v3 + 193) = 0;
              v48 = *(_QWORD *)(*(_QWORD *)(v47 + 32) + 88LL);
              if ( v48 )
                v48 = *(_QWORD *)(v48 + 40);
              MupUnpinKnownPrefix(*(_QWORD *)(v47 + 88), v48);
            }
            goto LABEL_36;
          }
          v15 = RxCheckForNetworkOpenRestrictions(RxContext, *((_QWORD *)RxContext->TrackerHistory[0].FileName + 4));
          if ( v15 < 0 )
          {
            FcbObject = (struct _MRX_FOBX_ *)P;
            v17 = 3727;
            v18 = (struct _MRX_SRV_OPEN_ *)P;
            v19 = 0;
            goto LABEL_13;
          }
          if ( (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x20) == 0
            || !Fcb
            || (BYTE6(RxContext->TrackerHistory[4].FileName) & 4) != 0 )
          {
LABEL_22:
            if ( LOWORD(Src[0]) || (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x1000) != 0 )
            {
              v3 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
              if ( (*(_DWORD *)(v3 + 56) & 0x50) == 0 )
              {
                if ( RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[18].Flink )
                {
                  if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
                  {
                    v15 = -1073741536;
                  }
                  else
                  {
                    *(_OWORD *)&RxContext->MRxContext[2] = 0;
                    *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
                    RxContext->ResumeRoutine = 0;
                    v15 = ((__int64 (__fastcall *)(PRX_CONTEXT, void **))RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[18].Flink)(
                            RxContext,
                            Src);
                    if ( v15 >= 0 )
                      goto LABEL_25;
                  }
                }
                else
                {
                  v15 = -1073741822;
                }
              }
              v39 = RxContext->NonPagedFcb;
              if ( (v39->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x20) != 0
                && Fcb
                && Fcb != (PFCB)v39
                && (BYTE6(RxContext->TrackerHistory[4].FileName) & 4) == 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
                }
                StoredStatus = RxContext->StoredStatus;
                RxContext->StoredStatus = v15;
                if ( *(_QWORD *)(*(_QWORD *)&Fcb->ShareAccess.Writers + 288LL) )
                {
                  if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
                  {
                    v15 = -1073741536;
                  }
                  else
                  {
                    *(_OWORD *)&RxContext->MRxContext[2] = 0;
                    *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
                    RxContext->ResumeRoutine = 0;
                    v15 = (*(__int64 (__fastcall **)(PRX_CONTEXT, void **))(*(_QWORD *)&Fcb->ShareAccess.Writers + 288LL))(
                            RxContext,
                            Src);
                  }
                }
                else
                {
                  v15 = -1073741822;
                }
                RxContext->StoredStatus = StoredStatus;
              }
            }
            if ( v15 < 0 )
            {
              FcbObject = (struct _MRX_FOBX_ *)P;
              v17 = 3824;
              v18 = (struct _MRX_SRV_OPEN_ *)P;
              v19 = 0;
              goto LABEL_13;
            }
LABEL_25:
            v3 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                55,
                WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
                (unsigned int)v15);
            }
            if ( RxContext->NonPagedFcb != *(PNON_PAGED_FCB *)(*(_QWORD *)(*(_QWORD *)(v3 + 32) + 32LL) + 48LL) )
            {
              v15 = 260;
              *((_QWORD *)Irp + 7) = 1;
              v17 = 3847;
              goto LABEL_36;
            }
            RxUpdateNetworkOpenLocationInformation(RxContext);
            FcbObject = (struct _MRX_FOBX_ *)RxAllocateFcbObject(
                                               *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease
                                                                       + 48LL),
                                               0xEC30u,
                                               (POOL_TYPE)256,
                                               0,
                                               0);
            if ( !FcbObject )
            {
              v18 = v54;
              v17 = 3872;
              v15 = -1073741670;
              v19 = 0;
              goto LABEL_13;
            }
            v20 = (struct _MRX_SRV_OPEN_ *)RxAllocateFcbObject(
                                             *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease
                                                                     + 48LL),
                                             0xEB1Cu,
                                             (POOL_TYPE)256,
                                             0,
                                             0);
            FcbObject->Context2 = v20;
            v18 = v20;
            v20->Context2 = &RxDeviceFCB;
            if ( LOWORD(Src[0]) )
            {
              Pool2 = ExAllocatePool2(258, LOWORD(Src[0]) + 16LL, 877492306);
              *(_QWORD *)&v18->DesiredAccess = Pool2;
              if ( !Pool2 )
              {
                v17 = 3899;
                v15 = -1073741670;
                v19 = 0;
                goto LABEL_13;
              }
              *(_QWORD *)(Pool2 + 8) = Pool2 + 16;
              memmove(*(void **)(*(_QWORD *)&v18->DesiredAccess + 8LL), Src[1], LOWORD(Src[0]));
              *(_WORD *)(*(_QWORD *)&v18->DesiredAccess + 2LL) = Src[0];
              **(_WORD **)&v18->DesiredAccess = Src[0];
              LODWORD(v18->Key) |= 0x80000u;
            }
            v21 = RxContext->NonPagedFcb;
            v19 = 0;
            if ( v21->BufferedLocksResource.SystemResourcesList.Blink && (*(_DWORD *)(v3 + 184) || v51) )
            {
              v30 = *(_QWORD *)(v3 + 32);
              v31 = *(_QWORD *)(*(_QWORD *)(v30 + 32) + 88LL);
              if ( v31 )
                v32 = *(_QWORD *)(v31 + 40);
              else
                v32 = 0;
              v15 = MupPinKnownPrefix(*(_QWORD *)(v30 + 88), &v21->AdvancedFcbHeaderMutex.OldIrql, v32);
              if ( v15 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_ZZD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    56,
                    v41,
                    &RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql,
                    *(_QWORD *)(*(_QWORD *)(v3 + 32) + 88LL),
                    v15);
                }
                v17 = 3954;
                if ( v15 == -1073741670 )
                  v15 = -1073741242;
                goto LABEL_13;
              }
              v19 = 1;
              LOBYTE(FcbObject[2].pSrvOpen) = 1;
            }
            if ( (RxContext->Create.PipeType & 2) != 0 )
            {
              RxReference((PVOID)v3);
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 212), 1, 0) )
              {
                RxDereference((PVOID)v3, LHS_LockNotHeld);
              }
              else if ( v19 )
              {
                v33 = *(_QWORD *)(v3 + 32);
                v34 = *(_QWORD *)(*(_QWORD *)(v33 + 32) + 88LL);
                if ( v34 )
                  v35 = *(_QWORD *)(v34 + 40);
                else
                  v35 = 0;
                v15 = MupPinKnownPrefix(
                        *(_QWORD *)(v33 + 88),
                        &RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql,
                        v35);
                if ( v15 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_ZZD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      57,
                      v42,
                      &RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql,
                      *(_QWORD *)(*(_QWORD *)(v3 + 32) + 88LL),
                      v15);
                  }
                  if ( v15 == -1073741670 )
                    v15 = -1073741242;
                  RxDereference((PVOID)v3, LHS_LockNotHeld);
                  v17 = 4011;
                  _InterlockedExchange((volatile __int32 *)(v3 + 212), 0);
                  v19 = 0;
                  goto LABEL_13;
                }
                v19 = 1;
                *(_BYTE *)(v3 + 193) = 1;
                goto LABEL_34;
              }
            }
            v19 = 0;
LABEL_34:
            v18->ShadowContext = *(PMRXSHADOW_SRV_OPEN *)&RxContext->TrackerHistory[0].Flags;
            v17 = 0;
            v22 = FileObject;
            FileObject->FsContext = &RxDeviceFCB;
            v22->FsContext2 = FcbObject;
            *(_BYTE *)(v3 + 192) = 1;
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&RxContext->TrackerHistory[0].Flags + 60LL));
            RxContext->pRelevantSrvOpen = v18;
            RxContext->pFobx = FcbObject;
            RxSetUpFobxForDfs(RxContext, FcbObject);
            v18 = 0;
            *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
            FcbObject = 0;
            RxContext->TrackerHistory[0].FileName = 0;
            *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = 0;
            goto LABEL_35;
          }
          if ( !*(_QWORD *)(*(_QWORD *)&Fcb->ShareAccess.Writers + 432LL) )
          {
            v15 = -1073741822;
LABEL_72:
            FcbObject = (struct _MRX_FOBX_ *)P;
            v17 = 3747;
            v18 = (struct _MRX_SRV_OPEN_ *)P;
            v19 = 0;
            goto LABEL_35;
          }
          if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
          {
            *(_OWORD *)&RxContext->MRxContext[2] = 0;
            *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
            RxContext->ResumeRoutine = 0;
            v15 = (*(__int64 (__fastcall **)(PRX_CONTEXT))(*(_QWORD *)&Fcb->ShareAccess.Writers + 432LL))(RxContext);
            if ( v15 >= 0 )
              goto LABEL_22;
            goto LABEL_72;
          }
          FcbObject = (struct _MRX_FOBX_ *)P;
          v15 = -1073741536;
          v18 = (struct _MRX_SRV_OPEN_ *)P;
          v17 = 3747;
          v19 = 0;
LABEL_35:
          if ( v15 < 0 )
            goto LABEL_13;
LABEL_36:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              58,
              WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              (unsigned int)v15,
              v17);
          }
          return (unsigned int)v15;
        }
LABEL_111:
        FcbObject = (struct _MRX_FOBX_ *)P;
        v17 = 3633;
        v18 = (struct _MRX_SRV_OPEN_ *)P;
        v19 = 0;
        goto LABEL_35;
      }
    }
    v15 = -1073741790;
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, (unsigned int)v8);
  }
  return v9;
}

```

## disassembly

```asm
0x140052bb0  mov     [rsp-8+arg_10], rbx
0x140052bb5  push    rbp
0x140052bb6  push    rsi
0x140052bb7  push    rdi
0x140052bb8  push    r12
0x140052bba  push    r13
0x140052bbc  push    r14
0x140052bbe  push    r15
0x140052bc0  lea     rbp, [rsp-27h]
0x140052bc5  sub     rsp, 0E0h
0x140052bcc  mov     rax, cs:__security_cookie
0x140052bd3  xor     rax, rsp
0x140052bd6  mov     [rbp+57h+var_40], rax
0x140052bda  mov     rdi, [rdx+0B8h]
0x140052be1  xor     r13d, r13d
0x140052be4  test    byte ptr [rcx+2EEh], 4
0x140052beb  xorps   xmm0, xmm0
0x140052bee  xorps   xmm1, xmm1
0x140052bf1  mov     r15, rdx
0x140052bf4  mov     rbx, rcx
0x140052bf7  mov     rax, [rdi+30h]
0x140052bfb  mov     [rbp+57h+var_68], rax
0x140052bff  movups  xmmword ptr [rbp+57h+CanonicalName.Length], xmm0
0x140052c03  mov     [rbp+57h+var_CF], 4
0x140052c07  lea     r14, [rax+58h]
0x140052c0b  mov     qword ptr [rbp+57h+Source.Length], r13
0x140052c0f  lea     rax, [rbp+57h+var_60]
0x140052c13  mov     [rbp+57h+Source.Buffer], r13
0x140052c17  mov     [rbp+57h+SymbolicLinkName.Buffer], rax
0x140052c1b  movups  xmmword ptr [rbp+57h+Src], xmm1
0x140052c1f  mov     qword ptr [rbp+57h+SymbolicLinkName.Length], 1A0000h
0x140052c27  jnz     loc_14005324D
0x140052c2d  xor     r12b, r12b
0x140052c30  mov     rcx, cs:WPP_GLOBAL_Control
0x140052c37  lea     rdx, WPP_GLOBAL_Control
0x140052c3e  cmp     rcx, rdx
0x140052c41  jnz     loc_140052FB2
0x140052c47  mov     eax, [rbx+210h]
0x140052c4d  test    al, 4
0x140052c4f  jnz     loc_14007BD78
0x140052c55  lea     rax, [rbp+57h+var_CF]
0x140052c59  mov     dword ptr [rbp+57h+CanonicalName.Length], r13d
0x140052c5d  lea     r9, [rbp+57h+CanonicalName]
0x140052c61  mov     [rsp+110h+AlreadyAllocatedObject], rax
0x140052c66  mov     r8, r14
0x140052c69  mov     [rbp+57h+CanonicalName.Buffer], r13
0x140052c6d  mov     rdx, r15
0x140052c70  mov     rcx, rbx
0x140052c73  call    RxFirstCanonicalize
0x140052c78  mov     r14d, eax
0x140052c7b  test    eax, eax
0x140052c7d  js      loc_140053232
0x140052c83  xor     eax, eax
0x140052c85  mov     qword ptr [rbp+57h+Destination.Length], r13
0x140052c89  mov     [rbp+57h+var_B8], rax
0x140052c8d  xor     cl, cl
0x140052c8f  mov     [rbp+57h+P], rax
0x140052c93  xor     r14b, r14b
0x140052c96  mov     [rbp+57h+var_CD], al
0x140052c99  movzx   eax, byte ptr [rbx+2EDh]
0x140052ca0  and     al, 0CFh
0x140052ca2  mov     [rbp+57h+var_CE], cl
0x140052ca5  or      al, 8
0x140052ca7  mov     [rbx+2EDh], al
0x140052cad  mov     eax, [rbx+210h]
0x140052cb3  bt      eax, 0Eh
0x140052cb7  jnb     loc_1400531A7
0x140052cbd  mov     rax, [rbx+2A0h]
0x140052cc4  mov     dword ptr [rax+8], 3
0x140052ccb  mov     eax, [rdi+20h]
0x140052cce  test    eax, eax
0x140052cd0  jnz     loc_140053073
0x140052cd6  mov     eax, [rbx+210h]
0x140052cdc  test    al, 4
0x140052cde  jnz     loc_140053290
0x140052ce4  cmp     [rbp+57h+Source.Length], 0
0x140052ce9  jnz     loc_1400532CC
0x140052cef  movzx   r9d, [rbp+57h+var_CF]
0x140052cf4  lea     rax, [rbp+57h+Src]
0x140052cf8  mov     [rsp+110h+var_E0], rax; __int64
0x140052cfd  lea     r8, [rbp+57h+CanonicalName]; CanonicalName
0x140052d01  mov     [rsp+110h+var_E8], r14b; char
0x140052d06  mov     rdx, r15; Irp
0x140052d09  mov     rcx, rbx; RxContext
0x140052d0c  mov     byte ptr [rsp+110h+AlreadyAllocatedObject], r12b; char
0x140052d11  call    RxFindOrConstructVirtualNetRootWithRetry
0x140052d16  mov     edi, eax
0x140052d18  test    eax, eax
0x140052d1a  jns     short loc_140052D4B
0x140052d1c  mov     r15, [rbp+57h+P]
0x140052d20  mov     esi, 0E83h
0x140052d25  mov     r12, r15
0x140052d28  xor     r14b, r14b
0x140052d2b  cmp     [rbp+57h+var_CD], 0
0x140052d2f  jz      loc_14007C1DF
0x140052d35  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x140052d39  call    cs:__imp_IoDeleteSymbolicLink
0x140052d40  nop     dword ptr [rax+rax+00h]
0x140052d45  nop
0x140052d46  jmp     loc_14007C1DF
0x140052d4b  mov     rdx, [rbx+288h]
0x140052d52  mov     rcx, rbx
0x140052d55  mov     rdx, [rdx+20h]
0x140052d59  call    RxCheckForNetworkOpenRestrictions
0x140052d5e  mov     edi, eax
0x140052d60  test    eax, eax
0x140052d62  js      loc_1400531E2
0x140052d68  mov     rax, [rbx+50h]
0x140052d6c  mov     ecx, [rax+150h]
0x140052d72  test    cl, 20h
0x140052d75  jz      short loc_140052DF0
0x140052d77  mov     rcx, cs:Fcb
0x140052d7e  test    rcx, rcx
0x140052d81  jz      short loc_140052DF0
0x140052d83  test    byte ptr [rbx+2EEh], 4
0x140052d8a  jnz     short loc_140052DF0
0x140052d8c  mov     rax, [rcx+160h]
0x140052d93  cmp     qword ptr [rax+1B0h], 0
0x140052d9b  jz      loc_1400531F6
0x140052da1  mov     eax, [rbx+80h]
0x140052da7  test    al, 2
0x140052da9  jnz     loc_14005320F
0x140052daf  xor     eax, eax
0x140052db1  xorps   xmm0, xmm0
0x140052db4  movups  xmmword ptr [rbx+0D0h], xmm0
0x140052dbb  movups  xmmword ptr [rbx+0E0h], xmm0
0x140052dc2  mov     [rbx+0F0h], rax
0x140052dc9  mov     rax, cs:Fcb
0x140052dd0  mov     rcx, [rax+160h]
0x140052dd7  mov     rax, [rcx+1B0h]
0x140052dde  mov     rcx, rbx
0x140052de1  call    _guard_dispatch_icall
0x140052de6  mov     edi, eax
0x140052de8  test    eax, eax
0x140052dea  js      loc_1400531FB
0x140052df0  cmp     word ptr [rbp+57h+Src], 0
0x140052df5  ja      loc_140052FEB
0x140052dfb  mov     rax, [rbx+50h]
0x140052dff  test    dword ptr [rax+150h], 1000h
0x140052e09  jnz     loc_140052FEB
0x140052e0f  lea     r12, WPP_GLOBAL_Control
0x140052e16  test    edi, edi
0x140052e18  js      loc_140053193
0x140052e1e  mov     r13, [rbx+290h]
0x140052e25  mov     rcx, cs:WPP_GLOBAL_Control
0x140052e2c  cmp     rcx, r12
0x140052e2f  jnz     loc_1400532F4
0x140052e35  mov     rax, [r13+20h]
0x140052e39  mov     rcx, [rax+20h]
0x140052e3d  mov     rax, [rcx+30h]
0x140052e41  cmp     [rbx+50h], rax
0x140052e45  jnz     loc_140053326
0x140052e4b  mov     rcx, rbx
0x140052e4e  call    RxUpdateNetworkOpenLocationInformation
0x140052e53  mov     rcx, [rbx+280h]
0x140052e5a  mov     edx, 0EC30h; NodeType
0x140052e5f  xor     r9d, r9d; NameSize
0x140052e62  mov     [rsp+110h+AlreadyAllocatedObject], 0; AlreadyAllocatedObject
0x140052e6b  mov     r8d, 100h; PoolType
0x140052e71  mov     rcx, [rcx+30h]; RxDeviceObject
0x140052e75  call    RxAllocateFcbObject
0x140052e7a  mov     r15, rax
0x140052e7d  test    rax, rax
0x140052e80  jz      loc_14005333E
0x140052e86  mov     rcx, [rbx+280h]
0x140052e8d  mov     edx, 0EB1Ch; NodeType
0x140052e92  xor     r9d, r9d; NameSize
0x140052e95  mov     [rsp+110h+AlreadyAllocatedObject], 0; AlreadyAllocatedObject
0x140052e9e  mov     r8d, 100h; PoolType
0x140052ea4  mov     rcx, [rcx+30h]; RxDeviceObject
0x140052ea8  call    RxAllocateFcbObject
0x140052ead  mov     [r15+20h], rax
0x140052eb1  mov     r12, rax
0x140052eb4  lea     rax, RxDeviceFCB
0x140052ebb  mov     [r12+20h], rax
0x140052ec0  movzx   edx, word ptr [rbp+57h+Src]
0x140052ec4  test    dx, dx
0x140052ec7  jnz     loc_140053354
0x140052ecd  mov     rdx, [rbx+50h]
0x140052ed1  xor     r14b, r14b
0x140052ed4  cmp     qword ptr [rdx+178h], 0
0x140052edc  jz      short loc_140052EF6
0x140052ede  cmp     dword ptr [r13+0B8h], 0
0x140052ee6  jnz     loc_140053392
0x140052eec  cmp     [rbp+57h+var_CE], r14b
0x140052ef0  jnz     loc_140053392
0x140052ef6  mov     eax, [rbx+210h]
0x140052efc  test    al, 2
0x140052efe  jnz     loc_1400533B0
0x140052f04  xor     r14b, r14b
0x140052f07  mov     rax, [rbx+290h]
0x140052f0e  lea     rcx, RxDeviceFCB
0x140052f15  mov     [r12+28h], rax
0x140052f1a  xor     esi, esi
0x140052f1c  mov     rax, [rbp+57h+var_68]
0x140052f20  mov     [rax+18h], rcx
0x140052f24  mov     [rax+20h], r15
0x140052f28  mov     byte ptr [r13+0C0h], 1
0x140052f30  mov     rax, [rbx+290h]
0x140052f37  lock inc dword ptr [rax+3Ch]
0x140052f3b  mov     rdx, r15
0x140052f3e  mov     [rbx+48h], r12
0x140052f42  mov     rcx, rbx
0x140052f45  mov     [rbx+40h], r15
0x140052f49  call    RxSetUpFobxForDfs
0x140052f4e  xor     r12d, r12d
0x140052f51  mov     [rbx+290h], rsi
0x140052f58  xor     r15d, r15d
0x140052f5b  mov     [rbx+288h], rsi
0x140052f62  mov     [rbx+280h], rsi
0x140052f69  test    edi, edi
0x140052f6b  js      loc_140052D2B
0x140052f71  mov     rcx, cs:WPP_GLOBAL_Control
0x140052f78  lea     rax, WPP_GLOBAL_Control
0x140052f7f  cmp     rcx, rax
0x140052f82  jnz     loc_140053153
0x140052f88  mov     eax, edi
0x140052f8a  mov     rcx, [rbp+57h+var_40]
0x140052f8e  xor     rcx, rsp; StackCookie
0x140052f91  call    __security_check_cookie
0x140052f96  mov     rbx, [rsp+110h+arg_10]
0x140052f9e  add     rsp, 0E0h
0x140052fa5  pop     r15
0x140052fa7  pop     r14
0x140052fa9  pop     r13
0x140052fab  pop     r12
0x140052fad  pop     rdi
0x140052fae  pop     rsi
0x140052faf  pop     rbp
0x140052fb0  retn
0x140052fb2  mov     eax, [rcx+2Ch]
0x140052fb5  test    al, 8
0x140052fb7  jz      loc_140052C47
0x140052fbd  cmp     byte ptr [rcx+29h], 2
0x140052fc1  jb      loc_140052C47
0x140052fc7  mov     rcx, [rcx+18h]
0x140052fcb  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140052fd2  mov     edx, 33h ; '3'
0x140052fd7  mov     r9, r14
0x140052fda  call    WPP_SF_Z
0x140052fdf  lea     rdx, WPP_GLOBAL_Control
0x140052fe6  jmp     loc_140052C47
0x140052feb  mov     r13, [rbx+290h]
0x140052ff2  mov     eax, [r13+38h]
0x140052ff6  test    al, 50h
0x140052ff8  jnz     loc_14007BF5A
0x140052ffe  mov     rax, [rbx+50h]
0x140053002  mov     rcx, [rax+160h]
0x140053009  cmp     qword ptr [rcx+120h], 0
0x140053011  jz      loc_1400532EA
0x140053017  mov     eax, [rbx+80h]
0x14005301d  test    al, 2
0x14005301f  jnz     loc_140053228
0x140053025  xor     eax, eax
0x140053027  lea     rdx, [rbp+57h+Src]
0x14005302b  xorps   xmm0, xmm0
0x14005302e  movups  xmmword ptr [rbx+0D0h], xmm0
0x140053035  movups  xmmword ptr [rbx+0E0h], xmm0
0x14005303c  mov     [rbx+0F0h], rax
0x140053043  mov     rax, [rbx+50h]
0x140053047  mov     rcx, [rax+160h]
0x14005304e  mov     rax, [rcx+120h]
0x140053055  mov     rcx, rbx
0x140053058  call    _guard_dispatch_icall
0x14005305d  mov     edi, eax
0x14005305f  test    eax, eax
0x140053061  js      loc_14007BF5A
0x140053067  lea     r12, WPP_GLOBAL_Control
0x14005306e  jmp     loc_140052E1E
0x140053073  mov     r13, [r15+18h]
0x140053077  mov     [rbp+57h+var_D0], cl
0x14005307a  mov     [rbx+2C8h], eax
0x140053080  mov     [rbx+2B8h], r13
0x140053087  lea     rdi, [r13+8]
0x14005308b  nop     dword ptr [rax+rax+00h]
0x140053090  lea     rdx, Str2; "NoConnect"
0x140053097  mov     rcx, rdi; Str1
0x14005309a  call    strcmp_0
0x14005309f  test    eax, eax
0x1400530a1  jz      loc_140053189
0x1400530a7  lea     rdx, aUsername; "UserName"
0x1400530ae  mov     rcx, rdi; Str1
0x1400530b1  call    strcmp_0
0x1400530b6  test    eax, eax
0x1400530b8  jz      short loc_1400530F3
0x1400530ba  lea     rdx, aPassword; "Password"
0x1400530c1  mov     rcx, rdi; Str1
0x1400530c4  call    strcmp_0
0x1400530c9  test    eax, eax
0x1400530cb  jz      short loc_1400530F3
0x1400530cd  lea     rdx, aDomain; "Domain"
0x1400530d4  mov     rcx, rdi; Str1
0x1400530d7  call    strcmp_0
0x1400530dc  test    eax, eax
0x1400530de  jz      short loc_1400530F3
0x1400530e0  lea     rdx, aAuthidentity; "AuthIdentity"
0x1400530e7  mov     rcx, rdi; Str1
0x1400530ea  call    strcmp_0
0x1400530ef  test    eax, eax
0x1400530f1  jnz     short loc_14005310A
  ... truncated ...
```
