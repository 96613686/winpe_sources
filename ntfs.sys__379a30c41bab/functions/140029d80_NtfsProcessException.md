# NtfsProcessException

- ea: `0x140029d80`
- end: `0x14002b24e`
- name: `NtfsProcessException`
- size: `5326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `59`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015540`
- `0x140015d10`
- `0x140016850`
- `0x14002c760`
- `0x14003c980`
- `0x140052bf0`
- `0x140055830`
- `0x1400b96a0`
- `0x1400bbf04`
- `0x1400cf580`
- `0x1400d21b0`
- `0x1400e0080`
- `0x1400ec79c`
- `0x1400f758c`
- `0x1400fa6e8`
- `0x1400fc0e0`
- `0x1401022ec`
- `0x140133f80`
- `0x14013a250`
- `0x14013af60`
- `0x14017b3a0`
- `0x14018f418`
- `0x140190bd0`
- `0x1401a0500`
- `0x1401a0d10`
- `0x1401a1e10`
- `0x1401a7630`
- `0x1401aae10`
- `0x1401bbd80`
- `0x1401c3130`
- `0x1401c3370`
- `0x1401ccd80`
- `0x1401cf8b0`
- `0x1401d437c`
- `0x1401d6108`
- `0x1401d6998`
- `0x1401d8390`
- `0x1401da26c`
- `0x1401dc638`
- `0x1401f4270`
- `0x1401f5470`
- `0x140201f90`
- `0x14020570c`
- `0x14020a774`
- `0x14020b204`
- `0x140218450`
- `0x14021c3c0`
- `0x14021e6dc`
- `0x140228a70`
- `0x140246054`

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
- `0x14004c85c`
- `0x14012b270`
- `0x14012be50`
- `0x140140370`
- `0x14015e444`
- `0x14018acf8`
- `0x140208350`
- `0x1402156a0`
- `0x140299ff4`

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
__int64 __fastcall NtfsProcessException(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // r12
  __int64 v6; // rsi
  _DWORD *v7; // rdi
  __int64 TopLevelIrpContext; // rax
  char IsTopLevelRequest; // al
  __int64 v10; // rbx
  char *v11; // r15
  __int64 v12; // r13
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  char *v16; // rdi
  __int64 v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rax
  char *v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rdx
  void *v23; // rcx
  __int64 v24; // rax
  unsigned __int64 *v25; // r15
  unsigned __int64 v26; // rax
  _QWORD *v27; // r14
  _QWORD *v28; // r15
  _QWORD *v29; // rdi
  char v30; // di
  __int64 v31; // rcx
  __int64 v32; // r12
  char v33; // al
  struct _IRP *v34; // rbx
  _QWORD *v35; // r15
  __int64 v36; // r8
  int v37; // eax
  _QWORD *v38; // r15
  __int64 v39; // r13
  unsigned int v40; // eax
  _QWORD *v41; // r15
  struct _MDL *v42; // rdx
  _QWORD *v43; // r14
  _QWORD *v44; // rdi
  unsigned __int64 v45; // rcx
  __int64 v46; // rax
  bool v47; // sf
  __int64 v48; // rdi
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v52; // [rsp+40h] [rbp-78h]
  PVOID StartContext; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 *v54; // [rsp+50h] [rbp-68h]
  _QWORD *v55; // [rsp+58h] [rbp-60h]
  _QWORD v56[2]; // [rsp+60h] [rbp-58h] BYREF
  char *i; // [rsp+70h] [rbp-48h]
  __int64 v58; // [rsp+78h] [rbp-40h]
  unsigned __int64 v59; // [rsp+D8h] [rbp+20h] BYREF

  v4 = a3;
  v5 = a2;
  v52 = a2;
  v6 = a1;
  StartContext = 0;
  if ( NtfsStatusDebugFlags
    && a3
    && a3 != 294
    && a3 - 298 > 1
    && a3 < 0xFFFFFFED
    && a3 != -1073741802
    && a3 + 2147483643 > 1
    && a3 != -1073741807
    && a3 != 259
    && a3 != -1073741608 )
  {
    NtfsStatusTraceAndDebugInternal(0, a3, 1640949);
  }
  v7 = (_DWORD *)(v6 + 16);
  if ( !v6 || (v54 = (unsigned __int64 *)(v6 + 16), (*v7 & 0x100000LL) == 0) )
  {
    if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
      McTemplateU0pd_EtwWriteTransfer(a1, ntfsdata_c2554, v6, v4);
    v54 = (unsigned __int64 *)(v6 + 16);
  }
  v56[0] = v6 + 16;
  if ( (!v6 || (*v7 & 0x100000LL) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0pd_EtwWriteTransfer(a1, ntfsdata_c2561, v6, v4);
  }
  if ( !v6 )
  {
    if ( NtfsStatusDebugFlags
      && v4
      && v4 != 294
      && v4 - 298 > 1
      && v4 < 0xFFFFFFED
      && v4 != -1073741802
      && v4 + 2147483643 > 1
      && v4 != -1073741807
      && v4 != 259
      && v4 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v4, 1640974);
    }
    LOBYTE(a4) = v5 != 0;
    NtfsExtendedCompleteRequestInternal(0, v5, v4, a4, (v4 & 0x80000000) == 0);
    return v4;
  }
  v55 = 0;
  v58 = 0;
  if ( v4 == -1073741432 )
  {
    a1 = *(_QWORD *)(v6 + 104);
    if ( a1 )
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8LL * *(int *)(v6 + 392) + 9352));
  }
  if ( (v4 == -1073741566 || v4 == -1073741774) && *(_QWORD *)(v6 + 384) )
  {
    TopLevelIrpContext = NtfsRepairGetTopLevelIrpContext(v6);
    a2 = *(_QWORD *)(v6 + 384);
    if ( (a2 & 1) != 0
      || (*(_DWORD *)(v6 + 12) & 0x8000000) != 0
      || (*(_DWORD *)(TopLevelIrpContext + 12) & 0x8000000) != 0
      || !*(_QWORD *)(v6 + 104)
      || *(_BYTE *)(TopLevelIrpContext + 32) == 18
      || (*(_DWORD *)(v6 + 436) & 0x80008) != 0 )
    {
      if ( !a2 || (a2 & 3) != 0 )
      {
        if ( (a2 & 2) != 0 )
        {
          a2 &= 0xFFFFFFFFFFFFFFFCuLL;
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a2 + 20), 0, 1) )
            NtfsFreeRepairItem((PVOID)a2);
          *(_QWORD *)(v6 + 384) = 0;
        }
      }
      else
      {
        v10 = *(_QWORD *)(a2 + 152);
        NtfsFreeRepairItem(*(PVOID *)(v6 + 384));
        *(_QWORD *)(v6 + 384) = 0;
        NtfsPostVcbIsCorrupt(v6, 0, 0, 0, v10);
      }
    }
    else
    {
      *(_DWORD *)(v6 + 4) |= 0x400u;
      v58 = v6;
      IsTopLevelRequest = NtfsRepairIsTopLevelRequest(v6);
      a2 = v5;
      if ( !IsTopLevelRequest )
        a2 = 0;
      v55 = (_QWORD *)a2;
    }
  }
  v11 = 0;
  v4 = *(_DWORD *)(v6 + 24);
  LODWORD(v59) = v4;
  v12 = *(_QWORD *)(v6 + 104);
  v56[1] = v12;
  if ( v12 )
  {
    v13 = *(_QWORD *)(v12 + 808);
    if ( v13 )
    {
      a2 = HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors;
      a1 = (unsigned int)a2;
      v14 = 704LL * (unsigned int)a2;
      if ( v4 == -1073741432 )
        ++*(_DWORD *)(v14 + v13 + 104);
      else
        ++*(_DWORD *)(v14 + v13 + 108);
    }
  }
  if ( *(_BYTE *)(v6 + 32) == 4 && (*(_BYTE *)(v6 + 33) & 6) == 2 )
  {
    if ( v5 )
    {
      a2 = *(_QWORD *)(v5 + 8);
      if ( a2 )
      {
        CcMdlWriteAbort(*(PFILE_OBJECT *)(*(_QWORD *)(v5 + 184) + 48LL), (PMDL)a2);
        *(_QWORD *)(v5 + 8) = 0;
      }
    }
  }
  if ( v12 )
  {
    LOBYTE(a2) = 1;
    NtfsRestoreScbSnapshots(v6, a2);
    v16 = (char *)(v6 + 232);
    for ( i = (char *)(v6 + 232); ; i = v20 )
    {
      v17 = *((_QWORD *)v16 + 1);
      if ( v17 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v17 + 104) + 8LL));
        if ( *(_QWORD *)(v17 + 296) )
        {
          if ( (*((_DWORD *)v16 + 6) & 0x3000) != 0 )
            *(_DWORD *)(v17 + 4) &= ~0x4000u;
          *(_DWORD *)(*(_QWORD *)(v17 + 296) + 248LL) &= ~*((_DWORD *)v16 + 6);
          v18 = *(_QWORD *)(v17 + 296);
          if ( *(_DWORD *)(v18 + 248) )
            *(_DWORD *)(v18 + 252) |= *((_DWORD *)v16 + 7);
          else
            *(_DWORD *)(v18 + 252) = 0;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v17 + 104) + 8LL));
        v19 = *((_QWORD *)v16 + 2);
        if ( v19 )
        {
          *(_DWORD *)(v19 + 144) &= ~0x20u;
          *(_OWORD *)(v16 + 24) = 0;
        }
        else
        {
          *(_OWORD *)(v16 + 8) = 0;
          *(_OWORD *)(v16 + 24) = 0;
          if ( v16 != (char *)(v6 + 232) )
          {
            *(_QWORD *)v11 = *(_QWORD *)v16;
            ExFreePoolWithTag(v16, 0);
            v16 = v11;
            i = v11;
          }
        }
      }
      v20 = *(char **)v16;
      if ( !*(_QWORD *)v16 )
        break;
      v11 = v16;
      v16 = *(char **)v16;
    }
    if ( *(_DWORD *)(v6 + 28) && (*(_DWORD *)(v12 + 4) & 1) != 0 )
    {
      NtfsAbortTransaction(v6);
    }
    else
    {
      v22 = (_QWORD *)(v6 + 280);
      if ( (_QWORD *)*v22 != v22 )
        NtfsProcessRollbackListPriv(v6, v22, (((int)v4 >> 31) & 3u) + 1, 0);
      LOBYTE(v15) = 1;
      TxfProcessTxfFcbCleanupList(v6, 1, v15, 0);
      v23 = *(void **)(v6 + 424);
      if ( v23 )
      {
        TxfRestoreIsoSnapshots(v23);
        *(_QWORD *)(v6 + 424) = 0;
      }
    }
    LOBYTE(v21) = 1;
    TxfProcessCancelList(v6, v21);
    NtfsRestoreScbSnapshots(v6, 0);
    if ( *(_QWORD *)(v12 + 296) != *(_QWORD *)(v12 + 336) )
    {
      v24 = *(_QWORD *)(v12 + 72);
      if ( v24 )
      {
        if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v24 + 184) + 104LL) + 64LL)) )
          *(_QWORD *)(v12 + 296) = *(_QWORD *)(v12 + 336);
      }
    }
  }
  v25 = v54;
  v26 = *v54;
  if ( (*v54 & 0x20) != 0 )
  {
    LOBYTE(a1) = 0;
    LOBYTE(v59) = 0;
    *v54 = v26 & 0xFFFFFFFFFFFFFFDFuLL;
    v27 = *(_QWORD **)(v6 + 152);
    while ( v27 != (_QWORD *)(v6 + 152) )
    {
      v28 = v27;
      v29 = v27 - 10;
      v56[0] = v27 - 10;
      v27 = (_QWORD *)*v27;
      if ( !(_BYTE)a1 )
      {
        NtfsAcquireFcbTableExclusive(a1, v12);
        LOBYTE(a1) = 1;
        LOBYTE(v59) = 1;
      }
      if ( (*((_DWORD *)v29 + 1) & 0x2000000) != 0 )
      {
        *((_DWORD *)v28 - 19) &= ~0x2000000u;
        if ( (*((_DWORD *)v29 + 1) & 0x4000000) != 0 && !*((_DWORD *)v29 + 7) )
        {
          NtfsDeleteFcb(v6, v56, &v59);
          a1 = (unsigned __int8)v59;
        }
        break;
      }
    }
    if ( (_BYTE)a1 )
      NtfsReleaseFcbTable(a1, v12);
    NtfsReleaseVcb(v6, v12);
    v25 = v54;
  }
  v30 = 0;
  LOBYTE(v59) = 0;
  v31 = *(_QWORD *)(v6 + 144);
  if ( v6 == v31 || *(int *)(v31 + 24) < 0 )
    goto LABEL_109;
  if ( v4 == -1073741740 )
  {
    *(_DWORD *)(*(_QWORD *)(v6 + 144) + 24LL) = -1073741608;
    *(_DWORD *)(*(_QWORD *)(v6 + 144) + 4LL) |= 0x8000000u;
LABEL_109:
    v32 = v52;
    goto LABEL_110;
  }
  if ( (v4 & 0x80000000) == 0 )
    goto LABEL_109;
  if ( *(_BYTE *)(v6 + 32) != 4 || v4 != -1073741801 && v4 != -1073741670 && v4 != -1073741663 )
  {
    v32 = v52;
LABEL_125:
    *(_DWORD *)(v31 + 24) = v4;
    *(_DWORD *)(*(_QWORD *)(v6 + 144) + 4LL) |= 0x8000000u;
    goto LABEL_110;
  }
  v32 = v52;
  if ( (*(_DWORD *)(v52 + 16) & 2) == 0 || *(_DWORD *)(*(_QWORD *)(v52 + 184) + 8LL) <= 0x1000u )
    goto LABEL_125;
