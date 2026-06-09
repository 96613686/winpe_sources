# RefsNonCachedIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,__int64,ulong,RefsIoStreamFlags)

- ea: `0x14033e290`
- end: `0x14033f1ca`
- name: `?RefsNonCachedIo@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@_JKW4RefsIoStreamFlags@@@Z`
- size: `3898`
- prototype: ``
- caller_count: `5`
- callee_count: `41`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a2c60`
- `0x1400ba4d0`
- `0x140291a00`
- `0x14029fc3c`
- `0x1402a0b10`

## callees

- `0x140009ecc`
- `0x140035da0`
- `0x140037820`
- `0x140076ad0`
- `0x140085ef0`
- `0x1400862c0`
- `0x140087380`
- `0x140093bc0`
- `0x140093c70`
- `0x140095370`
- `0x1400961f0`
- `0x1400983c8`
- `0x140099d90`
- `0x14009c360`
- `0x14009d180`
- `0x14009d350`
- `0x14009e670`
- `0x1400ab7ac`
- `0x1400b6480`
- `0x1400d0fd8`
- `0x1400e7edc`
- `0x1400e9728`
- `0x1400f1788`
- `0x1400f48d4`
- `0x1400f4a9c`
- `0x1400fe1b4`
- `0x140119e5c`
- `0x14011afec`
- `0x14011b214`
- `0x1401f3fb0`
- `0x1401f4400`
- `0x14028e0ec`
- `0x140297340`
- `0x140302e10`
- `0x140329b10`
- `0x140329ca0`
- `0x14032b300`
- `0x14032fac0`
- `0x140334528`
- `0x14033de50`
- `0x14033e290`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14033ee89`
- `ntoskrnl!IofCompleteRequest` at `0x14033ef9f`
- `ntoskrnl!IofCompleteRequest` at `0x140346aed`
- `ntoskrnl!IofCompleteRequest` at `0x14033ee89`
- `ntoskrnl!IofCompleteRequest` at `0x14033ef9f`
- `ntoskrnl!IofCompleteRequest` at `0x140346aed`
- `ntoskrnl!IoFreeIrp` at `0x140346967`
- `ntoskrnl!IoFreeIrp` at `0x140346967`
- `ntoskrnl!IoFreeMdl` at `0x140346950`
- `ntoskrnl!IoFreeMdl` at `0x140346950`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14033ebb5`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14033ebb5`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1403469b4`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1403469b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403469d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403469d5`

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
  char v17; // dl
  __int64 v18; // rdi
  unsigned __int64 v19; // rcx
  unsigned int v20; // r8d
  int v21; // eax
  NTSTATUS *v22; // r14
  char v23; // r8
  __int16 v24; // ax
  unsigned int v25; // r8d
  char v26; // r9
  struct _FCB_NONPAGED *Timer_high; // rcx
  unsigned int i; // edi
  __int64 v29; // rdx
  struct _IRP *v30; // r9
  __int64 v31; // r8
  int v32; // edx
  int v33; // eax
  NTSTATUS v34; // edi
  int v35; // edi
  struct CmsTransactionContext *v36; // rax
  int v37; // edi
  struct _DEVICE_OBJECT *v38; // rdi
  unsigned int v39; // r9d
  int v40; // eax
  struct _IRP_CONTEXT *v41; // rcx
  unsigned int v42; // eax
  char v43; // r12
  unsigned int v44; // r9d
  char v45; // bl
  struct _IRP_CONTEXT *v46; // rcx
  _DWORD *v47; // r13
  struct COMPRESSION_CONTEXT **v48; // r15
  unsigned int v50; // r8d
  unsigned int v51; // edi
  __int64 v52; // r10
  unsigned int v53; // r8d
  struct CmsTransactionContext *v54; // [rsp+10h] [rbp-100h]
  int v55; // [rsp+18h] [rbp-F8h]
  _OWORD v56[11]; // [rsp+50h] [rbp-C0h] BYREF
  __int128 v57; // [rsp+100h] [rbp-10h]
  char v58; // [rsp+110h] [rbp+0h]
  char v59; // [rsp+111h] [rbp+1h]
  char v60; // [rsp+112h] [rbp+2h]
  bool v61; // [rsp+113h] [rbp+3h]
  char v62; // [rsp+114h] [rbp+4h]
  unsigned int v63; // [rsp+118h] [rbp+8h] BYREF
  char v64; // [rsp+11Ch] [rbp+Ch]
  char v65; // [rsp+11Dh] [rbp+Dh]
  char v66; // [rsp+11Eh] [rbp+Eh]
  int v67; // [rsp+120h] [rbp+10h]
  struct _DEVICE_OBJECT *v68; // [rsp+128h] [rbp+18h]
  struct _IRP_CONTEXT *v69; // [rsp+130h] [rbp+20h]
  __int64 v70; // [rsp+138h] [rbp+28h]
  char v71; // [rsp+140h] [rbp+30h]
  struct REFS_IO_CONTEXT *v72; // [rsp+148h] [rbp+38h]
  PIRP Irp; // [rsp+150h] [rbp+40h]
  unsigned int v74; // [rsp+158h] [rbp+48h]
  NTSTATUS v75; // [rsp+15Ch] [rbp+4Ch]
  struct COMPRESSION_CONTEXT **v76; // [rsp+168h] [rbp+58h]
  _DWORD *v77; // [rsp+170h] [rbp+60h]
  unsigned int **v78; // [rsp+178h] [rbp+68h]
  __int64 v79; // [rsp+180h] [rbp+70h]
  _DWORD *v80; // [rsp+188h] [rbp+78h]
  _QWORD v81[2]; // [rsp+190h] [rbp+80h] BYREF
  unsigned int v82; // [rsp+1A0h] [rbp+90h]
  __int64 v83; // [rsp+1A8h] [rbp+98h]
  IO_STATUS_BLOCK *p_IoStatus; // [rsp+1B0h] [rbp+A0h]
  char *v85; // [rsp+1B8h] [rbp+A8h]
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // [rsp+1C0h] [rbp+B0h]
  struct _IRP *v87; // [rsp+1C8h] [rbp+B8h]
  _OWORD v88[12]; // [rsp+1D0h] [rbp+C0h] BYREF
  _BYTE v89[256]; // [rsp+290h] [rbp+180h] BYREF

  v68 = (struct _DEVICE_OBJECT *)a2;
  v83 = a2;
  v69 = (struct _IRP_CONTEXT *)a1;
  v72 = (struct REFS_IO_CONTEXT *)a2;
  v70 = a2;
  Irp = a3;
  v87 = a3;
  v81[1] = a4;
  v63 = 0;
  v67 = 0;
  v79 = *(_QWORD *)(*(_QWORD *)(a4 + 136) + 80LL);
  v77 = (_DWORD *)(*(_QWORD *)(v79 + 808)
                 + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
  memset(v89, 0, sizeof(v89));
  v13 = 0;
  v59 = 0;
  v65 = 0;
  v64 = 0;
  v62 = 0;
  v66 = 0;
  v75 = 0;
  v81[0] = 0;
  v58 = *(_BYTE *)(a1 + 8) & 1;
  v60 = v58;
  v80 = (_DWORD *)(a1 + 4);
  v61 = (*(_BYTE *)(a1 + 4) & 0x40) != 0;
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
  if ( (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(v79 + 112)) && _bittest16((const signed __int16 *)(a4 + 256), 0xDu) )
    *(_DWORD *)a2 |= 0x400000u;
  if ( v17 )
  {
    v13 = v56;
    memset(v88, 0, sizeof(v88));
    v56[0] = v88[0];
    v56[1] = v88[1];
    v56[2] = v88[2];
    v56[3] = v88[3];
    v56[4] = v88[4];
    v56[5] = v88[5];
    v56[6] = v88[6];
    v56[7] = v88[7];
    v56[8] = v88[8];
    v56[9] = v88[9];
    v56[10] = v88[10];
    v57 = v88[11];
    DWORD2(v57) = a7;
    v65 = 1;
    if ( RefsIsModifyingTransactionActive((struct _IRP_CONTEXT *)a1) )
      *(_DWORD *)a2 |= 1u;
  }
  v78 = (unsigned int **)(a2 + 144);
  *(_QWORD *)(a2 + 144) = v89;
  v76 = (struct COMPRESSION_CONTEXT **)(a2 + 848);
  *(_QWORD *)(a2 + 848) = v13;
  v18 = a2;
  *(_QWORD *)(a2 + 112) = -1;
  *(_QWORD *)(a2 + 120) = -1;
  v85 = (char *)(a2 + 844);
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
      (unsigned __int64)v54);
  v19 = a7;
  if ( (a7 & 4) != 0
    || *(_BYTE *)(a1 + 40) != 4
    || (*(_WORD *)a4 != 2053 || !*(_QWORD *)(a4 + 432) || !*(_WORD *)(a4 + 260))
    && (!_bittest16((const signed __int16 *)(a4 + 256), 0xEu) || !*(_QWORD *)(a4 + 288) || *(int *)(a4 + 152) < 0) )
  {
    goto LABEL_35;
  }
  v20 = a6;
  if ( ((a6 | (unsigned int)v16) & *(_DWORD *)(v79 + 544)) == 0 )
    goto LABEL_36;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 16LL) & 2) != 0 && !*(_QWORD *)(a4 + 240) )
  {
    RefsAcquireEofLockForRead((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4);
    RefsCreateInternalAttributeStream((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4, 0, &stru_140206ED0);
    RefsReleaseEofLock((struct _IRP_CONTEXT *)a1, (struct _SCB *)a4);
    if ( !*(_DWORD *)(a4 + 160) && !*(_DWORD *)(*(_QWORD *)(a4 + 136) + 208LL) )
    {
      RefsAcquireExclusiveScb(a1, a4, 0);
      RefsAddScbToDelayedClose((struct _SCB *)a4);
      RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(a4 + 136));
    }
    v19 = a7;
LABEL_35:
    v20 = a6;
    goto LABEL_36;
  }
  v19 = a7;
LABEL_36:
  if ( *(_BYTE *)(a1 + 40) == 3 && _bittest64((const signed __int64 *)(a1 + 8), 0x27u) )
    v21 = 1073741877;
  else
    v21 = 0;
  v22 = (NTSTATUS *)&a3->IoStatus.0;
  p_IoStatus = &a3->IoStatus;
  a3->IoStatus.Status = v21;
  *(_QWORD *)(v18 + 72) = v16;
  *(_DWORD *)(v18 + 80) = v20;
  *(_QWORD *)(v18 + 96) = 0;
  *(_DWORD *)(v18 + 104) = v20;
  *(_QWORD *)(v18 + 84) = 0;
  v81[0] = v16;
  *(_DWORD *)a2 &= 0xFFC7FEFF;
  while ( 1 )
  {
    if ( !*(_DWORD *)(v18 + 80) )
    {
LABEL_126:
      v37 = *v22;
      goto LABEL_127;
    }
    v64 = 0;
    RefsPrepareBuffers(a1, a2, a3, a4, v19, &v63, v81);
    v59 = 1;
    if ( (a3->Flags & 2) != 0 )
    {
      v23 = *(_BYTE *)(a1 + 40);
      v24 = *(_WORD *)(a4 + 216);
      if ( (v24 == 128 || v24 == 176) && (*(_QWORD *)(*(_QWORD *)(a4 + 136) + 8LL) & 0x100LL) == 0 )
      {
        if ( v23 == 4 )
          v77[7] += v63;
        else
          v77[4] += v63;
      }
      else if ( v23 == 4 )
      {
        v77[13] += v63;
      }
      else
      {
        v77[10] += v63;
      }
    }
    LOBYTE(v25) = v58;
    v19 = (unsigned __int64)v68;
    if ( !v58 && *(_DWORD *)(v18 + 80) && (*(_DWORD *)&v68->Type & 0x40000) == 0 )
    {
      RefsPreProcessIo((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3, 1u);
      *(_DWORD *)a2 |= 0x40000u;
      v62 = v26;
      v19 = (unsigned __int64)v68;
      LOBYTE(v25) = v58;
    }
    if ( v63 )
    {
      Timer_high = (struct _FCB_NONPAGED *)HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)Timer_high & 0x20) != 0 )
      {
        v74 = 0;
        for ( i = 0; ; ++i )
        {
          v74 = i;
          if ( i >= v63 )
            break;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v29 = (__int64)&(*v78)[8 * i];
            v30 = *(struct _IRP **)(v29 + 8);
            LODWORD(v31) = 0;
            if ( a3 != v30 )
              v31 = *(_QWORD *)(v29 + 8);
            WPP_SF_dqqqiqqDDiD(
              WPP_GLOBAL_Control->AttachedDevice,
              v29,
              v31,
              i,
              a4,
              (char)a3,
              v31,
              v55,
              (char)v30->MdlAddress,
              (char)v30->UserBuffer,
              *(_DWORD *)v29,
              *(_DWORD *)(v29 + 4),
              v30->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart,
              v30->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.Length);
          }
        }
        v18 = v70;
        LOBYTE(v25) = v58;
      }
      v32 = *(_DWORD *)(a1 + 720);
      if ( v32 > 0 )
      {
        v33 = RefsClaimDecompressWorkItem(Timer_high, v32);
        v34 = v33;
        v67 = v33;
        if ( v33 < 0 )
        {
          *(_DWORD *)(a1 + 720) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              63,
              WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
              (unsigned int)v33);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v34, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1C6Au);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v34, v25);
