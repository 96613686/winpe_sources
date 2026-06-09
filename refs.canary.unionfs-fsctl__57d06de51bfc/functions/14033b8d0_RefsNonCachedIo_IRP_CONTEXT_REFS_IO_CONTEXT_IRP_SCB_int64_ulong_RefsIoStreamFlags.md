# RefsNonCachedIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,__int64,ulong,RefsIoStreamFlags)

- ea: `0x14033b8d0`
- end: `0x14033c82b`
- name: `?RefsNonCachedIo@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@_JKW4RefsIoStreamFlags@@@Z`
- size: `3931`
- prototype: ``
- caller_count: `5`
- callee_count: `42`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003b3f0`
- `0x1400a7f90`
- `0x14028aa64`
- `0x140298ed4`
- `0x140299da8`

## callees

- `0x140008c10`
- `0x140009aa0`
- `0x14000bcc0`
- `0x14003d4cc`
- `0x140081670`
- `0x14008d800`
- `0x14008dbd0`
- `0x14008e280`
- `0x140099960`
- `0x140099ad0`
- `0x14009b060`
- `0x14009ce18`
- `0x14009f140`
- `0x1400a12b0`
- `0x1400a2410`
- `0x1400a2bf0`
- `0x1400a3da0`
- `0x1400ae14c`
- `0x1400af96c`
- `0x1400b9080`
- `0x1400ca788`
- `0x1400e2e8c`
- `0x1400e46d8`
- `0x1400ec738`
- `0x1400ef5c0`
- `0x1400ef788`
- `0x1400f92f4`
- `0x1401149fc`
- `0x140115aa4`
- `0x140115cf4`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x1402870ec`
- `0x1402903ac`
- `0x1402fec90`
- `0x140326790`
- `0x140326920`
- `0x1403283a0`
- `0x14032ead0`
- `0x140332868`
- `0x14033b490`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14033c4ea`
- `ntoskrnl!IofCompleteRequest` at `0x14033c600`
- `ntoskrnl!IofCompleteRequest` at `0x140343bfd`
- `ntoskrnl!IofCompleteRequest` at `0x14033c4ea`
- `ntoskrnl!IofCompleteRequest` at `0x14033c600`
- `ntoskrnl!IofCompleteRequest` at `0x140343bfd`
- `ntoskrnl!IoFreeIrp` at `0x140343a77`
- `ntoskrnl!IoFreeIrp` at `0x140343a77`
- `ntoskrnl!IoFreeMdl` at `0x140343a60`
- `ntoskrnl!IoFreeMdl` at `0x140343a60`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14033c216`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14033c216`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140343ac4`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140343ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343ae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343ae5`

## pseudocode

```c
__int64 __fastcall RefsNonCachedIo(
        __int64 a1,
        __int64 a2,
        struct _IRP *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v12; // r8
  _OWORD *v13; // rdi
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // r8
  char v18; // dl
  __int64 v19; // rdi
  unsigned int v20; // ecx
  unsigned int v21; // r8d
  int v22; // eax
  NTSTATUS *v23; // r14
  char v24; // r8
  __int16 v25; // ax
  unsigned int v26; // r8d
  _DWORD *v27; // rcx
  char v28; // r9
  struct _FCB_NONPAGED *Timer_high; // rcx
  unsigned int i; // edi
  __int64 v31; // rdx
  struct _IRP *v32; // r9
  __int64 v33; // r8
  int v34; // edx
  int v35; // eax
  NTSTATUS v36; // edi
  int v37; // edi
  struct CmsTransactionContext *v38; // rax
  int v39; // edi
  _DWORD *v40; // rdi
  unsigned int v41; // r9d
  int v42; // eax
  struct _IRP_CONTEXT *v43; // rcx
  unsigned int v44; // eax
  char v45; // r12
  __int64 v46; // rcx
  unsigned int v47; // r9d
  char v48; // bl
  struct _IRP_CONTEXT *v49; // rcx
  _DWORD *v50; // r13
  struct COMPRESSION_CONTEXT **v51; // r15
  unsigned int v53; // r8d
  unsigned int v54; // edi
  __int64 v55; // r10
  unsigned int v56; // r8d
  struct CmsTransactionContext *v57; // [rsp+10h] [rbp-100h]
  int v58; // [rsp+18h] [rbp-F8h]
  _OWORD v59[11]; // [rsp+50h] [rbp-C0h] BYREF
  __int128 v60; // [rsp+100h] [rbp-10h]
  char v61; // [rsp+110h] [rbp+0h]
  char v62; // [rsp+111h] [rbp+1h]
  char v63; // [rsp+112h] [rbp+2h]
  bool v64; // [rsp+113h] [rbp+3h]
  char v65; // [rsp+114h] [rbp+4h]
  unsigned int v66; // [rsp+118h] [rbp+8h] BYREF
  char v67; // [rsp+11Ch] [rbp+Ch]
  char v68; // [rsp+11Dh] [rbp+Dh]
  char v69; // [rsp+11Eh] [rbp+Eh]
  int v70; // [rsp+120h] [rbp+10h]
  _DWORD *v71; // [rsp+128h] [rbp+18h]
  struct _IRP_CONTEXT *v72; // [rsp+130h] [rbp+20h]
  __int64 v73; // [rsp+138h] [rbp+28h]
  char v74; // [rsp+140h] [rbp+30h]
  struct REFS_IO_CONTEXT *v75; // [rsp+148h] [rbp+38h]
  PIRP Irp; // [rsp+150h] [rbp+40h]
  unsigned int v77; // [rsp+158h] [rbp+48h]
  NTSTATUS v78; // [rsp+15Ch] [rbp+4Ch]
  struct COMPRESSION_CONTEXT **v79; // [rsp+168h] [rbp+58h]
  _DWORD *v80; // [rsp+170h] [rbp+60h]
  unsigned int **v81; // [rsp+178h] [rbp+68h]
  __int64 v82; // [rsp+180h] [rbp+70h]
  _DWORD *v83; // [rsp+188h] [rbp+78h]
  _QWORD v84[2]; // [rsp+190h] [rbp+80h] BYREF
  unsigned int v85; // [rsp+1A0h] [rbp+90h]
  __int64 v86; // [rsp+1A8h] [rbp+98h]
  IO_STATUS_BLOCK *p_IoStatus; // [rsp+1B0h] [rbp+A0h]
  char *v88; // [rsp+1B8h] [rbp+A8h]
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // [rsp+1C0h] [rbp+B0h]
  struct _IRP *v90; // [rsp+1C8h] [rbp+B8h]
  _OWORD v91[12]; // [rsp+1D0h] [rbp+C0h] BYREF
  _BYTE v92[256]; // [rsp+290h] [rbp+180h] BYREF

  v71 = (_DWORD *)a2;
  v86 = a2;
  v72 = (struct _IRP_CONTEXT *)a1;
  v75 = (struct REFS_IO_CONTEXT *)a2;
  v73 = a2;
  Irp = a3;
  v90 = a3;
  v84[1] = a4;
  v66 = 0;
  v70 = 0;
  v82 = *(_QWORD *)(*(_QWORD *)(a4 + 136) + 80LL);
  v80 = (_DWORD *)(*(_QWORD *)(v82 + 808)
                 + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
  memset(v92, 0, sizeof(v92));
  v13 = 0;
  v62 = 0;
  v68 = 0;
  v67 = 0;
  v65 = 0;
  v69 = 0;
  v78 = 0;
  v84[0] = 0;
  v61 = *(_BYTE *)(a1 + 8) & 1;
  v63 = v61;
  v83 = (_DWORD *)(a1 + 4);
  v64 = (*(_BYTE *)(a1 + 4) & 0x40) != 0;
  if ( *(_BYTE *)(a1 + 40) != 4 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 61;
      goto LABEL_6;
    }
LABEL_11:
    v16 = a5;
    goto LABEL_12;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_11;
  }
  v15 = 60;
LABEL_6:
  v16 = a5;
  WPP_SF_qiDq(v14->AttachedDevice, v15, v12, a4, a5, a6, a3);
LABEL_12:
  if ( (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(v82 + 112)) && _bittest16((const signed __int16 *)(a4 + 256), 0xDu) )
    *(_DWORD *)a2 |= 0x400000u;
  if ( (unsigned __int8)MsIsVolumeOnRemoteZones(*(_QWORD *)(v17 + 112))
    && _bittest16((const signed __int16 *)(a4 + 256), 9u) )
  {
    *(_DWORD *)a2 |= 0x800000u;
  }
  if ( v18 )
  {
    v13 = v59;
    memset(v91, 0, sizeof(v91));
    v59[0] = v91[0];
    v59[1] = v91[1];
    v59[2] = v91[2];
    v59[3] = v91[3];
    v59[4] = v91[4];
    v59[5] = v91[5];
    v59[6] = v91[6];
    v59[7] = v91[7];
    v59[8] = v91[8];
    v59[9] = v91[9];
    v59[10] = v91[10];
    v60 = v91[11];
    DWORD2(v60) = a7;
    v68 = 1;
    if ( RefsIsModifyingTransactionActive((struct _IRP_CONTEXT *)a1) )
      *(_DWORD *)a2 |= 1u;
  }
  v81 = (unsigned int **)(a2 + 144);
  *(_QWORD *)(a2 + 144) = v92;
  v79 = (struct COMPRESSION_CONTEXT **)(a2 + 848);
  *(_QWORD *)(a2 + 848) = v13;
  v19 = a2;
  *(_QWORD *)(a2 + 112) = -1;
  *(_QWORD *)(a2 + 120) = -1;
  v88 = (char *)(a2 + 844);
  *(_BYTE *)(a2 + 844) = 0;
  p_AssociatedIrp = &a3->AssociatedIrp;
  a3->AssociatedIrp.IrpCount = 0;
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 144) + 28LL) & 2) != 0 )
    RefsInsertDebugInfoIrpImplementation(
      (struct _IRP_CONTEXT *)a1,
      a3,
      0,
      *(struct _FCB **)(a4 + 136),
      0,
      0x72657355u,
      (unsigned __int64)v57);
  v20 = a7;
  if ( (a7 & 4) != 0
    || *(_BYTE *)(a1 + 40) != 4
    || (*(_WORD *)a4 != 2053 || !*(_QWORD *)(a4 + 432) || !*(_WORD *)(a4 + 260))
    && (!_bittest16((const signed __int16 *)(a4 + 256), 0xEu) || !*(_QWORD *)(a4 + 288) || *(int *)(a4 + 152) < 0) )
  {
    goto LABEL_38;
  }
  v21 = a6;
  if ( ((a6 | (unsigned int)v16) & *(_DWORD *)(v82 + 544)) == 0 )
    goto LABEL_39;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 16LL) & 2) != 0 && !*(_QWORD *)(a4 + 240) )
  {
    RefsAcquireEofLockForRead((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4);
    RefsCreateInternalAttributeStream((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4, 0, &stru_1401FFED0);
    RefsReleaseEofLock((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4);
    if ( !*(_DWORD *)(a4 + 160) && !*(_DWORD *)(*(_QWORD *)(a4 + 136) + 208LL) )
    {
      RefsAcquireExclusiveScb(a1, a4, 0);
      RefsAddScbToDelayedClose((struct _SCB *)a4);
      RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(a4 + 136));
    }
    v20 = a7;
LABEL_38:
    v21 = a6;
    goto LABEL_39;
  }
  v20 = a7;
LABEL_39:
  if ( *(_BYTE *)(a1 + 40) == 3 && _bittest64((const signed __int64 *)(a1 + 8), 0x27u) )
    v22 = 1073741877;
  else
    v22 = 0;
  v23 = (NTSTATUS *)&a3->IoStatus.0;
  p_IoStatus = &a3->IoStatus;
  a3->IoStatus.Status = v22;
  *(_QWORD *)(v19 + 72) = v16;
  *(_DWORD *)(v19 + 80) = v21;
  *(_QWORD *)(v19 + 96) = 0;
  *(_DWORD *)(v19 + 104) = v21;
  *(_QWORD *)(v19 + 84) = 0;
  v84[0] = v16;
  *(_DWORD *)a2 &= 0xFFC7FEFF;
  while ( 1 )
  {
    if ( !*(_DWORD *)(v19 + 80) )
    {
LABEL_129:
      v39 = *v23;
      goto LABEL_130;
    }
    v67 = 0;
    RefsPrepareBuffers(a1, a2, a3, a4, v20, &v66, v84);
    v62 = 1;
    if ( (a3->Flags & 2) != 0 )
    {
      v24 = *(_BYTE *)(a1 + 40);
      v25 = *(_WORD *)(a4 + 216);
      if ( (v25 == 128 || v25 == 176) && (*(_QWORD *)(*(_QWORD *)(a4 + 136) + 8LL) & 0x100LL) == 0 )
      {
        if ( v24 == 4 )
          v80[7] += v66;
        else
          v80[4] += v66;
      }
      else if ( v24 == 4 )
      {
        v80[13] += v66;
      }
      else
      {
        v80[10] += v66;
      }
    }
    LOBYTE(v26) = v61;
    v27 = v71;
    if ( !v61 && *(_DWORD *)(v19 + 80) && (*v71 & 0x40000) == 0 )
    {
      RefsPreProcessIo((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3, 1u);
      *(_DWORD *)a2 |= 0x40000u;
      v65 = v28;
      v27 = v71;
      LOBYTE(v26) = v61;
    }
    if ( v66 )
    {
      Timer_high = (struct _FCB_NONPAGED *)HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)Timer_high & 0x20) != 0 )
      {
        v77 = 0;
        for ( i = 0; ; ++i )
        {
          v77 = i;
          if ( i >= v66 )
            break;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v31 = (__int64)&(*v81)[8 * i];
            v32 = *(struct _IRP **)(v31 + 8);
            LODWORD(v33) = 0;
            if ( a3 != v32 )
              v33 = *(_QWORD *)(v31 + 8);
            WPP_SF_dqqqiqqDDiD(
              WPP_GLOBAL_Control->AttachedDevice,
              v31,
              v33,
              i,
              a4,
              (char)a3,
              v33,
              v58,
              (char)v32->MdlAddress,
              (char)v32->UserBuffer,
              *(_DWORD *)v31,
              *(_DWORD *)(v31 + 4),
              v32->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart,
              v32->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.Length);
          }
        }
        v19 = v73;
        LOBYTE(v26) = v61;
      }
      v34 = *(_DWORD *)(a1 + 720);
      if ( v34 > 0 )
      {
        v35 = RefsClaimDecompressWorkItem(Timer_high, v34);
        v36 = v35;
        v70 = v35;
        if ( v35 < 0 )
        {
          *(_DWORD *)(a1 + 720) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              63,
              WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
              (unsigned int)v35);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v36, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1CA7u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v36, v26);
LABEL_170:
          RefsIsTriagePending((struct _IRP_CONTEXT *)a1);
          v54 = (unsigned int)v71;
          if ( (*v71 & 0x400000) != 0
            && *(_BYTE *)(a1 + 40) == 4
            && (*v23 == -1073741391 || *v23 == -1073741435)
            && (unsigned __int8)MsIsWPOutOfSync(*(_QWORD *)(a1 + 24)) )
          {
            MsSetOkayToResyncSMRBands(v55);
            *v23 = -1073741608;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              66,
              WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
              (unsigned int)*v23);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(*v23, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1D86u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, *v23, v53);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, v54);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v54, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1E3Fu);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v54, v56);
          JUMPOUT(0x14033C82BLL);
        }
        v19 = v73;
        *(_DWORD *)(v73 + 152) += *(_DWORD *)(a1 + 720);
        *(_DWORD *)(a1 + 720) = 0;
      }
      if ( !(_BYTE)v26 && !*(_DWORD *)(v19 + 80) )
        RefsTransferNonCachedIoResourcesToCompletion(a1, a2, a3, a7);
      v37 = *(_DWORD *)(v19 + 80);
      v38 = *(struct CmsTransactionContext **)(a1 + 24);
      if ( !v38 )
        v38 = *(struct CmsTransactionContext **)(v73 + 856);
      RefsMultipleAsync(
        (struct _IRP_CONTEXT *)a1,
        (struct REFS_IO_CONTEXT *)a2,
        *(struct _DEVICE_OBJECT **)(v82 + 192),
        a3,
        v66,
        (struct IO_RUN *)*v81,
        v38);
      v67 = 1;
      if ( v61 )
      {
        RefsWaitOnIo((struct REFS_IO_CONTEXT *)a2);
        v40 = v71;
        if ( (int)(*v23 + 0x80000000) >= 0 && *v23 != -1073741608 && (*v71 & 0x400000) != 0 && *(_BYTE *)(a1 + 40) == 4 )
          MsSetWPOutOfSync(*(_QWORD *)(a1 + 24));
        if ( (*v40 & 0x4000) != 0 && (*v40 & 0x8000) != 0 && v66 == 1 )
        {
          v41 = **v81;
          if ( v41 )
          {
            RefsRestoreMdl((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3->MdlAddress, v41);
            v62 = 0;
          }
        }
      }
      else if ( !v37 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(259, 0, "DevIoSup.c", 0x1CDEu);
LABEL_88:
        v39 = 259;
        goto LABEL_130;
      }
      v19 = v73;
      goto LABEL_100;
    }
    if ( !*(_DWORD *)(v19 + 80) )
      break;