LABEL_110:
  if ( v4 != -1073741432 && v4 != -1073741608 && !(unsigned __int8)CcIsCacheManagerCallbackNeeded(v4) )
  {
LABEL_136:
    if ( v4 == -1073740761 && (*(_DWORD *)(v6 + 12) & 0x800) != 0 && *(_BYTE *)(v6 + 32) == 4 )
    {
      v4 = -1073741672;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225624LL, 1642044);
    }
    goto LABEL_159;
  }
  v33 = *(_BYTE *)(v6 + 32);
  if ( v33 == 2 )
  {
    v30 = 1;
    LOBYTE(v59) = 1;
    if ( (*(_DWORD *)(v6 + 4) & 0x800) != 0 )
    {
      v4 = 259;
      goto LABEL_159;
    }
    goto LABEL_136;
  }
  if ( v33 == 3
    && (v6 != *(_QWORD *)(v6 + 144) || !LOBYTE(IoGetTopLevelIrp()->Type) || (*(_DWORD *)(v32 + 16) & 2) != 0) )
  {
LABEL_135:
    v30 = 1;
    LOBYTE(v59) = 1;
    goto LABEL_136;
  }
  if ( v6 == *(_QWORD *)(v6 + 144) && LOBYTE(IoGetTopLevelIrp()->Type) && (*(_DWORD *)v25 & 0x400000) == 0 )
  {
    if ( (*(_DWORD *)(v6 + 4) & 0x800) != 0 )
    {
      StartContext = (PVOID)v6;
      goto LABEL_136;
    }
    goto LABEL_135;
  }
  if ( v4 == -1073741432 )
  {
    ++*(_DWORD *)(v12 + 4860);
    if ( *(_QWORD *)(v12 + 1336) == NtfsLarge0.QuadPart )
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)(v12 + 1336),
        *(_QWORD *)(v12 + 824),
        NtfsLarge0.QuadPart);
    if ( *(_QWORD *)(v6 + 144) == v6 && (*(_DWORD *)(v12 + 572) & 1) == 0 && (*(_DWORD *)(v6 + 4) & 0x80000) == 0 )
    {
      if ( (*(_DWORD *)(v6 + 12) & 0x800) != 0
        && *(_BYTE *)(v6 + 32) == 4
        && IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
      {
        v34 = (struct _IRP *)((__int64)IoGetTopLevelIrp()->AssociatedIrp.MasterIrp | 0x80000000LL);
        IoGetTopLevelIrp()->AssociatedIrp.MasterIrp = v34;
      }
      else
      {
        StartContext = 0;
        NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&StartContext);
        v35 = StartContext;
        if ( StartContext )
        {
          NtfsSetIrpContextVcb(StartContext, v12);
          v35[25] = *(_QWORD *)(v35[13] + 824LL);
          *((_DWORD *)v35 + 98) = *(_DWORD *)(v6 + 392);
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v12 + 576));
          v37 = *(_DWORD *)(v12 + 572);
          if ( (v37 & 1) != 0 )
          {
            NtfsCleanupIrpContext((__int64)v35, 0, v36);
            StartContext = 0;
          }
          else
          {
            *(_DWORD *)(v12 + 572) = v37 | 1;
          }
          KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v12 + 576));
        }
      }
    }
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225556LL, 1642025);
  v4 = -1073741740;
