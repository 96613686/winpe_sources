# RxCompleteRequestEx

- ea: `0x1400027b0`
- end: `0x140002fe4`
- name: `RxCompleteRequestEx`
- size: `2100`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `14`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400015e0`
- `0x140001760`
- `0x140002300`
- `0x140015290`
- `0x14001af40`
- `0x14001b490`
- `0x14001b760`
- `0x140044360`
- `0x14004698c`
- `0x140048874`
- `0x140048f10`
- `0x14004a4e0`
- `0x14006f470`
- `0x140077a20`

## callees

- `0x140001240`
- `0x1400027b0`
- `0x140002ff0`
- `0x1400037e0`
- `0x140003f50`
- `0x140015230`
- `0x1400166e0`
- `0x140016e70`
- `0x14001f780`
- `0x14001f7f4`
- `0x14001f8a8`
- `0x14002540c`
- `0x140058f00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002a28`
- `ntoskrnl!IofCompleteRequest` at `0x140002a28`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002da3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002da3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400029a9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002c06`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002c1e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400029a9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002c06`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002c1e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000292f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000292f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002eb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026fa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002eb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026fa8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000291b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000291b`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140002bd8`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140002bd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002893`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002893`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e43`

## pseudocode

```c
void __fastcall RxCompleteRequestEx(PRX_CONTEXT RxContext, PIRP Irp, NTSTATUS a3)
{
  ULONG Flags; // eax
  _QWORD *v7; // rdx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rtt
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rtt
  unsigned int v12; // r8d
  KIRQL v13; // r9
  __int64 v14; // rbp
  unsigned int v15; // edx
  char v16; // r8
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  CCHAR v21; // bp
  PFILE_OBJECT FileObject; // r13
  wchar_t *p_Length; // r12
  char RealDevice; // al
  PDEVICE_OBJECT v25; // rcx
  __int64 *LockManagerContext; // rdi
  __int64 *v27; // rcx
  int RdbssDbgExtension; // eax
  __int64 v29; // rsi
  KSPIN_LOCK *v30; // r14
  signed __int64 *v31; // rdx
  unsigned __int64 v32; // rtt
  PSZ v33; // rcx
  PMRX_FOBX pFobx; // rcx
  PVOID v35; // rcx
  signed __int64 j; // rax
  signed __int64 *v37; // rax
  __int64 v38; // r8
  signed __int64 *v39; // rdx
  unsigned __int64 v40; // rtt
  signed __int64 i; // rax
  signed __int64 *v42; // rax
  KIRQL v43; // al
  __int64 *v44; // rcx
  KIRQL v45; // r9
  __int64 *v46; // rdx
  __int64 **v47; // rax
  KSPIN_LOCK v48; // rax
  PSZ FileName; // rdx
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rtt
  signed __int64 v53; // rtt
  unsigned __int64 v54; // rtt
  signed __int64 v55; // rtt
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // rax
  __int64 v58; // r9
  int v59; // [rsp+20h] [rbp-78h]
  KIRQL Irql; // [rsp+A0h] [rbp+8h] BYREF
  ULONG Options; // [rsp+A8h] [rbp+10h]

  if ( RxContext )
  {
    Flags = RxContext->TrackerHistory[9].Flags;
    switch ( Flags )
    {
      case 1u:
        v38 = *(_QWORD *)&RxContext->NonPagedFcb[2].AdvancedFcbHeaderMutex.OldIrql;
        v39 = (signed __int64 *)(*(_QWORD *)v38
                               + (unsigned int)(*(_DWORD *)(v38 + 20)
                                              * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v38 + 24))));
        _m_prefetchw(v39);
        v40 = *v39 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v40 != _InterlockedCompareExchange64(v39, v40 - 2, v40) )
        {
          for ( i = *v39; ; i = *v42 )
          {
            while ( (i & 1) == 0 )
            {
              v53 = i;
              i = _InterlockedCompareExchange64(v39, i - 2, i);
              if ( v53 == i )
                goto LABEL_12;
            }
            if ( i != 1 )
              break;
            v42 = *(signed __int64 **)v38;
            if ( v39 == *(signed __int64 **)v38 )
              __int2c();
            v39 = *(signed __int64 **)v38;
            _m_prefetchw(v42);
          }
          RfsDecrementRundownWaitBlockCount(i & 0xFFFFFFFFFFFFFFFEuLL, v39);
        }
        goto LABEL_12;
      case 2u:
        v7 = *(_QWORD **)&RxContext->TrackerHistory[10].AcquireRelease;
        _m_prefetchw(v7);
        v8 = *v7 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v8 < 2 || (v9 = *v7 & 0xFFFFFFFFFFFFFFFEuLL, v9 != _InterlockedCompareExchange64(v7, v8 - 2, v8)) )
        {
          _m_prefetchw(v7);
          v10 = *v7;
          while ( (v10 & 1) == 0 )
          {
            if ( v10 < 2 )
              __int2c();
            v11 = v10;
            v10 = _InterlockedCompareExchange64(v7, v10 - 2, v10);
            if ( v11 == v10 )
              goto LABEL_11;
          }
          v56 = v10 & 0xFFFFFFFFFFFFFFFEuLL;
          if ( !v56 )
            __int2c();
          RfsDecrementRundownWaitBlockCount(v56, v7);
        }
LABEL_11:
        *(_QWORD *)&RxContext->TrackerHistory[10].AcquireRelease = 0;
LABEL_12:
        RxContext->TrackerHistory[9].Flags = 0;
        break;
      case 3u:
        FileName = RxContext->TrackerHistory[10].FileName;
        _m_prefetchw(FileName);
        v50 = *(_QWORD *)FileName & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v50 < 2
          || (v54 = *(_QWORD *)FileName & 0xFFFFFFFFFFFFFFFEuLL,
              v54 != _InterlockedCompareExchange64((volatile signed __int64 *)FileName, v50 - 2, v50)) )
        {
          _m_prefetchw(FileName);
          v51 = *(_QWORD *)FileName;
          while ( (v51 & 1) == 0 )
          {
            if ( v51 < 2 )
              __int2c();
            v52 = v51;
            v51 = _InterlockedCompareExchange64((volatile signed __int64 *)FileName, v51 - 2, v51);
            if ( v52 == v51 )
              goto LABEL_128;
          }
          v57 = v51 & 0xFFFFFFFFFFFFFFFEuLL;
          if ( !v57 )
            __int2c();
          RfsDecrementRundownWaitBlockCount(v57, FileName);
        }
LABEL_128:
        RxContext->TrackerHistory[10].FileName = 0;
        goto LABEL_12;
    }
  }
  if ( Irp )
  {
    if ( RxContext )
      v12 = ((unsigned __int8)(WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length)
                             % (unsigned int)RxActiveContextNodeBucketSize)
           + (_BYTE)RxActiveContextNodeBucketSize
           * (unsigned __int8)LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags))
          & 0x3F;
    else
      v12 = 0;
    v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock + 24 * v12);
    v14 = _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
    _InterlockedExchange64((volatile __int64 *)&Irp->Tail, 0);
    if ( RxContext )
    {
      v15 = WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length) % (unsigned int)RxActiveContextNodeBucketSize;
      v16 = RxActiveContextNodeBucketSize * LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags);
      RxContext->CurrentIrp = 0;
      RxContext->CurrentIrpSp = 0;
      v17 = ((_BYTE)v15 + v16) & 0x3F;
    }
    else
    {
      v17 = 0;
    }
    KeReleaseSpinLock(&SpinLock + 24 * v17, v13);
    if ( !v14 )
    {
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    if ( a3 != -1 )
    {
      if ( a3 == RxDebugBreakStatus && (RxDebugBreakOpcode == -1 || RxDebugBreakOpcode == LOBYTE(RxContext->RealDevice)) )
        __debugbreak();
      if ( (a3 & 0xC0000000) != 0xC0000000 )
        goto LABEL_25;
    }
    if ( (Irp->Flags & 0x40) != 0 )
    {
      Irp->IoStatus.Information = 0;
      v21 = 0;
    }
    else
    {
LABEL_25:
      v21 = 1;
    }
    Irp->IoStatus.Status = a3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qLDD(
        WPP_GLOBAL_Control->AttachedDevice,
        Irp->Tail.Overlay.CurrentStackLocation->MajorFunction,
        v19,
        Irp,
        Irp->Tail.Overlay.CurrentStackLocation->MajorFunction,
        a3,
        Irp->IoStatus.Information);
    }
    if ( !RxContext )
    {
LABEL_36:
      if ( CurrentStackLocation->MajorFunction || a3 == 259 )
      {
        if ( RxContext )
        {
LABEL_68:
          if ( CurrentStackLocation->MajorFunction && RxContext->pFcb )
            KeGetCurrentIrql();
          if ( ((CurrentStackLocation->MajorFunction & 0xED) != 0 || CurrentStackLocation->MajorFunction == 16)
            && KeGetCurrentIrql() < 2u )
          {
            pFobx = RxContext->pFobx;
            if ( pFobx )
            {
              if ( a3 != -1073741802 )
              {
                *(_DWORD *)&pFobx[3].UnicodeQueryTemplate.Length = HIDWORD(pFobx[3].PipeHandleInformation);
                HIDWORD(pFobx[3].PipeHandleInformation) = a3;
              }
            }
          }
        }
      }
      else if ( RxContext )
      {
        if ( a3 == -2147483603 )
        {
          Irp->IoStatus.Status = 260;
          v58 = *(_QWORD *)&RxContext->TrackerHistory[6].Flags;
          if ( v58 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids, v58);
            }
            Irp->Tail.Overlay.AuxiliaryBuffer = *(PCHAR *)&RxContext->TrackerHistory[6].Flags;
            Irp->IoStatus.Information = **(unsigned int **)&RxContext->TrackerHistory[6].Flags;
            if ( (BYTE2(RxContext->TrackerHistory[4].FileName) & 2) != 0 )
              *(_WORD *)(*(_QWORD *)&RxContext->TrackerHistory[6].Flags + 6LL) += 2;
            *(_QWORD *)&RxContext->TrackerHistory[6].Flags = 0;
          }
          else
          {
            Irp->Tail.Overlay.AuxiliaryBuffer = 0;
            Irp->IoStatus.Information = 0;
          }
        }
        v33 = RxContext->TrackerHistory[1].FileName;
        if ( v33 )
          FsRtlAcknowledgeEcp(v33);
        if ( (BYTE2(RxContext->TrackerHistory[4].FileName) & 2) != 0 )
          CurrentStackLocation->FileObject->FileName.Length += 2;
        RxpFinalizeCreateContext(RxContext);
        goto LABEL_68;
      }
      if ( RxEnablePerProcessCounters )
      {
        if ( RxContext )
        {
          v35 = RxContext->MRxContext[1];
          if ( v35 )
          {
            RdbssStatisticsEntryUpdateSocketCounters(
              v35,
              v18,
              LODWORD(RxContext->ForceLonglongAligmentDummyField),
              HIDWORD(RxContext->MRxContext[0]));
            RxContext->ForceLonglongAligmentDummyField = 0;
          }
        }
      }
      IofCompleteRequest(Irp, v21);
      goto LABEL_40;
    }
    FileObject = CurrentStackLocation->FileObject;
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( KeGetCurrentIrql() >= 2u )
      p_Length = DpcDummyName;
    else
      p_Length = &FileObject->FileName.Length;
    if ( ((__int64)RxContext->RealDevice & 0xFD) == 0 || (FCB *)RxContext->pFcb != &RxDeviceFCB )
    {
      v18 = MEMORY[0xFFFFF78000000008];
      if ( (int)(a3 + 0x80000000) < 0 || a3 == -2147483643 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          LOWORD(v59) = LOBYTE(RxContext->RealDevice);
          WPP_SF_qhDqDDqi(
            WPP_GLOBAL_Control->AttachedDevice,
            (MEMORY[0xFFFFF78000000008] - *(_QWORD *)&RxContext->MajorFunction) / 0x2710uLL,
            BYTE1(RxContext->RealDevice),
            Irp,
            v59,
            BYTE1(RxContext->RealDevice),
            RxContext,
            a3,
            Irp->IoStatus.Information,
            FileObject,
            (MEMORY[0xFFFFF78000000008] - *(_QWORD *)&RxContext->MajorFunction) / 0x2710uLL);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qhDqDDqiZ(
          WPP_GLOBAL_Control->AttachedDevice,
          (MEMORY[0xFFFFF78000000008] - *(_QWORD *)&RxContext->MajorFunction) / 0x2710uLL,
          BYTE1(RxContext->RealDevice),
          (_DWORD)Irp,
          (char)RxContext->RealDevice,
          BYTE1(RxContext->RealDevice),
          (char)RxContext,
          a3,
          Irp->IoStatus.Information,
          (char)FileObject,
          (MEMORY[0xFFFFF78000000008] - *(_QWORD *)&RxContext->MajorFunction) / 0x2710uLL,
          (__int64)p_Length);
      }
    }
    RealDevice = (char)RxContext->RealDevice;
    if ( RealDevice == 6 )
    {
      if ( Options - 10 <= 1 )
        goto LABEL_98;
    }
    else if ( RealDevice == 12 && BYTE1(RxContext->RealDevice) == 1 )
    {
LABEL_98:
      if ( *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) )
      {
        SeReleaseSubjectContext((PSECURITY_SUBJECT_CONTEXT)((char *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory
                                                          + 40));
        *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) = 0;
      }
    }
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 2) != 0 )
      McTemplateK0ppppphzr5hq_EtwWriteTransfer(
        *p_Length >> 1,
        v18,
        (_DWORD)RxContext + 412,
        (_DWORD)Irp,
        (char)RxContext,
        (char)FileObject->FsContext,
        (char)FileObject->FsContext2,
        (char)FileObject,
        *p_Length >> 1,
        *((_QWORD *)p_Length + 1),
        CurrentStackLocation->MajorFunction,
        a3);
    goto LABEL_36;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids, RxContext);
  }
LABEL_40:
  if ( RxContext )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v25, ActivityStop, &RxContext->LowIoContext.Flags + 1);
    LockManagerContext = (__int64 *)RxContext->LockManagerContext;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        RxContext,
        RxContext->LockManagerContext);
    }
    if ( LockManagerContext )
    {
      if ( LOBYTE(RxContext->RealDevice) != 12 || (v27 = LockManagerContext + 28, BYTE1(RxContext->RealDevice) != 2) )
        v27 = LockManagerContext + 27;
      RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
      if ( (RdbssDbgExtension & 0x40000) != 0 )
      {
        v29 = *v27;
        LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFBFFFF;
        v30 = (KSPIN_LOCK *)LockManagerContext[31];
        if ( v30 && (*((_DWORD *)v30 + 11) & 1) != 0 )
        {
          v43 = KeAcquireSpinLockRaiseToDpc(v30 + 6);
          v44 = (__int64 *)v30[2];
          v45 = v43;
          while ( 1 )
          {
            if ( v44 == (__int64 *)(v30 + 2) )
            {
              KeReleaseSpinLock(v30 + 6, v43);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  10,
                  WPP_c67f36e2ff9e320a2e17190ae1362256_Traceguids,
                  RxContext,
                  v30);
              }
              __debugbreak();
            }
            v46 = (__int64 *)*v44;
            if ( (PRX_CONTEXT)v44[7] == RxContext )
              break;
            v44 = (__int64 *)*v44;
          }
          if ( (__int64 *)v46[1] != v44
            || (v47 = (__int64 **)v44[1], *v47 != v44)
            || (*v47 = v46, v46[1] = (__int64)v47, v44[7] = 0, v48 = *v30, *(KSPIN_LOCK **)(*v30 + 8) != v30) )
          {
            __fastfail(3u);
          }
          *v44 = v48;
          v44[1] = (__int64)v30;
          *(_QWORD *)(v48 + 8) = v44;
          *v30 = (KSPIN_LOCK)v44;
          KeReleaseSpinLock(v30 + 6, v45);
        }
        v31 = (signed __int64 *)(*(_QWORD *)v29
                               + (unsigned int)(*(_DWORD *)(v29 + 20)
                                              * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v29 + 24))));
        _m_prefetchw(v31);
        v32 = *v31 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( v32 != _InterlockedCompareExchange64(v31, v32 - 2, v32) )
        {
          for ( j = *v31; ; j = *v37 )
          {
            while ( (j & 1) == 0 )
            {
              v55 = j;
              j = _InterlockedCompareExchange64(v31, j - 2, j);
              if ( v55 == j )
                goto LABEL_58;
            }
            if ( j != 1 )
              break;
            v37 = *(signed __int64 **)v29;
            if ( v31 == *(signed __int64 **)v29 )
              __int2c();
            v31 = *(signed __int64 **)v29;
            _m_prefetchw(v37);
          }
          RfsDecrementRundownWaitBlockCount(j & 0xFFFFFFFFFFFFFFFEuLL, v31);
        }
      }
LABEL_58:
      RxContext->LockManagerContext = 0;
      RxDereference(LockManagerContext, LHS_LockNotHeld);
    }
    RxDereferenceAndDeleteRxContext_Real(RxContext);
  }
}

```