LABEL_167:
          RefsIsTriagePending((struct _IRP_CONTEXT *)a1);
          v51 = (unsigned int)v68;
          if ( (*(_DWORD *)&v68->Type & 0x400000) != 0
            && *(_BYTE *)(a1 + 40) == 4
            && (*v22 == -1073741391 || *v22 == -1073741435)
            && (unsigned __int8)MsIsWPOutOfSync(*(_QWORD *)(a1 + 24)) )
          {
            MsSetOkayToResyncSMRBands(v52);
            *v22 = -1073741608;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              66,
              WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
              (unsigned int)*v22);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(*v22, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1D49u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, *v22, v50);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, v51);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v51, (struct _IRP_CONTEXT *)a1, "DevIoSup.c", 0x1E02u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v51, v53);
          JUMPOUT(0x14033F1CALL);
        }
        v18 = v70;
        *(_DWORD *)(v70 + 152) += *(_DWORD *)(a1 + 720);
        *(_DWORD *)(a1 + 720) = 0;
      }
      if ( !(_BYTE)v25 && !*(_DWORD *)(v18 + 80) )
        RefsTransferNonCachedIoResourcesToCompletion(a1, a2, a3, a7);
      v35 = *(_DWORD *)(v18 + 80);
      v36 = *(struct CmsTransactionContext **)(a1 + 24);
      if ( !v36 )
        v36 = *(struct CmsTransactionContext **)(v70 + 856);
      RefsMultipleAsync(
        (struct _IRP_CONTEXT *)a1,
        (struct REFS_IO_CONTEXT *)a2,
        *(struct _DEVICE_OBJECT **)(v79 + 192),
        a3,
        v63,
        (struct IO_RUN *)*v78,
        v36);
      v64 = 1;
      if ( v58 )
      {
        RefsWaitOnIo((struct REFS_IO_CONTEXT *)a2);
        v38 = v68;
        if ( (int)(*v22 + 0x80000000) >= 0
          && *v22 != -1073741608
          && (*(_DWORD *)&v68->Type & 0x400000) != 0
          && *(_BYTE *)(a1 + 40) == 4 )
        {
          MsSetWPOutOfSync(*(_QWORD *)(a1 + 24));
        }
        if ( (*(_DWORD *)&v38->Type & 0x4000) != 0 && (*(_DWORD *)&v38->Type & 0x8000) != 0 && v63 == 1 )
        {
          v39 = **v78;
          if ( v39 )
          {
            RefsRestoreMdl((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3->MdlAddress, v39);
            v59 = 0;
          }
        }
      }
      else if ( !v35 )
      {
        v19 = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(259, 0, "DevIoSup.c", 0x1CA1u);
LABEL_85:
        v37 = 259;
        goto LABEL_127;
      }
      v18 = v70;
      goto LABEL_97;
    }
    if ( !*(_DWORD *)(v18 + 80) )
      break;
