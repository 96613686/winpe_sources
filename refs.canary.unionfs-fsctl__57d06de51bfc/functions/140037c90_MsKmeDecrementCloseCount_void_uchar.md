# MsKmeDecrementCloseCount(void *,uchar)

- ea: `0x140037c90`
- end: `0x140038f14`
- name: `?MsKmeDecrementCloseCount@@YAXPEAXE@Z`
- size: `4740`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036860`
- `0x1400a2c8c`
- `0x14013f744`
- `0x140156fd8`

## callees

- `0x140037c90`
- `0x140038f80`
- `0x140039b60`
- `0x1400c8644`
- `0x1401e9ce0`
- `0x14030ffc0`
- `0x14031ac80`
- `0x140320020`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140037d21`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003833f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140037d21`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003833f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140037dc9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140038357`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140037dc9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140038357`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037d0f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037d0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003828e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003828e`
- `ntoskrnl!KeSetEvent` at `0x1400387d3`
- `ntoskrnl!KeSetEvent` at `0x1400387d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038282`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400386e2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003891f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b44`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038282`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400386e2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003891f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b44`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140038ed2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140038ed2`
- `ntoskrnl!IoWithinStackLimits` at `0x140037d38`
- `ntoskrnl!IoWithinStackLimits` at `0x140037d38`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038628`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038788`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038865`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038a85`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038628`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038788`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038865`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140038a85`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038637`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038797`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038874`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038a94`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038637`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038797`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038874`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038a94`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038673`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400387e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400388b0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038ad4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038673`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400387e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400388b0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038ad4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003867f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400387ef`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400388bc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140038ae0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003867f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400387ef`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400388bc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140038ae0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037f9b`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003846f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037f9b`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003846f`
- `ntoskrnl!ExReleaseFastResource` at `0x140037ec1`
- `ntoskrnl!ExReleaseFastResource` at `0x140037fbe`
- `ntoskrnl!ExReleaseFastResource` at `0x140037ff4`
- `ntoskrnl!ExReleaseFastResource` at `0x140038022`
- `ntoskrnl!ExReleaseFastResource` at `0x140038492`
- `ntoskrnl!ExReleaseFastResource` at `0x1400384c8`
- `ntoskrnl!ExReleaseFastResource` at `0x1400389e3`
- `ntoskrnl!ExReleaseFastResource` at `0x140038e6d`
- `ntoskrnl!ExReleaseFastResource` at `0x140037ec1`
- `ntoskrnl!ExReleaseFastResource` at `0x140037fbe`
- `ntoskrnl!ExReleaseFastResource` at `0x140037ff4`
- `ntoskrnl!ExReleaseFastResource` at `0x140038022`
- `ntoskrnl!ExReleaseFastResource` at `0x140038492`
- `ntoskrnl!ExReleaseFastResource` at `0x1400384c8`
- `ntoskrnl!ExReleaseFastResource` at `0x1400389e3`
- `ntoskrnl!ExReleaseFastResource` at `0x140038e6d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037ecf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038b75`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038e47`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038e89`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037ecf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038b75`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038e47`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038e89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038307`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ee4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ef7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038307`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ee4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ef7`

## pseudocode