LABEL_100:
    if ( !v61 )
      goto LABEL_128;
    v27 = v71;
LABEL_102:
    if ( !*(_DWORD *)(v19 + 84) )
    {
      if ( (*v27 & 0x100) != 0 )
      {
        if ( *v23 < 0 )
          goto LABEL_170;
        v42 = RefsFinishBuffers((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3, (struct _SCB *)a4, *v79);
        if ( v42 < 0 )
          *v23 = v42;
      }
      if ( *v23 < 0 )
        goto LABEL_170;
      if ( !*(_DWORD *)(v19 + 80) )
        goto LABEL_129;
      if ( !v64 && (*v83 & 0x40) != 0 )
      {
        RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
        if ( *v79 )
          RefsDeallocateCompressionBuffer(v43, a3, *v79);
        RefsReleaseRangeLockIoContext((struct REFS_IO_CONTEXT *)a2);
        *v83 &= ~0x40u;
      }
      v44 = *v23;
      if ( v69 )
      {
        *v23 = v78;
        IoSetMasterIrpStatus(a3, v44);
      }
      else
      {
        v69 = 1;
        v74 = 1;
        v78 = v44;
        v85 = v44;
      }
      *(_DWORD *)a2 &= 0xFFC7FEFF;
    }
LABEL_128:
    v20 = a7;
  }
  if ( (*v27 & 0x40000) == 0 )
  {
    v61 = 1;
    v63 = 1;
    goto LABEL_102;
  }
  RefsTransferNonCachedIoResourcesToCompletion(a1, a2, a3, a7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 259);
  }
  if ( !(_BYTE)RefsStatusDebugEnabled )
    goto LABEL_88;
  RefsStatusDebug(259, 0, "DevIoSup.c", 0x1D17u);
  v39 = 259;