LABEL_97:
    if ( !v58 )
      goto LABEL_125;
    v19 = (unsigned __int64)v68;
LABEL_99:
    if ( !*(_DWORD *)(v18 + 84) )
    {
      if ( (*(_DWORD *)v19 & 0x100) != 0 )
      {
        if ( *v22 < 0 )
          goto LABEL_167;
        v40 = RefsFinishBuffers((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3, (struct _SCB *)a4, *v76);
        if ( v40 < 0 )
          *v22 = v40;
      }
      if ( *v22 < 0 )
        goto LABEL_167;
      if ( !*(_DWORD *)(v18 + 80) )
        goto LABEL_126;
      if ( !v61 && (*v80 & 0x40) != 0 )
      {
        RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
        if ( *v76 )
          RefsDeallocateCompressionBuffer(v41, a3, *v76);
        RefsReleaseRangeLockIoContext((struct REFS_IO_CONTEXT *)a2);
        *v80 &= ~0x40u;
      }
      v42 = *v22;
      if ( v66 )
      {
        *v22 = v75;
        IoSetMasterIrpStatus(a3, v42);
      }
      else
      {
        v66 = 1;
        v71 = 1;
        v75 = v42;
        v82 = v42;
      }
      *(_DWORD *)a2 &= 0xFFC7FEFF;
    }
LABEL_125:
    v19 = a7;
  }
  if ( (*(_DWORD *)v19 & 0x40000) == 0 )
  {
    v58 = 1;
    v60 = 1;
    goto LABEL_99;
  }
  RefsTransferNonCachedIoResourcesToCompletion(a1, a2, a3, a7);
  v19 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 259);
  }
  if ( !(_BYTE)RefsStatusDebugEnabled )
    goto LABEL_85;
  RefsStatusDebug(259, 0, "DevIoSup.c", 0x1CDAu);
  v37 = 259;
