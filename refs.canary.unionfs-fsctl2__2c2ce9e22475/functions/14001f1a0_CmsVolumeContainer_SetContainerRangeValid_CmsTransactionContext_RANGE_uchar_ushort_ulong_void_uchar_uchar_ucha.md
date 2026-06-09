# CmsVolumeContainer::SetContainerRangeValid(CmsTransactionContext *,_RANGE,uchar,ushort,ulong,void *,uchar,uchar,uchar)

- ea: `0x14001f1a0`
- end: `0x14001f844`
- name: `?SetContainerRangeValid@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EGKPEAXEEE@Z`
- size: `1700`
- prototype: `int __high(struct CmsTransactionContext *, struct _RANGE, unsigned __int8, unsigned __int16, unsigned int, void *, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `8`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001fdf0`
- `0x140029570`
- `0x14006dc40`
- `0x1400c0cb4`
- `0x140140668`
- `0x140142a34`
- `0x1401449a8`
- `0x140147b0c`

## callees

- `0x140012660`
- `0x14001cbc0`
- `0x14001f1a0`
- `0x140023180`
- `0x14003234c`
- `0x140034ab0`
- `0x140043e80`
- `0x14006e2f0`
- `0x14009b240`
- `0x1400ade40`
- `0x140133f58`
- `0x140134f98`
- `0x140139aa4`
- `0x14014cc44`
- `0x14014f738`
- `0x14017208c`
- `0x1401722fc`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14001f64f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f664`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f696`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f43c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f43c`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef363`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef363`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001f524`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001f524`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14001f36a`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14001f36a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001f3a1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001f3a1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ef58d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ef58d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001f38a`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001f38a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f833`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f833`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ef382`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ef382`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::SetContainerRangeValid(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        char a4,
        __int16 a5,
        int a6,
        void *a7,
        char a8,
        char a9,
        char a10)
{
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  char v17; // bl
  unsigned __int8 v18; // dl
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  bool v21; // zf
  unsigned __int8 v22; // cl
  CmsBPlusTable **v23; // rcx
  CmsBPlusTable *v24; // rcx
  int v25; // r13d
  int RangeBitmap; // r12d
  __int64 v27; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v28; // r13
  unsigned int v29; // r9d
  unsigned int v30; // r8d
  _DWORD *Undo; // rbx
  struct _SLIST_ENTRY *v32; // r8
  __int64 v33; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v34; // rcx
  __int64 v35; // rax
  __int64 v37; // rcx
  char v38; // al
  unsigned __int8 v39; // cl
  unsigned __int8 v40; // al
  unsigned __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned int v43; // eax
  CmsTxMemLog *v44; // rcx
  CmsChecksum *v45; // rax
  _BYTE *v46; // r11
  unsigned __int64 v47; // r10
  unsigned __int64 ChecksumLength; // rax
  int v49; // edx
  __int64 v50; // rcx
  __int64 v51; // rcx
  PULONG Buffer; // rax
  __int64 v53; // rbx
  unsigned __int64 v54; // rax
  void *Pool2; // rax
  unsigned int NextForwardRunSet; // eax
  struct CmsBPlusTable *IntegrityStateTable; // rax
  int v58; // edx
  __int64 v59; // r9
  _OWORD *v60; // rcx
  __int128 v61; // xmm0
  CmsBPlusTable *v62; // rax
  int v63; // edx
  unsigned int v64; // [rsp+28h] [rbp-E0h]
  __int128 *v65; // [rsp+30h] [rbp-D8h]
  unsigned int v66; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v67; // [rsp+4Ch] [rbp-BCh]
  bool v68[8]; // [rsp+50h] [rbp-B8h] BYREF
  CmsChecksum *v69; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v70; // [rsp+60h] [rbp-A8h]
  char *v71; // [rsp+68h] [rbp-A0h]
  _QWORD v72[3]; // [rsp+70h] [rbp-98h] BYREF
  __int16 v73; // [rsp+88h] [rbp-80h]
  char v74; // [rsp+8Ah] [rbp-7Eh]
  unsigned __int8 v75; // [rsp+8Bh] [rbp-7Dh]
  unsigned __int8 v76; // [rsp+8Ch] [rbp-7Ch]
  __int64 v77; // [rsp+90h] [rbp-78h]
  int v78; // [rsp+98h] [rbp-70h]
  _BYTE v79[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v80; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v81; // [rsp+B8h] [rbp-50h]
  PVOID P; // [rsp+C0h] [rbp-48h]
  __int64 v83; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-38h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+D8h] [rbp-30h] BYREF
  void *v86; // [rsp+E8h] [rbp-20h]
  _QWORD v87[3]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v88[6]; // [rsp+108h] [rbp+0h] BYREF

  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3344LL) + 16LL) )
    return 0;
  v14 = *(unsigned __int8 *)(a1 + 392);
  v15 = *(_QWORD *)(a2 + 8);
  v16 = *(_QWORD *)a2;
  v17 = 0;
  v83 = 0;
  v84 = 0;
  v73 = 0;
  v78 = 0;
  v74 = 0;
  v68[0] = 0;
  P = 0;
  v66 = 0;
  BitMapHeader = 0;
  v69 = *(CmsChecksum **)(v15 + 8 * v14 + 3624);
  if ( (v16 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  ++*(_WORD *)(a2 + 212);
  v18 = *(_BYTE *)(a2 + 131);
  v78 = *(unsigned __int16 *)(a2 + 212);
  v72[0] = *(_QWORD *)(a2 + 144);
  v19 = (_QWORD *)(*(_QWORD *)(a2 + 416) + 8LL);
  v74 = 0;
  v20 = (_QWORD *)*v19;
  v21 = *v19 == 0;
  v77 = v16;
  v75 = v18;
  if ( v21 )
    v20 = v19;
  HIBYTE(v73) = 0;
  v72[2] = *(_QWORD *)(a2 + 200);
  v72[1] = v20;
  v22 = *(_BYTE *)(a2 + 132);
  *(_QWORD *)a2 = v16 & 0xFFFFEFFFFFFFFFFFuLL;
  v76 = v22;
  while ( 1 )
  {
    if ( v18 >= 0xDu )
      goto LABEL_9;
    if ( !*(_QWORD *)(a2 + 8LL * v18 + 560) )
      break;
    ++v18;
  }
  *(_BYTE *)(a2 + 131) = v18;
LABEL_9:
  while ( v22 < 0xDu )
  {
    if ( !*(_QWORD *)(a2 + 8LL * v22 + 424) )
    {
      *(_BYTE *)(a2 + 132) = v22;
      break;
    }
    ++v22;
  }
  if ( *(_BYTE *)(a2 + 131) < *(_BYTE *)(a2 + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *(_BYTE *)(a2 + 130) = *(_BYTE *)(a2 + 131);
  v23 = *(CmsBPlusTable ***)(*(_QWORD *)(a1 + 8) + 3312LL);
  if ( v23 )
  {
    v24 = *v23;
    if ( v24 )
      CmsBPlusTable::EnterTree(v24, (struct CmsTransactionContext *)a2);
  }
  v25 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL);
  v80 = *a3;
  RangeBitmap = CmsVolumeContainer::PinContainerRangeForRead(a1, a2, &v80, &v83, 0, 0, 0);
  if ( RangeBitmap >= 0 )
  {
    v27 = ExAcquireAutoExpandPushLockShared(a1 + 56, 2);
    v28 = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 48), *(_QWORD *)a3 >> ((unsigned __int8)v25 + 1), 0);
    ExReleaseAutoExpandPushLockShared(v27, 2);
    if ( (HIDWORD(v28[25].Linkage.Blink) & 0x201) == 0 )
    {
      if ( (__int64)v28[4].Linkage.Blink > *(_QWORD *)(*(_QWORD *)(a1 + 8) + 2112LL) )
      {
        v35 = *(_QWORD *)(a2 + 8);
        RangeBitmap = -1073741432;
        v17 = 1;
        goto LABEL_32;
      }
      if ( a4 || a8 )
      {
        v29 = v84;
        v30 = 0;
        v66 = 0;
        v67 = v84;
      }
      else
      {
        v53 = *((unsigned int *)a3 + 2);
        v54 = 4 * ((unsigned __int64)(v53 + 3) >> 2);
        if ( !is_mul_ok((unsigned __int64)(v53 + 3) >> 2, 4u) )
          v54 = -1;
        Pool2 = (void *)ExAllocatePool2(66, v54, 1766871885);
        P = Pool2;
        if ( !Pool2 )
        {
LABEL_91:
          v35 = *(_QWORD *)(a2 + 8);
          RangeBitmap = -1073741670;
          v17 = 1;
          goto LABEL_32;
        }
        RtlInitializeBitMap(&BitMapHeader, (PULONG)Pool2, v53);
        RangeBitmap = CmsIntegrityState::GetRangeBitmap(
                        *(CmsIntegrityState **)(*(_QWORD *)(a1 + 8) + 3344LL),
                        (struct CmsTransactionContext *)a2,
                        (const struct _RANGE *)&v83,
                        &BitMapHeader);
        if ( RangeBitmap < 0 )
          goto LABEL_30;
        NextForwardRunSet = CmsClusterOperations::FindNextForwardRunSet(&BitMapHeader, 0, &v66);
        v30 = v66;
        v29 = NextForwardRunSet;
        v67 = NextForwardRunSet;
      }
      Undo = 0;
      while ( v29 )
      {
        v87[0] = v83 + v30;
        v87[1] = v29;
        if ( a7 )
        {
          ChecksumLength = CmsChecksum::GetChecksumLength(v69, v29 << *(_DWORD *)(*(_QWORD *)(a1 + 8) + 64LL));
          v49 = ChecksumLength;
          v70 = ChecksumLength;
        }
        else
        {
          v49 = 0;
          v70 = 0;
        }
        if ( (*(_QWORD *)a2 & 0x400LL) == 0 || (*(_QWORD *)a2 & 0x1000LL) == 0 )
          LOBYTE(v28[1].Linkage.Flink) |= 1u;
        if ( !a8 && !a10 )
        {
          IntegrityStateTable = CmsIntegrityState::GetIntegrityStateTable(*(CmsIntegrityState **)(*(_QWORD *)(a1 + 8)
                                                                                                + 3344LL));
          Undo = CmsBPlusTable::AllocateUndo((__int64)IntegrityStateTable, a2, 34, v59, v58 + 32, 4);
          if ( !Undo )
            goto LABEL_91;
          v30 = v66;
          v29 = v67;
          v49 = v70;
        }
        if ( a9 )
        {
          RangeBitmap = CmsIntegrityState::SetClearIntegrityState(
                          *(CmsIntegrityState **)(*(_QWORD *)(a1 + 8) + 3344LL),
                          (struct CmsTransactionContext *)a2,
                          (const struct _RANGE *)v87,
                          a4 != 0,
                          v68,
                          (bool)v65);
          if ( RangeBitmap < 0 )
            goto LABEL_24;
          v30 = v66;
          v29 = v67;
          v49 = v70;
        }
        v45 = v69;
        v21 = *((_WORD *)v69 + 4) == 0;
        v46 = (char *)v69 + 20;
        v71 = (char *)v69 + 20;
        if ( v21 )
          v47 = 0;
        else
          v47 = (unsigned __int64)(v30 << *(_DWORD *)(*(_QWORD *)(a1 + 8) + 64LL)) >> *v46;
        v81 = v47;
        if ( !a8 && !a10 )
        {
          v60 = (_OWORD *)*((_QWORD *)Undo + 3);
          v61 = *a3;
          v86 = v60;
          *((_BYTE *)v60 + 16) = a4 == 0;
          *((_WORD *)v60 + 9) = a5;
          *v60 = v61;
          *((_DWORD *)v60 + 5) = v49;
          *((_QWORD *)v60 + 3) = 0;
          if ( a7 )
            CmsChecksum::CopyChecksum(
              v69,
              v47 + a6,
              a7,
              v29 << *(_DWORD *)(*(_QWORD *)(a1 + 8) + 64LL),
              v64,
              (char *)v60 + 24);
          v62 = CmsIntegrityState::GetIntegrityStateTable(*(CmsIntegrityState **)(*(_QWORD *)(a2 + 8) + 3344LL));
          CmsBPlusTable::FormatUndoRecord(
            v62,
            (struct CmsTransactionContext *)a2,
            (struct SmsUndoRecord *)Undo,
            0,
            v86,
            v63 + 32,
            0);
          v30 = v66;
          Undo = 0;
          v29 = v67;
          LODWORD(v47) = v81;
          v46 = v71;
          v45 = v69;
        }
        if ( a7 )
        {
          if ( *((_WORD *)v45 + 4) )
            v41 = (unsigned __int64)(((*(_DWORD *)(*(_QWORD *)(a1 + 8) + 84LL) - 1) & (v30 + *(_DWORD *)a3)) << *(_DWORD *)(*(_QWORD *)(a1 + 8) + 64LL)) >> *v46;
          else
            v41 = 0;
          v42 = *(_QWORD *)(a1 + 8);
          v88[0] = v28 + 28;
          LODWORD(v42) = *(_DWORD *)(v42 + 64);
          v88[1] = (unsigned int)(16 * *(_DWORD *)(a1 + 396));
          v71 = (char *)v41;
          v65 = (__int128 *)v88;
          v64 = v41;
          LODWORD(v70) = v47 + a6;
          CmsChecksum::MergeChecksums(v69, (unsigned int)(v47 + a6), a7, v29 << v42);
          v29 = v67;
          if ( (*(_DWORD *)a2 & 0x400LL) != 0 )
          {
            v50 = *(_QWORD *)(a1 + 8);
            *(_QWORD *)&v80 = v28[23].Signature;
            LODWORD(v50) = *(_DWORD *)(v50 + 64);
            *((_QWORD *)&v80 + 1) = (unsigned int)(16 * *(_DWORD *)(a1 + 396));
            v65 = &v80;
            v64 = (unsigned int)v71;
            CmsChecksum::MergeChecksums(v69, (unsigned int)v70, a7, v67 << v50);
            v29 = v67;
          }
          v30 = v66;
        }
        if ( a4 || a8 )
        {
          v29 = 0;
          v67 = 0;
        }
        else
        {
          v43 = CmsClusterOperations::FindNextForwardRunSet(&BitMapHeader, v30 + v29, &v66);
          v30 = v66;
          v29 = v43;
          v67 = v43;
        }
      }
      if ( (*(_DWORD *)a2 & 0x400LL) != 0 && a7 )
        CmsVolumeContainer::UpdateContainerChecksumsForCheckpoint(
          (CmsVolumeContainer *)a1,
          (struct CmsTransactionContext *)a2,
          (struct SmsContainer *)v28);
LABEL_24:
      if ( Undo && (Undo[5] & 4) == 0 )
      {
        v32 = (struct _SLIST_ENTRY *)(Undo - 4);
        v33 = *((_QWORD *)Undo - 2);
        if ( !v33 )
          goto LABEL_82;
        if ( *(_BYTE *)(v33 + 8) )
        {
          v34 = (struct _NPAGED_LOOKASIDE_LIST *)(v33 + 64);
          if ( *(_BYTE *)(v33 + 9) )
            ExFreeToNPagedLookasideList(v34, v32);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v34, v32);
          goto LABEL_30;
        }
        v51 = *(_QWORD *)(v33 + 88);
        if ( (int)v51 < *(_DWORD *)(v33 + 80) || SHIDWORD(v51) >= (int)v51 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v33 + 64), v32);
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 88));
        }
        else
        {
LABEL_82:
          ExFreePoolWithTag(v32, 0);
        }
      }
LABEL_30:
      v17 = 1;
      goto LABEL_31;
    }
    v17 = 1;
  }
LABEL_31:
  v35 = *(_QWORD *)(a2 + 8);
  if ( RangeBitmap >= 0 )
  {
    v78 = 0;
    --*(_WORD *)(a2 + 212);
    if ( v74 )
      --*(_WORD *)(a2 + 214);
    if ( HIBYTE(v73) )
    {
      v44 = *(CmsTxMemLog **)(a2 + 416);
      if ( *(_QWORD *)v44 )
        CmsTxMemLog::MergeTxLog(
          *(CmsTxMemLog **)&BitMapHeader.SizeOfBitMap,
          (struct CmsTxMemLog *)v79,
          (struct CmsDurableLog *)(v35 + 2880));
      else
        CmsTxMemLog::DiscardPendingRecords(v44, (struct CmsDurableLog *)(v35 + 2880));
      v37 = v77;
      if ( (v77 & 0x80000000000LL) != 0 )
      {
        Buffer = BitMapHeader.Buffer;
        *(_QWORD *)a2 |= 0x80000000000uLL;
        *(_QWORD *)(a2 + 112) = Buffer;
      }
      *(_QWORD *)(a2 + 416) = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
    }
    else
    {
      v37 = v77;
    }
    v38 = *(_BYTE *)(a2 + 130);
    *(_QWORD *)a2 |= v37 & 0x100000000000LL;
    if ( *(_BYTE *)(a2 + 131) != v38 && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    v39 = v75;
    v40 = v76;
    *(_BYTE *)(a2 + 131) = v75;
    *(_BYTE *)(a2 + 132) = v40;
    *(_BYTE *)(a2 + 130) = v39;
    goto LABEL_33;
  }
LABEL_32:
  CmsVolume::AbortTopLevelAction((CmsVolume *)v35, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v72);
LABEL_33:
  if ( v17 )
  {
    v80 = *a3;
    CmsVolumeContainer::UnpinContainerRange(a1, a2, &v80, 0);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)RangeBitmap;
}

```