```c
void __fastcall MsKmeDecrementCloseCount(volatile signed __int32 *a1, char a2)
{
  __int16 v2; // ax
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // r14
  volatile signed __int32 *v5; // rsi
  bool v6; // r12
  bool v7; // r15
  ULONG_PTR TopLevelIrp; // rdi
  volatile signed __int32 *v9; // rdx
  char v10; // dl
  _QWORD *Pointer; // rax
  volatile signed __int32 *v12; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _ERESOURCE *v14; // rcx
  struct _LIST_ENTRY **p_Blink; // rdx
  bool v16; // zf
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rsi
  _QWORD *v20; // rdi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v22; // r8
  unsigned int i; // ecx
  __int64 v24; // rdx
  _QWORD *j; // rax
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v27; // rcx
  int v28; // ecx
  struct _LIST_ENTRY *v29; // rdx
  PKEVENT UserEvent; // rdi
  IRP *v31; // rbx
  __int16 v32; // r13
  char *v33; // rsi
  IRP *v34; // r15
  _QWORD *v35; // rax
  _QWORD *v36; // r14
  _QWORD *n; // rcx
  char *v38; // r14
  struct _KTHREAD *v39; // r9
  __int64 v40; // r8
  _QWORD *v41; // rdi
  unsigned int k; // ecx
  __int64 v43; // rdx
  _QWORD *v44; // rax
  _QWORD *v45; // rdi
  PVOID *kk; // rcx
  __int64 v47; // rcx
  unsigned int Flink; // eax
  ULONG Flags; // eax
  struct _NPAGED_LOOKASIDE_LIST *v50; // r9
  __int64 v51; // rax
  _QWORD *ii; // rcx
  PIRP v53; // rax
  IRP *MdlAddress; // rcx
  __int64 v55; // rcx
  __int64 v56; // r8
  _QWORD *mm; // rcx
  _QWORD *m; // rax
  char v59; // al
  struct _ERESOURCE *v60; // rcx
  int v61; // ecx
  __int64 v62; // rcx
  __int64 v63; // rdx
  _QWORD *v64; // rsi
  __int64 v65; // rcx
  struct _FAST_MUTEX *v66; // rbx
  __int64 v67; // rcx
  _QWORD *v68; // rdx
  unsigned int v69; // eax
  struct _FAST_MUTEX *v70; // rbx
  struct _LIST_ENTRY **v71; // rcx
  struct _LIST_ENTRY *v72; // rcx
  __int64 v73; // rcx
  _QWORD *v74; // r15
  __int64 v75; // rcx
  struct _FAST_MUTEX *v76; // rdi
  __int64 v77; // rdx
  _QWORD *v78; // rcx
  unsigned int v79; // eax
  _QWORD *jj; // rax
  struct _ERESOURCE *v81; // rcx
  struct _LIST_ENTRY **v82; // rdx
  _QWORD *nn; // rcx
  _QWORD *v84; // r12
  __int64 v85; // rcx
  struct _FAST_MUTEX *v86; // rdi
  __int64 v87; // rdx
  _QWORD *v88; // rcx
  unsigned int v89; // eax
  _QWORD *v90; // rcx
  __int64 v91; // rax
  struct _IRP_CONTEXT *p_AssociatedIrp; // [rsp+20h] [rbp-E0h] BYREF
  IRP Irp; // [rsp+28h] [rbp-D8h] BYREF
  int v94; // [rsp+12Ch] [rbp+2Ch]
  int v95; // [rsp+184h] [rbp+84h]
  __int64 v96; // [rsp+190h] [rbp+90h]
  _QWORD v97[28]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v98[2]; // [rsp+280h] [rbp+180h] BYREF
  int v99; // [rsp+290h] [rbp+190h]
  PVOID P; // [rsp+298h] [rbp+198h]
  _QWORD v101[9]; // [rsp+2C0h] [rbp+1C0h] BYREF
  PVOID v102; // [rsp+308h] [rbp+208h]
  _BYTE v103[72]; // [rsp+318h] [rbp+218h] BYREF

  v2 = *(_WORD *)a1;
  memset(&Irp, 0, 24);
  if ( v2 == 2050 )
    v3 = a1;
  else
    v3 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
  v4 = (volatile signed __int32 *)*((_QWORD *)v3 + 10);
  v5 = 0;
  if ( v2 != 2050 )
    v5 = a1;
  if ( a2 )
  {
    KeEnterCriticalRegion();
    v6 = 1;
    v7 = 0;
    TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
    if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
      v7 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
    if ( TopLevelIrp )
    {
      if ( TopLevelIrp > 0xFFFF )
      {
        if ( v7 )
        {
          v91 = *(_QWORD *)(TopLevelIrp + 16);
          if ( !v91 || (*(_DWORD *)(v91 + 4) & 0x200) == 0 )
            goto LABEL_11;
        }
        v6 = TopLevelIrp != 2147483650;
      }
      else
      {
        v6 = 0;
      }
    }
    *(_DWORD *)(&Irp.Size + 1) = 0;
    Irp.MdlAddress = (PMDL)TopLevelIrp;
    *(_QWORD *)&Irp.Flags = 0;
    LOBYTE(Irp.Type) = v6;
    if ( v7 )
    {
      HIBYTE(Irp.Type) = 1;
      LOBYTE(Irp.Size) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(CSHORT *)((char *)&Irp.Type + 1) = 0;
    }
    TopLevelIrp = (ULONG_PTR)&Irp;
LABEL_11:
    p_AssociatedIrp = (struct _IRP_CONTEXT *)&Irp.AssociatedIrp;
    if ( !(unsigned int)RefsInitializeIrpContext(0, 1u, 0, &p_AssociatedIrp) )
      *((_WORD *)p_AssociatedIrp + 1) = 800;
    if ( !*(_QWORD *)(TopLevelIrp + 16) )
    {
      *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
      *(_QWORD *)(TopLevelIrp + 16) = &Irp.AssociatedIrp;
      Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)((unsigned __int64)Irp.ThreadListEntry.Flink | 0x100000);
      IoSetTopLevelIrp((PIRP)TopLevelIrp);
    }
    Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = *(struct _LIST_ENTRY **)(TopLevelIrp + 16);
    Irp.Overlay.AllocationSize.QuadPart = (LONGLONG)v4;
    RefsAcquireSharedVcb((struct _IRP_CONTEXT *)&Irp.AssociatedIrp, (struct _VCB *)v4, 1u);
    RefsAcquireFcbWithPaging(&Irp.AssociatedIrp, v3, v5, 5);
    if ( !v5 )
    {
      if ( _InterlockedExchangeAdd(v3 + 5, 0xFFFFFFFF) == 1 && (v3[2] & 4) != 0 )
        _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v3 + 10) + 232LL));
      _InterlockedDecrement(v4 + 57);
      v9 = v3;
      _InterlockedDecrement(v4 + 55);
LABEL_18:
      v10 = RefsTeardownStructures(&Irp.AssociatedIrp, v9, 0);
LABEL_20:
      if ( v10 )
        goto LABEL_54;
      Pointer = Irp.IoStatus.Pointer;
      if ( (!Irp.IoStatus.Pointer || !*((_QWORD *)Irp.IoStatus.Pointer + 18))
        && (volatile signed __int32 *)Irp.UserEvent == v3 )
      {
        if ( *(_WORD *)v3 == 2050 )
          v12 = v3;
        else
          v12 = (volatile signed __int32 *)*((_QWORD *)v3 + 17);
        Blink = Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
        v14 = (struct _ERESOURCE *)*((_QWORD *)v12 + 12);
        if ( (struct _ERESOURCE *)Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[21].Flink == v14
          && LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[20].Flink)
          && (p_Blink = &Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[15].Blink,
              Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink != (struct _LIST_ENTRY *)-248LL) )
        {
          v16 = LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[20].Flink)-- == 1;
          if ( v16 )
          {
            HIDWORD(Blink[20].Flink) &= ~2u;
            ExReleaseFastResource(v14, p_Blink);
          }
        }
        else
        {
          ExReleaseResourceLite(v14);
        }
        Pointer = Irp.IoStatus.Pointer;
        Irp.UserEvent = 0;
      }
      if ( !*((_QWORD *)v3 + 8) )
      {
LABEL_39:
        if ( *(_WORD *)v3 != 2050 )
          v3 = (volatile signed __int32 *)*((_QWORD *)v3 + 17);
        v20 = 0;
        CurrentThread = KeGetCurrentThread();
        v22 = *((_QWORD *)v3 + 11) + 64LL;
        for ( i = 0; i < 2; ++i )
        {
          v24 = 14LL * i;
          if ( v97[v24] == v22 && (struct _KTHREAD *)v97[14 * i + 1] == CurrentThread )
          {
            v20 = &v97[v24];
            if ( &v97[v24] )
              goto LABEL_47;
            break;
          }
        }
        for ( j = (_QWORD *)v98[0]; j != v98; j = (_QWORD *)*j )
        {
          if ( *(j - 12) == v22 && (struct _KTHREAD *)*(j - 11) == CurrentThread )
          {
            v20 = j - 12;
            break;
          }
        }
LABEL_47:
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v22);
        if ( !v20 )
        {
          v27 = (struct _ERESOURCE *)(*((_QWORD *)v3 + 11) + 64LL);
          if ( IsFastResourceHeldExclusive )
            ExReleaseFastResource(v27, 0);
          else
            ExReleaseResourceLite(v27);
          goto LABEL_54;
        }
        v28 = *((_DWORD *)v20 + 4);
        if ( IsFastResourceHeldExclusive )
        {
          if ( !v28 )
            goto LABEL_53;
          *((_DWORD *)v20 + 4) = v28 - 1;
          if ( v28 != 1 )
            goto LABEL_53;
        }
        else
        {
          *((_DWORD *)v20 + 4) = v28 - 1;
          if ( v28 != 1 )
          {
LABEL_53:
            ExReleaseFastResource(*((_QWORD *)v3 + 11) + 64LL, v20 + 3);
            goto LABEL_54;
          }
        }
        *v20 = 0;
        v20[1] = 0;
        goto LABEL_53;
      }
      if ( *((_WORD *)v3 + 14) != 1 )
        goto LABEL_38;
      if ( Pointer && Pointer[18] && ((v3[2] & 0x8000LL) == 0 || (WORD2(Irp.AssociatedIrp.SystemBuffer) & 0x1000) != 0) )
      {
LABEL_54:
        v29 = Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink + 10;
        if ( Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink == (struct _LIST_ENTRY *)-160LL )
        {
          v29 = 0;
        }
        else
        {
          v16 = LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[14].Blink)-- == 1;
          if ( !v16 )
            goto LABEL_58;
          HIDWORD(v29[4].Blink) &= ~2u;
        }
        ExReleaseFastResource(v4 + 328, v29);
LABEL_58:
        if ( Irp.UserIosb )
          RefsReleaseSharedResources((struct _IRP_CONTEXT *)&Irp.AssociatedIrp);
        UserEvent = Irp.UserEvent;
        if ( !Irp.UserEvent )
          goto LABEL_61;
        if ( Irp.UserEvent->Header.Lock == 2050 )
        {
          v81 = *(struct _ERESOURCE **)&Irp.UserEvent[4].Header.Lock;
          if ( (struct _ERESOURCE *)Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[21].Flink != v81
            || !LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[20].Flink)
            || (v82 = &Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[15].Blink,
                Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink == (struct _LIST_ENTRY *)-248LL) )
          {
            ExReleaseResourceLite(v81);
            Irp.UserEvent = 0;
            goto LABEL_61;
          }
          v16 = LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[20].Flink)-- == 1;
          if ( v16 )
          {
            *((_DWORD *)v82 + 19) &= ~2u;
            ExReleaseFastResource(v81, v82);
            Irp.UserEvent = 0;
            goto LABEL_61;
          }
        }
        else
        {
          Irp.UserEvent = 0;
          v70 = *(struct _FAST_MUTEX **)&UserEvent[2].Header.Lock;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v70);
          v71 = &UserEvent[18].Header.WaitListHead.Blink;
          if ( *v71 == (struct _LIST_ENTRY *)v71 )
          {
            UserEvent[18].Header.WaitListHead.Flink = 0;
          }
          else
          {
            v72 = *v71;
            UserEvent[18].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)((unsigned __int64)UserEvent[18].Header.WaitListHead.Flink
                                                                           | 3);
            ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v72);
            *(_QWORD *)(v73 + 8) = 0;
            *(_QWORD *)v73 = 0;
            KeSetEvent((PRKEVENT)(v73 + 16), 0, 0);
          }
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)&UserEvent[2].Header.Lock);
          KeLeaveGuardedRegion();
        }
        Irp.UserEvent = 0;
LABEL_61:
        if ( (WORD2(Irp.AssociatedIrp.SystemBuffer) & 0x2000) != 0 )
        {
          HIDWORD(Irp.AssociatedIrp.SystemBuffer) &= 0xFFFFCFFF;
          ExReleaseFastResource(Irp.Overlay.AllocationSize.QuadPart + 1208, 0);
        }
        v31 = (IRP *)Irp.Tail.Overlay.DriverContext[2];
LABEL_64:
        if ( v31 != (IRP *)(&Irp.Tail.CompletionKey + 2) )
        {
          v32 = *((_WORD *)&v31[-1].Tail.CompletionKey + 26);
          v33 = (char *)(&v31[-1].Tail.CompletionKey + 3);
          v34 = v31;
          v31 = *(IRP **)&v31->Type;
          while ( !*(_QWORD *)&v34->Type )
          {
LABEL_76:
            if ( *(_WORD *)v33 == 2050 )
              v38 = v33;
            else
              v38 = (char *)*((_QWORD *)v33 + 17);
            v39 = KeGetCurrentThread();
            v40 = *((_QWORD *)v38 + 11) + 64LL;
            v41 = 0;
            for ( k = 0; k < 2; ++k )
            {
              v43 = 14LL * k;
              if ( v97[v43] == v40 && (struct _KTHREAD *)v97[14 * k + 1] == v39 )
              {
                v41 = &v97[v43];
                if ( &v97[v43] )
                  goto LABEL_127;
                break;
              }
            }
            for ( m = (_QWORD *)v98[0]; m != v98; m = (_QWORD *)*m )
            {
              if ( *(m - 12) == v40 && (struct _KTHREAD *)*(m - 11) == v39 )
              {
                v41 = m - 12;
                break;
              }
            }
LABEL_127:
            v59 = ExIsFastResourceHeldExclusive(*((_QWORD *)v38 + 11) + 64LL);
            if ( !v41 )
            {
              v60 = (struct _ERESOURCE *)(*((_QWORD *)v38 + 11) + 64LL);
              if ( v59 )
                ExReleaseFastResource(v60, 0);
              else
                ExReleaseResourceLite(v60);
              goto LABEL_134;
            }
            v61 = *((_DWORD *)v41 + 4);
            if ( v59 )
            {
              if ( !v61 )
                goto LABEL_133;
              *((_DWORD *)v41 + 4) = v61 - 1;
              if ( v61 != 1 )
                goto LABEL_133;
LABEL_132:
              *v41 = 0;
              v41[1] = 0;
              goto LABEL_133;
            }
            *((_DWORD *)v41 + 4) = v61 - 1;
            if ( v61 == 1 )
              goto LABEL_132;
LABEL_133:
            ExReleaseFastResource(*((_QWORD *)v38 + 11) + 64LL, v41 + 3);
LABEL_134:
            if ( !--v32 )
              goto LABEL_64;
          }
          if ( *((_WORD *)v33 + 14) != 1 )
            goto LABEL_75;
          if ( Irp.IoStatus.Pointer
            && *((_QWORD *)Irp.IoStatus.Pointer + 18)
            && ((*((_DWORD *)v33 + 2) & 0x8000LL) == 0 || (WORD2(Irp.AssociatedIrp.SystemBuffer) & 0x1000) != 0) )
          {
            goto LABEL_134;
          }
          ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v34);
          v34->MdlAddress = 0;
          *(_QWORD *)&v34->Type = 0;
          v35 = (_QWORD *)v101[0];
          if ( (_QWORD *)v101[0] == v101 )
            goto LABEL_75;
          v36 = 0;
          for ( n = (_QWORD *)v101[0]; n != v101; n = (_QWORD *)*n )
          {
            if ( *((_WORD *)n - 4) == 2087 )
            {
              v36 = n - 1;
              break;
            }
          }
          if ( !v36 )
          {
LABEL_75:
            --*((_WORD *)v33 + 14);
            goto LABEL_76;
          }
          while ( 1 )
          {
            v84 = 0;
            if ( v35 != v101 )
            {
              if ( v36 )
                v90 = (_QWORD *)v36[1];
              else
                v90 = v35;
              while ( v90 != v101 )
              {
                if ( *((_WORD *)v90 - 4) == 2087 )
                {
                  v84 = v90 - 1;
                  break;
                }
                v90 = (_QWORD *)*v90;
              }
            }
            v85 = v36[6];
            if ( v85 )
            {
              if ( *(char **)(v85 + 136) != v33 )
                goto LABEL_223;
              if ( ((*(_DWORD *)(v85 + 152) & 0x2000) != 0 || (*(_DWORD *)(v85 + 300) & 0x40) != 0)
                && (*(_DWORD *)(v85 + 152) & 0x2000) != 0 )
              {
                _InterlockedAnd((volatile signed __int32 *)(v85 + 152), 0xFFFFDFFF);
              }
              v86 = *(struct _FAST_MUTEX **)(v36[6] + 48LL);
              KeEnterGuardedRegion();
              ExAcquireFastMutexUnsafe(v86);
              _InterlockedIncrement((volatile signed __int32 *)(v36[6] + 172LL));
              *(_QWORD *)(v36[6] + 280LL) = 0;
              ++*(_DWORD *)(v36[6] + 172LL);
              ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v36[6] + 48LL));
              KeLeaveGuardedRegion();
            }
            v87 = v36[1];
            if ( *(_QWORD **)(v87 + 8) != v36 + 1 )
              goto LABEL_236;
            v88 = (_QWORD *)v36[2];
            if ( (_QWORD *)*v88 != v36 + 1 )
              goto LABEL_236;
            *v88 = v87;
            *(_QWORD *)(v87 + 8) = v88;
            if ( v36 != (_QWORD *)v103 )
            {
              v89 = *((_DWORD *)v36 - 2);
              if ( v89 >= RefsNumberProcessors )
                v89 %= RefsNumberProcessors;
              ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v89], v36 - 1);
            }
            v35 = (_QWORD *)v101[0];
LABEL_223:
            v36 = v84;
            if ( !v84 )
              goto LABEL_75;
          }
        }
        v44 = (_QWORD *)v101[0];
        if ( (_QWORD *)v101[0] != v101 )
        {
          v45 = 0;
          for ( ii = (_QWORD *)v101[0]; ii != v101; ii = (_QWORD *)*ii )
          {
            if ( *((_WORD *)ii - 4) == 2087 )
            {
              v45 = ii - 1;
              break;
            }
          }
          if ( v45 )
          {
            while ( 1 )
            {
              v64 = 0;
              if ( v44 != v101 )
              {
                for ( jj = (_QWORD *)v45[1]; jj != v101; jj = (_QWORD *)*jj )
                {
                  if ( *((_WORD *)jj - 4) == 2087 )
                  {
                    v64 = jj - 1;
                    break;
                  }
                }
              }
              v65 = v45[6];
              if ( v65 )
              {
                if ( ((*(_DWORD *)(v65 + 152) & 0x2000) != 0 || (*(_DWORD *)(v65 + 300) & 0x40) != 0)
                  && (*(_DWORD *)(v65 + 152) & 0x2000) != 0 )
                {
                  _InterlockedAnd((volatile signed __int32 *)(v65 + 152), 0xFFFFDFFF);
                }
                v66 = *(struct _FAST_MUTEX **)(v45[6] + 48LL);
                KeEnterGuardedRegion();
                ExAcquireFastMutexUnsafe(v66);
                _InterlockedIncrement((volatile signed __int32 *)(v45[6] + 172LL));
                *(_QWORD *)(v45[6] + 280LL) = 0;
                ++*(_DWORD *)(v45[6] + 172LL);
                ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v45[6] + 48LL));
                KeLeaveGuardedRegion();
              }
              v67 = v45[1];
              if ( *(_QWORD **)(v67 + 8) != v45 + 1 )
                break;
              v68 = (_QWORD *)v45[2];
              if ( (_QWORD *)*v68 != v45 + 1 )
                break;
              *v68 = v67;
              *(_QWORD *)(v67 + 8) = v68;
              if ( v45 != (_QWORD *)v103 )
              {
                v69 = *((_DWORD *)v45 - 2);
                if ( v69 >= RefsNumberProcessors )
                  v69 %= RefsNumberProcessors;
                ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v69], v45 - 1);
              }
              if ( !v64 )
                goto LABEL_85;
              v44 = (_QWORD *)v101[0];
              v45 = v64;
            }
LABEL_236:
            __fastfail(3u);
          }
        }
LABEL_85:
        for ( kk = (PVOID *)P; P; kk = (PVOID *)P )
        {
          P = *kk;
          ExFreePoolWithTag(kk, 0);
        }
        if ( (WORD2(Irp.AssociatedIrp.SystemBuffer) & 0x400) != 0 || ((__int64)Irp.ThreadListEntry.Flink & 0x10000) != 0 )
        {
          if ( (HIDWORD(Irp.AssociatedIrp.SystemBuffer) & 0x40000) != 0 )
          {
            HIDWORD(Irp.AssociatedIrp.SystemBuffer) &= 0xFFFBFBFF;
          }
          else
          {
            HIDWORD(Irp.AssociatedIrp.SystemBuffer) &= 0xF779C0CD;
            Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)((unsigned __int64)Irp.ThreadListEntry.Flink & ~0x400uLL);
          }
          LODWORD(Irp.ThreadListEntry.Blink) = 0;
          goto LABEL_103;
        }
        if ( ((__int64)Irp.ThreadListEntry.Flink & 0x20000000000LL) != 0 )
        {
          v94 &= ~1u;
          Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)((unsigned __int64)Irp.ThreadListEntry.Flink
                                                           & ~0x20000000000uLL);
        }
        if ( v96 )
        {
          v95 &= ~1u;
          v96 = 0;
        }
        while ( 1 )
        {
          v47 = v98[0];
          if ( (_QWORD *)v98[0] == v98 )
            break;
          if ( *(_QWORD **)(v98[0] + 8LL) != v98 )
            goto LABEL_236;
          v51 = *(_QWORD *)v98[0];
          if ( *(_QWORD *)(*(_QWORD *)v98[0] + 8LL) != v98[0] )
            goto LABEL_236;
          v98[0] = *(_QWORD *)v98[0];
          *(_QWORD *)(v51 + 8) = v98;
          ExFreePoolWithTag((PVOID)(v47 - 96), 0);
        }
        v97[0] = 0;
        v97[14] = 0;
        v99 = 0;
        if ( ((__int64)Irp.ThreadListEntry.Flink & 0x20) != 0 )
        {
          SeReleaseSubjectContext((PSECURITY_SUBJECT_CONTEXT)Irp.Tail.Overlay.ListEntry.Flink);
          ExFreePoolWithTag(Irp.Tail.Overlay.ListEntry.Flink, 0);
        }
        Flink = (unsigned int)Irp.ThreadListEntry.Flink;
        Irp.Tail.Overlay.ListEntry.Flink = 0;
        if ( ((__int64)Irp.ThreadListEntry.Flink & 0x100000) != 0 )
        {
          v53 = IoGetTopLevelIrp();
          MdlAddress = (IRP *)v53->MdlAddress;
          *(_DWORD *)(&v53->Size + 1) = 0;
          *(_QWORD *)&v53->Flags = 0;
          IoSetTopLevelIrp(MdlAddress);
          Flink = (__int64)Irp.ThreadListEntry.Flink & 0xFFEFFFFF;
          Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)((unsigned __int64)Irp.ThreadListEntry.Flink & ~0x100000uLL);
        }
        if ( v102 )
        {
          ExFreePoolWithTag(v102, 0);
          Flink = (unsigned int)Irp.ThreadListEntry.Flink;
          v102 = 0;
        }
        if ( (*(_QWORD *)&Flink & 0x80000LL) == 0 )
          goto LABEL_103;
        Flags = Irp.Flags;
        if ( HIWORD(Irp.AssociatedIrp.IrpCount) == 1664 )
        {
          v50 = RefsIrpAndIoContextLookasideList;
          if ( Irp.Flags < RefsNumberProcessors )
            goto LABEL_102;
        }
        else
        {
          v50 = RefsIrpContextLookasideList;
          if ( Irp.Flags < RefsNumberProcessors )
          {
LABEL_102:
            ExFreeToNPagedLookasideList(&v50[(unsigned __int64)Flags], &Irp.Flags);
LABEL_103:
            KeLeaveCriticalRegion();
            return;
          }
        }
        Flags = Irp.Flags % RefsNumberProcessors;
        goto LABEL_102;
      }
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v3 + 16);
      v17[1] = 0;
      *v17 = 0;
      v18 = (_QWORD *)v101[0];
      if ( (_QWORD *)v101[0] == v101 )
        goto LABEL_38;
      v19 = 0;
      for ( mm = (_QWORD *)v101[0]; mm != v101; mm = (_QWORD *)*mm )
      {
        if ( *((_WORD *)mm - 4) == 2087 )
        {
          v19 = mm - 1;
          break;
        }
      }
      if ( !v19 )
      {
LABEL_38:
        --*((_WORD *)v3 + 14);
        goto LABEL_39;
      }
      while ( 1 )
      {
        v74 = 0;
        if ( v18 != v101 )
        {
          for ( nn = (_QWORD *)v19[1]; nn != v101; nn = (_QWORD *)*nn )
          {
            if ( *((_WORD *)nn - 4) == 2087 )
            {
              v74 = nn - 1;
              break;
            }
          }
        }
        v75 = v19[6];
        if ( v75 )
        {
          if ( *(volatile signed __int32 **)(v75 + 136) != v3 )
            goto LABEL_190;
          if ( ((*(_DWORD *)(v75 + 152) & 0x2000) != 0 || (*(_DWORD *)(v75 + 300) & 0x40) != 0)
            && (*(_DWORD *)(v75 + 152) & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)(v75 + 152), 0xFFFFDFFF);
          }
          v76 = *(struct _FAST_MUTEX **)(v19[6] + 48LL);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v76);
          _InterlockedIncrement((volatile signed __int32 *)(v19[6] + 172LL));
          *(_QWORD *)(v19[6] + 280LL) = 0;
          ++*(_DWORD *)(v19[6] + 172LL);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v19[6] + 48LL));
          KeLeaveGuardedRegion();
        }
        v77 = v19[1];
        if ( *(_QWORD **)(v77 + 8) != v19 + 1 )
          goto LABEL_236;
        v78 = (_QWORD *)v19[2];
        if ( (_QWORD *)*v78 != v19 + 1 )
          goto LABEL_236;
        *v78 = v77;
        *(_QWORD *)(v77 + 8) = v78;
        if ( v19 != (_QWORD *)v103 )
        {
          v79 = *((_DWORD *)v19 - 2);
          if ( v79 >= RefsNumberProcessors )
            v79 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v79], v19 - 1);
        }
        v18 = (_QWORD *)v101[0];
LABEL_190:
        if ( !v74 )
          goto LABEL_38;
        v19 = v74;
      }
    }
    v55 = *((_QWORD *)v5 + 18);
    v10 = 0;
    v56 = *((_QWORD *)v5 + 17);
    _InterlockedDecrement(v5 + 41);
    _InterlockedDecrement((volatile signed __int32 *)(v55 + 220));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v56 + 20), 0xFFFFFFFF) == 1
      && (*(_BYTE *)(v56 + 8) & 4) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v56 + 80) + 232LL));
    }
    _InterlockedDecrement((volatile signed __int32 *)(v55 + 228));
    if ( *(_WORD *)v5 == 2053 )
    {
      if ( *((_DWORD *)v5 + 41)
        && (*((_DWORD *)v5 + 40)
         || (*(_DWORD *)(v56 + 8) & 0x100LL) != 0
         || !*((_QWORD *)v5 + 30) && !*((_QWORD *)v5 + 54)) )
      {
        goto LABEL_20;
      }
    }
    else if ( *((_DWORD *)v5 + 41) )
    {
      if ( *((_DWORD *)v5 + 40) )
        goto LABEL_20;
      if ( !*((_QWORD *)v5 + 30)
        || (*(_DWORD *)(v56 + 8) & 0x100LL) != 0
        || *((volatile signed __int32 **)v5 + 47) != v5 + 94 )
      {
        if ( *((_DWORD *)v5 + 40) || !*((_QWORD *)v5 + 52) || *((volatile signed __int32 **)v5 + 47) != v5 + 94 )
          goto LABEL_20;
        v9 = v5;
        goto LABEL_18;
      }
    }
    v10 = RefsTeardownStructures(&Irp.AssociatedIrp, v5, 0);
    goto LABEL_20;
  }
  if ( v5 )
  {
    v62 = *((_QWORD *)v5 + 18);
    v63 = *((_QWORD *)v5 + 17);
    _InterlockedDecrement(v5 + 41);
    _InterlockedDecrement((volatile signed __int32 *)(v62 + 220));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v63 + 20), 0xFFFFFFFF) == 1
      && (*(_BYTE *)(v63 + 8) & 4) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v63 + 80) + 232LL));
    }
    _InterlockedDecrement((volatile signed __int32 *)(v62 + 228));
  }
  else
  {
    if ( _InterlockedExchangeAdd(v3 + 5, 0xFFFFFFFF) == 1 && (v3[2] & 4) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v3 + 10) + 232LL));
    _InterlockedDecrement(v4 + 57);
    _InterlockedDecrement(v4 + 55);
  }
}

```