LABEL_130:
  v70 = v39;
  v45 = v61;
  v46 = 0x4000;
  if ( v62 )
  {
    if ( v61 )
    {
      if ( v66 == 1 && (*v71 & 0x8000) != 0 && (*v71 & 0x4000) != 0 )
      {
        v47 = **v81;
        if ( v47 )
          RefsRestoreMdl((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3->MdlAddress, v47);
      }
    }
  }
  if ( v39 == 259 )
  {
    v48 = 0;
    if ( v65 )
    {
      *(_DWORD *)a2 &= ~0x40000u;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)p_AssociatedIrp, 0xFFFFFFFF) == 1 )
        IofCompleteRequest(a3, 1);
    }
  }
  else
  {
    v48 = *v88;
    if ( *v79 )
    {
      MsFreeChecksumContext(v46, (char *)*v79 + 160);
      RefsDeallocateCompressionBuffer(v49, a3, *v79);
    }
    if ( !v64 )
    {
      v50 = v83;
      if ( (*v83 & 0x40) != 0 )
      {
        if ( *(_QWORD *)(v73 + 816) )
        {
          RefsReleaseRangeLockIoContext((struct REFS_IO_CONTEXT *)a2);
          *v50 &= ~0x40u;
        }
      }
    }
    v51 = v79;
    if ( *v79 )
    {
      RefsReleasePrequel(*v79);
      RefsReleaseSequel(*v51);
      if ( !v68 )
        RefsFreeNPagedPerProcessorLookaside(RefsCompressCtxLookasideList, *v51);
    }
  }
  if ( v45 && v39 >= 0 )
  {
    if ( v48 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        v39 = 303;
      }
      else
      {
        v39 = 303;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 303);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(303, 0, "DevIoSup.c", 0x1EE4u);
      *v23 = 303;
    }
    v90->IoStatus.Information = a6;
  }
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x14033b8d0  push    rbp
0x14033b8d2  push    rbx
0x14033b8d3  push    rsi
0x14033b8d4  push    rdi
0x14033b8d5  push    r12
0x14033b8d7  push    r13
0x14033b8d9  push    r14
0x14033b8db  push    r15
0x14033b8dd  sub     rsp, 308h
0x14033b8e4  lea     rbp, [rsp+70h]
0x14033b8e9  mov     rax, cs:__security_cookie
0x14033b8f0  xor     rax, rbp
0x14033b8f3  mov     [rbp+2D0h+var_50], rax
0x14033b8fa  mov     r12, r9
0x14033b8fd  mov     r13, r8
0x14033b900  mov     [rbp+2D0h+var_2B8], rdx
0x14033b904  mov     rbx, rcx
0x14033b907  mov     [rbp+2D0h+var_238], rdx
0x14033b90e  mov     [rbp+2D0h+var_2B0], rcx
0x14033b912  mov     r15, rdx
0x14033b915  mov     [rbp+2D0h+var_298], rdx
0x14033b919  mov     r14, rdx
0x14033b91c  mov     [rbp+2D0h+var_2A8], rdx
0x14033b920  mov     [rbp+2D0h+Irp], r8
0x14033b924  mov     [rbp+2D0h+var_218], r8
0x14033b92b  mov     [rbp+2D0h+var_248], r9
0x14033b932  xor     esi, esi
0x14033b934  mov     [rbp+2D0h+var_2C8], esi
0x14033b937  mov     [rbp+2D0h+var_2C0], esi
0x14033b93a  mov     rax, [r9+88h]
0x14033b941  mov     rcx, [rax+50h]
0x14033b945  mov     [rbp+2D0h+var_260], rcx
0x14033b949  mov     al, gs:184h
0x14033b951  movzx   eax, al
0x14033b954  xor     edx, edx
0x14033b956  div     cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14033b95c  mov     eax, edx
0x14033b95e  shl     rax, 6
0x14033b962  add     rax, [rcx+328h]
0x14033b969  mov     [rbp+2D0h+var_270], rax
0x14033b96d  xor     edx, edx; Val
0x14033b96f  mov     r8d, 100h; Size
0x14033b975  lea     rcx, [rbp+2D0h+var_150]; void *
0x14033b97c  call    memset
0x14033b981  mov     edi, esi
0x14033b983  xor     dl, dl
0x14033b985  mov     [rbp+2D0h+var_2CF], dl
0x14033b988  mov     [rbp+2D0h+var_2C3], dl
0x14033b98b  mov     [rbp+2D0h+var_2C4], dl
0x14033b98e  xor     al, al
0x14033b990  mov     [rbp+2D0h+var_2CC], al
0x14033b993  mov     [rbp+2D0h+var_2C2], al
0x14033b996  mov     [rbp+2D0h+var_284], esi
0x14033b999  mov     [rbp+2D0h+var_250], rsi
0x14033b9a0  movzx   edx, byte ptr [rbx+8]
0x14033b9a4  and     dl, 1
0x14033b9a7  mov     [rbp+2D0h+var_2D0], dl
0x14033b9aa  mov     [rbp+2D0h+var_2CE], dl
0x14033b9ad  lea     rax, [rbx+4]
0x14033b9b1  mov     [rbp+2D0h+var_258], rax
0x14033b9b5  movzx   eax, byte ptr [rax]
0x14033b9b8  shr     al, 6
0x14033b9bb  and     al, 1
0x14033b9bd  mov     [rbp+2D0h+var_2CD], al
0x14033b9c0  cmp     byte ptr [rbx+28h], 4
0x14033b9c4  jnz     short loc_14033BA18
0x14033b9c6  lea     rax, WPP_GLOBAL_Control
0x14033b9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14033b9d4  cmp     rcx, rax
0x14033b9d7  jz      short loc_14033BA3F
0x14033b9d9  mov     eax, [rcx+2Ch]
0x14033b9dc  test    al, 10h
0x14033b9de  jz      short loc_14033BA3F
0x14033b9e0  cmp     byte ptr [rcx+29h], 2
0x14033b9e4  jb      short loc_14033BA3F
0x14033b9e6  mov     edx, 3Ch ; '<'
0x14033b9eb  mov     [rsp+340h+var_310], r13
0x14033b9f0  mov     eax, [rbp+2D0h+arg_28]
0x14033b9f6  mov     [rsp+340h+var_318], eax
0x14033b9fa  mov     rsi, [rbp+2D0h+arg_20]
0x14033ba01  mov     [rsp+340h+var_320], rsi
0x14033ba06  mov     r9, r12
0x14033ba09  mov     rcx, [rcx+18h]
0x14033ba0d  call    WPP_SF_qiDq
0x14033ba12  movzx   edx, [rbp+2D0h+var_2D0]
0x14033ba16  jmp     short loc_14033BA46
0x14033ba18  lea     rax, WPP_GLOBAL_Control
0x14033ba1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14033ba26  cmp     rcx, rax
0x14033ba29  jz      short loc_14033BA3F
0x14033ba2b  mov     eax, [rcx+2Ch]
0x14033ba2e  test    al, 8
0x14033ba30  jz      short loc_14033BA3F
0x14033ba32  cmp     byte ptr [rcx+29h], 2
0x14033ba36  jb      short loc_14033BA3F
0x14033ba38  mov     edx, 3Dh ; '='
0x14033ba3d  jmp     short loc_14033B9EB
0x14033ba3f  mov     rsi, [rbp+2D0h+arg_20]
0x14033ba46  mov     r8, [rbp+2D0h+var_260]
0x14033ba4a  mov     rcx, [r8+70h]
0x14033ba4e  call    MsIsVolumeOnSmr
0x14033ba53  test    al, al
0x14033ba55  jz      short loc_14033BA6B
0x14033ba57  bt      word ptr [r12+100h], 0Dh
0x14033ba62  jnb     short loc_14033BA6B
0x14033ba64  or      dword ptr [r15], 400000h
0x14033ba6b  mov     rcx, [r8+70h]
0x14033ba6f  call    MsIsVolumeOnRemoteZones
0x14033ba74  test    al, al
0x14033ba76  jz      short loc_14033BA8C
0x14033ba78  bt      word ptr [r12+100h], 9
0x14033ba83  jnb     short loc_14033BA8C
0x14033ba85  or      dword ptr [r15], 800000h
0x14033ba8c  test    dl, dl
0x14033ba8e  jz      loc_14033BB6A
0x14033ba94  mov     eax, [rsp+340h+var_340]
0x14033ba97  sub     rsp, 0C0h
0x14033ba9e  lea     rdi, [rsp+400h+var_390]
0x14033baa3  mov     eax, [rdi]
0x14033baa5  xor     edx, edx; Val
0x14033baa7  mov     r8d, 0C0h; Size
0x14033baad  lea     rcx, [rbp+2D0h+var_210]; void *
0x14033bab4  call    memset
0x14033bab9  movups  xmm0, [rbp+2D0h+var_210]
0x14033bac0  movups  xmmword ptr [rdi], xmm0
0x14033bac3  movups  xmm1, [rbp+2D0h+var_200]
0x14033baca  movups  xmmword ptr [rdi+10h], xmm1
0x14033bace  movups  xmm0, [rbp+2D0h+var_1F0]
0x14033bad5  movups  xmmword ptr [rdi+20h], xmm0
0x14033bad9  movups  xmm1, [rbp+2D0h+var_1E0]
0x14033bae0  movups  xmmword ptr [rdi+30h], xmm1
0x14033bae4  movups  xmm0, [rbp+2D0h+var_1D0]
0x14033baeb  movups  xmmword ptr [rdi+40h], xmm0
0x14033baef  movups  xmm1, [rbp+2D0h+var_1C0]
0x14033baf6  movups  xmmword ptr [rdi+50h], xmm1
0x14033bafa  movups  xmm0, [rbp+2D0h+var_1B0]
0x14033bb01  movups  xmmword ptr [rdi+60h], xmm0
0x14033bb05  movups  xmm1, [rbp+2D0h+var_1A0]
0x14033bb0c  movups  xmmword ptr [rdi+70h], xmm1
0x14033bb10  movups  xmm0, [rbp+2D0h+var_190]
0x14033bb17  movups  xmmword ptr [rdi+80h], xmm0
0x14033bb1e  movups  xmm1, [rbp+2D0h+var_180]
0x14033bb25  movups  xmmword ptr [rdi+90h], xmm1
0x14033bb2c  movups  xmm0, [rbp+2D0h+var_170]
0x14033bb33  movups  xmmword ptr [rdi+0A0h], xmm0
0x14033bb3a  movups  xmm1, [rbp+2D0h+var_160]
0x14033bb41  movups  xmmword ptr [rdi+0B0h], xmm1
0x14033bb48  mov     r9d, [rbp+2D0h+arg_30]
0x14033bb4f  mov     [rdi+0B8h], r9d
0x14033bb56  mov     [rbp+2D0h+var_2C3], 1
0x14033bb5a  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bb5d  call    ?RefsIsModifyingTransactionActive@@YAEPEAU_IRP_CONTEXT@@@Z; RefsIsModifyingTransactionActive(_IRP_CONTEXT *)
0x14033bb62  test    al, al
0x14033bb64  jz      short loc_14033BB6A
0x14033bb66  or      dword ptr [r15], 1
0x14033bb6a  lea     rax, [r14+90h]
0x14033bb71  mov     [rbp+2D0h+var_268], rax
0x14033bb75  lea     rcx, [rbp+2D0h+var_150]
0x14033bb7c  mov     [rax], rcx
0x14033bb7f  lea     rax, [r14+350h]
0x14033bb86  mov     [rbp+2D0h+var_278], rax
0x14033bb8a  mov     [rax], rdi
0x14033bb8d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14033bb94  mov     rdi, r14
0x14033bb97  mov     [r14+70h], rax
0x14033bb9b  mov     [r14+78h], rax
0x14033bb9f  lea     rax, [r14+34Ch]
0x14033bba6  mov     [rbp+2D0h+var_228], rax
0x14033bbad  mov     byte ptr [rax], 0
0x14033bbb0  lea     rax, [r13+18h]
0x14033bbb4  mov     [rbp+2D0h+var_220], rax
0x14033bbbb  xor     edx, edx
0x14033bbbd  mov     [rax], edx
0x14033bbbf  mov     rax, [r12+90h]
0x14033bbc7  mov     ecx, [rax+1Ch]
0x14033bbca  test    cl, 2
0x14033bbcd  jz      short loc_14033BBF4
0x14033bbcf  mov     [rsp+400h+var_3D8], 72657355h; unsigned __int64
0x14033bbd8  mov     [rsp+400h+var_3E0], rdx; union SmsBigIdentifier *
0x14033bbdd  mov     r9, [r12+88h]; struct _FCB *
0x14033bbe5  xor     r8d, r8d; unsigned __int8
0x14033bbe8  mov     rdx, r13; struct _IRP *
0x14033bbeb  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bbee  call    ?RefsInsertDebugInfoIrpImplementation@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EPEAU_FCB@@PEBTSmsBigIdentifier@@_K4@Z; RefsInsertDebugInfoIrpImplementation(_IRP_CONTEXT *,_IRP *,uchar,_FCB *,SmsBigIdentifier const *,unsigned __int64,unsigned __int64)
0x14033bbf3  nop
0x14033bbf4  mov     ecx, [rbp+2D0h+arg_30]
0x14033bbfa  bt      ecx, 2
0x14033bbfe  jb      loc_14033BD10
0x14033bc04  cmp     byte ptr [rbx+28h], 4
0x14033bc08  jnz     loc_14033BD10
0x14033bc0e  mov     eax, 805h
0x14033bc13  cmp     [r12], ax
0x14033bc18  jnz     short loc_14033BC31
0x14033bc1a  cmp     qword ptr [r12+1B0h], 0
0x14033bc23  jz      short loc_14033BC31
0x14033bc25  cmp     word ptr [r12+104h], 0
0x14033bc2f  jnz     short loc_14033BC60
0x14033bc31  bt      word ptr [r12+100h], 0Eh
0x14033bc3c  jnb     loc_14033BD10
0x14033bc42  cmp     qword ptr [r12+120h], 0
0x14033bc4b  jz      loc_14033BD10
0x14033bc51  cmp     dword ptr [r12+98h], 0
0x14033bc5a  jl      loc_14033BD10
0x14033bc60  mov     eax, esi
0x14033bc62  mov     r8d, [rbp+2D0h+arg_28]
0x14033bc69  or      eax, r8d
0x14033bc6c  mov     rdx, [rbp+2D0h+var_260]
0x14033bc70  test    [rdx+220h], eax
0x14033bc76  jz      loc_14033BD17
0x14033bc7c  mov     rax, [rbx+48h]
0x14033bc80  mov     ecx, [rax+10h]
0x14033bc83  test    cl, 2
0x14033bc86  jz      loc_14033BD2E
0x14033bc8c  cmp     qword ptr [r12+0F0h], 0
0x14033bc95  jnz     loc_14033BD2E
0x14033bc9b  mov     rdx, r12; struct _SCB *
0x14033bc9e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bca1  call    ?RefsAcquireEofLockForRead@@YAXAEAU_IRP_CONTEXT@@AEAU_SCB@@@Z; RefsAcquireEofLockForRead(_IRP_CONTEXT &,_SCB &)
0x14033bca6  nop
0x14033bca7  lea     r9, stru_1401FFED0; struct _UNICODE_STRING *
0x14033bcae  xor     r8d, r8d; unsigned __int8
0x14033bcb1  mov     rdx, r12; struct _SCB *
0x14033bcb4  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bcb7  call    ?RefsCreateInternalAttributeStream@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@EPEBU_UNICODE_STRING@@@Z; RefsCreateInternalAttributeStream(_IRP_CONTEXT *,_SCB *,uchar,_UNICODE_STRING const *)
0x14033bcbc  nop
0x14033bcbd  mov     rdx, r12; struct _SCB *
0x14033bcc0  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bcc3  call    ?RefsReleaseEofLock@@YAXAEAU_IRP_CONTEXT@@AEAU_SCB@@@Z; RefsReleaseEofLock(_IRP_CONTEXT &,_SCB &)
0x14033bcc8  cmp     dword ptr [r12+0A0h], 0
0x14033bcd1  jnz     short loc_14033BD0A
0x14033bcd3  mov     rax, [r12+88h]
0x14033bcdb  cmp     dword ptr [rax+0D0h], 0
0x14033bce2  jnz     short loc_14033BD0A
0x14033bce4  xor     r8d, r8d
0x14033bce7  mov     rdx, r12
0x14033bcea  mov     rcx, rbx
0x14033bced  call    ?RefsAcquireExclusiveScb@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveScb(_IRP_CONTEXT *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033bcf2  mov     rcx, r12; struct _SCB *
0x14033bcf5  call    ?RefsAddScbToDelayedClose@@YAXAEAU_SCB@@@Z; RefsAddScbToDelayedClose(_SCB &)
0x14033bcfa  mov     rdx, [r12+88h]; struct _FCB *
0x14033bd02  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033bd05  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x14033bd0a  mov     ecx, [rbp+2D0h+arg_30]
0x14033bd10  mov     r8d, [rbp+2D0h+arg_28]
0x14033bd17  cmp     byte ptr [rbx+28h], 3
0x14033bd1b  jnz     short loc_14033BD36
0x14033bd1d  bt      qword ptr [rbx+8], 27h ; '''
0x14033bd23  jnb     short loc_14033BD36
0x14033bd25  mov     eax, 40000035h
0x14033bd2a  xor     edx, edx
0x14033bd2c  jmp     short loc_14033BD3A
0x14033bd2e  mov     ecx, [rbp+2D0h+arg_30]
0x14033bd34  jmp     short loc_14033BD17
0x14033bd36  xor     edx, edx
0x14033bd38  mov     eax, edx
0x14033bd3a  lea     r14, [r13+30h]
0x14033bd3e  mov     [rbp+2D0h+var_230], r14
0x14033bd45  mov     [r14], eax
0x14033bd48  mov     [rdi+48h], rsi
0x14033bd4c  mov     [rdi+50h], r8d
0x14033bd50  mov     [rdi+60h], rdx
0x14033bd54  mov     [rdi+68h], r8d
0x14033bd58  mov     qword ptr [rdi+54h], 0
0x14033bd60  mov     [rbp+2D0h+var_250], rsi
0x14033bd67  and     dword ptr [r15], 0FFC7FEFFh
0x14033bd6e  lea     rsi, WPP_GLOBAL_Control
0x14033bd75  cmp     dword ptr [rdi+50h], 0
0x14033bd79  jbe     loc_14033C247
0x14033bd7f  mov     [rbp+2D0h+var_2C4], 0
0x14033bd83  lea     rax, [rbp+2D0h+var_250]
0x14033bd8a  mov     [rsp+400h+var_3D0], rax
0x14033bd8f  lea     rax, [rbp+2D0h+var_2C8]
0x14033bd93  mov     [rsp+400h+var_3D8], rax
0x14033bd98  mov     dword ptr [rsp+400h+var_3E0], ecx
0x14033bd9c  mov     r9, r12
0x14033bd9f  mov     r8, r13
0x14033bda2  mov     rdx, r15
0x14033bda5  mov     rcx, rbx
0x14033bda8  call    ?RefsPrepareBuffers@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@W4RefsIoStreamFlags@@PEAKPEA_J@Z; RefsPrepareBuffers(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,RefsIoStreamFlags,ulong *,__int64 *)
0x14033bdad  mov     [rbp+2D0h+var_2CF], 1
0x14033bdb1  mov     eax, [r13+10h]
0x14033bdb5  test    al, 2
0x14033bdb7  jz      short loc_14033BE33
0x14033bdb9  mov     edx, [rbp+2D0h+var_2C8]
0x14033bdbc  movzx   r8d, byte ptr [rbx+28h]
0x14033bdc1  movzx   eax, word ptr [r12+0D8h]
0x14033bdca  mov     ecx, 80h
0x14033bdcf  cmp     ax, cx
0x14033bdd2  jz      short loc_14033BDDE
0x14033bdd4  mov     ecx, 0B0h
0x14033bdd9  cmp     ax, cx
0x14033bddc  jnz     short loc_14033BDF1
0x14033bdde  mov     rax, [r12+88h]
0x14033bde6  mov     rcx, [rax+8]
0x14033bdea  bt      rcx, 8
0x14033bdef  jnb     short loc_14033BE13
0x14033bdf1  cmp     r8b, 4
0x14033bdf5  mov     r8, [rbp+2D0h+var_270]
0x14033bdf9  jnz     short loc_14033BE07
0x14033bdfb  mov     ecx, [r8+34h]
  ... truncated ...
```