## disassembly

```asm
0x1400027b0  push    rbx
0x1400027b2  push    rsi
0x1400027b3  push    rdi
0x1400027b4  push    r12
0x1400027b6  sub     rsp, 78h
0x1400027ba  xor     r12d, r12d
0x1400027bd  mov     esi, r8d
0x1400027c0  mov     rdi, rdx
0x1400027c3  mov     rbx, rcx
0x1400027c6  test    rcx, rcx
0x1400027c9  jz      short loc_140002834
0x1400027cb  mov     eax, [rcx+368h]
0x1400027d1  cmp     eax, 1
0x1400027d4  jz      loc_140002DD1
0x1400027da  cmp     eax, 2
0x1400027dd  jnz     loc_140002EDA
0x1400027e3  mov     rdx, [rcx+370h]
0x1400027ea  prefetchw byte ptr [rdx]
0x1400027ed  mov     rax, [rdx]
0x1400027f0  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400027f4  cmp     rax, 2
0x1400027f8  jb      short loc_140002805
0x1400027fa  lea     rcx, [rax-2]
0x1400027fe  lock cmpxchg [rdx], rcx
0x140002803  jz      short loc_140002826
0x140002805  prefetchw byte ptr [rdx]
0x140002808  mov     rax, [rdx]
0x14000280b  test    al, 1
0x14000280d  jnz     loc_140026E1C
0x140002813  cmp     rax, 2
0x140002817  jnb     short loc_14000281B
0x140002819  int     2Ch; Windows NT - assertion failure
0x14000281b  lea     rcx, [rax-2]
0x14000281f  lock cmpxchg [rdx], rcx
0x140002824  jnz     short loc_14000280B
0x140002826  mov     [rbx+370h], r12
0x14000282d  mov     [rbx+368h], r12d
0x140002834  mov     [rsp+98h+arg_10], rbp
0x14000283c  mov     [rsp+98h+var_30], r14
0x140002841  mov     [rsp+98h+var_38], r15
0x140002846  test    rdi, rdi
0x140002849  jz      loc_140002CDB
0x14000284f  test    rbx, rbx
0x140002852  jz      loc_140002F5C
0x140002858  movzx   eax, word ptr [rbx+1BAh]
0x14000285f  xor     edx, edx
0x140002861  div     cs:RxActiveContextNodeBucketSize
0x140002867  movzx   r8d, word ptr [rbx+1B8h]
0x14000286f  imul    r8d, cs:RxActiveContextNodeBucketSize
0x140002877  add     r8d, edx
0x14000287a  and     r8d, 3Fh
0x14000287e  mov     eax, r8d
0x140002881  lea     r14, SpinLock
0x140002888  lea     rcx, [rax+rax*2]
0x14000288c  shl     rcx, 6
0x140002890  add     rcx, r14; SpinLock
0x140002893  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000289a  nop     dword ptr [rax+rax+00h]
0x14000289f  mov     rbp, r12
0x1400028a2  mov     rcx, r12
0x1400028a5  movzx   r9d, al
0x1400028a9  xchg    rbp, [rdi+68h]
0x1400028ad  xchg    rcx, [rdi+78h]
0x1400028b1  test    rbx, rbx
0x1400028b4  jz      loc_140002ABA
0x1400028ba  movzx   eax, word ptr [rbx+1BAh]
0x1400028c1  xor     edx, edx
0x1400028c3  div     cs:RxActiveContextNodeBucketSize
0x1400028c9  movzx   r8d, word ptr [rbx+1B8h]
0x1400028d1  imul    r8d, cs:RxActiveContextNodeBucketSize
0x1400028d9  mov     [rbx+28h], r12
0x1400028dd  mov     [rbx+30h], r12
0x1400028e1  add     r8d, edx
0x1400028e4  and     r8d, 3Fh
0x1400028e8  mov     eax, r8d
0x1400028eb  movzx   edx, r9b; NewIrql
0x1400028ef  lea     rcx, [rax+rax*2]
0x1400028f3  shl     rcx, 6
0x1400028f7  add     rcx, r14; SpinLock
0x1400028fa  call    cs:__imp_KeReleaseSpinLock
0x140002901  nop     dword ptr [rax+rax+00h]
0x140002906  test    rbp, rbp
0x140002909  jnz     short loc_14000293B
0x14000290b  lea     rcx, [rsp+98h+Irql]; Irql
0x140002913  mov     [rsp+98h+Irql], r12b
0x14000291b  call    cs:__imp_IoAcquireCancelSpinLock
0x140002922  nop     dword ptr [rax+rax+00h]
0x140002927  movzx   ecx, [rsp+98h+Irql]; Irql
0x14000292f  call    cs:__imp_IoReleaseCancelSpinLock
0x140002936  nop     dword ptr [rax+rax+00h]
0x14000293b  mov     r14, [rdi+0B8h]
0x140002942  cmp     esi, 0FFFFFFFFh
0x140002945  jnz     short loc_140002957
0x140002947  mov     eax, [rdi+10h]
0x14000294a  test    al, 40h
0x14000294c  jz      short loc_140002973
0x14000294e  mov     [rdi+38h], r12
0x140002952  xor     bpl, bpl
0x140002955  jmp     short loc_140002976
0x140002957  mov     eax, cs:RxDebugBreakStatus
0x14000295d  cmp     esi, eax
0x14000295f  jz      loc_140002F64
0x140002965  mov     eax, esi
0x140002967  and     eax, 0C0000000h
0x14000296c  cmp     eax, 0C0000000h
0x140002971  jz      short loc_140002947
0x140002973  mov     bpl, 1
0x140002976  mov     [rdi+30h], esi
0x140002979  mov     rcx, cs:WPP_GLOBAL_Control
0x140002980  lea     r15, WPP_GLOBAL_Control
0x140002987  cmp     rcx, r15
0x14000298a  jnz     loc_140002C62
0x140002990  test    rbx, rbx
0x140002993  jz      short loc_140002A01
0x140002995  mov     eax, [r14+10h]
0x140002999  mov     [rsp+98h+var_28], r13
0x14000299e  mov     r13, [r14+30h]
0x1400029a2  mov     [rsp+98h+arg_8], eax
0x1400029a9  call    cs:__imp_KeGetCurrentIrql
0x1400029b0  nop     dword ptr [rax+rax+00h]
0x1400029b5  cmp     al, 2
0x1400029b7  jnb     loc_140002A5A
0x1400029bd  lea     r12, [r13+58h]
0x1400029c1  test    byte ptr [rbx+20h], 0FDh
0x1400029c5  jz      loc_140002AC2
0x1400029cb  lea     rax, RxDeviceFCB
0x1400029d2  cmp     [rbx+38h], rax
0x1400029d6  jnz     loc_140002AC2
0x1400029dc  movzx   eax, byte ptr [rbx+20h]
0x1400029e0  cmp     al, 6
0x1400029e2  jz      loc_140002F8A
0x1400029e8  cmp     al, 0Ch
0x1400029ea  jz      loc_140002D85
0x1400029f0  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 2
0x1400029f7  jnz     short loc_140002A66
0x1400029f9  mov     r13, [rsp+98h+var_28]
0x1400029fe  xor     r12d, r12d
0x140002a01  cmp     byte ptr [r14], 0
0x140002a05  jz      loc_140002BAB
0x140002a0b  test    rbx, rbx
0x140002a0e  jnz     loc_140002BF9
0x140002a14  cmp     cs:RxEnablePerProcessCounters, 0
0x140002a1b  jnz     loc_140002CA1
0x140002a21  movzx   edx, bpl; PriorityBoost
0x140002a25  mov     rcx, rdi; Irp
0x140002a28  call    cs:__imp_IofCompleteRequest
0x140002a2f  nop     dword ptr [rax+rax+00h]
0x140002a34  test    rbx, rbx
0x140002a37  jnz     loc_140002AFF
0x140002a3d  mov     r15, [rsp+98h+var_38]
0x140002a42  mov     r14, [rsp+98h+var_30]
0x140002a47  mov     rbp, [rsp+98h+arg_10]
0x140002a4f  add     rsp, 78h
0x140002a53  pop     r12
0x140002a55  pop     rdi
0x140002a56  pop     rsi
0x140002a57  pop     rbx
0x140002a58  retn
0x140002a5a  lea     r12, DpcDummyName; "\b\b"
0x140002a61  jmp     loc_1400029C1
0x140002a66  movzx   eax, byte ptr [r14]
0x140002a6a  lea     r8, [rbx+19Ch]
0x140002a71  movzx   ecx, word ptr [r12]
0x140002a76  mov     r9, rdi
0x140002a79  mov     dword ptr [rsp+98h+var_40], esi
0x140002a7d  mov     word ptr [rsp+98h+var_48], ax
0x140002a82  mov     rax, [r12+8]
0x140002a87  mov     [rsp+98h+var_50], rax
0x140002a8c  mov     rax, [r13+20h]
0x140002a90  shr     cx, 1
0x140002a93  mov     word ptr [rsp+98h+var_58], cx
0x140002a98  mov     [rsp+98h+var_60], r13
0x140002a9d  mov     [rsp+98h+var_68], rax
0x140002aa2  mov     rax, [r13+18h]
0x140002aa6  mov     [rsp+98h+var_70], rax
0x140002aab  mov     [rsp+98h+var_78], rbx
0x140002ab0  call    McTemplateK0ppppphzr5hq_EtwWriteTransfer
0x140002ab5  jmp     loc_1400029F9
0x140002aba  mov     r8d, r12d
0x140002abd  jmp     loc_1400028E8
0x140002ac2  mov     ecx, 80000000h
0x140002ac7  mov     rdx, 0FFFFF78000000008h
0x140002ad1  mov     rdx, [rdx]
0x140002ad4  lea     eax, [rsi+rcx]
0x140002ad7  test    ecx, eax
0x140002ad9  jz      loc_140002D24
0x140002adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ae6  cmp     rcx, r15
0x140002ae9  jz      loc_1400029DC
0x140002aef  mov     eax, [rcx+2Ch]
0x140002af2  test    al, 4
0x140002af4  jz      loc_1400029DC
0x140002afa  jmp     loc_140026EB3
0x140002aff  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140002b05  test    eax, eax
0x140002b07  jnz     loc_140002EC2
0x140002b0d  mov     rdi, [rbx+70h]
0x140002b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b18  cmp     rcx, r15
0x140002b1b  jz      short loc_140002B2A
0x140002b1d  test    dword ptr [rcx+2Ch], 400h
0x140002b24  jnz     loc_140002FB0
0x140002b2a  test    rdi, rdi
0x140002b2d  jz      short loc_140002B9E
0x140002b2f  cmp     byte ptr [rbx+20h], 0Ch
0x140002b33  jz      loc_140002DBB
0x140002b39  lea     rcx, [rdi+0D8h]
0x140002b40  mov     eax, [rbx+78h]
0x140002b43  bt      eax, 12h
0x140002b47  jnb     short loc_140002B90
0x140002b49  mov     rsi, [rcx]
0x140002b4c  btr     eax, 12h
0x140002b50  mov     [rbx+78h], eax
0x140002b53  mov     r14, [rdi+0F8h]
0x140002b5a  test    r14, r14
0x140002b5d  jnz     loc_140002E33
0x140002b63  mov     eax, gs:1A4h
0x140002b6b  xor     edx, edx
0x140002b6d  div     dword ptr [rsi+18h]
0x140002b70  imul    edx, [rsi+14h]
0x140002b74  add     rdx, [rsi]
0x140002b77  prefetchw byte ptr [rdx]
0x140002b7a  mov     rax, [rdx]
0x140002b7d  and     rax, 0FFFFFFFFFFFFFFFEh
0x140002b81  lea     rcx, [rax-2]
0x140002b85  lock cmpxchg [rdx], rcx
0x140002b8a  jnz     loc_140002D5D
0x140002b90  xor     edx, edx; LockHoldingState
0x140002b92  mov     [rbx+70h], r12
0x140002b96  mov     rcx, rdi; Instance
0x140002b99  call    RxDereference
0x140002b9e  mov     rcx, rbx; RxContext
0x140002ba1  call    RxDereferenceAndDeleteRxContext_Real
0x140002ba6  jmp     loc_140002A3D
0x140002bab  cmp     esi, 103h
0x140002bb1  jz      loc_140002A0B
0x140002bb7  test    rbx, rbx
0x140002bba  jz      loc_140002A14
0x140002bc0  cmp     esi, 8000002Dh
0x140002bc6  jz      loc_140026F13
0x140002bcc  mov     rcx, [rbx+2A0h]; EcpContext
0x140002bd3  test    rcx, rcx
0x140002bd6  jz      short loc_140002BE4
0x140002bd8  call    cs:__imp_FsRtlAcknowledgeEcp
0x140002bdf  nop     dword ptr [rax+rax+00h]
0x140002be4  test    byte ptr [rbx+2EAh], 2
0x140002beb  jnz     loc_140002FA2
0x140002bf1  mov     rcx, rbx
0x140002bf4  call    RxpFinalizeCreateContext
0x140002bf9  cmp     byte ptr [r14], 0
0x140002bfd  jz      short loc_140002C12
0x140002bff  cmp     qword ptr [rbx+38h], 0
0x140002c04  jz      short loc_140002C12
0x140002c06  call    cs:__imp_KeGetCurrentIrql
0x140002c0d  nop     dword ptr [rax+rax+00h]
0x140002c12  movzx   eax, byte ptr [r14]
0x140002c16  test    al, 0EDh
0x140002c18  jz      loc_140002D50
0x140002c1e  call    cs:__imp_KeGetCurrentIrql
0x140002c25  nop     dword ptr [rax+rax+00h]
0x140002c2a  cmp     al, 2
0x140002c2c  jnb     loc_140002A14
0x140002c32  mov     rcx, [rbx+40h]
0x140002c36  test    rcx, rcx
0x140002c39  jz      loc_140002A14
0x140002c3f  cmp     esi, 0C0000016h
0x140002c45  jz      loc_140002A14
0x140002c4b  mov     eax, [rcx+10Ch]
0x140002c51  mov     [rcx+108h], eax
0x140002c57  mov     [rcx+10Ch], esi
0x140002c5d  jmp     loc_140002A14
0x140002c62  mov     eax, [rcx+2Ch]
0x140002c65  test    al, 2
0x140002c67  jz      loc_140002990
0x140002c6d  cmp     byte ptr [rcx+29h], 4
0x140002c71  jb      loc_140002990
0x140002c77  mov     rax, [rdi+0B8h]
0x140002c7e  mov     r9, rdi
0x140002c81  mov     rcx, [rcx+18h]
0x140002c85  movzx   edx, byte ptr [rax]
0x140002c88  mov     eax, [rdi+38h]
0x140002c8b  mov     dword ptr [rsp+98h+var_68], eax
0x140002c8f  mov     dword ptr [rsp+98h+var_70], esi
0x140002c93  mov     dword ptr [rsp+98h+var_78], edx
0x140002c97  call    WPP_SF_qLDD
0x140002c9c  jmp     loc_140002990
0x140002ca1  test    rbx, rbx
0x140002ca4  jz      loc_140002A21
0x140002caa  mov     rcx, [rbx+0C8h]
0x140002cb1  test    rcx, rcx
0x140002cb4  jz      loc_140002A21
0x140002cba  mov     r9d, [rbx+0C4h]
0x140002cc1  mov     r8d, [rbx+0C0h]
0x140002cc8  call    RdbssStatisticsEntryUpdateSocketCounters
0x140002ccd  xor     eax, eax
0x140002ccf  mov     [rbx+0C0h], rax
0x140002cd6  jmp     loc_140002A21
0x140002cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ce2  lea     r15, WPP_GLOBAL_Control
0x140002ce9  cmp     rcx, r15
  ... truncated ...
```
