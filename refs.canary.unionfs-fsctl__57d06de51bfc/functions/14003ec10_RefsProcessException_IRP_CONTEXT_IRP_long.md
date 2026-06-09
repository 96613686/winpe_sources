# RefsProcessException(_IRP_CONTEXT *,_IRP *,long)

- ea: `0x14003ec10`
- end: `0x14003fbda`
- name: `?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z`
- size: `4042`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, int)`
- caller_count: `24`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003a1a0`
- `0x14003a850`
- `0x140040b20`
- `0x1400a4ff0`
- `0x1400bc440`
- `0x1400e14f0`
- `0x1400f1140`
- `0x1400f35c0`
- `0x1400f4428`
- `0x140291580`
- `0x1402c9ab0`
- `0x1402cdae0`
- `0x1402e3020`
- `0x1403012f0`
- `0x140309700`
- `0x140309ae0`
- `0x140311ed0`
- `0x140314a80`
- `0x1403204c0`
- `0x1403209e0`
- `0x1403284d0`
- `0x14032ac20`
- `0x14032c290`
- `0x1403391e0`

## callees

- `0x140039b60`
- `0x14003d440`
- `0x14003d4cc`
- `0x14003ec10`
- `0x14003fbe0`
- `0x140041b40`
- `0x140069750`
- `0x14008a460`
- `0x14008b690`
- `0x14008dbd0`
- `0x1400af96c`
- `0x1400b1dfc`
- `0x1400ca788`
- `0x1400e6e2c`
- `0x1400f98b8`
- `0x1400f9948`
- `0x1400fb690`
- `0x140115aa4`
- `0x1402870ec`
- `0x1402fec40`
- `0x140311984`
- `0x140331020`
- `0x140338660`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f4f7`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f538`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f59b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f5ae`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f878`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f997`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003fa9c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f4f7`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f538`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f59b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f5ae`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f878`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003f997`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003fa9c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003f1dd`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003f1dd`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14003f379`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14003f379`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003f472`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14003f472`
- `ntoskrnl!CcMdlWriteAbort` at `0x14003ecae`
- `ntoskrnl!CcMdlWriteAbort` at `0x14003f845`
- `ntoskrnl!CcMdlWriteAbort` at `0x14003ecae`
- `ntoskrnl!CcMdlWriteAbort` at `0x14003f845`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003f5fc`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003f5fc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003f60f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003f60f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eaeb6`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eaeb6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003f64a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003f64a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003f656`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003f656`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003edcf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003f163`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003edcf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003f163`
- `ntoskrnl!ExReleaseFastResource` at `0x14003f221`
- `ntoskrnl!ExReleaseFastResource` at `0x1401eae94`
- `ntoskrnl!ExReleaseFastResource` at `0x14003f221`
- `ntoskrnl!ExReleaseFastResource` at `0x1401eae94`

## pseudocode