## disassembly

```asm
0x140037c90  push    rbp
0x140037c92  push    rbx
0x140037c93  push    rsi
0x140037c94  push    r13
0x140037c96  push    r14
0x140037c98  lea     rbp, [rsp-270h]
0x140037ca0  sub     rsp, 370h
0x140037ca7  mov     rax, cs:__security_cookie
0x140037cae  xor     rax, rsp
0x140037cb1  mov     [rbp+290h+var_30], rax
0x140037cb8  xor     eax, eax
0x140037cba  mov     r8d, 802h
0x140037cc0  mov     qword ptr [rsp+390h+Irp.Flags], rax
0x140037cc5  xorps   xmm0, xmm0
0x140037cc8  movzx   eax, word ptr [rcx]
0x140037ccb  movups  xmmword ptr [rsp+390h+Irp.Type], xmm0
0x140037cd0  cmp     ax, r8w
0x140037cd4  jnz     loc_1400383FF
0x140037cda  mov     rbx, rcx
0x140037cdd  mov     r14, [rbx+50h]
0x140037ce1  xor     r13d, r13d
0x140037ce4  cmp     ax, r8w
0x140037ce8  mov     esi, r13d
0x140037ceb  cmovnz  rsi, rcx
0x140037cef  test    dl, dl
0x140037cf1  jz      loc_1400384F4
0x140037cf7  mov     [rsp+390h+arg_8], rdi
0x140037cff  mov     [rsp+390h+arg_10], r12
0x140037d07  mov     [rsp+390h+arg_18], r15
0x140037d0f  call    cs:__imp_KeEnterCriticalRegion
0x140037d16  nop     dword ptr [rax+rax+00h]
0x140037d1b  mov     r12b, 1
0x140037d1e  xor     r15b, r15b
0x140037d21  call    cs:__imp_IoGetTopLevelIrp
0x140037d28  nop     dword ptr [rax+rax+00h]
0x140037d2d  mov     rcx, rax; RegionStart
0x140037d30  mov     edx, 18h; RegionSize
0x140037d35  mov     rdi, rax
0x140037d38  call    cs:__imp_IoWithinStackLimits
0x140037d3f  nop     dword ptr [rax+rax+00h]
0x140037d44  test    eax, eax
0x140037d46  jnz     loc_140038C3D
0x140037d4c  test    rdi, rdi
0x140037d4f  jnz     loc_140038B8B
0x140037d55  mov     dword ptr [rsp+390h+Irp+4], r13d
0x140037d5a  mov     [rsp+390h+Irp.MdlAddress], rdi
0x140037d5f  mov     qword ptr [rsp+390h+Irp.Flags], r13
0x140037d64  mov     byte ptr [rsp+390h+Irp.Type], r12b
0x140037d69  test    r15b, r15b
0x140037d6c  jnz     loc_140038DBE
0x140037d72  mov     [rsp+390h+Irp.Type+1], r13w
0x140037d78  lea     rdi, [rsp+390h+Irp]
0x140037d7d  lea     rax, [rsp+390h+Irp.AssociatedIrp]
0x140037d82  xor     r8d, r8d; unsigned __int8
0x140037d85  lea     r9, [rsp+390h+var_370]; struct _IRP_CONTEXT **
0x140037d8a  mov     [rsp+390h+var_370], rax
0x140037d8f  mov     dl, 1; unsigned __int8
0x140037d91  xor     ecx, ecx; Irp
0x140037d93  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140037d98  test    eax, eax
0x140037d9a  jnz     short loc_140037DA7
0x140037d9c  mov     rax, [rsp+390h+var_370]
0x140037da1  mov     word ptr [rax+2], 320h
0x140037da7  cmp     [rdi+10h], r13
0x140037dab  jnz     short loc_140037DD5
0x140037dad  lea     rax, [rsp+390h+Irp.AssociatedIrp]
0x140037db2  mov     dword ptr [rdi+4], 5346ABBAh
0x140037db9  mov     [rdi+10h], rax
0x140037dbd  mov     rcx, rdi; Irp
0x140037dc0  or      [rsp+390h+Irp.ThreadListEntry.Flink], 100000h
0x140037dc9  call    cs:__imp_IoSetTopLevelIrp
0x140037dd0  nop     dword ptr [rax+rax+00h]
0x140037dd5  mov     rax, [rdi+10h]
0x140037dd9  lea     rcx, [rsp+390h+Irp.AssociatedIrp]; struct _IRP_CONTEXT *
0x140037dde  mov     r8b, 1; unsigned __int8
0x140037de1  mov     qword ptr [rbp+290h+Irp.Tail+8], rax
0x140037de5  mov     rdx, r14; struct _VCB *
0x140037de8  mov     qword ptr [rbp+290h+Irp.Overlay], r14
0x140037dec  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140037df1  mov     r9d, 5
0x140037df7  lea     rcx, [rsp+390h+Irp.AssociatedIrp]
0x140037dfc  mov     r8, rsi
0x140037dff  mov     rdx, rbx
0x140037e02  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140037e07  mov     eax, 0FFFFFFFFh
0x140037e0c  test    rsi, rsi
0x140037e0f  jnz     loc_140038377
0x140037e15  lock xadd [rbx+14h], eax
0x140037e1a  cmp     eax, 1
0x140037e1d  jz      loc_140038BDB
0x140037e23  lock dec dword ptr [r14+0E4h]
0x140037e2b  mov     rdx, rbx
0x140037e2e  lock dec dword ptr [r14+0DCh]
0x140037e36  xor     r8d, r8d
0x140037e39  lea     rcx, [rsp+390h+Irp.AssociatedIrp]
0x140037e3e  call    ?RefsTeardownStructures@@YA_NPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_LCB@@@Z; RefsTeardownStructures(_IRP_CONTEXT *,PFCBOrSCB,_LCB *)
0x140037e43  movzx   edx, al
0x140037e46  jmp     short loc_140037E5B
0x140037e48  lea     rcx, [rsi+178h]
0x140037e4f  mov     rax, [rcx]
0x140037e52  cmp     rax, rcx
0x140037e55  jz      loc_140038E34
0x140037e5b  mov     r15d, 827h
0x140037e61  test    dl, dl
0x140037e63  jnz     loc_140038000
0x140037e69  mov     rax, qword ptr [rsp+390h+Irp.IoStatus]
0x140037e6e  test    rax, rax
0x140037e71  jnz     loc_140038759
0x140037e77  mov     r12d, 802h
0x140037e7d  cmp     [rsp+390h+Irp.UserEvent], rbx
0x140037e82  jnz     short loc_140037EE5
0x140037e84  cmp     [rbx], r12w
0x140037e88  jnz     loc_140038562
0x140037e8e  mov     rcx, rbx
0x140037e91  mov     rax, qword ptr [rbp+290h+Irp.Tail+8]
0x140037e95  mov     rcx, [rcx+60h]; Resource
0x140037e99  cmp     [rax+150h], rcx
0x140037ea0  jnz     short loc_140037ECF
0x140037ea2  cmp     [rax+140h], r13d
0x140037ea9  jz      short loc_140037ECF
0x140037eab  lea     rdx, [rax+0F8h]
0x140037eb2  test    rdx, rdx
0x140037eb5  jz      short loc_140037ECF
0x140037eb7  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x140037ebb  jnz     short loc_140037EDB
0x140037ebd  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x140037ec1  call    cs:__imp_ExReleaseFastResource
0x140037ec8  nop     dword ptr [rax+rax+00h]
0x140037ecd  jmp     short loc_140037EDB
0x140037ecf  call    cs:__imp_ExReleaseResourceLite
0x140037ed6  nop     dword ptr [rax+rax+00h]
0x140037edb  mov     rax, qword ptr [rsp+390h+Irp.IoStatus]
0x140037ee0  mov     [rsp+390h+Irp.UserEvent], r13
0x140037ee5  cmp     [rbx+40h], r13
0x140037ee9  lea     rcx, [rbx+40h]
0x140037eed  jz      short loc_140037F43
0x140037eef  cmp     word ptr [rbx+1Ch], 1
0x140037ef4  jnz     short loc_140037F3A
0x140037ef6  test    rax, rax
0x140037ef9  jnz     loc_140038978
0x140037eff  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140037f04  mov     [rcx+8], r13
0x140037f08  mov     [rcx], r13
0x140037f0b  lea     rcx, [rbp+290h+var_D0]
0x140037f12  mov     rax, [rbp+290h+var_D0]
0x140037f19  cmp     rax, rcx
0x140037f1c  jz      short loc_140037F3A
0x140037f1e  lea     rcx, [rbp+290h+var_D0]
0x140037f25  mov     rsi, r13
0x140037f28  cmp     rax, rcx
0x140037f2b  jnz     loc_14003842E
0x140037f31  test    rsi, rsi
0x140037f34  jnz     loc_140038810
0x140037f3a  mov     eax, 0FFFFh
0x140037f3f  add     [rbx+1Ch], ax
0x140037f43  cmp     [rbx], r12w
0x140037f47  jnz     loc_1400384E8
0x140037f4d  mov     r8, [rbx+58h]
0x140037f51  mov     rdi, r13
0x140037f54  mov     r9, gs:188h
0x140037f5d  add     r8, 40h ; '@'
0x140037f61  mov     ecx, r13d
0x140037f64  cmp     ecx, 2
0x140037f67  jnb     short loc_140037F81
0x140037f69  mov     eax, ecx
0x140037f6b  imul    rdx, rax, 70h ; 'p'
0x140037f6f  cmp     [rbp+rdx+290h+var_1F0], r8
0x140037f77  jz      loc_14003840B
0x140037f7d  inc     ecx
0x140037f7f  jmp     short loc_140037F64
0x140037f81  mov     rax, [rbp+290h+var_110]
0x140037f88  lea     rcx, [rbp+290h+var_110]
0x140037f8f  cmp     rax, rcx
0x140037f92  jnz     loc_140038CB7
0x140037f98  mov     rcx, r8
0x140037f9b  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140037fa2  nop     dword ptr [rax+rax+00h]
0x140037fa7  test    rdi, rdi
0x140037faa  jnz     short loc_140037FCC
0x140037fac  mov     rcx, [rbx+58h]
0x140037fb0  add     rcx, 40h ; '@'; Resource
0x140037fb4  test    al, al
0x140037fb6  jz      loc_140038E47
0x140037fbc  xor     edx, edx
0x140037fbe  call    cs:__imp_ExReleaseFastResource
0x140037fc5  nop     dword ptr [rax+rax+00h]
0x140037fca  jmp     short loc_140038000
0x140037fcc  mov     ecx, [rdi+10h]
0x140037fcf  test    al, al
0x140037fd1  jnz     loc_140038C94
0x140037fd7  lea     eax, [rcx-1]
0x140037fda  mov     [rdi+10h], eax
0x140037fdd  test    eax, eax
0x140037fdf  jnz     short loc_140037FE8
0x140037fe1  mov     [rdi], r13
0x140037fe4  mov     [rdi+8], r13
0x140037fe8  mov     rcx, [rbx+58h]
0x140037fec  lea     rdx, [rdi+18h]
0x140037ff0  add     rcx, 40h ; '@'
0x140037ff4  call    cs:__imp_ExReleaseFastResource
0x140037ffb  nop     dword ptr [rax+rax+00h]
0x140038000  mov     rdx, qword ptr [rbp+290h+Irp.Tail+8]
0x140038004  lea     rcx, [r14+520h]
0x14003800b  add     rdx, 0A0h
0x140038012  jz      loc_140038B6E
0x140038018  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x14003801c  jnz     short loc_14003802E
0x14003801e  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x140038022  call    cs:__imp_ExReleaseFastResource
0x140038029  nop     dword ptr [rax+rax+00h]
0x14003802e  cmp     [rsp+390h+Irp.UserIosb], r13
0x140038033  jz      short loc_14003803F
0x140038035  lea     rcx, [rsp+390h+Irp.AssociatedIrp]; struct _IRP_CONTEXT *
0x14003803a  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x14003803f  mov     rdi, [rsp+390h+Irp.UserEvent]
0x140038044  test    rdi, rdi
0x140038047  jnz     loc_140038771
0x14003804d  test    dword ptr [rsp+390h+Irp.AssociatedIrp+4], 2000h
0x140038055  jnz     loc_140038E58
0x14003805b  mov     rbx, qword ptr [rbp+290h+Irp.Tail+10h]
0x14003805f  lea     rax, [rbp+290h+Irp.Tail+10h]
0x140038063  cmp     rbx, rax
0x140038066  jz      loc_14003814A
0x14003806c  movzx   r13d, word ptr [rbx-24h]
0x140038071  lea     rsi, [rbx-40h]
0x140038075  mov     r15, rbx
0x140038078  mov     eax, 0FFFFh
0x14003807d  mov     rbx, [rbx]
0x140038080  cmp     qword ptr [r15], 0
0x140038084  jz      short loc_1400380FE
0x140038086  cmp     word ptr [rsi+1Ch], 1
0x14003808b  jnz     short loc_1400380FA
0x14003808d  mov     rax, qword ptr [rsp+390h+Irp.IoStatus]
0x140038092  test    rax, rax
0x140038095  jnz     loc_140038BAC
0x14003809b  mov     rcx, r15
0x14003809e  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x1400380a3  mov     qword ptr [r15+8], 0
0x1400380ab  lea     rcx, [rbp+290h+var_D0]
0x1400380b2  mov     qword ptr [r15], 0
0x1400380b9  mov     rax, [rbp+290h+var_D0]
0x1400380c0  cmp     rax, rcx
0x1400380c3  jz      short loc_1400380F5
0x1400380c5  xor     r14d, r14d
0x1400380c8  mov     rcx, rax
0x1400380cb  mov     r8d, 827h
0x1400380d1  lea     rdx, [rbp+290h+var_D0]
0x1400380d8  cmp     rcx, rdx
0x1400380db  jz      short loc_1400380EC
0x1400380dd  cmp     [rcx-8], r8w
0x1400380e2  jnz     loc_140038CAF
0x1400380e8  lea     r14, [rcx-8]
0x1400380ec  test    r14, r14
0x1400380ef  jnz     loc_140038A30
0x1400380f5  mov     eax, 0FFFFh
0x1400380fa  add     [rsi+1Ch], ax
0x1400380fe  mov     eax, 802h
0x140038103  cmp     [rsi], ax
0x140038106  jnz     loc_1400385CE
0x14003810c  mov     r14, rsi
0x14003810f  mov     r8, [r14+58h]
0x140038113  mov     r9, gs:188h
0x14003811c  add     r8, 40h ; '@'
0x140038120  xor     r12d, r12d
0x140038123  mov     edi, r12d
0x140038126  mov     ecx, r12d
0x140038129  cmp     ecx, 2
0x14003812c  jnb     loc_140038455
0x140038132  mov     eax, ecx
0x140038134  imul    rdx, rax, 70h ; 'p'
0x140038138  cmp     [rbp+rdx+290h+var_1F0], r8
0x140038140  jz      loc_14003856E
0x140038146  inc     ecx
0x140038148  jmp     short loc_140038129
0x14003814a  mov     rax, [rbp+290h+var_D0]
0x140038151  lea     rcx, [rbp+290h+var_D0]
0x140038158  xor     r13d, r13d
0x14003815b  cmp     rax, rcx
0x14003815e  jz      short loc_140038182
0x140038160  lea     rcx, [rbp+290h+var_D0]
0x140038167  mov     edi, r13d
0x14003816a  mov     r15d, 827h
0x140038170  cmp     rax, rcx
0x140038173  jnz     loc_140038318
0x140038179  test    rdi, rdi
0x14003817c  jnz     loc_1400385E0
0x140038182  mov     rcx, [rbp+290h+P]; P
0x140038189  test    rcx, rcx
0x14003818c  jnz     loc_140038EA5
0x140038192  test    dword ptr [rsp+390h+Irp.AssociatedIrp+4], 400h
0x14003819a  mov     rax, [rsp+390h+Irp.ThreadListEntry.Flink]
0x14003819f  jnz     loc_140038538
0x1400381a5  bt      rax, 10h
0x1400381aa  jb      loc_140038538
0x1400381b0  bt      rax, 29h ; ')'
0x1400381b5  jnb     short loc_1400381CD
0x1400381b7  and     [rbp+290h+var_264], 0FFFFFFFEh
0x1400381bb  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x1400381c5  and     rax, rcx
0x1400381c8  mov     [rsp+390h+Irp.ThreadListEntry.Flink], rax
  ... truncated ...
```