LABEL_127:
  v67 = v37;
  v43 = v58;
  if ( v59 )
  {
    if ( v58 )
    {
      if ( v63 == 1 && (*(_DWORD *)&v68->Type & 0x8000) != 0 && (*(_DWORD *)&v68->Type & 0x4000) != 0 )
      {
        v44 = **v78;
        if ( v44 )
          RefsRestoreMdl((struct _IRP_CONTEXT *)a1, (struct REFS_IO_CONTEXT *)a2, a3->MdlAddress, v44);
      }
    }
  }
  if ( v37 == 259 )
  {
    v45 = 0;
    if ( v62 )
    {
      *(_DWORD *)a2 &= ~0x40000u;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)p_AssociatedIrp, 0xFFFFFFFF) == 1 )
        IofCompleteRequest(a3, 1);
    }
  }
  else
  {
    v45 = *v85;
    if ( *v76 )
    {
      MsFreeChecksumContext(v19, (char *)*v76 + 160);
      RefsDeallocateCompressionBuffer(v46, a3, *v76);
    }
    if ( !v61 )
    {
      v47 = v80;
      if ( (*v80 & 0x40) != 0 )
      {
        if ( *(_QWORD *)(v70 + 816) )
        {
          RefsReleaseRangeLockIoContext((struct REFS_IO_CONTEXT *)a2);
          *v47 &= ~0x40u;
        }
      }
    }
    v48 = v76;
    if ( *v76 )
    {
      RefsReleasePrequel(*v76);
      RefsReleaseSequel(*v48);
      if ( !v65 )
        RefsFreeNPagedPerProcessorLookaside(RefsCompressCtxLookasideList, *v48);
    }
  }
  if ( v43 && v37 >= 0 )
  {
    if ( v45 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        v37 = 303;
      }
      else
      {
        v37 = 303;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 303);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(303, 0, "DevIoSup.c", 0x1E96u);
      *v22 = 303;
    }
    v87->IoStatus.Information = a6;
  }
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x14033e290  push    rbp
0x14033e292  push    rbx
0x14033e293  push    rsi
0x14033e294  push    rdi
0x14033e295  push    r12
0x14033e297  push    r13
0x14033e299  push    r14
0x14033e29b  push    r15
0x14033e29d  sub     rsp, 308h
0x14033e2a4  lea     rbp, [rsp+70h]
0x14033e2a9  mov     rax, cs:__security_cookie
0x14033e2b0  xor     rax, rbp
0x14033e2b3  mov     [rbp+2D0h+var_50], rax
0x14033e2ba  mov     r12, r9
0x14033e2bd  mov     r13, r8
0x14033e2c0  mov     [rbp+2D0h+var_2B8], rdx
0x14033e2c4  mov     rbx, rcx
0x14033e2c7  mov     [rbp+2D0h+var_238], rdx
0x14033e2ce  mov     [rbp+2D0h+var_2B0], rcx
0x14033e2d2  mov     r15, rdx
0x14033e2d5  mov     [rbp+2D0h+var_298], rdx
0x14033e2d9  mov     r14, rdx
0x14033e2dc  mov     [rbp+2D0h+var_2A8], rdx
0x14033e2e0  mov     [rbp+2D0h+Irp], r8
0x14033e2e4  mov     [rbp+2D0h+var_218], r8
0x14033e2eb  mov     [rbp+2D0h+var_248], r9
0x14033e2f2  xor     esi, esi
0x14033e2f4  mov     [rbp+2D0h+var_2C8], esi
0x14033e2f7  mov     [rbp+2D0h+var_2C0], esi
0x14033e2fa  mov     rax, [r9+88h]
0x14033e301  mov     rcx, [rax+50h]
0x14033e305  mov     [rbp+2D0h+var_260], rcx
0x14033e309  mov     al, gs:184h
0x14033e311  movzx   eax, al
0x14033e314  xor     edx, edx
0x14033e316  div     cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14033e31c  mov     eax, edx
0x14033e31e  shl     rax, 6
0x14033e322  add     rax, [rcx+328h]
0x14033e329  mov     [rbp+2D0h+var_270], rax
0x14033e32d  xor     edx, edx; Val
0x14033e32f  mov     r8d, 100h; Size
0x14033e335  lea     rcx, [rbp+2D0h+var_150]; void *
0x14033e33c  call    memset
0x14033e341  mov     edi, esi
0x14033e343  xor     cl, cl
0x14033e345  mov     [rbp+2D0h+var_2CF], cl
0x14033e348  mov     [rbp+2D0h+var_2C3], cl
0x14033e34b  mov     [rbp+2D0h+var_2C4], cl
0x14033e34e  xor     al, al
0x14033e350  mov     [rbp+2D0h+var_2CC], al
0x14033e353  mov     [rbp+2D0h+var_2C2], al
0x14033e356  mov     [rbp+2D0h+var_284], esi
0x14033e359  mov     [rbp+2D0h+var_250], rsi
0x14033e360  movzx   edx, byte ptr [rbx+8]
0x14033e364  and     dl, 1
0x14033e367  mov     [rbp+2D0h+var_2D0], dl
0x14033e36a  mov     [rbp+2D0h+var_2CE], dl
0x14033e36d  lea     rax, [rbx+4]
0x14033e371  mov     [rbp+2D0h+var_258], rax
0x14033e375  movzx   eax, byte ptr [rax]
0x14033e378  shr     al, 6
0x14033e37b  and     al, 1
0x14033e37d  mov     [rbp+2D0h+var_2CD], al
0x14033e380  cmp     byte ptr [rbx+28h], 4
0x14033e384  jnz     short loc_14033E3D8
0x14033e386  lea     rax, WPP_GLOBAL_Control
0x14033e38d  mov     rcx, cs:WPP_GLOBAL_Control
0x14033e394  cmp     rcx, rax
0x14033e397  jz      short loc_14033E3FF
0x14033e399  mov     eax, [rcx+2Ch]
0x14033e39c  test    al, 10h
0x14033e39e  jz      short loc_14033E3FF
0x14033e3a0  cmp     byte ptr [rcx+29h], 2
0x14033e3a4  jb      short loc_14033E3FF
0x14033e3a6  mov     edx, 3Ch ; '<'
0x14033e3ab  mov     [rsp+340h+var_310], r13
0x14033e3b0  mov     eax, [rbp+2D0h+arg_28]
0x14033e3b6  mov     [rsp+340h+var_318], eax
0x14033e3ba  mov     rsi, [rbp+2D0h+arg_20]
0x14033e3c1  mov     [rsp+340h+var_320], rsi
0x14033e3c6  mov     r9, r12
0x14033e3c9  mov     rcx, [rcx+18h]
0x14033e3cd  call    WPP_SF_qiDq
0x14033e3d2  movzx   edx, [rbp+2D0h+var_2D0]
0x14033e3d6  jmp     short loc_14033E406
0x14033e3d8  lea     rax, WPP_GLOBAL_Control
0x14033e3df  mov     rcx, cs:WPP_GLOBAL_Control
0x14033e3e6  cmp     rcx, rax
0x14033e3e9  jz      short loc_14033E3FF
0x14033e3eb  mov     eax, [rcx+2Ch]
0x14033e3ee  test    al, 8
0x14033e3f0  jz      short loc_14033E3FF
0x14033e3f2  cmp     byte ptr [rcx+29h], 2
0x14033e3f6  jb      short loc_14033E3FF
0x14033e3f8  mov     edx, 3Dh ; '='
0x14033e3fd  jmp     short loc_14033E3AB
0x14033e3ff  mov     rsi, [rbp+2D0h+arg_20]
0x14033e406  mov     rax, [rbp+2D0h+var_260]
0x14033e40a  mov     rcx, [rax+70h]
0x14033e40e  call    MsIsVolumeOnSmr
0x14033e413  test    al, al
0x14033e415  jz      short loc_14033E42B
0x14033e417  bt      word ptr [r12+100h], 0Dh
0x14033e422  jnb     short loc_14033E42B
0x14033e424  or      dword ptr [r15], 400000h
0x14033e42b  test    dl, dl
0x14033e42d  jz      loc_14033E509
0x14033e433  mov     eax, [rsp+340h+var_340]
0x14033e436  sub     rsp, 0C0h
0x14033e43d  lea     rdi, [rsp+400h+var_390]
0x14033e442  mov     eax, [rdi]
0x14033e444  xor     edx, edx; Val
0x14033e446  mov     r8d, 0C0h; Size
0x14033e44c  lea     rcx, [rbp+2D0h+var_210]; void *
0x14033e453  call    memset
0x14033e458  movups  xmm0, [rbp+2D0h+var_210]
0x14033e45f  movups  xmmword ptr [rdi], xmm0
0x14033e462  movups  xmm1, [rbp+2D0h+var_200]
0x14033e469  movups  xmmword ptr [rdi+10h], xmm1
0x14033e46d  movups  xmm0, [rbp+2D0h+var_1F0]
0x14033e474  movups  xmmword ptr [rdi+20h], xmm0
0x14033e478  movups  xmm1, [rbp+2D0h+var_1E0]
0x14033e47f  movups  xmmword ptr [rdi+30h], xmm1
0x14033e483  movups  xmm0, [rbp+2D0h+var_1D0]
0x14033e48a  movups  xmmword ptr [rdi+40h], xmm0
0x14033e48e  movups  xmm1, [rbp+2D0h+var_1C0]
0x14033e495  movups  xmmword ptr [rdi+50h], xmm1
0x14033e499  movups  xmm0, [rbp+2D0h+var_1B0]
0x14033e4a0  movups  xmmword ptr [rdi+60h], xmm0
0x14033e4a4  movups  xmm1, [rbp+2D0h+var_1A0]
0x14033e4ab  movups  xmmword ptr [rdi+70h], xmm1
0x14033e4af  movups  xmm0, [rbp+2D0h+var_190]
0x14033e4b6  movups  xmmword ptr [rdi+80h], xmm0
0x14033e4bd  movups  xmm1, [rbp+2D0h+var_180]
0x14033e4c4  movups  xmmword ptr [rdi+90h], xmm1
0x14033e4cb  movups  xmm0, [rbp+2D0h+var_170]
0x14033e4d2  movups  xmmword ptr [rdi+0A0h], xmm0
0x14033e4d9  movups  xmm1, [rbp+2D0h+var_160]
0x14033e4e0  movups  xmmword ptr [rdi+0B0h], xmm1
0x14033e4e7  mov     r9d, [rbp+2D0h+arg_30]
0x14033e4ee  mov     [rdi+0B8h], r9d
0x14033e4f5  mov     [rbp+2D0h+var_2C3], 1
0x14033e4f9  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e4fc  call    ?RefsIsModifyingTransactionActive@@YAEPEAU_IRP_CONTEXT@@@Z; RefsIsModifyingTransactionActive(_IRP_CONTEXT *)
0x14033e501  test    al, al
0x14033e503  jz      short loc_14033E509
0x14033e505  or      dword ptr [r15], 1
0x14033e509  lea     rax, [r14+90h]
0x14033e510  mov     [rbp+2D0h+var_268], rax
0x14033e514  lea     rcx, [rbp+2D0h+var_150]
0x14033e51b  mov     [rax], rcx
0x14033e51e  lea     rax, [r14+350h]
0x14033e525  mov     [rbp+2D0h+var_278], rax
0x14033e529  mov     [rax], rdi
0x14033e52c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14033e533  mov     rdi, r14
0x14033e536  mov     [r14+70h], rax
0x14033e53a  mov     [r14+78h], rax
0x14033e53e  lea     rax, [r14+34Ch]
0x14033e545  mov     [rbp+2D0h+var_228], rax
0x14033e54c  mov     byte ptr [rax], 0
0x14033e54f  lea     rax, [r13+18h]
0x14033e553  mov     [rbp+2D0h+var_220], rax
0x14033e55a  xor     edx, edx
0x14033e55c  mov     [rax], edx
0x14033e55e  mov     rax, [r12+90h]
0x14033e566  mov     ecx, [rax+1Ch]
0x14033e569  test    cl, 2
0x14033e56c  jz      short loc_14033E593
0x14033e56e  mov     [rsp+400h+var_3D8], 72657355h; unsigned __int64
0x14033e577  mov     [rsp+400h+var_3E0], rdx; union SmsBigIdentifier *
0x14033e57c  mov     r9, [r12+88h]; struct _FCB *
0x14033e584  xor     r8d, r8d; unsigned __int8
0x14033e587  mov     rdx, r13; struct _IRP *
0x14033e58a  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e58d  call    ?RefsInsertDebugInfoIrpImplementation@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EPEAU_FCB@@PEBTSmsBigIdentifier@@_K4@Z; RefsInsertDebugInfoIrpImplementation(_IRP_CONTEXT *,_IRP *,uchar,_FCB *,SmsBigIdentifier const *,unsigned __int64,unsigned __int64)
0x14033e592  nop
0x14033e593  mov     ecx, [rbp+2D0h+arg_30]
0x14033e599  bt      ecx, 2
0x14033e59d  jb      loc_14033E6AF
0x14033e5a3  cmp     byte ptr [rbx+28h], 4
0x14033e5a7  jnz     loc_14033E6AF
0x14033e5ad  mov     eax, 805h
0x14033e5b2  cmp     [r12], ax
0x14033e5b7  jnz     short loc_14033E5D0
0x14033e5b9  cmp     qword ptr [r12+1B0h], 0
0x14033e5c2  jz      short loc_14033E5D0
0x14033e5c4  cmp     word ptr [r12+104h], 0
0x14033e5ce  jnz     short loc_14033E5FF
0x14033e5d0  bt      word ptr [r12+100h], 0Eh
0x14033e5db  jnb     loc_14033E6AF
0x14033e5e1  cmp     qword ptr [r12+120h], 0
0x14033e5ea  jz      loc_14033E6AF
0x14033e5f0  cmp     dword ptr [r12+98h], 0
0x14033e5f9  jl      loc_14033E6AF
0x14033e5ff  mov     eax, esi
0x14033e601  mov     r8d, [rbp+2D0h+arg_28]
0x14033e608  or      eax, r8d
0x14033e60b  mov     rdx, [rbp+2D0h+var_260]
0x14033e60f  test    [rdx+220h], eax
0x14033e615  jz      loc_14033E6B6
0x14033e61b  mov     rax, [rbx+48h]
0x14033e61f  mov     ecx, [rax+10h]
0x14033e622  test    cl, 2
0x14033e625  jz      loc_14033E6CD
0x14033e62b  cmp     qword ptr [r12+0F0h], 0
0x14033e634  jnz     loc_14033E6CD
0x14033e63a  mov     rdx, r12; struct _SCB *
0x14033e63d  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e640  call    ?RefsAcquireEofLockForRead@@YAXAEAU_IRP_CONTEXT@@AEAU_SCB@@@Z; RefsAcquireEofLockForRead(_IRP_CONTEXT &,_SCB &)
0x14033e645  nop
0x14033e646  lea     r9, stru_140206ED0; struct _UNICODE_STRING *
0x14033e64d  xor     r8d, r8d; unsigned __int8
0x14033e650  mov     rdx, r12; struct _SCB *
0x14033e653  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e656  call    ?RefsCreateInternalAttributeStream@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@EPEBU_UNICODE_STRING@@@Z; RefsCreateInternalAttributeStream(_IRP_CONTEXT *,_SCB *,uchar,_UNICODE_STRING const *)
0x14033e65b  nop
0x14033e65c  mov     rdx, r12; struct _SCB *
0x14033e65f  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e662  call    ?RefsReleaseEofLock@@YAXAEAU_IRP_CONTEXT@@AEAU_SCB@@@Z; RefsReleaseEofLock(_IRP_CONTEXT &,_SCB &)
0x14033e667  cmp     dword ptr [r12+0A0h], 0
0x14033e670  jnz     short loc_14033E6A9
0x14033e672  mov     rax, [r12+88h]
0x14033e67a  cmp     dword ptr [rax+0D0h], 0
0x14033e681  jnz     short loc_14033E6A9
0x14033e683  xor     r8d, r8d
0x14033e686  mov     rdx, r12
0x14033e689  mov     rcx, rbx
0x14033e68c  call    ?RefsAcquireExclusiveScb@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveScb(_IRP_CONTEXT *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033e691  mov     rcx, r12; struct _SCB *
0x14033e694  call    ?RefsAddScbToDelayedClose@@YAXAEAU_SCB@@@Z; RefsAddScbToDelayedClose(_SCB &)
0x14033e699  mov     rdx, [r12+88h]; struct _FCB *
0x14033e6a1  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14033e6a4  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x14033e6a9  mov     ecx, [rbp+2D0h+arg_30]
0x14033e6af  mov     r8d, [rbp+2D0h+arg_28]
0x14033e6b6  cmp     byte ptr [rbx+28h], 3
0x14033e6ba  jnz     short loc_14033E6D5
0x14033e6bc  bt      qword ptr [rbx+8], 27h ; '''
0x14033e6c2  jnb     short loc_14033E6D5
0x14033e6c4  mov     eax, 40000035h
0x14033e6c9  xor     edx, edx
0x14033e6cb  jmp     short loc_14033E6D9
0x14033e6cd  mov     ecx, [rbp+2D0h+arg_30]
0x14033e6d3  jmp     short loc_14033E6B6
0x14033e6d5  xor     edx, edx
0x14033e6d7  mov     eax, edx
0x14033e6d9  lea     r14, [r13+30h]
0x14033e6dd  mov     [rbp+2D0h+var_230], r14
0x14033e6e4  mov     [r14], eax
0x14033e6e7  mov     [rdi+48h], rsi
0x14033e6eb  mov     [rdi+50h], r8d
0x14033e6ef  mov     [rdi+60h], rdx
0x14033e6f3  mov     [rdi+68h], r8d
0x14033e6f7  mov     qword ptr [rdi+54h], 0
0x14033e6ff  mov     [rbp+2D0h+var_250], rsi
0x14033e706  and     dword ptr [r15], 0FFC7FEFFh
0x14033e70d  lea     rsi, WPP_GLOBAL_Control
0x14033e714  cmp     dword ptr [rdi+50h], 0
0x14033e718  jbe     loc_14033EBE6
0x14033e71e  mov     [rbp+2D0h+var_2C4], 0
0x14033e722  lea     rax, [rbp+2D0h+var_250]
0x14033e729  mov     [rsp+400h+var_3D0], rax
0x14033e72e  lea     rax, [rbp+2D0h+var_2C8]
0x14033e732  mov     [rsp+400h+var_3D8], rax
0x14033e737  mov     dword ptr [rsp+400h+var_3E0], ecx
0x14033e73b  mov     r9, r12
0x14033e73e  mov     r8, r13
0x14033e741  mov     rdx, r15
0x14033e744  mov     rcx, rbx
0x14033e747  call    ?RefsPrepareBuffers@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@W4RefsIoStreamFlags@@PEAKPEA_J@Z; RefsPrepareBuffers(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,RefsIoStreamFlags,ulong *,__int64 *)
0x14033e74c  mov     [rbp+2D0h+var_2CF], 1
0x14033e750  mov     eax, [r13+10h]
0x14033e754  test    al, 2
0x14033e756  jz      short loc_14033E7D2
0x14033e758  mov     edx, [rbp+2D0h+var_2C8]
0x14033e75b  movzx   r8d, byte ptr [rbx+28h]
0x14033e760  movzx   eax, word ptr [r12+0D8h]
0x14033e769  mov     ecx, 80h
0x14033e76e  cmp     ax, cx
0x14033e771  jz      short loc_14033E77D
0x14033e773  mov     ecx, 0B0h
0x14033e778  cmp     ax, cx
0x14033e77b  jnz     short loc_14033E790
0x14033e77d  mov     rax, [r12+88h]
0x14033e785  mov     rcx, [rax+8]
0x14033e789  bt      rcx, 8
0x14033e78e  jnb     short loc_14033E7B2
0x14033e790  cmp     r8b, 4
0x14033e794  mov     r8, [rbp+2D0h+var_270]
0x14033e798  jnz     short loc_14033E7A6
0x14033e79a  mov     ecx, [r8+34h]
0x14033e79e  add     ecx, edx
0x14033e7a0  mov     [r8+34h], ecx
0x14033e7a4  jmp     short loc_14033E7D2
0x14033e7a6  mov     ecx, [r8+28h]
0x14033e7aa  add     ecx, edx
0x14033e7ac  mov     [r8+28h], ecx
0x14033e7b0  jmp     short loc_14033E7D2
  ... truncated ...
```