## disassembly

```asm
0x14001f1a0  mov     r11, rsp
0x14001f1a3  push    rbp
0x14001f1a4  push    rsi
0x14001f1a5  push    rdi
0x14001f1a6  push    r14
0x14001f1a8  push    r15
0x14001f1aa  lea     rbp, [r11-38h]
0x14001f1ae  sub     rsp, 110h
0x14001f1b5  mov     rax, [rcx+8]
0x14001f1b9  mov     rdi, rdx
0x14001f1bc  movzx   r14d, r9b
0x14001f1c0  mov     r15, r8
0x14001f1c3  mov     rsi, rcx
0x14001f1c6  mov     rdx, [rax+0D10h]
0x14001f1cd  cmp     byte ptr [rdx+10h], 0
0x14001f1d1  jz      loc_14001F512
0x14001f1d7  movzx   ecx, byte ptr [rcx+188h]
0x14001f1de  xorps   xmm0, xmm0
0x14001f1e1  mov     rax, [rdi+8]
0x14001f1e5  mov     r8, [rdi]
0x14001f1e8  mov     [r11+10h], rbx
0x14001f1ec  xor     bl, bl
0x14001f1ee  mov     [r11+18h], r12
0x14001f1f2  xor     r12d, r12d
0x14001f1f5  mov     [rbp+30h+var_70], r12
0x14001f1f9  mov     [rbp+30h+var_68], r12
0x14001f1fd  mov     [rbp+30h+var_B0], r12w
0x14001f202  mov     [rbp+30h+var_A0], r12d
0x14001f206  mov     [rbp+30h+var_AE], bl
0x14001f209  mov     [r11+20h], r13
0x14001f20d  mov     [rsp+130h+var_E8], 0
0x14001f212  mov     [rbp+30h+P], r12
0x14001f216  mov     [rsp+130h+var_F0], r12d
0x14001f21b  movups  xmmword ptr [rbp+30h+BitMapHeader.SizeOfBitMap], xmm0
0x14001f21f  mov     rax, [rax+rcx*8+0E28h]
0x14001f227  mov     [rsp+130h+var_E0], rax
0x14001f22c  bt      r8, 15h
0x14001f231  jb      loc_14001F64F
0x14001f237  inc     word ptr [rdi+0D4h]
0x14001f23e  movzx   eax, word ptr [rdi+0D4h]
0x14001f245  movzx   edx, byte ptr [rdi+83h]
0x14001f24c  mov     [rbp+30h+var_A0], eax
0x14001f24f  mov     rax, [rdi+90h]
0x14001f256  mov     [rsp+130h+var_C8], rax
0x14001f25b  mov     rax, [rdi+1A0h]
0x14001f262  add     rax, 8
0x14001f266  mov     [rbp+30h+var_AE], bl
0x14001f269  mov     rcx, [rax]
0x14001f26c  test    rcx, rcx
0x14001f26f  mov     [rbp+30h+var_A8], r8
0x14001f273  mov     [rbp+30h+var_AD], dl
0x14001f276  cmovz   rcx, rax
0x14001f27a  mov     byte ptr [rbp+30h+var_B0+1], bl
0x14001f27d  mov     rax, [rdi+0C8h]
0x14001f284  mov     [rsp+78h], rax
0x14001f289  mov     rax, 0FFFFEFFFFFFFFFFFh
0x14001f293  mov     [rsp+130h+var_C0], rcx
0x14001f298  and     r8, rax
0x14001f29b  movzx   ecx, byte ptr [rdi+84h]
0x14001f2a2  mov     [rdi], r8
0x14001f2a5  mov     [rbp+30h+var_AC], cl
0x14001f2a8  cmp     dl, 0Dh
0x14001f2ab  jnb     short loc_14001F2C4
0x14001f2ad  movzx   eax, dl
0x14001f2b0  cmp     [rdi+rax*8+230h], r12
0x14001f2b8  jnz     loc_14001F53C
0x14001f2be  mov     [rdi+83h], dl
0x14001f2c4  cmp     cl, 0Dh
0x14001f2c7  jnb     short loc_14001F2E0
0x14001f2c9  movzx   eax, cl
0x14001f2cc  cmp     [rdi+rax*8+1A8h], r12
0x14001f2d4  jnz     loc_14001F535
0x14001f2da  mov     [rdi+84h], cl
0x14001f2e0  movzx   eax, byte ptr [rdi+82h]
0x14001f2e7  cmp     [rdi+83h], al
0x14001f2ed  jb      loc_14001F664
0x14001f2f3  movzx   eax, byte ptr [rdi+83h]
0x14001f2fa  mov     [rdi+82h], al
0x14001f300  mov     rax, [rsi+8]
0x14001f304  mov     rcx, [rax+0CF0h]
0x14001f30b  test    rcx, rcx
0x14001f30e  jz      short loc_14001F320
0x14001f310  mov     rcx, [rcx]; this
0x14001f313  test    rcx, rcx
0x14001f316  jz      short loc_14001F320
0x14001f318  mov     rdx, rdi; struct CmsTransactionContext *
0x14001f31b  call    ?EnterTree@CmsBPlusTable@@UEAAEPEAVCmsTransactionContext@@@Z; CmsBPlusTable::EnterTree(CmsTransactionContext *)
0x14001f320  mov     rax, [rsi+8]
0x14001f324  lea     r9, [rbp+30h+var_70]
0x14001f328  movups  xmm0, xmmword ptr [r15]
0x14001f32c  mov     [rsp+30h], r12
0x14001f331  lea     r8, [rbp+30h+var_90]
0x14001f335  mov     [rsp+130h+var_108], r12
0x14001f33a  mov     rdx, rdi
0x14001f33d  mov     r13d, [rax+50h]
0x14001f341  mov     rcx, rsi
0x14001f344  movaps  [rbp+30h+var_90], xmm0
0x14001f348  mov     [rsp+130h+var_110], r12
0x14001f34d  call    ?PinContainerRangeForRead@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@PEAU3@PEAU_SmsContainerOverflowPinList@@PEAE4@Z; CmsVolumeContainer::PinContainerRangeForRead(CmsTransactionContext *,_RANGE,_RANGE *,_SmsContainerOverflowPinList *,uchar *,uchar *)
0x14001f352  mov     r12d, eax
0x14001f355  test    eax, eax
0x14001f357  js      loc_14001F44C
0x14001f35d  lea     rcx, [rsi+38h]
0x14001f361  mov     [rbp+30h+arg_0], 1
0x14001f365  mov     edx, 2
0x14001f36a  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x14001f371  nop     dword ptr [rax+rax+00h]
0x14001f376  mov     rdx, [r15]
0x14001f379  lea     ecx, [r13+1]
0x14001f37d  shr     rdx, cl; Signature
0x14001f380  xor     r8d, r8d; Context
0x14001f383  mov     rcx, [rsi+30h]; HashTable
0x14001f387  mov     rbx, rax
0x14001f38a  call    cs:__imp_RtlLookupEntryHashTable
0x14001f391  nop     dword ptr [rax+rax+00h]
0x14001f396  mov     edx, 2
0x14001f39b  mov     rcx, rbx
0x14001f39e  mov     r13, rax
0x14001f3a1  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x14001f3a8  nop     dword ptr [rax+rax+00h]
0x14001f3ad  test    dword ptr [r13+264h], 201h
0x14001f3b8  jnz     loc_14001F7DA
0x14001f3be  mov     rax, [rsi+8]
0x14001f3c2  mov     rcx, [rax+840h]
0x14001f3c9  cmp     [r13+68h], rcx
0x14001f3cd  jg      loc_14001F6AC
0x14001f3d3  test    r14b, r14b
0x14001f3d6  jz      loc_1401EF32C
0x14001f3dc  mov     r9d, dword ptr [rbp+30h+var_68]
0x14001f3e0  xor     r8d, r8d
0x14001f3e3  mov     [rsp+130h+var_F0], r8d
0x14001f3e8  mov     [rsp+130h+var_EC], r9d
0x14001f3ed  xor     ebx, ebx
0x14001f3ef  test    r9d, r9d
0x14001f3f2  jnz     loc_14001F6BF
0x14001f3f8  mov     eax, [rdi]
0x14001f3fa  bt      rax, 0Ah
0x14001f3ff  jb      loc_14001F78A
0x14001f405  test    rbx, rbx
0x14001f408  jz      short loc_14001F448
0x14001f40a  test    byte ptr [rbx+14h], 4
0x14001f40e  jnz     short loc_14001F448
0x14001f410  lea     r8, [rbx-10h]
0x14001f414  mov     rbx, [rbx-10h]
0x14001f418  test    rbx, rbx
0x14001f41b  jz      loc_14001F7C4
0x14001f421  cmp     byte ptr [rbx+8], 0
0x14001f425  jz      loc_14001F7A8
0x14001f42b  cmp     byte ptr [rbx+9], 0
0x14001f42f  lea     rcx, [rbx+40h]; Lookaside
0x14001f433  mov     rdx, r8; Entry
0x14001f436  jz      loc_14001F524
0x14001f43c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f443  nop     dword ptr [rax+rax+00h]
0x14001f448  movzx   ebx, [rbp+30h+arg_0]
0x14001f44c  mov     rax, [rdi+8]
0x14001f450  test    r12d, r12d
0x14001f453  jns     short loc_14001F4A5
0x14001f455  lea     r8, [rsp+130h+var_C8]; struct _SmsTopLevelAction *
0x14001f45a  mov     rdx, rdi; struct CmsTransactionContext *
0x14001f45d  mov     rcx, rax; this
0x14001f460  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x14001f465  mov     r13, [rsp+130h+arg_18]
0x14001f46d  test    bl, bl
0x14001f46f  mov     rbx, [rsp+130h+arg_8]
0x14001f477  jnz     loc_14001F812
0x14001f47d  mov     rcx, [rbp+30h+P]; P
0x14001f481  test    rcx, rcx
0x14001f484  jnz     loc_14001F831
0x14001f48a  mov     eax, r12d
0x14001f48d  mov     r12, [rsp+130h+arg_10]
0x14001f495  add     rsp, 110h
0x14001f49c  pop     r15
0x14001f49e  pop     r14
0x14001f4a0  pop     rdi
0x14001f4a1  pop     rsi
0x14001f4a2  pop     rbp
0x14001f4a3  retn
0x14001f4a5  mov     ecx, 0FFFFh
0x14001f4aa  mov     [rbp+30h+var_A0], 0
0x14001f4b1  add     [rdi+0D4h], cx
0x14001f4b8  cmp     [rbp+30h+var_AE], 0
0x14001f4bc  jnz     loc_14001F7E1
0x14001f4c2  cmp     byte ptr [rbp+30h+var_B0+1], 0
0x14001f4c6  jnz     loc_14001F60B
0x14001f4cc  mov     rcx, [rbp+30h+var_A8]
0x14001f4d0  mov     rax, 100000000000h
0x14001f4da  and     rcx, rax
0x14001f4dd  movzx   eax, byte ptr [rdi+82h]
0x14001f4e4  or      [rdi], rcx
0x14001f4e7  cmp     [rdi+83h], al
0x14001f4ed  jnz     loc_14001F696
0x14001f4f3  movzx   ecx, [rbp+30h+var_AD]
0x14001f4f7  movzx   eax, [rbp+30h+var_AC]
0x14001f4fb  mov     [rdi+83h], cl
0x14001f501  mov     [rdi+84h], al
0x14001f507  mov     [rdi+82h], cl
0x14001f50d  jmp     loc_14001F465
0x14001f512  xor     eax, eax
0x14001f514  add     rsp, 110h
0x14001f51b  pop     r15
0x14001f51d  pop     r14
0x14001f51f  pop     rdi
0x14001f520  pop     rsi
0x14001f521  pop     rbp
0x14001f522  retn
0x14001f524  call    cs:__imp_ExFreeToPagedLookasideList
0x14001f52b  nop     dword ptr [rax+rax+00h]
0x14001f530  jmp     loc_14001F448
0x14001f535  inc     cl
0x14001f537  jmp     loc_14001F2C4
0x14001f53c  inc     dl
0x14001f53e  jmp     loc_14001F2A8
0x14001f543  mov     rax, [rdi]
0x14001f546  bt      rax, 0Ah
0x14001f54b  jb      short loc_14001F557
0x14001f54d  or      byte ptr [r13+18h], 1
0x14001f552  jmp     loc_1401EF3F4
0x14001f557  bt      rax, 0Ch
0x14001f55c  jnb     short loc_14001F54D
0x14001f55e  jmp     loc_1401EF3F4
0x14001f563  cmp     word ptr [rax+8], 0
0x14001f568  jnz     loc_14001F718
0x14001f56e  xor     edx, edx
0x14001f570  mov     rcx, [rsi+8]
0x14001f574  lea     rax, [r13+2A0h]
0x14001f57b  mov     r8, [rbp+30h+arg_30]
0x14001f57f  mov     [rbp+30h+var_30], rax
0x14001f583  mov     eax, [rsi+18Ch]
0x14001f589  mov     ecx, [rcx+40h]
0x14001f58c  shl     eax, 4
0x14001f58f  mov     [rbp+30h+var_28], rax
0x14001f593  mov     eax, [rbp+30h+arg_28]
0x14001f596  shl     r9d, cl
0x14001f599  add     eax, r10d
0x14001f59c  lea     rcx, [rbp+30h+var_30]
0x14001f5a0  mov     [rsp+130h+var_D0], rdx
0x14001f5a5  mov     [rsp+130h+var_108], rcx
0x14001f5aa  mov     rcx, [rsp+130h+var_E0]
0x14001f5af  mov     dword ptr [rsp+130h+var_110], edx
0x14001f5b3  mov     edx, eax
0x14001f5b5  mov     dword ptr [rsp+130h+var_D8], eax
0x14001f5b9  call    ?MergeChecksums@CmsChecksum@@QEBAXKPEAXKKV?$span@W4byte@utl@@$0?0@utl@@_N@Z; CmsChecksum::MergeChecksums(ulong,void *,ulong,ulong,utl::span<utl::byte,-1>,bool)
0x14001f5be  mov     eax, [rdi]
0x14001f5c0  mov     r9d, [rsp+130h+var_EC]
0x14001f5c5  bt      rax, 0Ah
0x14001f5ca  jb      loc_14001F73A
0x14001f5d0  mov     r8d, [rsp+130h+var_F0]
0x14001f5d5  test    r14b, r14b
0x14001f5d8  jnz     loc_1401EF579
0x14001f5de  cmp     [rbp+30h+arg_38], r14b
0x14001f5e2  jnz     loc_1401EF579
0x14001f5e8  lea     edx, [r8+r9]; unsigned int
0x14001f5ec  lea     r8, [rsp+130h+var_F0]; unsigned int *
0x14001f5f1  lea     rcx, [rbp+30h+BitMapHeader]; struct _RTL_BITMAP *
0x14001f5f5  call    ?FindNextForwardRunSet@CmsClusterOperations@@SAKPEAU_RTL_BITMAP@@KPEAK@Z; CmsClusterOperations::FindNextForwardRunSet(_RTL_BITMAP *,ulong,ulong *)
0x14001f5fa  mov     r8d, [rsp+130h+var_F0]
0x14001f5ff  mov     r9d, eax
0x14001f602  mov     [rsp+130h+var_EC], eax
0x14001f606  jmp     loc_14001F3EF
0x14001f60b  mov     rcx, [rdi+1A0h]; this
0x14001f612  lea     rdx, [rax+0B40h]; struct CmsDurableLog *
0x14001f619  cmp     qword ptr [rcx], 0
0x14001f61d  jnz     loc_14001F7ED
0x14001f623  call    ?DiscardPendingRecords@CmsTxMemLog@@QEAAXPEAVCmsDurableLog@@@Z; CmsTxMemLog::DiscardPendingRecords(CmsDurableLog *)
0x14001f628  mov     rcx, [rbp+30h+var_A8]
0x14001f62c  mov     rdx, 80000000000h
0x14001f636  test    rdx, rcx
0x14001f639  jnz     loc_14001F802
0x14001f63f  mov     rax, qword ptr [rbp+30h+BitMapHeader.SizeOfBitMap]
0x14001f643  mov     [rdi+1A0h], rax
0x14001f64a  jmp     loc_14001F4D0
0x14001f64f  mov     rax, cs:KdDebuggerEnabled
0x14001f656  cmp     [rax], bl
0x14001f658  jz      loc_14001F237
0x14001f65e  int     3; Trap to Debugger
0x14001f65f  jmp     loc_14001F237
0x14001f664  mov     rax, cs:KdDebuggerEnabled
0x14001f66b  cmp     [rax], bl
0x14001f66d  jz      loc_14001F2F3
0x14001f673  int     3; Trap to Debugger
0x14001f674  jmp     loc_14001F2F3
0x14001f679  mov     rax, [rsp+130h+var_E0]
0x14001f67e  cmp     word ptr [rax+8], 0
0x14001f683  lea     r11, [rax+14h]
0x14001f687  mov     [rsp+130h+var_D0], r11
0x14001f68c  jnz     short loc_14001F6FF
0x14001f68e  xor     r10d, r10d
0x14001f691  jmp     loc_1401EF49E
0x14001f696  mov     rax, cs:KdDebuggerEnabled
0x14001f69d  cmp     byte ptr [rax], 0
0x14001f6a0  jz      loc_14001F4F3
0x14001f6a6  int     3; Trap to Debugger
0x14001f6a7  jmp     loc_14001F4F3
0x14001f6ac  mov     rax, [rdi+8]
0x14001f6b0  mov     r12d, 0C0000188h
0x14001f6b6  movzx   ebx, [rbp+30h+arg_0]
0x14001f6ba  jmp     loc_14001F455
0x14001f6bf  mov     eax, r8d
0x14001f6c2  add     rax, [rbp+30h+var_70]
  ... truncated ...
```
