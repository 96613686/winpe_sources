# NtfsProcessException

- ea: `0x140029d80`
- end: `0x14002b24e`
- name: `NtfsProcessException`
- size: `5326`
- prototype: `__int64 __fastcall(__int64, unsigned __int64 MdlAddress, __int64)`
- caller_count: `59`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015540`
- `0x140015d10`
- `0x140016850`
- `0x14002c760`
- `0x14003c980`
- `0x140052b80`
- `0x1400557c0`
- `0x1400b96a0`
- `0x1400bbf04`
- `0x1400cf580`
- `0x1400d21b0`
- `0x1400e0080`
- `0x1400ec74c`
- `0x1400f753c`
- `0x1400fa698`
- `0x1400fc090`
- `0x14010229c`
- `0x140133f30`
- `0x14013a200`
- `0x14013af10`
- `0x14017b350`
- `0x14018f3c8`
- `0x140190b80`
- `0x1401a04b0`
- `0x1401a0cc0`
- `0x1401a1dc0`
- `0x1401a75e0`
- `0x1401aadc0`
- `0x1401bbd30`
- `0x1401c30e0`
- `0x1401c3320`
- `0x1401ccd30`
- `0x1401cf860`
- `0x1401d432c`
- `0x1401d60b8`
- `0x1401d6948`
- `0x1401d8340`
- `0x1401da21c`
- `0x1401dc5e8`
- `0x1401f4220`
- `0x1401f5420`
- `0x140201f40`
- `0x1402056bc`
- `0x14020a724`
- `0x14020b1b4`
- `0x140218400`
- `0x14021c370`
- `0x14021e68c`
- `0x140228a20`
- `0x140246004`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140008740`
- `0x140009c80`
- `0x14000ea70`
- `0x1400108f0`
- `0x140012b50`
- `0x140017030`
- `0x14001e810`
- `0x14001e940`
- `0x140020de0`
- `0x140022a00`
- `0x140029d80`
- `0x14002b8d0`
- `0x14002bc00`
- `0x14003380c`
- `0x14003aea8`
- `0x14003bb8c`
- `0x14003c34c`
- `0x14003fa30`
- `0x140040b40`
- `0x14004161c`
- `0x1400416d4`
- `0x1400419f8`
- `0x14004c7ec`
- `0x14012b220`
- `0x14012be00`
- `0x140140320`
- `0x14015e3f4`
- `0x14018aca8`
- `0x140208300`
- `0x140215650`
- `0x140299fa4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002aa31`
- `ntoskrnl!KeSetEvent` at `0x14002aa31`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14002ab8c`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14002ab8c`
- `ntoskrnl!CcMdlWriteAbort` at `0x14002a0ae`
- `ntoskrnl!CcMdlWriteAbort` at `0x14002b018`
- `ntoskrnl!CcMdlWriteAbort` at `0x14002a0ae`
- `ntoskrnl!CcMdlWriteAbort` at `0x14002b018`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002ae21`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002ae21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1a1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14002ade8`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14002ade8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002a9f8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002a9f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aa44`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aa44`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a0f6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002a0f6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a164`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a164`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ac44`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ac6b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad57`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad6a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad82`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ac44`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ac6b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad57`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad6a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ad82`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a27e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a9cb`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a27e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a9cb`

## pseudocode