```c
__int64 __fastcall RefsProcessException(struct _IRP_CONTEXT *a1, struct _IRP *a2, __int64 a3)
{
  unsigned int v3; // esi
  struct _IRP *v4; // r14
  struct _IRP_CONTEXT *v5; // rbx
  struct _IRP_CONTEXT *v6; // rdi
  __int64 v7; // r15
  __int64 v8; // rax
  struct _MDL *MdlAddress; // rdx
  __int64 v10; // rcx
  struct _LIST_ENTRY *v11; // rdx
  unsigned int v12; // r8d
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *i; // rax
  struct _FCB *v17; // r13
  unsigned __int8 v18; // al
  char v19; // r13
  int *v20; // r8
  char v21; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  unsigned int v23; // r9d
  char v24; // al
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rax
  struct _MDL *v28; // rdx
  struct _IRP_CONTEXT *v29; // rcx
  struct _SmsTriageContext *v30; // rdi
  NTSTATUS v31; // edi
  char v32; // al
  __int64 v33; // rcx
  struct _IRP_CONTEXT *v34; // rcx
  __int64 v35; // rax
  struct _IRP_CONTEXT *v37[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 v38; // [rsp+C8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = 0;
  v37[0] = 0;
  if ( !a1 )
    goto LABEL_212;
  v7 = *((_QWORD *)a1 + 8);
  v37[1] = (struct _IRP_CONTEXT *)v7;
  if ( (_DWORD)a3 == -1073741432 )
  {
    RefsSqmLogFileFull(*((unsigned int *)a1 + 166), v7);
    if ( v7 )
    {
      v8 = *((int *)v5 + 166);
      if ( (unsigned int)v8 <= 0xE )
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 8 * v8 + 10224));
    }
  }
  v3 = *((_DWORD *)v5 + 4);
  if ( *((_BYTE *)v5 + 40) == 4 && (*((_BYTE *)v5 + 41) & 6) == 2 )
  {
    if ( v4 )
    {
      MdlAddress = v4->MdlAddress;
      if ( MdlAddress )
      {
        CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, MdlAddress);
        v4->MdlAddress = 0;
      }
    }
  }
  if ( v7 )
  {
    RefsRestoreScbSnapshots(v5, 1u);
    RefsAbortPendingUsnReasons(v5);
    v10 = *((_QWORD *)v5 + 3);
    if ( v10 )
    {
      if ( !*((_QWORD *)v5 + 43) )
        MsTriageGetContext(v10, (char *)v5 + 344);
      if ( *((_BYTE *)v5 + 40) == 4
        && (*(_DWORD *)(v7 + 24) & 1) != 0
        && (*(_DWORD *)(*(_QWORD *)(v7 + 112) + 3460LL) & 0x800000) != 0
        && (*((_DWORD *)v5 + 1) & 0x8000000) == 0 )
      {
        MsSetOkayToResyncSMRBands(*((_QWORD *)v5 + 3));
      }
      RefsAbortTransaction(v5);
    }
    else
    {
      v11 = (struct _LIST_ENTRY *)((char *)v5 + 640);
      if ( v11->Flink != v11 )
      {
        v12 = 4;
        if ( (v3 & 0x80000000) == 0 )
          v12 = 1;
        RefsProcessRollbackListPriv(0, v11, v12);
      }
      if ( (*((_DWORD *)v5 + 2) & 0x20000000) != 0 )
      {
        v13 = (_QWORD *)*((_QWORD *)v5 + 8);
        v13[116] = v13[124];
        v13[121] = v13[125];
        v13[122] = v13[126];
        *((_QWORD *)v5 + 1) &= ~0x20000000uLL;
      }
    }
    RefsRestoreScbSnapshots(v5, 0);
    if ( *(_QWORD *)(v7 + 240) != *(_QWORD *)(v7 + 264) )
    {
      v14 = *(_QWORD *)(v7 + 72);
      if ( v14 )
      {
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(v14 + 136) + 88LL) + 64LL) )
          *(_QWORD *)(v7 + 240) = *(_QWORD *)(v7 + 264);
      }
    }
  }
  else
  {
    if ( v3 == -1073741400 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 3221227528LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x658u);
      v3 = -1073739768;
    }
    v15 = *((_QWORD *)v5 + 3);
    if ( v15 && !*((_QWORD *)v5 + 43) )
      MsTriageGetContext(v15, (char *)v5 + 344);
    if ( *((_QWORD *)v5 + 43) )
      RefsDiscardTriageInfo(v5);
    if ( v3 == -1073741432 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v3 = -1073741697;
      }
      else
      {
        v3 = -1073741697;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 3221225599LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741697, 0, "NtfsData.c", 0x675u);
    }
  }
  if ( _bittest64((const signed __int64 *)v5 + 1, 0x25u) )
  {
    for ( i = (_QWORD *)*((_QWORD *)v5 + 14); i != (_QWORD *)((char *)v5 + 112); i = (_QWORD *)*i )
    {
      v17 = (struct _FCB *)(i - 8);
      if ( (*(_DWORD *)(i - 7) & 0x4000000) != 0 )
      {
        *((_QWORD *)v5 + 1) &= ~0x2000000000uLL;
        LOBYTE(a3) = 1;
        ExAcquireFastResourceExclusive(v7 + 624, 0, a3);
        v18 = 1;
        v38 = 1;
        if ( !v17->Header.AllocationSize.LowPart )
        {
          RefsDeleteFcb(v5, v17, &v38);
          v18 = v38;
        }
        if ( v18 )
          ExReleaseFastResource(v7 + 624, 0);
        break;
      }
    }
    *((_QWORD *)v5 + 1) &= ~0x2000000000uLL;
    MsReleaseFastResource(v7 + 1312);
  }
  v19 = 0;
  v38 = 0;
  v20 = (int *)*((_QWORD *)v5 + 13);
  if ( v5 != (struct _IRP_CONTEXT *)v20 )
  {
    v21 = *((_BYTE *)v5 + 40);
    if ( (v21 != 3
       || !*((_QWORD *)v5 + 84)
       && v4->Tail.Overlay.CurrentStackLocation->FileObject->FsContext != *(PVOID *)(*((_QWORD *)v5 + 8) + 40LL))
      && (v20[4] >= 0 || v3 == -1073741400) )
    {
      if ( v3 == -1073741740 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, 0, "NtfsData.c", 0x75Eu);
        *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = -1073741608;
        goto LABEL_100;
      }
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_100;
      if ( v4 )
      {
        if ( v21 == 4 )
        {
          CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
          if ( (v3 == -1073741670
             || v3 == -1073741663
             || v3 == -1073741801
             || CurrentStackLocation->Parameters.Read.Length > 0x1000 && !FsRtlIsTotalDeviceFailure(v3))
            && (v4->Flags & 2) != 0
            && CurrentStackLocation->Parameters.Read.Length > 0x1000 )
          {
            goto LABEL_100;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, v3);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
        {
LABEL_93:
          *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = v3;
          goto LABEL_100;
        }
        v23 = 1928;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, v3);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_93;
        v23 = 1934;
      }
      RefsStatusDebug(v3, 0, "NtfsData.c", v23);
      goto LABEL_93;
    }
  }
LABEL_100:
  if ( v3 != -1073741432
    && v3 != -1073741400
    && v3 != -1073741608
    && !(unsigned __int8)CcIsCacheManagerCallbackNeeded(v3) )
  {
    goto LABEL_141;
  }
  v24 = *((_BYTE *)v5 + 40);
  if ( v24 == 2 )
  {
    v19 = 1;
    v38 = 1;
    if ( (*((_DWORD *)v5 + 1) & 0x800) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 259);
      }
      v3 = 259;
    }
    goto LABEL_141;
  }
  if ( v24 == 3
    && (v5 != *((struct _IRP_CONTEXT **)v5 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type) || (v4->Flags & 2) != 0) )
  {
    if ( v3 == -1073741400 && v5 != *((struct _IRP_CONTEXT **)v5 + 13) )
      goto LABEL_141;
LABEL_117:
    v19 = 1;
    v38 = 1;
    goto LABEL_141;
  }
  if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    if ( (*((_DWORD *)v5 + 1) & 0x800) != 0 && !*((_QWORD *)v5 + 43) )
    {
      v6 = v5;
      v37[0] = v5;
      goto LABEL_141;
    }
    goto LABEL_117;
  }
  if ( v3 == -1073741432 )
  {
    ++*(_DWORD *)(v7 + 3496);
    if ( *((struct _IRP_CONTEXT **)v5 + 13) == v5 && (*(_DWORD *)(v7 + 560) & 1) == 0 )
    {
      if ( *((_BYTE *)v5 + 40) == 4 && IoGetTopLevelIrp()->MdlAddress == (PMDL)2 )
      {
        IoGetTopLevelIrp()->MdlAddress = (PMDL)2147483650LL;
      }
      else
      {
        v37[0] = 0;
        RefsInitializeIrpContext(0, 1u, 0, v37);
        v6 = v37[0];
        if ( v37[0] )
        {
          *((_QWORD *)v37[0] + 8) = v7;
          *((_DWORD *)v6 + 166) = *((_DWORD *)v5 + 166);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 568));
          v25 = *(_DWORD *)(v7 + 560);
          if ( (v25 & 1) != 0 )
          {
            RefsCleanupIrpContext(v6, 0);
            v6 = 0;
            v37[0] = 0;
          }
          else
          {
            *(_DWORD *)(v7 + 560) = v25 | 1;
          }
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 568));
          KeLeaveGuardedRegion();
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 3221225556LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741740, 0, "NtfsData.c", 0x82Fu);
  v3 = -1073741740;
LABEL_141:
  if ( !v6 )
    goto LABEL_146;
  *((_DWORD *)v6 + 4) = 0;
  v26 = RefsPostRequest(v6, *((struct _IRP **)v6 + 9), v6 == v5, 0);
  if ( v6 == v5 )
  {
    v4 = 0;
    v5 = 0;
    v3 = v26;
  }
  if ( !v5 )
  {
    if ( !v4 )
      return v3;
LABEL_146:
    if ( !v5 )
      goto LABEL_150;
  }
  v27 = *((_QWORD *)v5 + 1);
  if ( (v27 & 0x40) == 0 && (v27 & 2) != 0 )
  {
    v4 = 0;
    goto LABEL_156;
  }
LABEL_150:
  if ( v4 )
  {
    if ( !v19 && *((_BYTE *)v5 + 40) == 4 && (*((_BYTE *)v5 + 41) & 6) == 6 )
    {
      v28 = v4->MdlAddress;
      if ( v28 )
      {
        CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, v28);
        v4->MdlAddress = 0;
      }
    }
  }
LABEL_156:
  if ( !v5 || !*((_QWORD *)v5 + 43) )
    goto LABEL_166;
  if ( *((_BYTE *)v5 + 40) == 2 && (v5 != *((struct _IRP_CONTEXT **)v5 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type)) )
  {
    v19 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 259);
    }
    v3 = 259;
    RefsDiscardTriageInfo(v5);
    goto LABEL_166;
  }
  v29 = (struct _IRP_CONTEXT *)*((_QWORD *)v5 + 13);
  if ( v5 != v29 )
  {
    *((_QWORD *)v29 + 43) = *((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = -1073741400;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 3221227528LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x8D0u);
    v3 = -1073739768;
    goto LABEL_166;
  }
  if ( LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    v30 = (struct _SmsTriageContext *)*((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    if ( (*((_DWORD *)v5 + 2) & 0x10000) == 0 )
      *((_DWORD *)v5 + 1) |= 0x400u;
    RefsCleanupIrpContext(v5, 1u);
    v31 = RefsPerformTriage(v5, v30);
    if ( v31 < 0 )
    {
      v32 = *((_BYTE *)v5 + 40);
      if ( v32 != 2 || (v33 = *((_QWORD *)v5 + 1), (v33 & 4) != 0) )
      {
        if ( v32 != 18 || v31 != -1073741202 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids,
              (unsigned int)v31);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v31, 0, "NtfsData.c", 0x963u);
          v3 = v31;
          if ( v31 != -1073741608 && v31 != -1073741432 )
            v19 = 0;
        }
      }
      else
      {
        *((_QWORD *)v5 + 1) = v33 | 4;
      }
    }
LABEL_166:
    if ( v19 )
    {
      *((_DWORD *)v5 + 1) |= 0x400u;
      *((_DWORD *)v5 + 4) = 0;
      a2 = 0;
LABEL_211:
      a1 = v5;
      LODWORD(a3) = v3;
LABEL_212:
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, a2, a3);
      return v3;
    }
    goto LABEL_206;
  }
  if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)7
    || (*((_DWORD *)v5 + 2) & 0x400000) != 0
    || (RefsInitializeIrpContext(0, 1u, 0, v37), (v34 = v37[0]) == 0) )
  {
    RefsDiscardTriageInfo(v5);
  }
  else
  {
    *((_QWORD *)v37[0] + 8) = *((_QWORD *)v5 + 8);
    *((_QWORD *)v34 + 43) = *((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v5 + 8) + 556LL));
    RefsPostSpecial(
      v34,
      *((struct _VCB **)v34 + 8),
      (void (*)(struct _IRP_CONTEXT *, void *))RefsPerformTriageWorkItem,
      *((void **)v34 + 43),
      1u,
      0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, 3221227528LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x924u);
  v3 = -1073739768;
LABEL_206:
  if ( !v5 || !v4 || (v35 = *((_QWORD *)v5 + 1), (v35 & 0x100000000LL) == 0) )
  {
    a2 = v4;
    goto LABEL_211;
  }
  *((_QWORD *)v5 + 1) = v35 | 0x200000000LL;
  return v3;
}

```