LABEL_159:
  v38 = StartContext;
  v39 = v52;
  if ( StartContext )
  {
    *((_DWORD *)StartContext + 6) = 0;
    v38[2] &= ~0x20000uLL;
    *((_DWORD *)v38 + 2) |= 2u;
    v40 = NtfsPostRequest(v38);
    if ( v38 == (_QWORD *)v6 )
    {
      v39 = 0;
      v6 = 0;
      v4 = v40;
    }
    v41 = v55;
  }
  else
  {
    v41 = v55;
  }
  if ( v30 )
  {
    *(_DWORD *)(v6 + 4) |= 0x400u;
    v39 = 0;
    *(_DWORD *)(v6 + 24) = 0;
  }
  else if ( v6 && ((*(_DWORD *)(v6 + 12) & 0x42) == 2 || v41) )
  {
    v39 = 0;
    goto LABEL_171;
  }
  if ( v39 )
  {
    if ( *(_BYTE *)(v6 + 32) == 4 && (*(_BYTE *)(v6 + 33) & 6) == 6 )
    {
      v42 = *(struct _MDL **)(v39 + 8);
      if ( v42 )
      {
        CcMdlWriteAbort(*(PFILE_OBJECT *)(*(_QWORD *)(v39 + 184) + 48LL), v42);
        *(_QWORD *)(v39 + 8) = 0;
      }
    }
  }