```c
__int64 __fastcall NtfsProcessException(__int64 a1, unsigned __int64 MdlAddress, __int64 a3)
{
  int v3; // ebx
  IRP *v4; // r12
  __int64 v5; // rsi
  _DWORD *v6; // rdi
  __int64 TopLevelIrpContext; // rax
  char IsTopLevelRequest; // al
  __int64 v9; // rbx
  char *v10; // r15
  __int64 v11; // r13
  __int64 v12; // rax
  __int64 v13; // r8
  char *v14; // rdi
  __int64 v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rax
  char *v18; // rax
  _QWORD *v19; // rdx
  void *v20; // rcx
  __int64 v21; // rax
  unsigned __int64 *v22; // r15
  unsigned __int64 v23; // rax
  _QWORD *v24; // r14
  _QWORD *v25; // r15
  _QWORD *v26; // rdi
  char v27; // di
  __int64 v28; // rcx
  IRP *v29; // r12
  char v30; // al
  struct _IRP *v31; // rbx
  _QWORD *v32; // r15
  __int64 v33; // r8
  int v34; // eax
  PVOID v35; // r15
  IRP *v36; // r13
  char v37; // r9
  int v38; // eax
  IRP *v39; // r15
  struct _MDL *v40; // rdx
  _QWORD *v41; // r14
  _QWORD *v42; // rdi
  _QWORD *v43; // rcx
  __int64 v44; // rax
  bool v45; // sf
  __int64 v46; // rdi
  __int64 v47; // rax
  IRP *v49; // [rsp+40h] [rbp-78h]
  PVOID StartContext; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 *v51; // [rsp+50h] [rbp-68h]
  IRP *v52; // [rsp+58h] [rbp-60h]
  _QWORD v53[2]; // [rsp+60h] [rbp-58h] BYREF
  char *i; // [rsp+70h] [rbp-48h]
  __int64 v55; // [rsp+78h] [rbp-40h]
  _QWORD *v56; // [rsp+D8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = (IRP *)MdlAddress;
  v49 = (IRP *)MdlAddress;
  v5 = a1;
  StartContext = 0;
  if ( NtfsStatusDebugFlags
    && (_DWORD)a3
    && (_DWORD)a3 != 294
    && (unsigned int)(a3 - 298) > 1
    && (unsigned int)a3 < 0xFFFFFFED
    && (_DWORD)a3 != -1073741802
    && (unsigned int)(a3 + 2147483643) > 1
    && (_DWORD)a3 != -1073741807
    && (_DWORD)a3 != 259
    && (_DWORD)a3 != -1073741608 )
  {
    NtfsStatusTraceAndDebugInternal(0, a3, 0x1909F5u);
  }
  v6 = (_DWORD *)(v5 + 16);
  if ( !v5 || (v51 = (unsigned __int64 *)(v5 + 16), (*v6 & 0x100000LL) == 0) )
  {
    if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
      McTemplateU0pd_EtwWriteTransfer(a1, ntfsdata_c2554, v5, (unsigned int)v3);
    v51 = (unsigned __int64 *)(v5 + 16);
  }
  v53[0] = v5 + 16;
  if ( (!v5 || (*v6 & 0x100000LL) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0pd_EtwWriteTransfer(a1, ntfsdata_c2561, v5, (unsigned int)v3);
  }
  if ( !v5 )
  {
    if ( NtfsStatusDebugFlags
      && v3
      && v3 != 294
      && (unsigned int)(v3 - 298) > 1
      && (unsigned int)v3 < 0xFFFFFFED
      && v3 != -1073741802
      && (unsigned int)(v3 + 2147483643) > 1
      && v3 != -1073741807
      && v3 != 259
      && v3 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v3, 0x190A0Eu);
    }
    NtfsExtendedCompleteRequestInternal(0, v4, v3, v4 != 0, v3 >= 0);
    return (unsigned int)v3;
  }
  v52 = 0;
  v55 = 0;
  if ( v3 == -1073741432 )
  {
    a1 = *(_QWORD *)(v5 + 104);
    if ( a1 )
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8LL * *(int *)(v5 + 392) + 9352));
  }
  if ( (v3 == -1073741566 || v3 == -1073741774) && *(_QWORD *)(v5 + 384) )
  {
    TopLevelIrpContext = NtfsRepairGetTopLevelIrpContext(v5);
    MdlAddress = *(_QWORD *)(v5 + 384);
    if ( (MdlAddress & 1) != 0
      || (*(_DWORD *)(v5 + 12) & 0x8000000) != 0
      || (*(_DWORD *)(TopLevelIrpContext + 12) & 0x8000000) != 0
      || !*(_QWORD *)(v5 + 104)
      || *(_BYTE *)(TopLevelIrpContext + 32) == 18
      || (*(_DWORD *)(v5 + 436) & 0x80008) != 0 )
    {
      if ( !MdlAddress || (MdlAddress & 3) != 0 )
      {
        if ( (MdlAddress & 2) != 0 )
        {
          MdlAddress &= 0xFFFFFFFFFFFFFFFCuLL;
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(MdlAddress + 20), 0, 1) )
            NtfsFreeRepairItem((PVOID)MdlAddress);
          *(_QWORD *)(v5 + 384) = 0;
        }
      }
      else
      {
        v9 = *(_QWORD *)(MdlAddress + 152);
        NtfsFreeRepairItem(*(PVOID *)(v5 + 384));
        *(_QWORD *)(v5 + 384) = 0;
        NtfsPostVcbIsCorrupt(v5, 0, 0, 0, v9);
      }
    }
    else
    {
      *(_DWORD *)(v5 + 4) |= 0x400u;
      v55 = v5;
      IsTopLevelRequest = NtfsRepairIsTopLevelRequest(v5);
      MdlAddress = (unsigned __int64)v4;
      if ( !IsTopLevelRequest )
        MdlAddress = 0;
      v52 = (IRP *)MdlAddress;
    }
  }
  v10 = 0;
  v3 = *(_DWORD *)(v5 + 24);
  LODWORD(v56) = v3;
  v11 = *(_QWORD *)(v5 + 104);
  v53[1] = v11;
  if ( v11 )
  {
    a3 = *(_QWORD *)(v11 + 808);
    if ( a3 )
    {
      MdlAddress = HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors;
      a1 = (unsigned int)MdlAddress;
      v12 = 704LL * (unsigned int)MdlAddress;
      if ( v3 == -1073741432 )
        ++*(_DWORD *)(v12 + a3 + 104);
      else
        ++*(_DWORD *)(v12 + a3 + 108);
    }
  }
  if ( *(_BYTE *)(v5 + 32) == 4 && (*(_BYTE *)(v5 + 33) & 6) == 2 )
  {
    if ( v4 )
    {
      MdlAddress = (unsigned __int64)v4->MdlAddress;
      if ( MdlAddress )
      {
        CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, (PMDL)MdlAddress);
        v4->MdlAddress = 0;
      }
    }
  }
  if ( v11 )
  {
    LOBYTE(MdlAddress) = 1;
    NtfsRestoreScbSnapshots(v5, MdlAddress);
    v14 = (char *)(v5 + 232);
    for ( i = (char *)(v5 + 232); ; i = v18 )
    {
      v15 = *((_QWORD *)v14 + 1);
      if ( v15 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 104) + 8LL));
        if ( *(_QWORD *)(v15 + 296) )
        {
          if ( (*((_DWORD *)v14 + 6) & 0x3000) != 0 )
            *(_DWORD *)(v15 + 4) &= ~0x4000u;
          *(_DWORD *)(*(_QWORD *)(v15 + 296) + 248LL) &= ~*((_DWORD *)v14 + 6);
          v16 = *(_QWORD *)(v15 + 296);
          if ( *(_DWORD *)(v16 + 248) )
            *(_DWORD *)(v16 + 252) |= *((_DWORD *)v14 + 7);
          else
            *(_DWORD *)(v16 + 252) = 0;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 104) + 8LL));
        v17 = *((_QWORD *)v14 + 2);
        if ( v17 )
        {
          *(_DWORD *)(v17 + 144) &= ~0x20u;
          *(_OWORD *)(v14 + 24) = 0;
        }
        else
        {
          *(_OWORD *)(v14 + 8) = 0;
          *(_OWORD *)(v14 + 24) = 0;
          if ( v14 != (char *)(v5 + 232) )
          {
            *(_QWORD *)v10 = *(_QWORD *)v14;
            ExFreePoolWithTag(v14, 0);
            v14 = v10;
            i = v10;
          }
        }
      }
      v18 = *(char **)v14;
      if ( !*(_QWORD *)v14 )
        break;
      v10 = v14;
      v14 = *(char **)v14;
    }
    if ( *(_DWORD *)(v5 + 28) && (*(_DWORD *)(v11 + 4) & 1) != 0 )
    {
      NtfsAbortTransaction(v5);
    }
    else
    {
      v19 = (_QWORD *)(v5 + 280);
      if ( (_QWORD *)*v19 != v19 )
        NtfsProcessRollbackListPriv(v5, v19, ((v3 >> 31) & 3u) + 1, 0);
      LOBYTE(v13) = 1;
      TxfProcessTxfFcbCleanupList(v5, 1, v13, 0);
      v20 = *(void **)(v5 + 424);
      if ( v20 )
      {
        TxfRestoreIsoSnapshots(v20);
        *(_QWORD *)(v5 + 424) = 0;
      }
    }
    TxfProcessCancelList(v5, 1);
    NtfsRestoreScbSnapshots(v5, 0);
    if ( *(_QWORD *)(v11 + 296) != *(_QWORD *)(v11 + 336) )
    {
      v21 = *(_QWORD *)(v11 + 72);
      if ( v21 )
      {
        if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v21 + 184) + 104LL) + 64LL)) )
          *(_QWORD *)(v11 + 296) = *(_QWORD *)(v11 + 336);
      }
    }
  }
  v22 = v51;
  v23 = *v51;
  if ( (*v51 & 0x20) != 0 )
  {
    LOBYTE(a1) = 0;
    LOBYTE(v56) = 0;
    *v51 = v23 & 0xFFFFFFFFFFFFFFDFuLL;
    v24 = *(_QWORD **)(v5 + 152);
    while ( v24 != (_QWORD *)(v5 + 152) )
    {
      v25 = v24;
      v26 = v24 - 10;
      v53[0] = v24 - 10;
      v24 = (_QWORD *)*v24;
      if ( !(_BYTE)a1 )
      {
        NtfsAcquireFcbTableExclusive(a1, v11);
        LOBYTE(a1) = 1;
        LOBYTE(v56) = 1;
      }
      if ( (*((_DWORD *)v26 + 1) & 0x2000000) != 0 )
      {
        *((_DWORD *)v25 - 19) &= ~0x2000000u;
        if ( (*((_DWORD *)v26 + 1) & 0x4000000) != 0 && !*((_DWORD *)v26 + 7) )
        {
          NtfsDeleteFcb(v5, v53, &v56);
          a1 = (unsigned __int8)v56;
        }
        break;
      }
    }
    if ( (_BYTE)a1 )
      NtfsReleaseFcbTable(a1, v11);
    NtfsReleaseVcb(v5, v11);
    v22 = v51;
  }
  v27 = 0;
  LOBYTE(v56) = 0;
  v28 = *(_QWORD *)(v5 + 144);
  if ( v5 == v28 || *(int *)(v28 + 24) < 0 )
    goto LABEL_109;
  if ( v3 == -1073741740 )
  {
    *(_DWORD *)(*(_QWORD *)(v5 + 144) + 24LL) = -1073741608;
    *(_DWORD *)(*(_QWORD *)(v5 + 144) + 4LL) |= 0x8000000u;
LABEL_109:
    v29 = v49;
    goto LABEL_110;
  }
  if ( v3 >= 0 )
    goto LABEL_109;
  if ( *(_BYTE *)(v5 + 32) != 4 || v3 != -1073741801 && v3 != -1073741670 && v3 != -1073741663 )
  {
    v29 = v49;
LABEL_125:
    *(_DWORD *)(v28 + 24) = v3;
    *(_DWORD *)(*(_QWORD *)(v5 + 144) + 4LL) |= 0x8000000u;
    goto LABEL_110;
  }
  v29 = v49;
  if ( (v49->Flags & 2) == 0 || v49->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length <= 0x1000 )
    goto LABEL_125;
LABEL_110:
  if ( v3 != -1073741432 && v3 != -1073741608 && !(unsigned __int8)CcIsCacheManagerCallbackNeeded((unsigned int)v3) )
  {
LABEL_136:
    if ( v3 == -1073740761 && (*(_DWORD *)(v5 + 12) & 0x800) != 0 && *(_BYTE *)(v5 + 32) == 4 )
    {
      v3 = -1073741672;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000098, 0x190E3Cu);
    }
    goto LABEL_159;
  }
  v30 = *(_BYTE *)(v5 + 32);
  if ( v30 == 2 )
  {
    v27 = 1;
    LOBYTE(v56) = 1;
    if ( (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
    {
      v3 = 259;
      goto LABEL_159;
    }
    goto LABEL_136;
  }
  if ( v30 == 3 && (v5 != *(_QWORD *)(v5 + 144) || !LOBYTE(IoGetTopLevelIrp()->Type) || (v29->Flags & 2) != 0) )
  {
LABEL_135:
    v27 = 1;
    LOBYTE(v56) = 1;
    goto LABEL_136;
  }
  if ( v5 == *(_QWORD *)(v5 + 144) && LOBYTE(IoGetTopLevelIrp()->Type) && (*(_DWORD *)v22 & 0x400000) == 0 )
  {
    if ( (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
    {
      StartContext = (PVOID)v5;
      goto LABEL_136;
    }
    goto LABEL_135;
  }
  if ( v3 == -1073741432 )
  {
    ++*(_DWORD *)(v11 + 4860);
    if ( *(_QWORD *)(v11 + 1336) == NtfsLarge0.QuadPart )
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)(v11 + 1336),
        *(_QWORD *)(v11 + 824),
        NtfsLarge0.QuadPart);
    if ( *(_QWORD *)(v5 + 144) == v5 && (*(_DWORD *)(v11 + 572) & 1) == 0 && (*(_DWORD *)(v5 + 4) & 0x80000) == 0 )
    {
      if ( (*(_DWORD *)(v5 + 12) & 0x800) != 0
        && *(_BYTE *)(v5 + 32) == 4
        && IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
      {
        v31 = (struct _IRP *)((__int64)IoGetTopLevelIrp()->AssociatedIrp.MasterIrp | 0x80000000LL);
        IoGetTopLevelIrp()->AssociatedIrp.MasterIrp = v31;
      }
      else
      {
        StartContext = 0;
        NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&StartContext);
        v32 = StartContext;
        if ( StartContext )
        {
          NtfsSetIrpContextVcb((__int64)StartContext, v11);
          v32[25] = *(_QWORD *)(v32[13] + 824LL);
          *((_DWORD *)v32 + 98) = *(_DWORD *)(v5 + 392);
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v11 + 576));
          v34 = *(_DWORD *)(v11 + 572);
          if ( (v34 & 1) != 0 )
          {
            NtfsCleanupIrpContext((__int64)v32, 0, v33);
            StartContext = 0;
          }
          else
          {
            *(_DWORD *)(v11 + 572) = v34 | 1;
          }
          KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v11 + 576));
        }
      }
    }
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC0000054, 0x190E29u);
  v3 = -1073741740;
LABEL_159:
  v35 = StartContext;
  v36 = v49;
  if ( StartContext )
  {
    v37 = 0;
    if ( *((_QWORD *)StartContext + 14) && (unsigned __int8)(*((_BYTE *)StartContext + 32) - 3) <= 1u )
      v37 = (*((_DWORD *)v49->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 128) & 0x400000) != 0;
    *((_DWORD *)StartContext + 6) = 0;
    *((_QWORD *)v35 + 2) &= ~0x20000uLL;
    *((_DWORD *)v35 + 2) |= 2u;
    LOBYTE(a3) = v35 == (PVOID)v5;
    v38 = NtfsPostRequest((char *)v35, *((IRP **)v35 + 14), a3, v37);
    if ( v35 == (PVOID)v5 )
    {
      v36 = 0;
      v5 = 0;
      v3 = v38;
    }
    v39 = v52;
  }
  else
  {
    v39 = v52;
  }
  if ( v27 )
  {
    *(_DWORD *)(v5 + 4) |= 0x400u;
    v36 = 0;
    *(_DWORD *)(v5 + 24) = 0;
  }
  else if ( v5 && ((*(_DWORD *)(v5 + 12) & 0x42) == 2 || v39) )
  {
    v36 = 0;
    goto LABEL_174;
  }
  if ( v36 )
  {
    if ( *(_BYTE *)(v5 + 32) == 4 && (*(_BYTE *)(v5 + 33) & 6) == 6 )
    {
      v40 = v36->MdlAddress;
      if ( v40 )
      {
        CcMdlWriteAbort(v36->Tail.Overlay.CurrentStackLocation->FileObject, v40);
        v36->MdlAddress = 0;
      }
    }
  }
LABEL_174:
  if ( !v5 )
    goto LABEL_191;
  if ( (*(_DWORD *)(v5 + 4) & 0x400) == 0 && (*(_DWORD *)(v5 + 12) & 0x10000) == 0
    || v3 != -1073741608 && v3 != -1073741432 )
  {
    v41 = (_QWORD *)(v5 + 440);
    v42 = *(_QWORD **)(v5 + 440);
    if ( v42 )
    {
      while ( v42 != v41 )
      {
        v43 = v42 - 7;
        v56 = v43;
        v42 = (_QWORD *)*v42;
        if ( (v43[2] & 0xF) == 5 )
        {
          *((_DWORD *)v43 + 4) = (unsigned __int8)*((_DWORD *)v43 + 4);
          TxfRemoveTxfFcbCleanupStruct(v43, &v56, 0);
        }
      }
    }
  }
  v44 = *(_QWORD *)(v5 + 16);
  if ( (v44 & 1) == 0 || !v36 )
  {
LABEL_191:
    if ( NtfsStatusDebugFlags )
    {
      v45 = v3 < 0;
      if ( !v3 )
      {
LABEL_203:
        NtfsExtendedCompleteRequestInternal(v5, v36, v3, v36 != 0, !v45);
        goto LABEL_204;
      }
      if ( v3 != 294
        && (unsigned int)(v3 - 298) > 1
        && (unsigned int)v3 < 0xFFFFFFED
        && v3 != -1073741802
        && (unsigned int)(v3 + 2147483643) > 1
        && v3 != -1073741807
        && v3 != 259
        && v3 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(v5, v3, 0x190F20u);
      }
    }
    v45 = v3 < 0;
    goto LABEL_203;
  }
  *(_QWORD *)(v5 + 16) = v44 | 2;
LABEL_204:
  v46 = v55;
  if ( v55 )
  {
    *(_DWORD *)(v5 + 24) = v3;
    v3 = NtfsPostRepairRequest(v46, v39);
    if ( v3 != -1073741608 && (*(_DWORD *)(v5 + 12) & 0x42) != 2 )
    {
      v47 = *(_QWORD *)(v46 + 16);
      if ( (v47 & 1) != 0 && v39 )
      {
        *(_QWORD *)(v46 + 16) = v47 | 2;
      }
      else
      {
        if ( NtfsStatusDebugFlags
          && v3
          && v3 != 294
          && (unsigned int)(v3 - 298) > 1
          && (unsigned int)v3 < 0xFFFFFFED
          && v3 != -1073741802
          && (unsigned int)(v3 + 2147483643) > 1
          && v3 != -1073741807
          && v3 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(v46, v3, 0x190F52u);
        }
        NtfsExtendedCompleteRequestInternal(v46, v39, v3, v39 != 0, v3 >= 0);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140029d80  mov     [rsp+arg_8], rdx
0x140029d85  mov     [rsp+arg_0], rcx
0x140029d8a  push    rbx
0x140029d8b  push    rsi
0x140029d8c  push    rdi
0x140029d8d  push    r12
0x140029d8f  push    r13
0x140029d91  push    r14
0x140029d93  push    r15
0x140029d95  sub     rsp, 80h
0x140029d9c  mov     ebx, r8d
0x140029d9f  mov     r12, rdx
0x140029da2  mov     [rsp+0B8h+var_78], rdx
0x140029da7  mov     rsi, rcx
0x140029daa  xor     r14d, r14d
0x140029dad  mov     [rsp+0B8h+StartContext], r14
0x140029db2  movzx   eax, cs:NtfsStatusDebugFlags
0x140029db9  test    al, al
0x140029dbb  jz      short loc_140029E15
0x140029dbd  test    ebx, ebx
0x140029dbf  jz      short loc_140029E15
0x140029dc1  cmp     ebx, 126h
0x140029dc7  jz      short loc_140029E15
0x140029dc9  lea     eax, [r8-12Ah]
0x140029dd0  cmp     eax, 1
0x140029dd3  jbe     short loc_140029E15
0x140029dd5  cmp     ebx, 0FFFFFFEDh
0x140029dd8  jnb     short loc_140029E15
0x140029dda  cmp     ebx, 0C0000016h
0x140029de0  jz      short loc_140029E15
0x140029de2  lea     eax, [r8+7FFFFFFBh]
0x140029de9  cmp     eax, 1
0x140029dec  jbe     short loc_140029E15
0x140029dee  cmp     ebx, 0C0000011h
0x140029df4  jz      short loc_140029E15
0x140029df6  cmp     ebx, 103h
0x140029dfc  jz      short loc_140029E15
0x140029dfe  cmp     ebx, 0C00000D8h
0x140029e04  jz      short loc_140029E15
0x140029e06  mov     r8d, 1909F5h
0x140029e0c  mov     edx, ebx
0x140029e0e  xor     ecx, ecx
0x140029e10  call    NtfsStatusTraceAndDebugInternal
0x140029e15  lea     rdi, [rsi+10h]
0x140029e19  test    rsi, rsi
0x140029e1c  jz      short loc_140029E2C
0x140029e1e  mov     [rsp+0B8h+var_68], rdi
0x140029e23  mov     eax, [rdi]
0x140029e25  bt      rax, 14h
0x140029e2a  jb      short loc_140029E4C
0x140029e2c  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 4
0x140029e33  jz      short loc_140029E47
0x140029e35  mov     r9d, ebx
0x140029e38  mov     r8, rsi
0x140029e3b  lea     rdx, ntfsdata_c2554
0x140029e42  call    McTemplateU0pd_EtwWriteTransfer
0x140029e47  mov     [rsp+0B8h+var_68], rdi
0x140029e4c  mov     [rsp+0B8h+var_58], rdi
0x140029e51  test    rsi, rsi
0x140029e54  jz      short loc_140029E5F
0x140029e56  mov     eax, [rdi]
0x140029e58  bt      rax, 14h
0x140029e5d  jb      short loc_140029E7A
0x140029e5f  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 2
0x140029e66  jz      short loc_140029E7A
0x140029e68  mov     r9d, ebx
0x140029e6b  mov     r8, rsi
0x140029e6e  lea     rdx, ntfsdata_c2561
0x140029e75  call    McTemplateU0pd_EtwWriteTransfer
0x140029e7a  test    rsi, rsi
0x140029e7d  jnz     short loc_140029EFC
0x140029e7f  movzx   eax, cs:NtfsStatusDebugFlags
0x140029e86  test    al, al
0x140029e88  jz      short loc_140029EE0
0x140029e8a  test    ebx, ebx
0x140029e8c  jz      short loc_140029EE0
0x140029e8e  cmp     ebx, 126h
0x140029e94  jz      short loc_140029EE0
0x140029e96  lea     eax, [rbx-12Ah]
0x140029e9c  cmp     eax, 1
0x140029e9f  jbe     short loc_140029EE0
0x140029ea1  cmp     ebx, 0FFFFFFEDh
0x140029ea4  jnb     short loc_140029EE0
0x140029ea6  cmp     ebx, 0C0000016h
0x140029eac  jz      short loc_140029EE0
0x140029eae  lea     eax, [rbx+7FFFFFFBh]
0x140029eb4  cmp     eax, 1
0x140029eb7  jbe     short loc_140029EE0
0x140029eb9  cmp     ebx, 0C0000011h
0x140029ebf  jz      short loc_140029EE0
0x140029ec1  cmp     ebx, 103h
0x140029ec7  jz      short loc_140029EE0
0x140029ec9  cmp     ebx, 0C00000D8h
0x140029ecf  jz      short loc_140029EE0
0x140029ed1  mov     r8d, 190A0Eh
0x140029ed7  mov     edx, ebx
0x140029ed9  xor     ecx, ecx
0x140029edb  call    NtfsStatusTraceAndDebugInternal
0x140029ee0  mov     eax, ebx
0x140029ee2  not     eax
0x140029ee4  shr     eax, 1Fh
0x140029ee7  test    r12, r12
0x140029eea  setnz   r9b
0x140029eee  mov     dword ptr [rsp+0B8h+var_98], eax
0x140029ef2  mov     rdx, r12
0x140029ef5  xor     ecx, ecx
0x140029ef7  jmp     loc_14002B230
0x140029efc  mov     [rsp+0B8h+var_60], r14
0x140029f01  mov     [rsp+0B8h+var_40], r14
0x140029f06  cmp     ebx, 0C0000188h
0x140029f0c  jnz     short loc_140029F27
0x140029f0e  mov     rcx, [rsi+68h]
0x140029f12  test    rcx, rcx
0x140029f15  jz      short loc_140029F27
0x140029f17  movsxd  rax, dword ptr [rsi+188h]
0x140029f1e  lock inc qword ptr [rcx+rax*8+2488h]
0x140029f27  cmp     ebx, 0C0000102h
0x140029f2d  jz      short loc_140029F3B
0x140029f2f  cmp     ebx, 0C0000032h
0x140029f35  jnz     loc_14002A02F
0x140029f3b  cmp     [rsi+180h], r14
0x140029f42  jz      loc_14002A02F
0x140029f48  mov     rcx, rsi
0x140029f4b  call    NtfsRepairGetTopLevelIrpContext
0x140029f50  mov     rdx, [rsi+180h]
0x140029f57  test    dl, 1
0x140029f5a  jnz     short loc_140029FAD
0x140029f5c  test    dword ptr [rsi+0Ch], 8000000h
0x140029f63  jnz     short loc_140029FAD
0x140029f65  test    dword ptr [rax+0Ch], 8000000h
0x140029f6c  jnz     short loc_140029FAD
0x140029f6e  cmp     [rsi+68h], r14
0x140029f72  jz      short loc_140029FAD
0x140029f74  cmp     byte ptr [rax+20h], 12h
0x140029f78  jz      short loc_140029FAD
0x140029f7a  test    dword ptr [rsi+1B4h], 80008h
0x140029f84  jnz     short loc_140029FAD
0x140029f86  or      dword ptr [rsi+4], 400h
0x140029f8d  mov     [rsp+0B8h+var_40], rsi
0x140029f92  mov     rcx, rsi
0x140029f95  call    NtfsRepairIsTopLevelRequest
0x140029f9a  mov     rdx, r12
0x140029f9d  test    al, al
0x140029f9f  cmovz   rdx, r14
0x140029fa3  mov     [rsp+0B8h+var_60], rdx
0x140029fa8  jmp     loc_14002A02F
0x140029fad  test    rdx, rdx
0x140029fb0  jz      short loc_14002A008
0x140029fb2  test    dl, 3
0x140029fb5  jnz     short loc_14002A008
0x140029fb7  mov     rbx, [rdx+98h]
0x140029fbe  mov     rcx, rdx; P
0x140029fc1  call    NtfsFreeRepairItem
0x140029fc6  mov     [rsi+180h], r14
0x140029fcd  mov     [rsp+0B8h+var_98], rbx
0x140029fd2  xor     r9d, r9d
0x140029fd5  xor     r8d, r8d
0x140029fd8  xor     edx, edx
0x140029fda  mov     rcx, rsi
0x140029fdd  call    NtfsPostVcbIsCorrupt
0x140029fe2  jmp     short loc_14002A02F
0x140029fe4  xor     r14d, r14d
0x140029fe7  mov     r12, [rsp+0B8h+arg_8]
0x140029fef  mov     [rsp+0B8h+var_78], r12
0x140029ff4  mov     rsi, [rsp+0B8h+arg_0]
0x140029ffc  mov     rax, [rsp+0B8h+var_58]
0x14002a001  mov     [rsp+0B8h+var_68], rax
0x14002a006  jmp     short loc_14002A02F
0x14002a008  test    dl, 2
0x14002a00b  jz      short loc_14002A02F
0x14002a00d  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14002a011  mov     eax, 1
0x14002a016  lock cmpxchg [rdx+14h], r14d
0x14002a01c  test    eax, eax
0x14002a01e  jnz     short loc_14002A028
0x14002a020  mov     rcx, rdx; P
0x14002a023  call    NtfsFreeRepairItem
0x14002a028  mov     [rsi+180h], r14
0x14002a02f  mov     r15, r14
0x14002a032  mov     ebx, [rsi+18h]
0x14002a035  mov     dword ptr [rsp+0B8h+arg_18], ebx
0x14002a03c  mov     r13, [rsi+68h]
0x14002a040  mov     [rsp+0B8h+var_50], r13
0x14002a045  test    r13, r13
0x14002a048  jz      short loc_14002A083
0x14002a04a  mov     r8, [r13+328h]
0x14002a051  test    r8, r8
0x14002a054  jz      short loc_14002A083
0x14002a056  mov     eax, gs:1A4h
0x14002a05e  xor     edx, edx
0x14002a060  div     cs:NtfsNumberProcessors
0x14002a066  mov     ecx, edx
0x14002a068  imul    rax, rcx, 2C0h
0x14002a06f  cmp     ebx, 0C0000188h
0x14002a075  jnz     short loc_14002A07E
0x14002a077  inc     dword ptr [rax+r8+68h]
0x14002a07c  jmp     short loc_14002A083
0x14002a07e  inc     dword ptr [rax+r8+6Ch]
0x14002a083  cmp     byte ptr [rsi+20h], 4
0x14002a087  jnz     short loc_14002A0BF
0x14002a089  movzx   eax, byte ptr [rsi+21h]
0x14002a08d  and     al, 6
0x14002a08f  cmp     al, 2
0x14002a091  jnz     short loc_14002A0BF
0x14002a093  test    r12, r12
0x14002a096  jz      short loc_14002A0BF
0x14002a098  mov     rdx, [r12+8]; MdlChain
0x14002a09d  test    rdx, rdx
0x14002a0a0  jz      short loc_14002A0BF
0x14002a0a2  mov     rcx, [r12+0B8h]
0x14002a0aa  mov     rcx, [rcx+30h]; FileObject
0x14002a0ae  call    cs:__imp_CcMdlWriteAbort
0x14002a0b5  nop     dword ptr [rax+rax+00h]
0x14002a0ba  mov     [r12+8], r14
0x14002a0bf  test    r13, r13
0x14002a0c2  jz      loc_14002A29C
0x14002a0c8  mov     dl, 1
0x14002a0ca  mov     rcx, rsi
0x14002a0cd  call    NtfsRestoreScbSnapshots
0x14002a0d2  lea     r12, [rsi+0E8h]
0x14002a0d9  mov     rdi, r12
0x14002a0dc  mov     [rsp+0B8h+var_48], r12
0x14002a0e1  mov     r14, [rdi+8]
0x14002a0e5  test    r14, r14
0x14002a0e8  jz      loc_14002A1B5
0x14002a0ee  mov     rcx, [r14+68h]
0x14002a0f2  add     rcx, 8; FastMutex
0x14002a0f6  call    cs:__imp_ExAcquireFastMutex
0x14002a0fd  nop     dword ptr [rax+rax+00h]
0x14002a102  cmp     qword ptr [r14+128h], 0
0x14002a10a  jz      short loc_14002A15C
0x14002a10c  test    dword ptr [rdi+18h], 3000h
0x14002a113  jz      short loc_14002A125
0x14002a115  mov     eax, [r14+4]
0x14002a119  btr     eax, 0Eh
0x14002a11d  mov     [r14+4], eax
0x14002a121  mov     eax, [r14+4]
0x14002a125  mov     rcx, [r14+128h]
0x14002a12c  mov     eax, [rdi+18h]
0x14002a12f  not     eax
0x14002a131  and     [rcx+0F8h], eax
0x14002a137  mov     rcx, [r14+128h]
0x14002a13e  cmp     dword ptr [rcx+0F8h], 0
0x14002a145  jnz     short loc_14002A153
0x14002a147  mov     dword ptr [rcx+0FCh], 0
0x14002a151  jmp     short loc_14002A15C
0x14002a153  mov     eax, [rdi+1Ch]
0x14002a156  or      [rcx+0FCh], eax
0x14002a15c  mov     rcx, [r14+68h]
0x14002a160  add     rcx, 8; FastMutex
0x14002a164  call    cs:__imp_ExReleaseFastMutex
0x14002a16b  nop     dword ptr [rax+rax+00h]
0x14002a170  mov     rax, [rdi+10h]
0x14002a174  xorps   xmm0, xmm0
0x14002a177  test    rax, rax
0x14002a17a  jz      short loc_14002A189
0x14002a17c  and     dword ptr [rax+90h], 0FFFFFFDFh
0x14002a183  movups  xmmword ptr [rdi+18h], xmm0
0x14002a187  jmp     short loc_14002A1B5
0x14002a189  movups  xmmword ptr [rdi+8], xmm0
0x14002a18d  movups  xmmword ptr [rdi+18h], xmm0
0x14002a191  cmp     rdi, r12
0x14002a194  jz      short loc_14002A1B5
0x14002a196  mov     rax, [rdi]
0x14002a199  mov     [r15], rax
0x14002a19c  xor     edx, edx; Tag
0x14002a19e  mov     rcx, rdi; P
0x14002a1a1  call    cs:__imp_ExFreePoolWithTag
0x14002a1a8  nop     dword ptr [rax+rax+00h]
0x14002a1ad  mov     rdi, r15
0x14002a1b0  mov     [rsp+0B8h+var_48], r15
0x14002a1b5  mov     rax, [rdi]
0x14002a1b8  test    rax, rax
0x14002a1bb  jz      short loc_14002A1CD
0x14002a1bd  mov     r15, rdi
0x14002a1c0  mov     rdi, rax
0x14002a1c3  mov     [rsp+0B8h+var_48], rax
0x14002a1c8  jmp     loc_14002A0E1
0x14002a1cd  cmp     dword ptr [rsi+1Ch], 0
0x14002a1d1  jz      short loc_14002A1EB
0x14002a1d3  mov     eax, [r13+4]
0x14002a1d7  test    al, 1
0x14002a1d9  jz      short loc_14002A1EB
0x14002a1db  xor     r8d, r8d
0x14002a1de  mov     rdx, r13
0x14002a1e1  mov     rcx, rsi
0x14002a1e4  call    NtfsAbortTransaction
0x14002a1e9  jmp     short loc_14002A23F
0x14002a1eb  lea     rdx, [rsi+118h]
0x14002a1f2  cmp     [rdx], rdx
0x14002a1f5  jz      short loc_14002A210
0x14002a1f7  mov     r8d, ebx
0x14002a1fa  sar     r8d, 1Fh
0x14002a1fe  and     r8d, 3
0x14002a202  inc     r8d
0x14002a205  xor     r9d, r9d
0x14002a208  mov     rcx, rsi
0x14002a20b  call    NtfsProcessRollbackListPriv
0x14002a210  xor     r9d, r9d
0x14002a213  mov     r8b, 1
  ... truncated ...
```