## disassembly

```asm
0x14003ec10  mov     [rsp+arg_8], rdx
0x14003ec15  mov     [rsp+arg_0], rcx
0x14003ec1a  push    rbx
0x14003ec1b  push    rsi
0x14003ec1c  push    rdi
0x14003ec1d  push    r12
0x14003ec1f  push    r13
0x14003ec21  push    r14
0x14003ec23  push    r15
0x14003ec25  sub     rsp, 70h
0x14003ec29  mov     esi, r8d
0x14003ec2c  mov     r14, rdx
0x14003ec2f  mov     rbx, rcx
0x14003ec32  xor     edi, edi
0x14003ec34  mov     [rsp+0A8h+var_58], rdi
0x14003ec39  test    rcx, rcx
0x14003ec3c  jz      loc_14003FBC2
0x14003ec42  mov     r15, [rcx+40h]
0x14003ec46  mov     [rsp+0A8h+var_50], r15
0x14003ec4b  cmp     esi, 0C0000188h
0x14003ec51  jnz     short loc_14003EC7B
0x14003ec53  mov     rdx, r15
0x14003ec56  mov     ecx, [rcx+298h]
0x14003ec5c  call    ?RefsSqmLogFileFull@@YAXW4_LF_REASON@@PEAU_VCB@@@Z; RefsSqmLogFileFull(_LF_REASON,_VCB *)
0x14003ec61  test    r15, r15
0x14003ec64  jz      short loc_14003EC7B
0x14003ec66  movsxd  rax, dword ptr [rbx+298h]
0x14003ec6d  cmp     eax, 0Eh
0x14003ec70  ja      short loc_14003EC7B
0x14003ec72  lock inc qword ptr [r15+rax*8+27F0h]
0x14003ec7b  mov     esi, [rbx+10h]
0x14003ec7e  mov     [rsp+0A8h+arg_10], esi
0x14003ec85  cmp     byte ptr [rbx+28h], 4
0x14003ec89  jnz     short loc_14003ECC2
0x14003ec8b  movzx   eax, byte ptr [rbx+29h]
0x14003ec8f  and     al, 6
0x14003ec91  cmp     al, 2
0x14003ec93  jnz     short loc_14003ECC2
0x14003ec95  test    r14, r14
0x14003ec98  jz      short loc_14003ECC2
0x14003ec9a  mov     rdx, [r14+8]; MdlChain
0x14003ec9e  test    rdx, rdx
0x14003eca1  jz      short loc_14003ECC2
0x14003eca3  mov     rcx, [r14+0B8h]
0x14003ecaa  mov     rcx, [rcx+30h]; FileObject
0x14003ecae  call    cs:__imp_CcMdlWriteAbort
0x14003ecb5  nop     dword ptr [rax+rax+00h]
0x14003ecba  mov     qword ptr [r14+8], 0
0x14003ecc2  test    r15, r15
0x14003ecc5  jz      loc_14003EDF6
0x14003eccb  mov     dl, 1; unsigned __int8
0x14003eccd  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003ecd0  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14003ecd5  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003ecd8  call    ?RefsAbortPendingUsnReasons@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortPendingUsnReasons(_IRP_CONTEXT *)
0x14003ecdd  mov     rcx, [rbx+18h]; struct _IRP_CONTEXT *
0x14003ece1  test    rcx, rcx
0x14003ece4  jz      short loc_14003ED32
0x14003ece6  lea     rdx, [rbx+158h]
0x14003eced  cmp     qword ptr [rdx], 0
0x14003ecf1  jnz     short loc_14003ECF8
0x14003ecf3  call    MsTriageGetContext
0x14003ecf8  cmp     byte ptr [rbx+28h], 4
0x14003ecfc  jnz     short loc_14003ED28
0x14003ecfe  mov     eax, [r15+18h]
0x14003ed02  test    al, 1
0x14003ed04  jz      short loc_14003ED28
0x14003ed06  mov     rax, [r15+70h]
0x14003ed0a  test    dword ptr [rax+0D84h], 800000h
0x14003ed14  jz      short loc_14003ED28
0x14003ed16  test    dword ptr [rbx+4], 8000000h
0x14003ed1d  jnz     short loc_14003ED28
0x14003ed1f  mov     rcx, [rbx+18h]
0x14003ed23  call    MsSetOkayToResyncSMRBands
0x14003ed28  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003ed2b  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x14003ed30  jmp     short loc_14003ED95
0x14003ed32  lea     rdx, [rbx+280h]; struct _LIST_ENTRY *
0x14003ed39  cmp     [rdx], rdx
0x14003ed3c  jz      short loc_14003ED55
0x14003ed3e  mov     r8d, 4
0x14003ed44  mov     r12d, 1
0x14003ed4a  test    esi, esi
0x14003ed4c  cmovns  r8d, r12d; unsigned int
0x14003ed50  call    ?RefsProcessRollbackListPriv@@YAXPEAU_IRP_CONTEXT@@PEAU_LIST_ENTRY@@K@Z; RefsProcessRollbackListPriv(_IRP_CONTEXT *,_LIST_ENTRY *,ulong)
0x14003ed55  mov     eax, [rbx+8]
0x14003ed58  bt      rax, 1Dh
0x14003ed5d  jnb     short loc_14003ED95
0x14003ed5f  mov     rcx, [rbx+40h]
0x14003ed63  mov     rax, [rcx+3E0h]
0x14003ed6a  mov     [rcx+3A0h], rax
0x14003ed71  mov     rax, [rcx+3E8h]
0x14003ed78  mov     [rcx+3C8h], rax
0x14003ed7f  mov     rax, [rcx+3F0h]
0x14003ed86  mov     [rcx+3D0h], rax
0x14003ed8d  and     qword ptr [rbx+8], 0FFFFFFFFDFFFFFFFh
0x14003ed95  xor     edx, edx; unsigned __int8
0x14003ed97  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003ed9a  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14003ed9f  mov     rax, [r15+108h]
0x14003eda6  cmp     [r15+0F0h], rax
0x14003edad  jz      loc_14003EF2C
0x14003edb3  mov     rax, [r15+48h]
0x14003edb7  test    rax, rax
0x14003edba  jz      loc_14003EF2C
0x14003edc0  mov     rax, [rax+88h]
0x14003edc7  mov     rcx, [rax+58h]
0x14003edcb  add     rcx, 40h ; '@'
0x14003edcf  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14003edd6  nop     dword ptr [rax+rax+00h]
0x14003eddb  test    al, al
0x14003eddd  jz      loc_14003EF2C
0x14003ede3  mov     rax, [r15+108h]
0x14003edea  mov     [r15+0F0h], rax
0x14003edf1  jmp     loc_14003EF2C
0x14003edf6  cmp     esi, 0C00001A8h
0x14003edfc  jnz     short loc_14003EE7B
0x14003edfe  lea     rdx, WPP_GLOBAL_Control
0x14003ee05  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ee0c  cmp     rcx, rdx
0x14003ee0f  jz      short loc_14003EE42
0x14003ee11  test    dword ptr [rcx+2Ch], 100h
0x14003ee18  jz      short loc_14003EE42
0x14003ee1a  cmp     byte ptr [rcx+29h], 4
0x14003ee1e  jb      short loc_14003EE42
0x14003ee20  mov     edx, 16h
0x14003ee25  mov     r9d, 0C0000808h
0x14003ee2b  lea     r8, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids
0x14003ee32  mov     rcx, [rcx+18h]
0x14003ee36  call    WPP_SF_d
0x14003ee3b  lea     rdx, WPP_GLOBAL_Control
0x14003ee42  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003ee49  test    al, al
0x14003ee4b  jz      short loc_14003EE6D
0x14003ee4d  mov     r9d, 658h; unsigned int
0x14003ee53  lea     r8, aNtfsdataC; "NtfsData.c"
0x14003ee5a  xor     edx, edx; struct _IRP_CONTEXT *
0x14003ee5c  mov     ecx, 0C0000808h; Status
0x14003ee61  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14003ee66  lea     rdx, WPP_GLOBAL_Control
0x14003ee6d  mov     esi, 0C0000808h
0x14003ee72  mov     [rsp+0A8h+arg_10], esi
0x14003ee79  jmp     short loc_14003EE82
0x14003ee7b  lea     rdx, WPP_GLOBAL_Control
0x14003ee82  mov     rcx, [rbx+18h]
0x14003ee86  test    rcx, rcx
0x14003ee89  jz      short loc_14003EEA4
0x14003ee8b  lea     rdx, [rbx+158h]
0x14003ee92  cmp     qword ptr [rdx], 0
0x14003ee96  jnz     short loc_14003EE9D
0x14003ee98  call    MsTriageGetContext
0x14003ee9d  lea     rdx, WPP_GLOBAL_Control
0x14003eea4  cmp     qword ptr [rbx+158h], 0
0x14003eeac  jz      short loc_14003EEBD
0x14003eeae  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003eeb1  call    ?RefsDiscardTriageInfo@@YAXPEAU_IRP_CONTEXT@@@Z; RefsDiscardTriageInfo(_IRP_CONTEXT *)
0x14003eeb6  lea     rdx, WPP_GLOBAL_Control
0x14003eebd  cmp     esi, 0C0000188h
0x14003eec3  jnz     short loc_14003EF2C
0x14003eec5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eecc  cmp     rcx, rdx
0x14003eecf  jz      short loc_14003EEFF
0x14003eed1  test    dword ptr [rcx+2Ch], 100h
0x14003eed8  jz      short loc_14003EEFF
0x14003eeda  cmp     byte ptr [rcx+29h], 4
0x14003eede  jb      short loc_14003EEFF
0x14003eee0  mov     edx, 17h
0x14003eee5  mov     esi, 0C000007Fh
0x14003eeea  mov     r9d, esi
0x14003eeed  lea     r8, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids
0x14003eef4  mov     rcx, [rcx+18h]
0x14003eef8  call    WPP_SF_d
0x14003eefd  jmp     short loc_14003EF04
0x14003eeff  mov     esi, 0C000007Fh
0x14003ef04  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003ef0b  test    al, al
0x14003ef0d  jz      short loc_14003EF25
0x14003ef0f  mov     r9d, 675h; unsigned int
0x14003ef15  lea     r8, aNtfsdataC; "NtfsData.c"
0x14003ef1c  xor     edx, edx; struct _IRP_CONTEXT *
0x14003ef1e  mov     ecx, esi; Status
0x14003ef20  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14003ef25  mov     [rsp+0A8h+arg_10], esi
0x14003ef2c  jmp     loc_14003F195
0x14003ef31  inc     cs:?RefsFailedAborts@@3KA; ulong RefsFailedAborts
0x14003ef37  lea     rdx, WPP_GLOBAL_Control; unsigned int
0x14003ef3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ef45  cmp     rcx, rdx
0x14003ef48  jz      short loc_14003EF88
0x14003ef4a  mov     edx, [rcx+2Ch]
0x14003ef4d  test    dl, 4
0x14003ef50  jz      short loc_14003EF88
0x14003ef52  cmp     byte ptr [rcx+29h], 2
0x14003ef56  jb      short loc_14003EF88
0x14003ef58  mov     dword ptr [rsp+0A8h+var_70], eax
0x14003ef5c  mov     rbx, [rsp+0A8h+arg_0]
0x14003ef64  mov     rax, [rbx+40h]
0x14003ef68  mov     qword ptr [rsp+0A8h+var_80], rax
0x14003ef6d  mov     r14, [rsp+0A8h+arg_8]
0x14003ef75  mov     qword ptr [rsp+0A8h+var_88], r14
0x14003ef7a  mov     r9, rbx
0x14003ef7d  mov     rcx, [rcx+18h]
0x14003ef81  call    WPP_SF_qqqDd
0x14003ef86  jmp     short loc_14003EF98
0x14003ef88  mov     r14, [rsp+0A8h+arg_8]
0x14003ef90  mov     rbx, [rsp+0A8h+arg_0]
0x14003ef98  lea     rcx, [rbx+280h]; struct _LIST_ENTRY *
0x14003ef9f  xor     r8d, r8d; struct _ROLLBACK_STRUCT *
0x14003efa2  call    ?RefsFindRollbackStructByType@@YAPEAU_ROLLBACK_STRUCT@@PEAU_LIST_ENTRY@@KPEAU1@@Z; RefsFindRollbackStructByType(_LIST_ENTRY *,ulong,_ROLLBACK_STRUCT *)
0x14003efa7  mov     rsi, rax
0x14003efaa  test    rax, rax
0x14003efad  jz      loc_14003F12F
0x14003efb3  mov     rdi, [rsi+30h]
0x14003efb7  test    rdi, rdi
0x14003efba  jz      loc_14003F114
0x14003efc0  lea     rax, WPP_GLOBAL_Control
0x14003efc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003efce  cmp     rcx, rax
0x14003efd1  jz      short loc_14003F022
0x14003efd3  mov     eax, [rcx+2Ch]
0x14003efd6  test    al, 4
0x14003efd8  jz      short loc_14003F022
0x14003efda  cmp     byte ptr [rcx+29h], 2
0x14003efde  jb      short loc_14003F022
0x14003efe0  mov     rax, [rdi+88h]
0x14003efe7  mov     rdx, [rax+58h]
0x14003efeb  mov     rax, [rdx+0F8h]
0x14003eff2  mov     [rsp+0A8h+var_68], rax
0x14003eff7  mov     rax, [rdx+100h]
0x14003effe  mov     [rsp+0A8h+var_70], rax
0x14003f003  mov     [rsp+0A8h+var_78], rdi
0x14003f008  mov     rax, [rbx+40h]
0x14003f00c  mov     qword ptr [rsp+0A8h+var_80], rax
0x14003f011  mov     qword ptr [rsp+0A8h+var_88], r14
0x14003f016  mov     r9, rbx
0x14003f019  mov     rcx, [rcx+18h]
0x14003f01d  call    WPP_SF_qqqqii
0x14003f022  mov     rax, [rdi+88h]
0x14003f029  mov     ecx, [rax+8]
0x14003f02c  test    rcx, 104h
0x14003f033  jnz     short loc_14003F0B1
0x14003f035  mov     eax, [rdi+98h]
0x14003f03b  test    eax, 220h
0x14003f040  jz      short loc_14003F04D
0x14003f042  lock and dword ptr [rdi+98h], 0FFFFFDDFh
0x14003f04d  mov     qword ptr [rdi+18h], 0
0x14003f055  mov     eax, 805h
0x14003f05a  cmp     [rdi], ax
0x14003f05d  jnz     short loc_14003F06A
0x14003f05f  mov     qword ptr [rdi+1A8h], 0
0x14003f06a  mov     qword ptr [rdi+20h], 0
0x14003f072  mov     qword ptr [rdi+28h], 0
0x14003f07a  cmp     [rdi], ax
0x14003f07d  jnz     short loc_14003F094
0x14003f07f  cmp     qword ptr [rdi+1A8h], 0
0x14003f087  jge     short loc_14003F094
0x14003f089  mov     qword ptr [rdi+1A8h], 0
0x14003f094  cmp     qword ptr [rdi+0F0h], 0
0x14003f09c  jz      short loc_14003F110
0x14003f09e  mov     r8d, 1; unsigned int
0x14003f0a4  mov     rdx, rdi; struct _SCB *
0x14003f0a7  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003f0aa  call    ?RefsDeleteInternalAttributeStream@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@KE@Z; RefsDeleteInternalAttributeStream(_IRP_CONTEXT *,_SCB *,ulong,uchar)
0x14003f0af  jmp     short loc_14003F110
0x14003f0b1  mov     rax, [rdi+18h]
0x14003f0b5  cmp     [rsi+18h], rax
0x14003f0b9  jge     short loc_14003F0D8
0x14003f0bb  mov     rax, [rsi+18h]
0x14003f0bf  mov     [rdi+18h], rax
0x14003f0c3  mov     eax, 805h
0x14003f0c8  cmp     [rdi], ax
0x14003f0cb  jnz     short loc_14003F0D8
0x14003f0cd  mov     rax, [rsi+18h]
0x14003f0d1  mov     [rdi+1A8h], rax
0x14003f0d8  mov     rax, [rdi+20h]
0x14003f0dc  cmp     [rsi+20h], rax
0x14003f0e0  jge     short loc_14003F110
0x14003f0e2  mov     rax, [rsi+20h]
0x14003f0e6  mov     [rdi+20h], rax
0x14003f0ea  mov     rax, [rsi+20h]
0x14003f0ee  mov     [rdi+28h], rax
0x14003f0f2  mov     eax, 805h
0x14003f0f7  cmp     [rdi], ax
0x14003f0fa  jnz     short loc_14003F110
0x14003f0fc  mov     rax, [rsi+20h]
0x14003f100  cmp     [rdi+1A8h], rax
0x14003f107  jge     short loc_14003F110
0x14003f109  mov     [rdi+1A8h], rax
0x14003f110  mov     byte ptr [rdi+5], 0
0x14003f114  mov     r8, rsi; struct _ROLLBACK_STRUCT *
0x14003f117  lea     rcx, [rbx+280h]; struct _LIST_ENTRY *
0x14003f11e  call    ?RefsFindRollbackStructByType@@YAPEAU_ROLLBACK_STRUCT@@PEAU_LIST_ENTRY@@KPEAU1@@Z; RefsFindRollbackStructByType(_LIST_ENTRY *,ulong,_ROLLBACK_STRUCT *)
0x14003f123  mov     rsi, rax
0x14003f126  test    rax, rax
0x14003f129  jnz     loc_14003EFB3
0x14003f12f  mov     r15, [rsp+0A8h+var_50]
0x14003f134  test    r15, r15
0x14003f137  jz      short loc_14003F181
0x14003f139  mov     rax, [r15+108h]
0x14003f140  cmp     [r15+0F0h], rax
  ... truncated ...
```