LABEL_171:
  if ( !v6 )
    goto LABEL_188;
  if ( (*(_DWORD *)(v6 + 4) & 0x400) == 0 && (*(_DWORD *)(v6 + 12) & 0x10000) == 0
    || v4 != -1073741608 && v4 != -1073741432 )
  {
    v43 = (_QWORD *)(v6 + 440);
    v44 = *(_QWORD **)(v6 + 440);
    if ( v44 )
    {
      while ( v44 != v43 )
      {
        v45 = (unsigned __int64)(v44 - 7);
        v59 = v45;
        v44 = (_QWORD *)*v44;
        if ( (*(_BYTE *)(v45 + 16) & 0xF) == 5 )
        {
          *(_DWORD *)(v45 + 16) = (unsigned __int8)*(_DWORD *)(v45 + 16);
          TxfRemoveTxfFcbCleanupStruct(v45, &v59, 0);
        }
      }
    }
  }
  v46 = *(_QWORD *)(v6 + 16);
  if ( (v46 & 1) == 0 || !v39 )
  {
LABEL_188:
    if ( NtfsStatusDebugFlags )
    {
      v47 = (v4 & 0x80000000) != 0;
      if ( !v4 )
      {
LABEL_200:
        LOBYTE(a4) = v39 != 0;
        NtfsExtendedCompleteRequestInternal(v6, v39, v4, a4, !v47);
        goto LABEL_201;
      }
      if ( v4 != 294
        && v4 - 298 > 1
        && v4 < 0xFFFFFFED
        && v4 != -1073741802
        && v4 + 2147483643 > 1
        && v4 != -1073741807
        && v4 != 259
        && v4 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(v6, v4, 1642272);
      }
    }
    v47 = (v4 & 0x80000000) != 0;
    goto LABEL_200;
  }
  *(_QWORD *)(v6 + 16) = v46 | 2;
LABEL_201:
  v48 = v58;
  if ( v58 )
  {
    *(_DWORD *)(v6 + 24) = v4;
    v4 = NtfsPostRepairRequest(v48, v41);
    if ( v4 != -1073741608 && (*(_DWORD *)(v6 + 12) & 0x42) != 2 )
    {
      v50 = *(_QWORD *)(v48 + 16);
      if ( (v50 & 1) != 0 && v41 )
      {
        *(_QWORD *)(v48 + 16) = v50 | 2;
      }
      else
      {
        if ( NtfsStatusDebugFlags
          && v4
          && v4 != 294
          && v4 - 298 > 1
          && v4 < 0xFFFFFFED
          && v4 != -1073741802
          && v4 + 2147483643 > 1
          && v4 != -1073741807
          && v4 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(v48, v4, 1642322);
        }
        LOBYTE(v49) = v41 != 0;
        NtfsExtendedCompleteRequestInternal(v48, v41, v4, v49, (v4 & 0x80000000) == 0);
      }
    }
  }
  return v4;
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
